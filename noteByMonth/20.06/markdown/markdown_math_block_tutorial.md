# Math and Academic Functions

## 背景

* Typora使用**MathJax**渲染*LaTex*/*TeX*风格的语法 数学表达式

## Math块使用

* 使用`$$`加回车键就可以开始编写*Tex/LaTex*代码

```latex
$$
\begin{align*}
y = y(x,t) &= A e^{i\theta} \\
&= A (\cos \theta + i \sin \theta) \\
&= A (\cos(kx - \omega t) + i \sin(kx - \omega t)) \\
&= A\cos(kx - \omega t) + i A\sin(kx - \omega t)  \\
&= A\cos \Big(\frac{2\pi}{\lambda}x - \frac{2\pi v}{\lambda} t \Big) + i A\sin \Big(\frac{2\pi}{\lambda}x - \frac{2\pi v}{\lambda} t \Big)  \\
&= A\cos \frac{2\pi}{\lambda} (x - v t) + i A\sin \frac{2\pi}{\lambda} (x - v t)
\end{align*}
$$
```

> 渲染效果

$$
\begin{align*}
y = y(x,t) &= A e^{i\theta} \\
&= A (\cos \theta + i \sin \theta) \\
&= A (\cos(kx - \omega t) + i \sin(kx - \omega t)) \\
&= A\cos(kx - \omega t) + i A\sin(kx - \omega t)  \\
&= A\cos \Big(\frac{2\pi}{\lambda}x - \frac{2\pi v}{\lambda} t \Big) + i A\sin \Big(\frac{2\pi}{\lambda}x - \frac{2\pi v}{\lambda} t \Big)  \\
&= A\cos \frac{2\pi}{\lambda} (x - v t) + i A\sin \frac{2\pi}{\lambda} (x - v t)
\end{align*}
$$



## 内联Math

* 使用`$<Math Expression>$`包裹

```latex
$<f = \frac{2 \pi}{T}>$
```

>渲染效果

 $<f = \frac{2 \pi}{T}$>



## 化学表达式



```latex
$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$
```

> 渲染效果

$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$



## 自动排序

![img](C:\Users\Administrator\Desktop\note\assets\images\Snip20180818_4.png)



