# Javascript tutorial 6 - 物件 (Object)

## 什麼是物件

物件(Object)是一種資料結構，可以用來儲存多個值，每個值都有一個名稱，稱為屬性(property)。

就比如一個人，可以有姓名、年齡、性別等屬性，這些屬性就是物件的屬性。

## 宣告物件

宣告物件的語法是使用大括號 `{}` 包住多個屬性，每個屬性使用冒號 `:` 分隔名稱和值，屬性之間使用逗號 `,` 分隔。

語法：

```js
let object = {
  property1: value1,
  property2: value2,
}
```

- `object` 是物件名稱
- `property` 是屬性名稱
- `value` 是屬性值

範例：

```js
let person = {
  name: "Alice",
  age,
}
```

## 獲得物件的屬性

獲得、訪問 (access) 物件的屬性可以使用點 `.` 或中括號 `[]`。

範例：

```js
let person = {
  name: "Alice",
  age: 18,
}

console.log(person.name) // Alice
console.log(person["age"]) // 18
```

通常使用點 `.` 的方式比較簡潔，但是如果屬性名稱包含特殊字元或變數時，必須使用中括號 `[]` 的方式。

範例：

```js
let person = {
  first name: "Alice",
  last name: "Smith",
}
console.log(person["first name"]) // Alice

let key = "name"
console.log(person["last " + key]) // Alice

console.log(person.first name) // 錯誤
```

## 刪除物件的屬性

刪除物件的屬性可以使用 `delete` 關鍵字。

範例：

```js
let person = {
  name: "Alice",
  age: 18,
}

delete person.age
console.log(person) // { name: "Alice" }
```

## 物件的屬性

物件的屬性可以是任何型別，包括數值、字串、布林、陣列、物件等。

範例：

```js
let person = {
  name: "Alice",
  age: 18,
  isStudent: true,
  scores: [90, 80, 70],
  address: {
    city: "Taipei",
    street: "Zhongxiao East Road",
  },
}
```

## 物件的方法 (Method)

物件的屬性也可以是函式，稱為方法(method)。

範例：

```js
let person = {
  name: "Alice",
  sayHello: function () {
    console.log("Hello, my name is " + person.name)
  },

  // 簡寫語法
  sayHi() {
    console.log("Hi, my name is " + person.name)
  },
}

person.sayHello() // Hello, my name is Alice
```

## 物件的屬性列舉

可以使用 `for...in` 迴圈對物件的屬性進行列舉。

語法：

```js
for (let key in object) {
  ...
}
```

- `key` 是屬性名稱
- `object` 是物件

範例：

```js
let person = {
  name: "Alice",
  age: 18,
}

for (let key in person) {
  console.log(person[key])
}

// Alice
// 18
```

## this 關鍵字

在物件的方法中，可以使用 `this` 關鍵字來存取物件本身。

範例：

```js
let person = {
  name: "Alice",
  sayHello: function () {
    console.log("Hello, my name is " + this.name)
  },
}

person.sayHello() // Hello, my name is Alice
```

> 在這個範例中，`this` 代表物件 `person` 本身。

箭頭函式(Arrow function)中的 `this` 關鍵字會繼承外層的 `this`。

範例：

```js
let person = {
  name: "Alice",
  sayHello: function () {
    console.log("Hello, my name is " + this.name)
    //this 代表 person

    let innerFunction = () => {
      console.log("Hello, my name is " + this.name)
      //這裡this繼承sayHello的this，所以也代表person
    }
  },
  sayGoodbye: () => {
    console.log("Goodbye, my name is " + this.name)
    //這裡this代表全域物件，目前是undefined
  },
}

person.sayHello() // Hello, my name is Alice
person.sayGoodbye() // Goodbye, my name is undefined
```

> 在這個範例中，`sayHello` 方法中的 `innerFunction` 繼承了外層的 `this`，所以可以正確存取 `name` 屬性。而 `sayGoodbye` 方法是箭頭函式，繼承了外層的 `this`，但是外層的 `this` 是 `undefined`，所以無法存取 `name` 屬性。

## 物件的建構函式 (Constructor)

如果要建立多個相同結構的物件，可以使用建構函式(Constructor)來定義物件的結構。

就像現實中的身分證，每張身分證都有姓名、性別、出生日期等屬性，而身分證的結構是一樣的。

語法：

```js
function ObjectName(property1, property2) {
  this.property1 = property1
  this.property2 = property2
}

let object = new ObjectName(value1, value2)
```

範例：

```js
function IdentityCard(name, age, address) {
  this.name = name
  this.age = age
  this.address = address
}

let alice = new IdentityCard("Alice", 18, "Taipei")

console.log(alice) // IdentityCard { name: "Alice", age: 18, address: "Taipei" }
```

## 解構 (Destructuring assignment)

會不會嫌物件的取值方式太麻煩呢？

解構賦值(Destructuring assignment)是一種用來從物件中取得屬性值的語法。

語法：

```js
let { property1, property2 } = object
```

- `property1`, `property2` 是要取得的屬性名稱

範例：

```js
let person = {
  name: "Alice",
  age: 18,
}

let { name, age } = person

console.log(name) // Alice
console.log(age) // 18
```

解構賦值也可以用來取得物件的屬性值並賦值給變數。

範例：

```js
let person = {
  name: "Alice",
  age: 18,
}

let { name: personName, age: personAge } = person

console.log(personName) // Alice
console.log(personAge) // 18
```

## 物件中的展開運算子 (Spread operator)

展開運算子(Spread operator)是一種用來將物件展開成多個屬性的語法。

範例：

```js
let person = {
  name: "Alice",
  age: 18,
}

let person2 = {
  ...person,
  isStudent: true,
}

console.log(person2) // { name: "Alice", age: 18, isStudent: true }
```

## 總結

- 物件是一種資料結構，可以用來儲存多個值，每個值都有一個名稱，稱為屬性(property)。
- 物件的屬性可以是任何型別，包括數值、字串、布林、陣列、物件等。
- 物件的屬性也可以是函式，稱為方法(method)。
- 可以使用 `for...in` 迴圈對物件的屬性進行列舉。
- 在物件的方法中，可以使用 `this` 關鍵字來存取物件本身。
- 物件的建構函式(Constructor)可以用來建立多個相同結構的物件。
- 解構賦值(Destructuring assignment)是一種用來從物件中取得屬性值的語法。
- 展開運算子(Spread operator)是一種用來將物件展開成多個屬性的語法。
