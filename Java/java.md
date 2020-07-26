### 一、JAVA类加载顺序

项目先加载最先加载的同名类，后面的同名类不加载；

> 例如，POM文件先申明的版本依赖是有效的，后面申明的同名依赖不起作用。

###二、线程的六种状态

- New(新创建)
- Runable(可运行)
- Blocked（被阻塞）
- Waiting（等待）
- Timed waiting（计时等待）
- Terminated（被终止）

> 可通过getState方法确定线程的当前状态

