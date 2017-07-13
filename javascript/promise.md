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
  if (request.status === 200){
    resolve(); // 成功時のレスポンスを()内に記述
  }
  // リクエスト失敗した場合
  else {
    reject(); // 失敗時のレスポンスを()内に記述
  }
});

```

`.then()` で成功時の処理を記述していく。  

```javascript

promise.then(function (res) {
  console.log(res); // resの中身が表示される
});

```

`.catch()` で失敗時の処理を指定できる。  

```javascript

promise.catch(function (err) {
  console.log(err); // errの中身が表示される
});

```

## 非同期処理の連結

`.then()` や `catch()` はメソッドチェーンとして繋げて書くことも可能。  

```javascript

var promise = new Promise(function (resolve, reject) {
  if (request.status === 200){
    resolve('OK');
  }
  else {
    reject('NG');
  }
});

promise(request)
.then(function (res) {
  console.log(res); // 'OK'と出力される。
})
.catch(function (err) {
  console.log(err); // 'NG'と出力される。
});

```

## 複数の非同期処理を並列して実行する
### allメソッド
### raceメソッド

## 脚注
[^1]: XMLHttpRequestの略
