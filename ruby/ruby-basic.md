# Rubyの基本などまとめ
## 参考文献
- http://qiita.com/ryo2132/items/2bb76e4012c80a654119

### unless構文
ifの逆で判定が偽の場合のみ処理を実行する。

```Ruby

x = 0

unless x > 1 then
  puts "ok"
elese
  puts "no"
end

# "ok" が出力される

```
