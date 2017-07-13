# Promise
## 参考文献
- http://azu.github.io/promises-book/
- https://app.codegrid.net/entry/es6-1
## Promiseとは
非同期処理を扱うための仕組みの一つ。  
ES6から実装された。  
フロントエンドでの用途としては、XHR[^1]やアニメーションの終了タイミング通知など。  

## 利点
コールバック地獄を防げる。  

## 使い方

```javascript

var promise = new Promise(function (resolve, reject) {
  // 非同期処理記述

  // リクエスト成功した場合
  if (requiest.status === 200){
  }
  // リクエスト失敗した場合
  else {
  }
}

```

## 脚注
[^1]: XMLHttpRequestの略
