# RailsでJSONをいい感じに使おう
## 参考文献
- http://r7kamura.hatenablog.com/entry/2016/10/03/001212
- http://llcc.hatenablog.com/entry/2015/03/07/103121

## 以下書け

## Viewテンプレで読み込みと出力
```HTML
<p>
  名前:<%= @user["name"] %><br />
  年齢:<%= @user["age"] %>
</p>
```

## Rails側でJSON編集のベストプラクティス
### JSON -> Hash
```Ruby
require "json"

dict = {name: yamada, age: 22}
dict.to_json
# => "{\"name\":\"yamada\",\"age\":22}"
```

### Hahs -> JSON
```Ruby
require "json"

json = '{ "name" : "yamada", "age" : 14}'
JSON.parse json
# => {"name"=>"yamada", "age"=> 22}
```

## jbuilder良いらしい
### jbuilderとは？
jsonのエンジンテンプレート。  
Rails4以降はデフォルトで使えるっぽい。複雑なJSON生成する時に良さそう。  

### 使い方
views以下に`xxx.json.jbuilder`を作成し、`localhost:3000/xxx.json`にアクセスすると取得できる。  

### jbuilder書き方
