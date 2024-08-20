# Javascript tutorial 3 - 條件判斷式 (Condition)

## 什麼是條件判斷式

有時候我們需要根據不同的條件來執行不同的程式碼，這時候就需要使用條件判斷式。

條件判斷式 (condition) 是用來判斷程式中的條件是否成立，如果條件成立則執行某些程式碼，如果條件不成立則執行其他程式碼。

## 條件判斷式的種類

### if 如果...就

`if` 是最基本的條件判斷式，當條件成立時執行程式碼。

語法：

```js
if (condition) {
  ...
}
```

- `if`：關鍵字，用來宣告條件判斷式。
- `condition`：條件，通常是一個比較式，例如 `num > 5`。
- `{}`：大括號內的程式碼，是當條件成立時要執行的程式碼。

範例：

```js
let num = 10

if (num > 5) {
  console.log("num 大於 5")
}
```

> 如果程式碼只有一行，可以省略大括號 `{}`：
>
> ```js
> if (num > 5) console.log("num 大於 5")
> ```
>
> 換行是為了程式碼的可讀性，並不會影響程式的執行，但**強烈建議要**，請養成良好的程式碼習慣（同時不要殘害自己的大腦 XD）。

### if...else 如果...就...否則

`if...else` 是當條件成立時執行某些程式碼，條件不成立時執行其他程式碼。

語法：

```js
if (condition) {
  ...
} else {
  ...
}
```

- `else`：關鍵字，用來宣告條件不成立時要執行的程式碼。

範例：

```js
let num = 10

if (num > 5) {
  console.log("num 大於 5")
} else {
  console.log("num 小於等於 5")
}
```

### if...else if 如果...就...否則如果

當有多個條件需要判斷時，可以使用 `if...else if`。

語法：

```js
if (condition1) {
  ...
} else if (condition2) {
  ...
} else {
  ...
}
```

- `else if`：關鍵字，用來宣告條件不成立時要繼續判斷的程式碼。

範例：

```js
let num = 10

if (num > 5) {
  console.log("num 大於 5")
} else if (num < 5) {
  console.log("num 小於 5")
} else {
  console.log("num 等於 5")
}
```

> 可以有多個 `else if`，但只會執行第一個符合條件的程式碼。

### switch...case 多重條件判斷

`switch...case` 是另一種多重條件判斷的方式，當有多個條件需要判斷時，也可以使用 `switch...case`。

語法：

```js
switch (expression) {
  case value1:
    ...
    break
  case value2:
    ...
    break
  default:
    ...
}
```

- `switch`：關鍵字，用來宣告多重條件判斷。
- `expression`：要判斷的表達式，通常是變數或值。
- `case`：當表達是符合值時要執行的程式碼。
- `break`：用來跳出 `switch` 條件式。
- `default`：當沒有符合的條件時。

> 中文意思就是：「根據 `expression` 的值，執行對應的程式碼，如果都不符合，就執行 `default` 的程式碼」。

範例：

```js
let num = 100

switch (num) {
  case 5:
    console.log("num 等於 5")
    break
  case 10:
    console.log("num 等於 10")
    break
  default:
    console.log("num 不等於 5 也不等於 10")
}
```

> 如果沒有 `break`，會繼續執行下一個 `case` 的程式碼。
>
> 以這個範例，default case 下的程式碼也會被執行。

### 三元運算子 (Ternary Operator)

三元運算子是一種簡潔的寫法，用來取代 `if...else` 的語法。

語法：

```js
condition ? expression1 : expression2
```

- `condition`：條件，通常是一個比較式，例如 `num > 5`。
- `expression1`：條件成立時要執行的程式碼。
- `expression2`：條件不成立時要執行的程式碼。

範例：

```js
let num1 = 10
let num2 = 5

let result = num1 > num2 ? "num1 大於 num2" : "num1 小於 num2"

console.log(result) // num1 大於 num2
```

## 作用域 (Scope)

在 JavaScript 中，變數的作用域 (scope) 是指變數的有效範圍，也就是變數可以被存取的範圍。

### 區域變數 (Local Variable)

顧名思義，區域變數是指在區域範圍`{}`內宣告的變數，只能在區域範圍`{}`內存取。

範例：

```js
{
  let x = 10
  console.log(x) // 10
}

console.log(x) // Uncaught ReferenceError: x is not defined
```

### 全域變數 (Global Variable)

在全域範圍內宣告的變數是全域變數，可以在程式的任何地方存取。

範例：

```js
let x = 10

{
  console.log(x) // 10
}

console.log(x) // 10
```

## 總結

- 條件判斷式是用來判斷程式中的條件是否成立，根據條件的結果執行不同的程式碼。
- `if` 是最基本的條件判斷式，當條件成立時執行程式碼。
- `if...else` 是當條件成立時執行某些程式碼，條件不成立時執行其他程式碼。
- `if...else if` 是當有多個條件需要判斷時，可以使用 `if...else if`。
- `switch...case` 是另一種多重條件判斷的方式，根據 `expression` 的值執行對應的程式碼。
- 三元運算子是一種簡潔的寫法，用來取代 `if...else` 的語法。
- 變數的作用域是指變數的有效範圍，區域變數只能在區域範圍內存取，全域變數可以在程式的任何地方存取。
