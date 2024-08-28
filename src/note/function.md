# Javascript tutorial 5 - 函式 (Function)

## 什麼是函式

以前相似度很高的程式碼，必須重複寫很多次，這樣會讓程式碼變得冗長且難以維護。

為了解決這個問題，我們可以將相似的程式碼抽象成一個函式（就像數學中的函數），這樣就可以重複使用這段程式碼。

就像點餐機與服務生一樣，有了點餐機後，顧客可以自己點餐，服務生只需要將食物送到顧客面前，這樣就可以節省人力與時間。

函式(function)是一段程式碼的集合，可以重複使用，並且可以接受參數，並回傳結果。

## 宣告函式

宣告函式的語法是使用 `function` 關鍵字，後面接函式名稱，然後使用小括號 `()` 包住參數，最後使用大括號 `{}` 包住程式碼。

語法：

```js
function functionName() {
  ...
}
```

- `function`：關鍵字，用來宣告函式。
- `functionName`：函式名稱，用來呼叫函式。

範例：

```js
function sayHello() {
  console.log("Hello, world!")
}
```

## 呼叫函式

如果只是宣告函式，程式碼不會執行，必須呼叫 (call) 他才會執行裡面的程式碼。

就像打電話一樣，單純拿著電話並不能幹嘛，只有撥打電話才能與對方通話。

語法：

```js
functionName()
```

- `functionName`：函式名稱，用來呼叫函式。

範例：

```js
function sayHello() {
  console.log("Hello, world!")
}

sayHello()
```

## 函式的參數 (Parameters)

當函數需要參考外部的資料時，可以使用參數 (Parameters) 來接收傳入的值。

就像打電話時，需要對方的電話號碼，這個電話號碼就是參數，用來指定要撥打的對象。

參數是在函式名稱後面的小括號 `()` 中，用逗號 `,` 分隔。

語法：

```js
function functionName(parameter1, parameter2, ...) {
  ...
}
```

- `parameter1, parameter2, ...`：參數，用來接收傳入的值。

範例：

```js
function sayHello(name) {
  console.log("Hello, " + name + "!")
}

sayHello("Alice") // Hello, Alice!
sayHello("Bob") // Hello, Bob!
```

## 函式的回傳與結束 (Return)

當需要將函式的結果回傳給呼叫者時，可以使用 `return` 關鍵字來回傳值。

就像現實生活中去餐廳點餐，服務生會將點餐結果回傳給廚房，廚房再將食物回傳給服務生，最後服務生再將食物回傳給你。

語法：`

```js
function functionName() {
  return value
}
```

- `return`：關鍵字，用來回傳值。
- `value`：回傳的值。

範例：

```js
function add(a, b) {
  return a + b
}

let result = add(3, 5) // result = 3 + 5

console.log(result) // 8
```

`return` 關鍵字也可以用於提前結束函式的執行。

範例：

```js
function add(a, b) {
  if (a < 0 || b < 0) {
    return "Error: a and b must be positive numbers"
  }

  return a + b
}

let result = add(-3, 5)

console.log(result) // Error: a and b must be positive numbers
```

## 回呼函式 (Callback function)

函式的參數中也可以接受另一個函式，這種成為別人參數的函式稱為**回呼函式 (Callback function)**。

範例：

```js
// 定義 sayHello 函式，接受一個回呼函式做為參數
function sayHello(callback, name) {
  console.log("Hello, " + name + "!")
  callback(name)
}

function sayGoodbye(name) {
  console.log("Goodbye, " + name + "!")
}

sayHello(sayGoodbye)
// Hello, Alice!
// Goodbye, Alice!
```

## 宣告函式的其他方式

### 匿名函式 (Anonymous function)

有時候函式只會使用一次，這時函數的名稱就沒那麼重要，就可以使用匿名函式(Anonymous function)。

匿名函式(Anonymous function)是指沒有名稱的函式，通常用在回呼函式中。

範例：

```js
function sayHello(callback, name) {
  console.log("Hello, " + name + "!")
  callback(name)
}

sayHello(
  // 匿名函式
  function (name) {
    console.log("Goodbye, " + name + "!")
  },
  "Alice"
)

// Hello, Alice!
// Goodbye, Alice!
```

匿名函式也可以直接指定給變數

```js
let sayGoodbye = function (name) {
  console.log("Goodbye, " + name + "!")
}

function sayHello(callback, name) {
  console.log("Hello, " + name + "!")
  callback(name)
}

sayHello(
  // 匿名函式
  sayGoodbye,
  "Alice"
)
```

### 箭頭函式(Arrow function)

如果你覺得函式的語法太冗長，可以使用箭頭函式(Arrow function)來簡化。

語法：

```js
(parameter1, parameter2, ...) => {
  ...
}
```

- `parameter1, parameter2, ...`：參數，用來接收傳入的值。
- `=>`：箭頭符號，用來分隔參數與程式碼。
- `{}`：程式碼區塊。

範例：

```js
const sayHello = () => {
  console.log("Hello, world!")
}

sayHello() // Hello, world!
```

### 箭頭函式的簡寫

如果箭頭函式只有一行程式碼，可以省略大括號 `{}`。

```js
const sayHello = () => console.log("Hello, world!")

sayHello() // Hello, world!
```

如果箭頭函式只有一個參數，可以省略小括號 `()`。

```js
const sayHello = name => console.log("Hello, " + name + "!")
```

如果函式直接回傳值，可以省略 `return` 關鍵字，並省略大括號 `{}`。

```js
// 一般寫法
const addOld = (a, b) => {
  return a + b
}

// 簡化
const add = (a, b) => a + b

let result = add(3, 5)

console.log(result) // 8
```

### 箭頭函式的應用

箭頭函式常用在回呼函式中：

```js
const sayHello = (callback, name) => {
  console.log("Hello, " + name + "!")
  callback(name)
}

sayHello(
  // 箭頭函式
  name => {
    console.log("Goodbye, " + name + "!")
  },
  "Alice"
)

// Hello, Alice!
// Goodbye, Alice!
```

## 函式的遞迴 (Recursion)

有時候只使用迴圈會讓程式碼變得複雜，這時候可以使用遞迴(Recursion)來解決問題。

函式自己呼叫自己的行為，就叫遞迴。

通常用在處理樹狀結構或是數學運算。

範例：

```js
function factorial(n) {
  if (n === 0) {
    return 1
  } else {
    return n * factorial(n - 1)
  }
}

let result = factorial(5)

console.log(result) // 120
```

> 通常遞迴的函式跟迴圈的效果是一樣的，但是遞迴的程式碼通常比較簡潔。
>
> 但遞迴的效能較差，不適合用在大量資料的處理。
