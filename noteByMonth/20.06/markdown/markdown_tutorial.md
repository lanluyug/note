# 主要内容

* **markdown的作用**
* **markdown的基本语法**
* **快捷键的使用**

## 1. markdown的作用

> 背景： Markdown For Typora
>
> Typora使用的是github风格的markdown语法

意义： Markdown使读、写和编辑散文变得容易。

#### 1.1 实时预览

* 实时预览意味着当您完成后就能看到内联样式（支持inline HTML ）
* 当你按下回车或者鼠标点击到其他段落后，就能看到块样式了
* `Ctrl + /`切换显示源码或渲染后的内容

#### 1.2 智能粘贴

* 从html，office复制的标签，或者表格内容，会自动转换成markdown语法

#### 1.3 主题

* `alt + t `查看主题风格，默认支持五种风格。
  * Github
  * Newsprint
  * Night
  * Pixyll
  * Whitey

#### 1.4 快捷键

* 左上角menu中格式和段落中可查看

* 拥有丰富简单的快捷键
  * ` ctrl + 1` 一级标题
  * ` ctrl + 6` 六级标题
  * ` ctrl + b` 加粗
  * ` ctrl + i` 斜体

#### 1.5 自动保存

* 需要设置： 文件 --> 偏好设置 --> 勾选自动保存

#### 1.6 发布

* 支持导出为PDF和HTML格式
* 安装第三方插件可支持office以及更多的格式



## 2. markdown的基本语法

### 2.1 1~6级标题

```markdown
# This is an H1

## This is an H2

###### This is an H6
```

> 效果：

# This is an H1

## This is an H2

###### This is an H6



### 2.2 引述块

```markdown
> This is a blockquote with two paragraphs. This is first paragraph.
>
> This is second pragraph. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.



> This is another blockquote with one paragraph. There is three empty line to seperate two blockquote.
```

> 效果：

> This is a blockquote with two paragraphs. This is first paragraph.
>
> This is second pragraph. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.



> This is another blockquote with one paragraph. There is three empty line to seperate two blockquote.



### 2.3 列表List

#### 2.3.1 无序列表

```markdown
*   Red
*   Green
*   Blue
```

> 效果

*   Red
*   Green
*   Blue

#### 2.3.2 有序列表

```markdown
1.  Red
2. 	Green
3.	Blue
```

> 效果

1.  Red
2.  Green
3.  Blue

#### 2.3.3 任务列表

```markdown
- [ ] a task list item
- [ ] list syntax required
- [ ] normal **formatting**, @mentions, #1234 refs
- [ ] incomplete
- [x] completed
```

> 效果

- [x] a task list item
- [ ] list syntax required
- [ ] normal **formatting**, @mentions, #1234 refs
- [ ] incomplete
- [ ] completed

### 2.4 代码块（最常用）

* 开头``` + 语言类型 +  enter

```markdown
​```js
function test() {
  console.log("notice the blank line before this function?");
}
​```
```

> 效果

```js
function test() {
  console.log("notice the blank line before this function?");
}
```

### 2.5 数学公式

```markdown
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$
```

> 效果

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$

### 2.6 表格

```markdown
| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
```

> 效果

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ | :-------------: | ------------: |
| col 3 is      | some wordy text |         $1600 |
| col 2 is      |    centered     |           $12 |
| zebra stripes |    are neat     |            $1 |

### 2.7 分割线

```markdown
---
或
***
```

> 效果

---

或

----------

---

***

******



***

### 2.8 链接

#### 2.8.1 超链接

* ` ctrl + click` 访问地址

```markdown
This is [an example](eip.sinovatio.com) inline link.

[This link](./markdown_tutorial) has no title attribute.
```

> 效果

This is [an example](eip.sinovatio.com) inline link.

[This link](./markdown_tutorial) has no title attribute.

#### 2.8.2 URLS

```markdown
www.eip.sinovatio.com
```

www.eip.sinovatio.com



####2.8.3 图片

```
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
```

### 2.9 Emoji :smile:

* 

### 2.10 HTML

* 支持inline HTML（例：`<span style='color:red'>This is red</span>`）
* HTML 实体（例：`&frac14;`,效果：&frac14;）
* HTML块（例： `<details>     <summary>I have keys but no locks. I have space but no room. You can enter but can't leave. What am I?</summary>     A keyboard. </details>`）

```markdown
<span style="color:red;background: #F8F8F8;border:gray 1px solid;border-radius: 4px;">this text is red</span>
```

> 效果

<span style="color:red;background: #F8F8F8;border:gray 1px solid;border-radius: 4px;">this text is red</span>

#### 2.10.1 Video && Audio && Embed Web Contents

```markdow
<video src="xxx.mp4" />
<audio src="xxx.mp3" />

<iframe height='265' scrolling='no' title='Fancy Animated SVG Menu' src='//codepen.io/jeangontijo/embed/OxVywj/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/jeangontijo/pen/OxVywj/'>Fancy Animated SVG Menu</a> by Jean Gontijo (<a href='https://codepen.io/jeangontijo'>@jeangontijo</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
```

> 效果

<video src="xxx.mp4" />

<audio src="xxx.mp3" />



<iframe height='265' scrolling='no' title='Fancy Animated SVG Menu' src='//codepen.io/jeangontijo/embed/OxVywj/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/jeangontijo/pen/OxVywj/'>Fancy Animated SVG Menu</a> by Jean Gontijo (<a href='https://codepen.io/jeangontijo'>@jeangontijo</a>) on <a href='https://codepen.io'>CodePen</a>. </iframe>

<!-- I am some comments not end, not end... here the comment ends -->

