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

## getElementsByClassName 使用指定的class獲取element
可能會取到很多個element

## getElementsByTagName 使用指定的html tag獲取element
可能會取到很多個element

## firstChild 獲取第一個子元素

## lastChild 獲取最後一個子元素

## children 獲取所有子元素

## childNodes 獲取所有子元素

## parentNode 獲取父元素

## previousSibling 獲取前面的兄弟元素

## nextSibling 獲取後面的兄弟元素

## innerHTML 獲取子元素的html

## innerText 獲取子元素的字串