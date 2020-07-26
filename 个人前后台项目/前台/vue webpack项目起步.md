### 环境准备

* node环境 和 基于shell的命令行工具，如windows下的git bash, mac 和 linux下的terminal，以下统称为终端。

* npm包管理工具，最好在3.x以上，npm 3.x提供了更有效的包依赖管理。

* 安装`vue-li`, 命令如下：

```shell
npm install -g vue-cli
```

### 使用vue-webpack-simple模板

在终端中运行如下命令，其中`webpack-simple`是项目模板的名称，`web-starter`是你要生成的项目名称。

```shell
vue init webpack-simple web-starter
```

* 执行完成之后，生成的文件目录结构：

```
├─.babelrc        // babel配置文件
├─.gitignore    
├─index.html        // 主页
├─package.json      // 项目配置文件
├─README.md  
├─webpack.config.js // webpack配置文件
├─dist          // 发布目录
│   ├─.gitkeep       
├─src           // 开发目录 
│   ├─App.vue       // App.vue组件
│   ├─main.js       // 预编译入口
```

* 进到项目文件目录下安装依赖

```
cd web-starter
npm install 
```

* 运行实例

```
npm run dev
```

* 如果项目报错

```
Failed to compile.

./node_modules/css-loader!./node_modules/vue-loader/lib/style-compiler?{"vue":true,"id":"data-v-7ba5bd90","scoped":false,"hasInlineConfig":false}!./node_modules/sass-loader/lib/loader.js!./node_modules/vue-loader/lib/selector.js?type=styles&index=0!./src/App.vue
Module build failed: Error: Missing binding C:\Users\Administrator\Desktop\web-starter\node_modules\node-sass\vendor\win32-x64-64\binding.node
Node Sass could not find a binding for your current environment: Windows 64-bit with Node.js 10.x

Found bindings for the following environments:
  - Windows 64-bit with Node.js 10.x

This usually happens because your environment has changed since running `npm install`.
Run `npm rebuild node-sass` to download the binding for your current environment.
    at module.exports (C:\Users\Administrator\Desktop\web-starter\node_modules\node-sass\lib\binding.js:15:13)
    at Object.<anonymous> (C:\Users\Administrator\Desktop\web-starter\node_modules\node-sass\lib\index.js:14:35)
    at Module._compile (internal/modules/cjs/loader.js:776:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Module.require (internal/modules/cjs/loader.js:690:17)
    at require (internal/modules/cjs/helpers.js:25:18)
    at Object.<anonymous> (C:\Users\Administrator\Desktop\web-starter\node_modules\sass-loader\lib\loader.js:3:14)
 @ ./node_modules/vue-style-loader!./node_modules/css-loader!./node_modules/vue-loader/lib/style-compiler?{"vue":true,"id":"data-v-7ba5bd90","scoped":false,"hasInlineConfig":false}!./node_modules/sass-loader/lib/loader.js!./node_modules/vue-loader/lib/selector.js?type=styles&index=0!./src/App.vue 4:14-317 13:3-17:5 14:22-325
 @ ./src/App.vue
 @ ./src/main.js
 @ multi (webpack)-dev-server/client?http://localhost:8081 webpack/hot/dev-server ./src/main.js
```

* 解决办法
  * 去`github`下载`win32-x64-64_binding.node`
  * 环境变量设置SASS_BINARY_PATH，路径为`win32-x64-64_binding.node`所在路径



### 下载element UI

```shell
npm i element-ui –-save
```

### 引入element-ui

```js
import Vue from 'vue'
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';
import App from './App.vue'
Vue.use(ElementUI); // 这句一定得用上，不然无法识别
new Vue({
  el: '#app',
  render: h => h(App)
})

```



* #### 解决vue使用element-ui时，报xxx/element-ui/lib/theme-chalk/fonts/element-icons.ttf的问题

```
./node_modules/_element-ui@2.13.0@element-ui/lib/theme-chalk/fonts/element-icons.ttf
Module parse failed: Unexpected character '' (1:0)
You may need an appropriate loader to handle this file type.
(Source code omitted for this binary file)
 @ ./node_modules/_css-loader@0.28.11@css-loader!./node_modules/_element-ui@2.13.0@element-ui/lib/theme-chalk/base.css 7:3991-4027
 @ ./node_modules/_element-ui@2.13.0@element-ui/lib/theme-chalk/base.css
 @ ./src/plugins/element.js
 @ ./src/main.js
 @ multi ./node_modules/_webpack-dev-server@2.11.5@webpack-dev-server/client?http://localhost:8080 webpack/hot/dev-server ./src/main.js
```

#### 原因：缺少匹配规则

* 在webpack.config.js文件中的`module`中增加如下json

```
{
   test: /\.(eot|svg|ttf|woff|woff2)(\?\S*)?$/,
   loader: 'file-loader'
}

```

* 用以下代码测试element是否安装好

```vue
<template>
  <div id="app">
    <el-button type="primary">按钮</el-button>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>

</style>

```

结果样式没显示出

https://www.jianshu.com/p/3bf277714588





