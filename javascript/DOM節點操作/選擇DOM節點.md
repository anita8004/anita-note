# 選擇DOM節點

## querySelector 取得指定element
只會取到一個element
```html
<div id="hello">
  <div class="world">Hello World!</div>
</div>
```
```js
const hello = document.querySelector('#hello');
const world = hello.querySelector('.world');
console.log(world.innerText); // Hello World!
```

## querySelectorAll 取得複數個element
```html
<ul class="list">
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
```
```js
const list = document.querySelector('.list');
const items = list.querySelectorAll('li');
console.log(items);
// [<li>1</li>, <li>2</li>, <li>3</li>]
```

## getElementById 使用指定的id獲取element
只會取到一個element
```html
<div id="container"></div>
```
```js
const container = document.getElementById('container');
```

## getElementsByClassName 使用指定的class獲取element
可能會取到很多個element
```html
<ul class="list">
  <li class="list-item"></li>
  <li class="list-item"></li>
  <li class="list-item"></li>
</ul>
```
```js
const listItems = document.getElementsByClassName('list-item');
```

## getElementsByTagName 使用指定的html tag獲取element
可能會取到很多個element
```html
<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>
```
```js
const listItems = document.getElementsByTagName('li');
```

## firstChild 獲取第一個子元素
```html
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
```
```js
const ul = document.querySelector('ul');
console.log(ul.firstChild) // <li>1</li>
```

## lastChild 獲取最後一個子元素
```html
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
```
```js
const ul = document.querySelector('ul');
console.log(ul.lastChild) // <li>3</li>
```

## children 獲取所有子元素
```html
<ul>
  <li>1</li>
  <li>2</li>
  <li>3</li>
</ul>
```
```js
const ul = document.querySelector('ul');
console.log(ul.children) // <li>1</li><li>2</li><li>3</li>
```

## childNodes 獲取所有子元素
```js
const ul = document.querySelector('ul');
console.log(ul.childNodes) // <li>1</li><li>2</li><li>3</li>
```

## parentNode 獲取父元素
```html
<ul>
  <li class="first-item">1</li>
  <li>2</li>
  <li>3</li>
</ul>
```
```js
const firstItem = document.querySelector('.first-item');
console.log(firstItem.parentNode) // <ul>...</ul>
```

## previousSibling 獲取前面的兄弟元素
```html
<p>Hello</p><b>World!</b>
```
```js
const b = document.querySelector('b');
console.log(b.previousSibling) // <p>Hello</p>
```

## nextSibling 獲取後面的兄弟元素
```html
<p>Hello</p><b>World!</b>
```
```js
const p = document.querySelector('p');
console.log(p.nextSibling) // <b>World!</b>
```

> ps. 元素之间的空白也是文本节点。

```html
<p>Hello</p> <!-- 如果element之間有換行就會多出一個文本節點 -->
<b>World!</b>
```
```js
const p = document.querySelector('p');
console.log(p.nextSibling) // ''
```

## innerHTML 獲取/設定子元素的html
可以獲取/設定html格式的內容
```html
<p></p>
```
```css
span { color: red; }
```
```js
const p = document.querySelector('p');
p.innerHTML = "Hello <span>World</span>!";
```

Output:

![Alt text](<innerHTML-output.png>)

## innerText 獲取/設定子元素的字串
可以獲取/設定純文字的內容
```html
<p></p>
```
```css
span { color: red; }
```
```js
const p = document.querySelector('p');
p.innerText = "Hello <span>World</span>!";
```

Output:

![Alt text](<innerText-output.png>)

## Node.hasChildNodes() 判斷是否包含子節點
返回布林值

```html
<ul>
  <li></li>
</ul>
<div></div>
```

```js
const ul = document.querySelector('ul');
console.log(ul.hasChildNodes()); // true

const div = document.querySelector('div');
console.log(div.hasChildNodes()); // false
```
