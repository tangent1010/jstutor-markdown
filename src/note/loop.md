# Javascript tutorial 4 - 迴圈 (Loop)

## 什麼是迴圈

當需要重重複做同樣的事情時，原本的做法是將程式碼複製貼上，但這樣會讓程式碼變得冗長且難以維護。

而迴圈(loop)是一種程式結構，可以讓程式碼重複執行，直到滿足某個條件為止。

## for 迴圈

`for` 迴圈是一種最常用的迴圈，可以讓程式碼重複執行指定次數。

語法：

```js
for (initialization; condition; increment) {
  ...
}
```

- `for`：關鍵字，用來宣告迴圈。
- `initialization`：初始化變數，通常是設定一個變數，用來計數。
- `condition`：條件，當條件成立時，執行程式碼。
- `increment`：遞增（或遞減），每次執行完程式碼後，讓變數遞增；需配合條件避免無窮迴圈 (infinite loop)。

範例：

```js
for (let i = 0; i < 5; i++) {
  console.log(i)
}
```

> 中文意思就是「從 0 開始，當 i 小於 5 時，執行程式碼，每次執行完程式碼後，i 遞增 1」。

## while 迴圈

`while` 迴圈是當條件成立時，重複執行程式碼。

語法：

```js
while (condition) {
  ...
}
```

- `while`：關鍵字，用來宣告迴圈。
- `condition`：條件，當條件成立時，執行程式碼。

範例：

```js
let i = 0

while (i < 5) {
  console.log(i)
  i++
}
```

> 請注意，`while` 迴圈的條件必須在迴圈內部改變，否則會造成無窮迴圈。

## 迴圈的控制 (break, continue)

在迴圈中，可以使用 `break` 關鍵字來**結束**迴圈，也可以使用 `continue` 關鍵字來**跳過**當前迴圈，繼續執行下一次迴圈。

範例：

```js
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    break
  }

  console.log(i)
}
// 0
// 1
// 2
```

> 這個範例中，當 `i` 等於 3 時，會執行`break` 結束迴圈。

```js
for (let i = 0; i < 5; i++) {
  if (i === 3) {
    continue
  }

  console.log(i)
}
// 0
// 1
// 2
// 4
```

> 這個範例中，當 `i` 等於 3 時，會執行 `continue` 跳過當前迴圈，繼續執行下一次迴圈。

## 總結

- 迴圈是一種程式結構，可以讓程式碼重複執行。
- `for` 迴圈是用來重複執行指定次數的程式碼。
- `while` 迴圈是用來重複執行當條件成立的程式碼。
- `break` 關鍵字可以結束迴圈。
- `continue` 關鍵字可以跳過當前迴圈，繼續執行下一次迴圈。
