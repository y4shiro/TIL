# ActionCable関連まとめ
## 参考文献
- http://qiita.com/jnchito/items/aec75fab42804287d71b
- http://qiita.com/sasurai_usagi3/items/75a30cc0d2d0faa9dfe8

## 導入方法
Rails 5.*以上ならデフォで使用できます。  
Rails 4.*以下の場合はGemfileを追加して下さい。  

## 生成コマンド
```Bash

$ rails g channel "名前" "追加するAction名"
// 今回は"chat"という名前のチャネルを作成します。
$ rails g channel chat speak

```

## 初期に生成されるファイル
下記のファイルが作成されます。  

### app/channels/chat_channel.rb
MVCで言う所のControllerに相当。  
chat.coffeeからActionが呼ばれる。  

```Ruby

class ChatChannel < ApplicationCable::Channel
  def subscribed
    # stream_from "some_channel"
  end

  def unsubscribed
    # Any cleanup needed when channel is unsubscribed
  end

  def speak
  end
end

```

### app/assets/javascript/channels/chat.coffee
クライアント的役割がある。  
デフォだとCoffeeScriptが生成された気がするので、適宜読み替えてください。  

```CoffeeScript

App.room = App.cable.subscriptions.create "ChatChannel",
  connected: ->
    # Called when the subscription is ready for use on the server

  disconnected: ->
    # Called when the subscription has been terminated by the server

  received: (data) ->
    # Called when there's incoming data on the websocket for this channel

  speak: ->
    @perform 'speak'

```

## コントローラの作成とルーティング
コントローラ作ってルーティングまで行います。  
```Bash

$ rails g controller chat index

```

```Ruby

Rails.application.routes.draw do
  root 'chat#index'
end

```

## ストリーム接続とspeak実行
流れは下記のとおりです。  
- stream接続
- chat.coffee speak実行
- ChatChannel.rb speakアクションにてブロードキャスト実行
- chat.coffee recieveにてメッセージ受け取り

```Ruby

class ChatChannel < ApplicationCable::Channel
  def subscribed
    stream_from "chat_channel"
  end

  def unsubscribed
    # Any cleanup needed when channel is unsubscribed
  end

  def speak
    ChatChannel.broadcast_to('message', 'hello')
  end
end

```

```CoffeeScript

App.room = App.cable.subscriptions.create "ChatChannel",
  connected: ->
    # Called when the subscription is ready for use on the server

  disconnected: ->
    # Called when the subscription has been terminated by the server

  received: (data) ->
    console.log(data)

  speak: ->
    @perform 'speak'

```



## Turbolinksとの共存
Turbolinksが有効な場合、ActionCableのコネクションがページ遷移時でも切断されない。  
ActionCableはTurbolinksと相性が良いので、JSをゴリゴリ使わずRailに乗る場合は是非とも利用しましょう。  
