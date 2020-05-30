---
title: "2013 年上海高考数学卷一道题的多种解法"
categories:
- mathematics
tags:
- "高考"
date: 2019-08-18 21:18:00
mathjax: true
draft: false
---

**题源** 2013 年上海高考数学卷 第 13 题

**题面** 在 $xOy$ 平面上，将两个半圆弧 $(x-1)^2+y^2=1~(x\geq 1)$ 和 $(x-3)^2+y^2=1~(x\geq 3)$ 、两条直线 $y=1$ 和 $y=-1$ 围成的封闭图形记为 $D$ ，如图中阴影部分. 记 $D$ 绕 $y$ 轴旋转一周而成的几何体为 $\Omega$ ，过 $(0,y)~(|y|\leq 1)$ 作 $\Omega$ 的水平截面，所得截面面积为 $4\pi\sqrt{1-y^2}+8\pi$ ，试用祖暅原理、一个平放的圆柱和一个长方体，得出 $\Omega$ 的体积值为 $\boxed{?}$ .

![gaokao-zugeng-figure.png][1]

**法 1 (标准解法)** 根据提示利用祖暅原理，构造几何体由一个半径为 $1$ ，高为 $2\pi$ 的平放圆柱和一个高为 $2$ ，底面面积为 $8\pi$ 的长方体组成，其体积为 $V=2\pi^2+16\pi$ .

我并不知道题面中的水平截面面积为何要额外给出，在我看来这是冗余的条件，下文给出几种非祖暅原理的解法，可能有点小题大作，不过主要是为了熟悉一下微积分相关知识点……

**法 2 (旋转体)** 注意到水平截面的表达式为 $4\pi\sqrt{1-y^2}+8\pi$ ，可得到
$$
\begin{aligned}V&=\int_{-1}^{1}4\pi\sqrt{1-y^2}+8\pi\mathrm{d}y\\&=4\pi\int_{-1}^{1}\sqrt{1-y^2}+2\mathrm{d}y\\(x=\sin(\theta))&=4\pi\int_{-\frac\pi2}^{\frac\pi2}(\cos(\theta)+2)\cos(\theta)\mathrm{d}\theta\\&=4\pi\int_{-\frac\pi2}^{\frac\pi2}\cos^2(\theta)+2\cos(\theta)\mathrm{d}\theta\\&=4\pi\int_{-\frac\pi2}^{\frac\pi2}\frac{\cos(2\theta)+1}{2}+2\cos(\theta)\mathrm{d}\theta\\&=4\pi\left[\frac{\sin(2\theta)}{4}+\frac\theta2+2\sin(\theta)\right]^{\frac\pi2}_{-\frac\pi2}\\&=4\pi\left(\frac\pi2+4\right)\\&=2\pi^2+16\pi.\end{aligned}
$$
虽然这里直接用到了题面所给截面面积表达式，但是该方法与利用旋转体公式求
$$
V=\pi\int_{-1}^{1}(\sqrt{1-y^2}+3)^2-(\sqrt{1-y^2}+1)^2\mathrm{d}y
$$
是等价的.

**法 3 (帕普斯法则)** 应用帕普斯法则求体积，需要先求该平面图形的质心，可利用分割法与二重积分求得，首先分割区域如下图

![gaokao-zugeng-region.png][2]

其中 $R_0$ 是中央的 $2\times2$ 矩形区域， $R_1,R_2$ 分别为两个半圆区域。（由于这些区域的质心显然在 $x$ 轴上，下文直接使用 $x$ 坐标表示其质心。）
区域 $R_0$ 的质心显然为 $x_0=2$ ；为求得 $R_1,R_2$ 两个区域的质心，逆用帕普斯法则可以知道其质心分别为
$$
x_1=1+\frac{4}{3\pi},x_2=3+\frac{4}{3\pi}.
$$
接着利用二重积分求区域 $D$ 的质心 $G$ ，又注意到 $D=R_0-R_1+R_2$ ，根据质心公式有
$$
\begin{aligned}G_x&=\frac{1}{S_D}\iint_{D}x\mathrm{d}A\\&=\frac{1}{S_D}\left(\iint_{R_0}x\mathrm{d}A-\iint_{R_1}x\mathrm{d}A+\iint_{R_2}x\mathrm{d}A\right),\end{aligned}
$$
其中 $S_D=4$ 表示区域 $D$ 的面积.
对于区域 $R_0,R_1, R_2$ 分别使用质心公式可以知道
$$
\begin{aligned}
x_0&=\frac{1}{S_{R_0}}\iint_{R_0}x\mathrm{d}A\\
x_1&=\frac{1}{S_{R_1}}\iint_{R_1}x\mathrm{d}A\\
x_2&=\frac{1}{S_{R_2}}\iint_{R_2}x\mathrm{d}A,
\end{aligned}
$$
其中 $S_{R_0},S_{R_1},S_{R_2}$ 分别表示区域 $R_0,R_1,R_2$ 的面积，经过变形后得到一组二重积分的表达式
$$
\begin{aligned}\iint_{R_0}x\mathrm{d}A&=S_{R_0}x_0\\\iint_{R_1}x\mathrm{d}A&=S_{R_1}x_1\\\iint_{R_2}x\mathrm{d}A&=S_{R_2}x_2,\end{aligned}
$$
将其代入之前的式子可得到
$$
\begin{aligned}
G_x&=x_0-\frac{S_{R_1}}{S_D}x_1+\frac{S_{R_2}}{S_D}x_2\\
&=2-\frac{\frac\pi2}{4}\left(1+\frac{4}{3\pi}\right)+\frac{\frac\pi2}{4}\left(3+\frac{4}{3\pi}\right)\\
&=\frac\pi4+2,
\end{aligned}
$$
则几何体的体积可表示为
$$
\begin{aligned}V&=2\pi\cdot G_x\cdot S_D\\&=2\pi\cdot(\frac\pi4+2)\cdot4\\&=2\pi^2+16\pi.\end{aligned}
$$
[1]: /old/uploads/2019/08/3196861200.png
[2]: /old/uploads/2019/08/2556948323.png