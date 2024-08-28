# Javascript tutorial 1 - 變數 (Variable)

## 什麼是變數

如果想要在程式中做任何事情，就需要資料提供所需的資訊。

而變數 (variable) 是用來儲存資料 (data) 的容器。

例如：`num = 18;`，`num` 就是變數，`18` 就是資料。

## 宣告變數 (Declare Variable)

在使用變數前必須先創造出來，也就是宣告 (declare) 變數。

語法：

```js
Modifier variableName = value
```

- `Modifier`：修飾詞，用來修飾變數的特性。
- `variableName`：變數名稱，用來識別變數。
- `value`：值，可以是數字、字串、布林值等等。
- `=`：賦值運算子，用來將值指定給變數。

範例：

```js
let num = 18
```

## 修飾詞 (Modifier)

在宣告變數時，可以使用修飾詞 (modifier) 來修飾變數的特性，例如：是否可以在宣告後更改資料。

通常宣告變數時都會使用修飾詞，常見的修飾詞有三種：

1. `var`
2. `let`
3. `const`

### `var`

`var` 是最早期的宣告變數的修飾詞。

```js
var num = 18
```

> 在現代的 Javascript 中，`var` 已經不常用，因為它有一些問題，例如：變數的[作用域 (scope)](https://hackmd.io/lmBa4uFoQaipvVoP3tfDNg) 不夠清楚，容易造成變數名稱衝突等等。

### `let`

`let` 是一般變數的修飾詞，宣告後可以更改其資料。

```js
let num = 18
```

### `const`

`const` 是常數的修飾詞，宣告後就**不可以**再更改其資料。

```js
const PI = 3.14
```

> 建議如果能用 `const` 就用 `const`，因為這樣可以避免不小心更改常數的值。

## 變數命名規則與邏輯

1. 不能用**保留詞**當變數名稱

   簡單來說當那個詞本身在就有特殊意義時，就不要用它當變數名稱，主控台會報錯( error message )，因為電腦會搞混。

   ```js
   let let = "John";
   ```

2. 取跟變數本身意義相關的詞

   變數名稱要有意義，不然別人和自己都會看不懂，不知道這個變數是幹嘛的。

   ```js
   //不良示範
   let a = "John"
   ```

3. 小駝峰式大小寫(lower camel case)

   每個詞的字首大寫，除了第一個字

   ```js
   const myFirstName = "John"
   ```

## 變數型別

變數的型別有很多種，以下是一些常見的型別：

1. 數字 number
2. 字串 string
3. 布林值 boolen

> 可以用 `typeof` 來查看變數的型別：
>
> ```js
> let num = 18
> console.log(typeof num) // number
> ```

### 數字 number

數字型別是用來儲存數字的變數：

```js
let age = 18
const PI = 3.14
```

### 字串 string

字串型別是用來儲存一串文字的變數，字串要用雙引號`" "`或單引號`' '`包起來：

```js
let name = "John"
```

### 布林值 boolen

布林值型別是用來儲存真值 `true` 或假值 `false` 的變數：

```js
let age = 18
let isAdult = true
```

> `true` 對應值是數字 `1`，`false` 對應值是數字 `0`。
>
> 但只有 `0` 對應 `false`，其他非零數字則對應 `true`。

## 額外：註解

註解是用來解釋程式碼的文字，不會被電腦執行，可以幫助自己或他人了解程式碼的用途。

```js
// 單行註解

/*
多行註解
*/
```

> 可以在 **Visual Studio Code** 用 `Ctrl` + `/` 快速註解程式碼。

## 總結

- 變數是用來儲存資料的容器。
- 宣告變數時，可以使用 `var`、`let`、`const` 來修飾變數的特性。
- 變數的型別有數字、字串、布林值等等。
- 變數名稱要有意義，並且遵守小駝峰式大小寫。
- 註解是用來解釋程式碼的文字，不會被電腦執行。
