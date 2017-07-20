# JSONについて
## 参考文献
- http://oki2a24.com/2015/07/26/what-is-json-and-how-to-control-with-javascript/
- http://www.webopixel.net/javascript/91.html

## JSONとは
- JavaScript Object Notation
- 中身はテキスト
- "key": value
- 値は色々入る
  - String
  - number
  - boolean
  - null
  - Array
  - Object

データ構造は配列[]とオブジェクト{}で定義する。  
配列とオブジェクトは自由にネストさせることが可能。  
配列のvalueは文字列のみ。  
オブジェクトのkeyは文字列のみ。  

## 凡例
```JavaScript
var data = [
  {
    "id": 1,
    "name": "hoge",
    "lang": ["JavaScript", "Ruby", "Python"],
    "bool": true
  },
  {
    "id": 2,
    "name": "fuga",
    "lang": ["JavaScript", "PHP"],
    "bool": false
  }
];

alert(data[0].id + data[0].name);
// "1 hoge"と出力
```

## JSON扱うときのポイント
### JSON.parse()
JSONデータからJavaScriptオブジェクトへ変換。  

### JSON.stringify()
JavaScriptオブジェクトからJSONデータにシリアライズ。  

### JSONでは関数や正規表現リテラルは使用できない
JSON.stringify()実行時に関数が除去される。  
