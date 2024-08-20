# Javascript tutorial 7 - 陣列 (Array)

## 什麼是陣列

如果要使用一般的變數代表一組資料，例如：`let fruit1 = "apple"`, `let fruit2 = "banana"`, `let fruit3 = "cherry"`，這樣的寫法會讓程式碼變得冗長且難以維護。

這時候，如果我們可以使用一個變數來代表多個資料該有多好。

陣列(array)是一種用來儲存多個資料的資料結構，可以將多個資料放在同一個變數中。

就像用一個盒子裝著多個水果一樣，陣列就像是一個盒子，可以裝著多個資料。

陣列的元素(element)是從 0 開始編號，第一個元素的編號是 0，第二個元素的編號是 1，以此類推。

## 宣告陣列

宣告陣列的語法是使用中括號 `[]`，並在中括號中放入元素，元素之間使用逗號 `,` 分隔。

語法：

```js
let array = [element1, element2, ...]
```

- `array` 是陣列名稱
- `element1, element2, ...` 是陣列中的元素

範例：

```js
let fruits = ["apple", "banana", "cherry"]
```

## 存取陣列元素

存取陣列元素的語法是使用中括號 `[]`，並在中括號中放入元素的編號。

語法：

```js
array[index]
```

範例：

```js
let fruits = ["apple", "banana", "cherry"]

console.log(fruits[0]) // apple
console.log(fruits[1]) // banana
console.log(fruits[2]) // cherry
```

## 修改陣列元素

修改陣列元素的語法是使用中括號 `[]`，並在中括號中放入元素的編號，然後使用等號 `=` 來指定新的值。

語法：`array[index] = newValue`

範例：

```js
let fruits = ["apple", "banana", "cherry"]

fruits[1] = "orange"

console.log(fruits) // ["apple", "orange", "cherry"]
```

## 取得陣列的長度

可以使用 `length` 屬性來取得陣列的長度，即陣列中的元素個數。

範例：

```js
let fruits = ["apple", "banana", "cherry"]

console.log(fruits.length) // 3

console.log(fruits[fruits.length - 1]) // cherry
console.log(fruits[fruits.length]) // undefined
```

## 陣列的迭代

可以使用 `for` 迴圈來迭代陣列中的元素。

語法：

```js
for (let i = 0; i < array.length; i++) {
  console.log(array[i])
}
```

範例：

```js
let fruits = ["apple", "banana", "cherry"]

for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i])
}
```

### for...of 迴圈

`for...of` 迴圈是一種用來迭代陣列中的元素的語法。

語法：

```js
for (let element of array) {
  console.log(element)
}
```

範例：

```js
let fruits = ["apple", "banana", "cherry"]

for (let fruit of fruits) {
  console.log(fruit)
}
```

## 陣列的方法

JavaScript 提供了許多內建的陣列方法，可以用來操作陣列。

### push() 方法

`push()` 方法用來在陣列的末端新增一個元素。

語法：`array.push(element)`

範例：

```js
let fruits = ["apple", "banana", "cherry"]

fruits.push("orange")

console.log(fruits) // ["apple", "banana", "cherry", "orange"]
```

### pop() 方法

`pop()` 方法用來移除陣列的最後一個元素。

語法：`array.pop()`

範例：

```js
let fruits = ["apple", "banana", "cherry"]

fruits.pop()

console.log(fruits) // ["apple", "banana"]
```

### shift() 方法

`shift()` 方法用來移除陣列的第一個元素。

語法：`array.shift()`

範例：

```js
let fruits = ["apple", "banana", "cherry"]

fruits.shift()

console.log(fruits) // ["banana", "cherry"]
```

### unshift() 方法

`unshift()` 方法用來在陣列的開頭新增一個元素。

語法：`array.unshift(element)`

範例：

```js
let fruits = ["apple", "banana", "cherry"]

fruits.unshift("orange")

console.log(fruits) // ["orange", "apple", "banana", "cherry"]
```

### splice() 方法

`splice()` 方法用來刪除、新增或取代陣列中的元素。

語法：`array.splice(start, deleteCount, element1, element2, ...)`

- `start`：要開始刪除或新增的位置
- `deleteCount`：要刪除的元素個數
- `element1, element2, ...`：要新增的元素
- 回傳值：刪除的元素組成的陣列

範例：

```js
let fruits = ["apple", "banana", "cherry"]

fruits.splice(1, 1, "orange")

console.log(fruits) // ["apple", "orange", "cherry"]
```

### map() 方法

`map()` 方法用來對陣列中的每個元素進行處理，並回傳處理後的結果。

語法：`array.map(callback)`

- `callback`：處理每個元素的函式
- 回傳值：處理後的結果組成的陣列

範例：

```js
let numbers = [1, 2, 3, 4, 5]

let doubledNumbers = numbers.map(number => number * 2)

console.log(doubledNumbers) // [2, 4, 6, 8, 10]
```

### filter() 方法

`filter()` 方法用來過濾陣列中的元素，只回傳符合條件的元素。

語法：`array.filter(callback)`

- `callback`：過濾條件的函式
- 回傳值：符合條件的元素組成的陣列

範例：

```js
let numbers = [1, 2, 3, 4, 5]

let evenNumbers = numbers.filter(number => number % 2 === 0)

console.log(evenNumbers) // [2, 4]
```

### reduce() 方法

`reduce()` 方法用來對陣列中的元素進行累加或累乘等操作。

語法：`array.reduce(callback, initialValue)`

- `callback`：累加或累乘等操作的函式
- `initialValue`：初始值
- 回傳值：累加或累乘等操作的結果

範例：

```js
let numbers = [1, 2, 3, 4, 5]

let sum = numbers.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  0
)
```

### find() 方法

`find()` 方法用來找出陣列中符合條件的第一個元素。

語法：`array.find(callback)`

- `callback`：條件的函式
- 回傳值：符合條件的第一個元素

範例：

```js
let numbers = [1, 2, 3, 4, 5]

let evenNumber = numbers.find(number => number % 2 === 0)

console.log(evenNumber) // 2
```

### includes() 方法

`includes()` 方法用來判斷陣列中是否包含某個元素。

語法：`array.includes(element)`

- 回傳值：布林值，表示是否包含該元素

範例：

```js
let fruits = ["apple", "banana", "cherry"]

console.log(fruits.includes("banana")) // true
console.log(fruits.includes("orange")) // false
```
