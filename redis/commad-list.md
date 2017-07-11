# Redisコマンド一覧

個人的に使いそうな奴を列挙

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
存在する場合は"1"、存在しない場合は"0"が返る。  
keyが存在する場合、valueが空文字列でも"1"が返る。  

## EXPIRE

```bash
expire "key", time
```

指定したkeyのタイムアウト時間を秒数で設定する。  
ただし、下記の場合はタイムアウトが削除される。  
- SETで新しい値を紐付けた場合
- DELで削除された場合

# 文字列型の操作
## SET

```bash
set "key", value
```

文字列値valueをkeyにセットする。  
String、Integerが保存可能。  
返り値はStatus code reply  

## GET

```bash
get "key"
```

指定したkeyに対応するvalueを取得する。  
keyが存在しなかった場合は"nil"が返る。  
valueが文字列型以外だった場合、エラーが返る。  

## SETEX

```bash
setex "key", time, value
```

このコマンドは `SET` + `EXPIRE` を同時に実行します。

# セット型の操作
## SADD

```bash
sadd "key", member
```

指定したmemberをkeyにセットする。  
追加出来た場合は"1"、既にmemberが存在している場合は"0"が返る。  

## SREM

```bash
srem "key", member
```

指定したmemberをkeyに対応するセットから取り除く。  
memberがkeyの中に存在しなかった場合は何も実行されない。  
もしkeyに対応する値がセット型で無かった場合はエラーが返る。  

## SISMEMBER

```bash
```

## SMEMBERS

```bash
```

