# 修改DOM節點

## NODE.appendChild(childNode)
在Node底下子元素的末尾添加新的子元素

## NODE.append(childNode)
在Node底下子元素的末尾添加新的子元素

## NODE.prepend(Node or DOMString)
在Node底下子元素的開頭添加新的子元素

## NODE.insertBefore(newNode, refNode) 將新的元素插入NODE的前面

## NODE.replaceChild(newChildNode, oldChildNode) 替換指定的子元素

## NODE.removeChild(childNode) 刪除指定的子元素

## NODE.remove() 刪除自己

## insertAfter js沒有提供這個方法，需要自行添加
```js
function insertAfter (newElement, targetElement) {
	var parent = targetElement.parentNode;
	if (parent.lastChild == targetElement) {
		parent.appendChild(newElement);
	}else{
		parent.insertBefore(newElement,targetElement.nextSibling);
	}
}
```