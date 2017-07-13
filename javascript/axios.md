# Axiosまとめ

## 参考URL
https://github.com/mzabriskie/axios

## Axiosとは
PromiseベースのHTTPクライアント。  
XMLHttpRequestをラップしたAPIで、HTTPリクエストを行うことが出来る。  

## 使い方
### GET

```javascript

axios.get('/example.json')
  .then(function (response) {
    // ここでresponse.dataなどを加工する
    console.log(response);
  })
  .catch(function (error) {
    // error時の処理
    console.log(error);
  });

```

### POST

```javascript

axios.post('/user', {
    firstName: 'Taro',
    lastName: 'Tanaka'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });

```

### 複数同時リクエストの実行

```javascript

function getUserAccount() {
  return axios.get('/user/1');
}

function getUserPermissions() {
  return axios.get('/user/1/permissions');
}

axios.all([getUserAccount(), getUserPermissions()])
  .then(axios.spread(function (acct, perms) {
    // nanika
  }));

```

## レスポンススキーマ(レスポンスの中身)

```javascript
{
  // サーバの返した値
  data: {},

  // HTTPステータスコード
  status: 200,

  // HTTPステータスメッセージ
  statusText: 'OK',

  // サーバの返したヘッダー
  headers: {},

  // リクエスト時の設定
  config: {},

  // リクエストの内容
  request: {}
}

```

## 使用例

```javascript

axios.get('api/example.json')
  .then(function(response){
    console.log(response.data);
  })
  .catch(function (error) {
    console.log(error);
  })
);

```
