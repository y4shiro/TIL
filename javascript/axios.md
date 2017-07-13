# Axiosまとめ

## 参考URL
https://github.com/mzabriskie/axios

## Axiosとは

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
