# Javascript tutorial 2 - 運算子 (Operator)

## 什麼是運算子

運算子(operator)是用來執行運算的符號，例如加減乘除等等。

運算子可以用來執行數學運算、比較運算、邏輯運算等等。

## 運算子的種類

運算子有很多種不同的種類，常見的運算子有：算術運算子、比較運算子、邏輯運算子、三元運算子等等，每一種運算子都有不同的功能，可以用來處理不同的問題。

## 算術運算子 (Arithmetic Operator)

算術運算子是用來執行數學運算的符號，基本的算術運算子有：

加法 `+`、減法 `-`、乘法 `*`、除法 `/`、取餘數 `%`、指數 `**`

範例：

```js
console.log(10 + 5) // 15
```

```js
let num1 = 10
let num2 = 5
let multiply = 0

multiply = num1 * num2
console.log(multiply) // 50
```

除了以上寫法，我們也可以使用 `+=`、`-=`、`*=`、`/=`、`%=` 來簡化程式碼：

```js
let num1 = 10
let num2 = 5

num1 += num2 // num1 = num1 + num2
console.log(num1) // 15
```

也可以使用 `++`、`--` 來增加或減少變數的值：

```js
let num1 = 10

num1++ // num1 = num1 + 1
console.log(num1) // 11
```

## 比較運算子 (Comparison Operator)

比較運算子是用來比較兩個值的大小，依結果回傳真（是） `true` 或假（否） `false` 。常見的比較運算子有：

1. `>` 大於、`<` 小於
2. `>=` 大於等於、`<=` 小於等於
3. `==` 等於、`!=` 不等於
4. `===` 嚴格等於、`!==` 嚴格不等於

範例：

```js
let num1 = 10
let num2 = 5

console.log(num1 > num2) // true
```

> 嚴格等於 `===` 與等於 `==` 的差別在於，嚴格等於還會比較資料的**型別**，例如：

```js
let num1 = 10 // number
let num2 = "10" // string

console.log(num1 == num2) // true
console.log(num1 === num2) // false
```

## 邏輯運算子 (Logical Operator)

邏輯運算子是用來執行邏輯運算的符號，例如：

1. `&&` 且 (and)
2. `||` 或 (or)
3. `!` 非 (not)

範例：

```js
let num1 = 10
let num2 = 5

console.log(num1 > 9 && num2 > 9) // false
```

> 必較運算子與邏輯運算子通常用在條件判斷式中

## 總結

- 運算子是用來執行運算的符號
- 運算子有很多種不同的種類，例如算術運算子、比較運算子、邏輯運算子等等
- 每一種運算子都有不同的功能，可以用來處理不同的問題
