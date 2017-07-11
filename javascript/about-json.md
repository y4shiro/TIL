# JSONについて

## 参考文献

- http://oki2a24.com/2015/07/26/what-is-json-and-how-to-control-with-javascript/

## JSONとは

- JavaScript Object Notation  
- 中身はテキスト
- "key": value
- 値は色々入る
  - String
  - number
  - boolean
  - null
  - Object
  - Array
- データ構造は配列[]とオブジェクト{}で定義

## JSON扱うときのポイント

### JSON.parse()

JSONデータからJavaScriptオブジェクトへ変換。  

### JSON.stringify()

JavaScriptオブジェクトからJSONデータにシリアライズ。  

### JSONでは関数や正規表現リテラルは使用できない

JSON.stringify()実行時に関数が除去される。  
