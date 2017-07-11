# Redisコマンド一覧

よく使いそうな奴を列挙

## 参考文献
* https://redis.io/commands
* http://redis.shibu.jp/commandreference/index.html
* http://mayo.hatenablog.com/entry/2013/10/15/074237

# 全データ型対応の操作
## EXISTS

``` bash
exists "key"
```

keyが存在するか確認。

- 返り値
存在する場合は"1"、存在しない場合は"0"が返る。
keyが存在する場合、valueが空文字列でも"1"が返る。


## EXPIRE

```bash
expire "key", seconds
```

指定したkeyのタイムアウト時間を設定する。
ただし、下記の場合はタイムアウトが削除される。
* SETで新しい値を紐付けた場合
* DELで削除された場合


# 文字列型の操作
## SET

```bash
set "key", value
```

文字列値valueをkeyにセットする。
String、Integerが保存可能。

- 返り値
Status code reply

## GET

```bash
get "key"
```


## SETEX
