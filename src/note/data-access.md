# Javascript tutorial 10 - 資料存取 (Data Access)

## 什麼是資料存取

資料存取（Data Access）是指從網頁中讀取或寫入資料的過程。在網頁開發中，我們常常需要從後端伺服器讀取資料（例如：使用者資訊、文章內容等），或將使用者輸入的資料儲存到後端伺服器中。

## 非同步函式

在 Javascript 中，函式可以分為兩種類型：同步函式（Synchronous Function）和非同步函式（Asynchronous Function）。

同步函式是指函式會依序執行，直到函式執行完畢後才會繼續執行下一行程式碼。

非同步函式是指函式會在背景執行，不會阻塞程式的執行，當函式執行完畢後會呼叫一個回調函式。

在網頁開發中，我們常常會使用非同步函式來處理資料存取。

### 承諾 (Promise)

Promise 是一種用來處理非同步操作的物件。它代表一個尚未完成但預計會在未來完成的操作。Promise 有三種狀態：

- Pending：操作尚未完成。
- Fulfilled：操作成功完成。
- Rejected：操作失敗。

Promise 的語法如下：

```js
let promise = new Promise((resolve, reject) => {
  // 非同步操作
})
```

- `resolve`：用來處理操作成功的情況。
- `reject`：用來處理操作失敗的情況。

範例：

```js
let promise = new Promise((resolve, reject) => {
  // 模擬非同步操作
  setTimeout(() => {
    if (Math.random() > 0.5) {
      resolve("操作成功")
    } else {
      reject("操作失敗")
    }
  }, 1000)
})
```

Promise 可以使用 `.then()` 方法來處理操作成功的情況，使用 `.catch()` 方法來處理操作失敗的情況。

#### then

`.then()` 方法用來處理 Promise 物件成功的情況。它接受兩個回調函式作為參數：

- 第一個回調函式用來處理操作成功 (result) 的情況。
- 第二個回調函式用來處理操作失敗 (error) 的情況。（可選）

範例：

```js
let promise = new Promise((resolve, reject) => {
  // 模擬非同步操作
  setTimeout(() => {
    if (Math.random() > 0.5) {
      resolve("操作成功")
    } else {
      reject("操作失敗")
    }
  }, 1000)
})

promise.then(
  result => {
    console.log(result)
  },
  error => {
    console.error(error)
  }
)
```

> Promise 的 `.then()` 方法可以串接多個，用來處理多個非同步操作。

#### catch

`.catch()` 方法用來處理 Promise 物件失敗的情況。它接受一個回調函式作為參數，用來處理操作失敗的情況。

範例：

```js
let promise = new Promise((resolve, reject) => {
  // 模擬非同步操作
  setTimeout(() => {
    if (Math.random() > 0.5) {
      resolve("操作成功")
    } else {
      reject("操作失敗")
    }
  }, 1000)
})

promise
  .then(result => {
    console.log(result)
  })
  .catch(error => {
    console.error(error)
  })
```

> `.catch()` 方法可以用來處理 `.then()` 方法中的錯誤。
>
> 更常見的寫法是使用 `.catch()` 方法來處理所有的錯誤，而非使用 `.then()` 方法中的第二個回調函式。

#### finally

`.finally()` 方法用來處理 Promise 物件無論成功或失敗都會執行的情況。

它接受一個回調函式作為參數。

範例：

```js
let promise = new Promise((resolve, reject) => {
  // 模擬非同步操作
  setTimeout(() => {
    if (Math.random() > 0.5) {
      resolve("操作成功")
    } else {
      reject("操作失敗")
    }
  }, 1000)
})

promise
  .then(result => {
    console.log(result)
  })
  .catch(error => {
    console.error(error)
  })
  .finally(() => {
    console.log("操作完成")
  })
```

### async/await

`async` 和 `await` 是 ES2017 的新特性，用來簡化 Promise 的使用。

`async` 用來定義一個函式是非同步的，而 `await` 用來等待 Promise 物件的執行結果。

範例：

```js
let promise = new Promise((resolve, reject) => {
  // 模擬非同步操作
  setTimeout(() => {
    if (Math.random() > 0.5) {
      resolve("操作成功")
    } else {
      reject("操作失敗")
    }
  }, 1000)
})

promise
  .then(result => {
    console.log(result)
  })
  .catch(error => {
    console.error(error)
  })

async function doSomething() {
  try {
    let result = await promise
    console.log(result)
  } catch (error) {
    console.error(error)
  }
}
doSomething()
```

- `async`：用來定義一個函式是非同步的。
- `await`：用來等待 Promise 物件的執行結果。
- `try`：用來執行可能會拋出錯誤的程式碼。
- `catch`：用來處理錯誤。

> `async` 函式會回傳一個 Promise 物件，可以使用 `.then()` 方法來處理操作成功的情況，使用 `.catch()` 方法來處理操作失敗的情況。
>
> `await` 只能在 `async` 函式中使用。
>
> `try` 和 `catch` 用來處理錯誤，可以用來取代 `.catch()` 方法。
>
> 可以使用 `throw` 關鍵字拋出錯誤。

## 資料存取

在網頁開發中，我們常常需要從後端伺服器讀取資料，或將使用者輸入的資料儲存到後端伺服器中。

### API

API（Application Programming Interface）是一組定義如何與軟體元件進行互動的規範。在網頁開發中，API 通常用來從後端伺服器讀取資料。

現實生活中，餐廳的內場與外場之間的溝通就是一種 API。外場服務生將客人的點餐需求傳遞給內場廚師，廚師根據客人的需求製作菜餚，再將菜餚送到外場服務生手中，最後服務生將菜餚送到客人手中。

在網頁開發中，API 通常是一個 URL，用來從後端伺服器讀取資料。

### Fetch

`fetch()` 函式用來從網路中取得資源，例如：從後端伺服器讀取資料。

`fetch()` 函式是一個非同步函式，它會回傳一個 Promise 物件。

範例：

```js
fetch("https://jsonplaceholder.typicode.com/posts")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error))
```

### JSON

JSON（JavaScript Object Notation）是一種資料格式，常用來儲存和交換資料。

以下是一個 JSON 格式的範例：

```json
{
  "name": "Alice",
  "age": 18,
  "friends": ["Bob", "Charlie"]
}
```

JSON 格式的資料可轉成一個 JavaScript 物件，可以使用 `JSON.parse()` 方法將 JSON 格式的資料轉換為 JavaScript 物件；使用 `JSON.stringify()` 方法將 JavaScript 物件轉換為 JSON 格式的資料。

範例：

```js
let json = '{"name": "Alice", "age": 18}'
let obj = JSON.parse(json)
console.log(obj) // { name: 'Alice', age: 18 }

let obj = { name: "Alice", age: 18 }
let json = JSON.stringify(obj)
console.log(json) // '{"name":"Alice","age":18}'
```

### LocalStorage

LocalStorage 是一種瀏覽器提供的儲存機制，可以將資料儲存在瀏覽器中。

LocalStorage 是一種 Key-Value 儲存機制，可以將資料以 Key-Value 的形式存入 LocalStorage 中。

LocalStorage 的資料是永久性的，除非使用者手動刪除，否則資料會一直存在。

#### 存取資料

可以使用 `localStorage.setItem()` 方法將資料存入 LocalStorage 中，使用 `localStorage.getItem()` 方法取得資料。

範例：

```js
localStorage.setItem("name", "Alice")
let name = localStorage.getItem("name")
console.log(name) // Alice
```

#### 刪除資料

可以使用 `localStorage.removeItem()` 方法刪除 LocalStorage 中的資料。

範例：

```js
localStorage.removeItem("name")
let name = localStorage.getItem("name")
console.log(name) // null
```

#### 清空資料

可以使用 `localStorage.clear()` 方法清空 LocalStorage 中的所有資料。

範例：

```js
localStorage.setItem("name", "Alice")
localStorage.clear()
let name = localStorage.getItem("name")
console.log(name) // null
```

#### 其他方法

- `localStorage.key(index)`：取得指定索引的 Key。
- `localStorage.length`：取得 LocalStorage 中的資料筆數。
