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

### %記法
"や'の代わりに使用できる。"と'をエスケープする必要がない。  
%、%w、%Wのといった複数種がある。()以外の記号も使用できる。  
下記が参考になる。  
- http://qiita.com/mogulla3/items/46bb876391be07921743

#### %、%Q
ダブルクォートで囲う場合と同等。  
シングル・ダブルクォートのエスケープが不要になる。  
後述の%qと違い、変数や定数の展開が出来る。  

```Ruby
str = %(hello, Ruby)
puts str
# hello, Ruby

ruby = "Ruby"
str2 = %(hello, "#{ruby}")
puts str2
# hello, Ruby
```

#### %q
シングルクォートで囲う場合と同等。  
シングルクォートなので、変数や定数の展開が行われない。  

```Ruby
ruby = "Ruby"
str = %q(hello, "#{ruby}")
puts str
# hello, "#{ruby}"
```

#### %w
配列を作成する。配列の要素はスペース区切りで分割する。
式の展開は行われない。

```Ruby
array = %w(one two three four)
p array
# ["one", "two", "three", "four"]
```

#### %W
配列を作成する。%w()と違い式の展開が行われる。  

```Ruby
ruby = "Ruby"
PYTHON = 'Python'
array = %W(#{ruby} #{PYTHON} PHP)
p array
# ["Ruby", "Python", "PHP"]
```
