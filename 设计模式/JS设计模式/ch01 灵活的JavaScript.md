### 用对象收编变量

> 日常方法定义1

```js
function checkName(){}
function checkEmail(){}
function checkPassword(){}
```

> 日常方法定义2

```js
var checkName = ()=>{}
var checkEmail =()=>{}
var checkPassword=()=>{}
```

> 推荐定义1 （**减少变量数量**）

```js
var CheckObject = {
    checkName(){},
    checkEmail(){},
    checkPassword(){}
}
```

> 推荐定义2

```js
var CheckObject = () =>{}
CheckObject.checkName = ()=>{}
CheckObject.checkEmail = ()=>{}
CheckObject.checkPassword = ()=>{}
```

> 上述对象不可复制
>
> 可复制，互不影响

```js
var CheckObject = function(){
    return {
        checkName(){},
        checkEmail(){},
        checkPassword(){}
    }
}
```

> 创建的对象与CheckObject无关(此类对象可以看成类)

```js
var CheckObject = {
    this.checkName = ()=>{}
	this.checkEmail =()=>{}
	this.checkPassword=()=>{}
}
// 可以通过new 来实例化

var a = new CheckObject()
a.checkName()
```

> 上述每次创建类都会对类的this属性进行复制，消耗内存比较奢侈，改进一下：

```js
var CheckObject = function(){
    CheckObject.prototype.checkName = () =>{}
    CheckObject.prototype.checkEmail = () =>{}
    CheckObject.prototype.checkPassword = () =>{}
}
```

> 创建类时，复制的函数不能采用()=> （ES6箭头函数），箭头函数无constructor方法；

> 上面所依赖的方法就只有一个，但prorotype要写多遍，可改进写法：

```js
var CheckObject = function(){}
CheckObject.prototype = {
    checkName(){},
    checkEmail(){},
    checkPassword(){}
}

//调用
var a = new  CheckObject()
a.checkName()
a.checkEmail()
a.checkPassword()
```

> 以上两种方式不能混合着使用，对象赋值会出现覆盖前面的prototype对象

> 链式调用

```js
var CheckObject = {
    checkName(){
        return this
    },
    checkEmail(){
        return this
    },
    checkPassword(){
        return this
    }
}
CheckObject.checkName().checkEmail().checkPassword()
```

> 同样，可以放入类的原型中

```js
var CheckObject = () =>{}
CheckObject.prototype = {
    checkName(){return this},
    checkEmail(){return this},
    checkPassword(){return this}
}
var a = new CheckObject()
a.checkName().checkEmail().checkPassword()
```

> 为每个函数都添加一个检测邮箱的方法

```js
Function.prototype.checkEmail = () =>{}

// 使用时
var f = () =>{}
f.checkEmail()
// 或者
var f = new Function()
f.checkName()
```

> 但上述代码会污染整个原生的Function,造成不必要的开销

> 可以抽象出一个统添加方法的功能方法

```js
Function.prototype.addMethod = (name, fn) => this[name] = fn

var methods = () =>{}
// 或者
// var methods = new Function()

methods.addMethod('checkName',()=>{})
methods.addMethod('checkEmail',()=>{})
methods.checkName()
methods.checkEmail()
```

> 链式添加

```js
Function.prototype.addMethod = (name, fn) => {
    this[name] = fn
    return this
}

var methods = () =>{}
// 或者
// var methods = new Function()

methods.addMethod('checkName',()=>{return this}).addMethod('checkEmail',()=>{return this})
methods.checkName().checkEmail()
```

> 使用类方式创建方法

```js
Function.prototype.addMethod = (name, fn) => {
    this.prototype[name] = fn
    return this
}

var Methods = () =>{}
// 或者
// var methods = new Function()

methods.addMethod('checkName',()=>{return this}).addMethod('checkEmail',()=>{return this})
var m = new Methods()
m.checkEmail()
```

