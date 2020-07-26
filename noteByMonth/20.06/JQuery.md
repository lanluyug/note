### jQuery入口函数

```js
// 第一种写法
$(document).ready(function (){
    
})
// 第二种写法
jQuery(document).ready(function (){
    
})
// 第三种写法
$(function (){
    
})
// 第四种写法
jQuery(function (){
    
})
```

> 功能上相当于js中的(部分特性有区别)

```
function onload(){

}
```

> 可暂停入口函数执行

```js
$.holdReady(true)
```



### $冲突问题

```js
// 此时可用 自定义的j来代替$
var j = jQuery.noConflict()
```



### 内容选择器

```js
:contains(text)
:has(selector)
:empty()
:parent()
```

