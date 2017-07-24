# RubyのHashについて
## 参考文献
- http://www.sejuku.net/blog/11429
- http://ref.xaio.jp/ruby/classes/array/sort

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

### each_key, each_value
```Ruby
hash = { ruby: "Rails", python: "Django", java: "Play" }

# each_key
hash.each_key {|key| puts "#{key}"}

hash.each_key do |key|
  puts "#{key}"
end
=>
ruby
python
java

# each_value
hash.each_value {|val| puts "#{val}"}

hash.each_val do |val|
  puts "#{val}"
end
=>
Rails
Django
Play
```

### map(Hashを任意の配列で返す)
```Ruby
hash = { ruby: "Rails", python: "Django", java: "Play" }

hash.map { |key, val| [key, val] }
=> [[:ruby, "Rails"], [:python, "Django"], [:java, "Play"]]

# Hashで返す
Hash[hash.map { |key, val| [key, val] }]
=> {:ruby => "Rails", :python => "Django", :java => "Play"}

# Hashで返す(Ruby2.1以降)
hash.map { |key, val| [key, val] }.to_h
=> {:ruby => "Rails", :python => "Django", :java => "Play"}
```

### sort
```Ruby
hash = { ruby: 90 , python: 70, java: 50, c: 60 }
hash.sort
# keyでソートされる
=> [[:c,  60], [:java, 50], [:python, 70], [:ruby, 90]]

# ブロックの戻り値によって比較
hash.sort { |(key1, val1), (key2, val2)| block }

# valueが大きい順にソート
hash.sort { |(key1, val1), (key2, val2)| val2 <=> val1 }
=> [[:ruby, 90], [:python, 70], [:c, 60], [:java, 50]]
```

### merge, merge!
```Ruby
```

### has_key?, key?
```Ruby
```

### has_value?
```Ruby
```
