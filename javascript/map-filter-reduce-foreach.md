# mapやfilterなどのメモ
## 参考文献
https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Arra://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Array
http://qiita.com/itagakishintaro/items/29e301f3125760b81302
http://www.sejuku.net/blog/20257

## これらは何？
Arrayオブジェクトに実装されているメソッド。  
Arrayの特定の値を探索、処理したい場合に楽になる。  

## map
配列内のすべての要素に対して与えられた関数を呼び出し、その結果を格納した新しい配列を生成する。  
写像。  
  
arrayは元の配列。  
index, arrayは省略可能。  

```javascript

var square = [1, 2, 3, 4, 5].map(function(element, index, array) {
  return element * element;
});

// [1, 4, 9, 16, 25] が出力される。
console.log(square);

```

## filter
指定したフィルタリング関数が true を返す、配列中の要素を格納した新しい配列を生成。  
条件を指定して合致したものを抽出する。  

arrayは元の配列。  
index,arrayは省略可能。  

```javascript

var filtered = [5, 10, 229, 41, 78].filter(function(element, index, array) {
  return (element >= 50);
});

// [229, 78] が出力される。
console.log(filtered);

```

## reduce, reduceRight
アキュムレータと配列内のすべての要素に対して (左から右の順で) 関数を適用し、単一の値に還元。  
値を一つに絞り込む。  
reduceは左から、reduceRightは右から処理を始める。

arrayは元の配列。  
index,arrayは省略可能。  
```javascript

var total = [0, 1, 2, 3].reduce(function(preValue, currentValue, index, array) {
  return preValue + currretValue;
});

// 6 が出力される。
console.log(total);

```

## every,some
- every
指定したテスト関数を配列中のすべての要素が満たした場合に true を返す。  

- some
指定したテスト関数を配列中の少なくとも 1 個の要素が満たした場合に true を返す。  

結果はboolean。  
arrayは元の配列。index, arrayは省略可能。  
```javascript

var lists = [3, 77, 40, 805, 19]

// falseが返る
lists.every(function(value, index, array){
  return (value >= 10);
});

// trueが返る
lists.some(function(value, index, array){
  return (value >= 10);
});


```

## forEach
配列中のそれぞれの要素について関数を呼び出す。  

```javascript

// 0:2, 1:5, 2:9 と出力される。
[2, 5, 9].forEach(function(element, index, array) {
  console.log(index + ":" + element);
});

```

配列自体を操作する場合  
```javascript

var lists = [2, 5, 9]
lists.forEach(function(value, index, array) {
  array[index] = value * 2;
});

// [2, 10, 18]と出力される。
console.log(lists);

```


## 使用例

### filter

```javascript

// userListを走査して、user.idと合致すればtrueを返す
(userList.filter(v => v.id === this.user.id).length != 0)

```
