# Javascript tutorial 9 - 事件 (Event)

## 什麼是事件

事件（Event）是指網頁中的各種操作，例如：點擊、滑鼠移動、鍵盤輸入等等。當使用者進行這些操作時，瀏覽器會觸發相對應的事件，並執行相對應的程式碼。

## 事件的種類

常見的事件有很多種，以下是其中幾種常見的事件：

- `click`：點擊事件
- `mouseover`：滑鼠移入事件
- `mouseout`：滑鼠移出事件
- `keydown`：按下鍵盤事件
- `keyup`：放開鍵盤事件

完整的事件列表可以參考 [MDN Web Docs](https://developer.mozilla.org/zh-TW/docs/Web/Events)。

## 事件的監聽

在 HTML 中，可以使用 `on` 屬性來監聽事件。

語法：`<element onevent="function">`

- `element`：要監聽的元素
- `onevent`：要監聽的事件名稱
- `function`：當事件觸發時要執行的函式

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>事件監聽範例</title>
  </head>
  <body>
    <button id="btn" onclick="alert('Hello, World!')">點我</button>
  </body>
</html>
```

在 JavaScript 中，可以使用 `addEventListener()` 方法來監聽事件。

語法：`element.addEventListener(event, function)`

- `element`：要監聽的元素
- `event`：要監聽的事件名稱
- `function`：當事件觸發時要執行的函式

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>事件監聽範例</title>
  </head>
  <body>
    <button id="btn">點我</button>

    <script>
      let btn = document.getElementById("btn")
      btn.addEventListener("click", function () {
        alert("Hello, World!")
      })
    </script>
  </body>
</html>
```
