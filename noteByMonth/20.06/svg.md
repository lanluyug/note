### 背景

>  svg是基于XML的技术

### 语法

* 画圆(circle)
  * cx 屏幕左上角到圆心的横向距离
  * cy 左上角到圆心的纵向距离
  * r 圆半径
  * stroke 圆框颜色
  * stroke-width 圆框宽度
  * fill 填充色， transparent默认与背景色一致，none为不设置填充色

``` html
<svg xmlns="lanlyug" height="400px">
	`<circle cx="100" cy="100" r="40" fill="transparent" troke="black" troke-width="5"></circle>
</svg>
```

* 画矩形(rect)
  * x 屏幕左上角到矩形左上角的横向距离
  * y  屏幕左上角到矩形左上角的纵向距离
  * width 矩形宽度
  * height 矩形高度
  * rx ， ry边框弧度（类似于border-radius）

```html
<svg xmlns="lanlyug" height="400px">
    `<rect x="100" y="100" width="40" height="40"
           rx="5" ry="5"
           fill="transparent" stroke="black" stroke-width="5"></rect>
</svg>
```

* 画线（line）
  * x1,y1 起点坐标的x轴，y轴（相对屏幕左上角）
  * x1,y1 终点坐标的x轴，y轴（相对屏幕左上角）

```html
<svg xmlns="lanlyug" height="400px">
    `<line x1="50" y1="50" x2="100" y2="100" stroke="black" stroke-width="5"></line>
</svg>
```

* 画多条线段(polyline)
  * points 内容“x1 y1 x2 y2 x3 y3”；例如："10 10 20 20 30 30";可用空格或逗号隔离，但不可以混用

- 分组标签（g标签）
  - transform="translate(200, 100)" 横向偏移200px，纵向偏移100px
- 文本标签（text）
  - x 屏幕左上角到矩形左上角的横向距离
  - y  屏幕左上角到矩形左上角的纵向距离
  - text-anchor 可选参数middle start end等
- 图片标签(image)
  * x 屏幕左上角到矩形左上角的横向距离
  * y  屏幕左上角到矩形左上角的纵向距离
  * width 矩形宽度
  * height 矩形高度
  * xlink:href 引用图片地址
- 路径(path)
  - d
    - M 起始坐标点
    - L 下一个坐标点
    - Z 和起始点连接的闭合操作
    - H 水平线段，后接一个点（正负方向相反）
    - V垂直线段，后接一个点（正负方向相反）
    - A 绘制弧形
      - X半径
      - Y半径
      - 角度
        - 椭圆的角度
      - 弧长
        - 0 短弧
        - 1 长弧
      - 方向
        - 0 顺时针
        - 1 逆时针

```html
<svg xmlns="lanlyug" height="400px">
    `<path d="M100 100A150 100 50 1 1 200 200" stroke="black" stroke-width="5" fill="none"></path>
</svg>
```

* 动态效果（animate）
  * attributeName 运动属性：width或者height
  * dur 运动时间 单位s
  * from 起始位置
  * to 结束位置

```html
<svg xmlns="lanlyug" height="400px">
    `<path d="M100 100A150 100 50 1 1 200 200" stroke="black" stroke-width="5" fill="none">
    	<animate attributeName="width" dur="1" from="50" to="200"></animate>
    </path>
</svg>
```



### JS创建svg

> 采用createElementNS(ns, tag)