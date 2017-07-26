# Rubyの基本などまとめ
## 参考文献
- http://qiita.com/ryo2132/items/2bb76e4012c80a654119
- http://qiita.com/na1412/items/65f883896c85011d6509
- https://hydrocul.github.io/wiki/programming_languages_diff/list/to-set.html
- https://ja.stackoverflow.com/questions/69/ruby%E3%81%A7%E6%96%87%E5%AD%97%E5%88%97%E3%81%A8%E6%95%B0%E5%AD%97%E3%81%8C%E6%B7%B7%E5%9C%A8%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E9%85%8D%E5%88%97%E3%82%92%E3%82%BD%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95%E3%82%92%E6%95%99%E3%81%88%E3%81%A6%E3%81%8F%E3%81%A0%E3%81%95%E3%81%84

## 配列(Array)
### flatten
配列のネストを平坦化した新しい配列を返す。  
```Ruby
array = [1, 2, [3, 4]]
array.flatten!
p array
# array = [1, 2, 3, 4]
```

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
