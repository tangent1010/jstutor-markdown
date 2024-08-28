# Javascript tutorial 8 - 文件物件模型 (DOM)

## 什麼是 DOM

DOM（Document Object Model）是一種用來描述網頁結構的模型，可以將網頁中的元素（例如：標籤、屬性、文字）視為物件，並使用這些物件來操作網頁。

簡單來說，DOM 就是一個用來操作網頁的介面，可以透過程式碼來新增、刪除、修改網頁元素。

## 存取 DOM 元素

存取 DOM 元素的方法有很多種，以下是其中幾種常見的方法：

### 1. 使用 `document.getElementById()`

`document.getElementById()` 方法可以用來取得指定 ID 的元素。

語法：`document.getElementById(id)`

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <h1 id="title">Hello, World!</h1>

    <script>
      let title = document.getElementById("title")
      console.log(title) // <h1 id="title">Hello, World!</h1>
    </script>
  </body>
</html>
```

### 2. 使用 `document.querySelector()`

`document.querySelector()` 方法可以用來取得符合指定 CSS 選擇器的第一個元素。

語法：`document.querySelector(selector)`

- `selector`：CSS 選擇器，例如：`#id`、`.class`、`tag` 等等

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <h1 class="title">Hello, World!</h1>

    <script>
      let title = document.querySelector(".title")
      console.log(title) // <h1 class="title">Hello, World!</h1>
    </script>
  </body>
</html>
```

### 3. 使用 `document.querySelectorAll()`

`document.querySelectorAll()` 方法可以用來取得符合指定 CSS 選擇器的所有元素。

語法：`document.querySelectorAll(selector)`

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <h1 class="title">Hello, World!</h1>
    <p class="content">Lorem ipsum dolor sit amet.</p>

    <script>
      let elements = document.querySelectorAll(".title, .content")
      console.log(elements) // NodeList(2) [h1.title, p.content]
    </script>
  </body>
</html>
```

## 修改 DOM 元素

修改 DOM 元素的方法有很多種，以下是其中幾種常見的方法：

### 1. 修改元素的文字內容

可以使用 `textContent` 屬性來修改元素的文字內容。

語法：`element.textContent = text`

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <h1 id="title">Hello, World!</h1>

    <script>
      let title = document.getElementById("title")
      title.textContent = "Hello, JavaScript!"
    </script>
  </body>
</html>
```

### 2. 修改元素的樣式

可以使用 `style` 屬性來修改元素的樣式。

語法：`element.style.property = value`

- `property`：要修改的樣式屬性，例如：`color`、`fontSize`、`backgroundColor` 等等

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <h1 id="title">Hello, World!</h1>

    <script>
      let title = document.getElementById("title")
      title.style.color = "red"
      title.style.fontSize = "24px"
    </script>
  </body>
</html>
```

### 3. 新增元素

可以使用 `document.createElement()` 方法來新增元素。

語法：`document.createElement(tagName)`

- `tagName`：要新增的元素的標籤名稱，例如：`div`、`p`、`span` 等等

然後使用 `element.appendChild()` 方法將元素加入到指定的父元素中。

語法：`parentElement.appendChild(childElement)`

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <div id="container"></div>

    <script>
      let container = document.getElementById("container")
      let paragraph = document.createElement("p")
      paragraph.textContent = "Lorem ipsum dolor sit amet."
      container.appendChild(paragraph)
    </script>
  </body>
</html>
```

### 4. 刪除元素

可以使用 `element.remove()` 方法來刪除元素。

語法：`element.remove()`

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <div id="container">
      <p>Lorem ipsum dolor sit amet.</p>
    </div>

    <script>
      let paragraph = document.querySelector("p")
      paragraph.remove()
    </script>
  </body>
</html>
```

也可以刪除元素的子元素，例如：`element.removeChild()` 方法。

語法：`element.removeChild(child)`

- `child`：要刪除的子元素

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <div id="container">
      <p>Lorem ipsum dolor sit amet.</p>
    </div>

    <script>
      let container = document.getElementById("container")
      let paragraph = document.querySelector("p")
      container.removeChild(paragraph)
    </script>
  </body>
</html>
```

### 5. 替換元素

可以使用 `element.replaceWith()` 方法來替換元素。

語法：`element.replaceWith(newElement)`

- `newElement`：要替換的新元素

範例：

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM 範例</title>
  </head>
  <body>
    <div id="container">
      <p>Lorem ipsum dolor sit amet.</p>
    </div>

    <script>
      let container = document.getElementById("container")
      let newParagraph = document.createElement("p")
      newParagraph.textContent = "Hello, World!"
      container.replaceWith(newParagraph)
    </script>
  </body>
</html>
```
