---
title: "新接触到的积分的代换"
categories:
- mathematics
- calculus
date: 2018-07-19 20:24:00
mathjax: true
draft: false
---
许久没接触与继续学习积分的技巧了，把最近接触到的个别积分代换技巧来小结一下。


<!--more-->


# 1. 万能公式代换
$$
I = \int{\frac{\mathrm{d}x}{(1+\cos x)^2}}
$$
实际上，关于 $ R(\sin x, \cos x)\mathrm{d}x $ 的积分，都可令 $ t= \tan \frac{x}{2}, x \in (-\pi,\pi) $ 来使其有理化。
在本例中，我们便可由如下关系求其积分
$$
\begin{cases}\cos x &=\dfrac{1-t^2}{1+t^2} \\x &=2\arctan t\\ \mathrm{d}x &=\dfrac{2\mathrm{d}t}{1+t^2} \Leftrightarrow \mathrm{d}t=\dfrac{1}{2}\mathrm{d}x\sec^2\dfrac{x}{2}\end{cases}
$$

$$
\begin{aligned}
\therefore I & = \int{\frac{\mathrm{d}x}{(1+\cos x)^2}} \\
& = \int{\frac{2}{(1+t^2)(1+\frac{1-t^2}{1+t^2})^2}\mathrm{d}t} \\
& = \int{\dfrac{1+t^2}{2}\mathrm{d}t} \\
& = \dfrac{t}{2} + \dfrac{t^3}{6} + C \\
& = \frac{1}{2}\tan\dfrac{x}{2} +  \frac{1}{6}\tan^3\dfrac{x}{2} + C.
\end{aligned}
$$
# 2. 双曲代换（也可三角代换）
$$
I = \int{\frac{x^2}{a-bx^2}\mathrm{d}x}
$$
二话不多说，先分离常数，转化为
$$
\begin{aligned}
I &= \dfrac{a}{b}\int{\dfrac{\mathrm{d}x}{a-bx^2}}-\dfrac{1}{b}\int{\mathrm{d}x} \\
&= -\dfrac{a}{b}\int{\dfrac{\mathrm{d}x}{bx^2-a}}-\dfrac{x}{b} \\
&= -\dfrac{1}{b}\int{\dfrac{\mathrm{d}x}{\frac{b}{a} x^2-1}}-\dfrac{x}{b}.
\end{aligned}
$$
令 $\frac{\sqrt b}{\sqrt a}x=\cosh t$ ，则 $x = \frac{\sqrt a}{\sqrt b}\cosh t, \mathrm{d}x = \frac{\sqrt a}{\sqrt b}\sinh t\mathrm{d}t$ 
原式转化为
$$
\begin{aligned}I & = -\dfrac{1}{b}\int{\dfrac{\frac{\sqrt a}{\sqrt b}\sinh t}{\cosh^2 t-1}\mathrm{d}t}-\dfrac{x}{b}\\ & =  -\dfrac{\sqrt a}{b\sqrt b}\int{\dfrac{\mathrm{d}t}{\sinh t}}-\dfrac{x}{b}\end{aligned}
$$
已知 $\int{\dfrac{\mathrm{d}t}{\sinh t}} = \ln\tanh\dfrac{t}{2}.$ 且根据之前的代换式，我们可以知道
$$
\begin{aligned}
\ln \tanh\dfrac{t}{2} & = \dfrac{1}{2}\ln\dfrac{\sinh^2 t}{(1+\cosh t)^2}\\
& = \dfrac{1}{2}\ln\dfrac{\cosh^2 t - 1}{(1+\cosh t)^2} \\
& = \frac{1}{2}\ln\dfrac{\frac{b}{a}x^2 - 1}{(1+\frac{\sqrt b}{\sqrt a}x)^2} \\
& = \dfrac{1}{2}\ln\dfrac{(\frac{\sqrt b}{\sqrt a}x+1)(\frac{\sqrt b}{\sqrt a}x-1)}{(\frac{\sqrt b}{\sqrt a}x+1)^2} \\
& = \dfrac{1}{2}\ln\dfrac{\frac{\sqrt b}{\sqrt a}x-1}{\frac{\sqrt b}{\sqrt a}x+1} \\
& = -\dfrac{1}{2}\ln\dfrac{\sqrt b x+\sqrt a}{\sqrt b x-\sqrt a}.\\
\therefore I & = \dfrac{\sqrt a}{2b\sqrt b}\ln\dfrac{\sqrt b x+\sqrt a}{\sqrt b x-\sqrt a} -\dfrac{x}{b} +C.
\end{aligned}
$$
实际上，也可直接利用原先的三角代换，来达到相同的效果。
# 习题
 1. $\int{\dfrac{\sin^2 x \cos x}{\sin x+\cos x} \mathrm{d}x}$ 
 2. $\int{\dfrac{\mathrm{d}x}{a+b\cos x}}$ 
 2. $\int{\sqrt{x^2+x}\mathrm{d}x}$ 