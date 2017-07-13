# Axiosまとめ

## 参考URL
https://github.com/mzabriskie/axios

## Axiosとは

## 使い方

```bash

axios.get('/example.json')
  .then(function (response) {
    // ここでresponse.dataなどを加工する
    console.log(response);
  })
  .catch(function (error) {
    // error時の処理
    console.log(error)
  });

```
