# classList

## classList.length 返回类列表中类的数量

## classList.add(class1, class2, ...) 在元素中添加一个或多个类名。
```js
document.getElementById("myDIV").classList.add("mystyle");
```

## classList.contains(class) 返回布尔值，判断指定的类名是否存在。

## classList.item(index) 返回元素中索引值对应的类名。索引值从 0 开始。
如果索引值在区间范围外则返回 null

## classList.remove(class1, class2, ...) 移除元素中一个或多个类名。
注意： 移除不存在的类名，不会报错。

## classList.toggle(class, true|false) 在元素中切换类名。