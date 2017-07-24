# RubyのHashについて
## 参考文献
- http://www.sejuku.net/blog/11429
## Hashとは
連想配列とも呼ばれる型。  
keyとvalueの2つが入っている。  
Array(配列)とHash(連想配列)の違いを下に示す。  

```Ruby
array = ["ruby", "python", "java"]
hash  = {lang1: "ruby", lang2: "python", lang3: "java"}
```

## リテラル


## コマンド一覧
### new(初期化)
```Ruby
# 下記は等価
hash = {}
hash = Hash.new

# デフォルト値を設定
hash = Hash.new("hello")
hash[1]
=> "hello"
```
### each
```Ruby
hash = { ruby: "Rails", python: "Django", java: "Play" }

hash.each {|key, val| puts "#{key}: #{val}"}

hash.each do |key, val|
  puts "#{key}: #{val}"
end
=>
ruby: Rails
python: Django
java: Play
```
### each_key, each_valueh
### map
### sort
### merge, merge!
