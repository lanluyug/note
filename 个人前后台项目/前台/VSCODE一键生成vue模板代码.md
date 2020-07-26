# VSCode 初次写vue项目并一键生成.vue模版

https://www.jianshu.com/p/8610215a8a84



1. 安装Vetur插件
2. 新建代码片段

```
File -> preference -> User snippers -> New global snipper files -> 命名vue.json
```

3. 输入内容

```json
{
    "Print to console": {
        "prefix": "vue",
        "body": [
            "<!-- $1 -->",
            "<template>",
            "<div class='$2'>$5</div>",
            "</template>",
            "",
            "<script>",
            "",
            "export default {",
            "components: {},",
            "data() {",
            "return {",
            "",
            "};",
            "},",
            "computed: {},",
            "watch: {},",
            "methods: {",
            "",
            "},",
            "created() {",
            "",
            "},",
            "mounted() {",
            "",
            "},",
            "beforeCreate() {}, //生命周期 - 创建之前",
            "beforeMount() {}, //生命周期 - 挂载之前",
            "beforeUpdate() {}, //生命周期 - 更新之前",
            "updated() {}, //生命周期 - 更新之后",
            "beforeDestroy() {}, //生命周期 - 销毁之前",
            "destroyed() {}, //生命周期 - 销毁完成",
            "activated() {}, //如果页面有keep-alive缓存功能，这个函数会触发",
            "}",
            "</script>",
            "<style lang='scss' scoped>",
            "//@import url($3); 引入公共css类",
            "$4",
            "</style>"
        ],
        "description": "Log output to console"
    }
}
```

4. 上面代码中的 "prefix": "vue", 就是快捷键；保存好之后，新建.vue结尾的文件试试

```
输入vue 按键盘的tab就行
```

5. shift + alt + F自动对齐

#### 安装vue-router

```
npm install vue-router
```

新建router/index.js

```js
import Vue from 'vue'
import Router from 'vue-router'
import Login from '~/views/login'

Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'Login',
      component: Login
    }
  ]
})

```

