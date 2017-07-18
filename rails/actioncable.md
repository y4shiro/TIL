# ActionCable関連まとめ
## 参考文献
## 導入方法
## Gemfileなど
Rails 5.*以上ならデフォで使用できます。  
Rails 4.*以下の場合はGemfileを追加して下さい。  
## 生成コマンド
```Ruby

$ rails g channel "名前" "追加するAction名"
// 今回は"speak"という名前のチャネルを作成します。
$ rails g channel chat speak

```

## 初期に生成されるファイル
下記のファイルが作成されます。  

### app/channels/chat_channel.rb
MVCで言う所のControllerに相当。  
chat.jsからActionが呼ばれる。  

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

### app/assets/javascript/channels/chat.js
デフォだとCoffeeScriptが生成された気がするので、適宜読み替えてください。  

```JavaScript

App.chat = App.cable.subscriptions.create("ChatChannel", {
  connected: function() {
    // Called when the subscription is ready for use on the server
  },

  disconnected: function() {
    // Called when the subscription has been terminated by the server
  },

  received: function(data) {
    // Called when there's incoming data on the websocket for this channel
  },

  speak: function() {
    return this.perform('speak');
  }
});

```

## Turbolinksとの共存
Turbolinksが有効な場合、ActionCableのコネクションがページ遷移時でも切断されない。  
ActionCableはTurbolinksと相性が良いので、JSをゴリゴリ使わずRailに乗る場合は是非とも利用しましょう。  
