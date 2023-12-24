# 新增DOM節點

## document.createElement(tagName) 新增html標籤
```js
const newDiv = document.createElement('div');
newDiv.id = "id_name";
newDiv.className = "class_name";
```
Output:
```html
<div id="id_name" class="class_name"></div>
```

## document.createTextNode(string) 新增文字節點
```js
const textNode = document.createTextNode("Hello World!");
// 接上一項的newDiv
newDiv.appendChild(textNode);
```
Output:
```html
<div id="id_name" class="class_name">Hello World!</div>
```

## document.createDocumentFragment() 新增虛擬DOM
是一種沒有父層節點的「最小化文件物件」。
當需要進行大量的 DOM 操作時，用 DocumentFragment 的效能會比直接操作 DOM 好很多。
```js
// 取得外層容器 myList
var ul = document.getElementById("myList");

// 建立一個 DocumentFragment，可以把它看作一個「虛擬的容器」
var fragment = document.createDocumentFragment();

for (var i = 0; i < 3; i++){
  // 生成新的 li，加入文字後置入 fragment 中。
  let li = document.createElement("li");
  li.appendChild(document.createTextNode("Item " + (i+1)));
  fragment.appendChild(li);
}

// 最後將組合完成的 fragment 放進 ul 容器
ul.appendChild(fragment);
```
Output:
```html
<ul>
  <li>Item 0</li>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

## document.write() 將內容寫入網頁
```js
// example 1
document.write("<script type=\"text\javascript\" src=\"file.js\">" + "<\/script>");

// example 2
// 需要特別注意的是，當網頁已經讀取完成後才執行 document.write()，則裡面的內容會完全覆蓋掉目前的網頁
window.onload = function(){
  document.write("Hello world!");
};
```