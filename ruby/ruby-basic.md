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

### %記法"と'をエスケープする必要がない
"や'の代わりに使用できる。"と'をエスケープする必要がない。  
%、%w、%Wのといった複数種がある。()以外の記号も使用できる。  
下記が参考になる。  
- http://qiita.com/mogulla3/items/46bb876391be07921743

#### %、%Q
ダブルクォートで囲う場合と同等。  

```Ruby
str = %(hello, Ruby)
puts str
# hello, xxxx

ruby = "Ruby"
str2 = %(hello, "#{ruby}")
puts str2
# hello, Ruby
```

####
```Ruby


```

