---
title: "[MIT OCW] 18.02 Multivariable Calculus - 8, 9, 10 笔记"
categories:
- "mooc-notes"
tags:
- "MIT 18.02"
date: 2019-07-31 13:23:00
mathjax: true
draft: false
---
# MIT OCW 18.02 Multivariable Calculus
<!--more-->
## Basics of Multivariable Functions
### Map
At a higher point of view, a single variable function maps some number to a number, and a multivariable function maps some $n$ -tuple to a number. The essence of a function doesn't change.
### Domain
Like a single variable function, a multivariable function have its domain, like
$$
f(x,y)=x^2+y^2
$$
can be defined all the time, and
$$
f(x,y)=\sqrt{y}
$$
is only defined when $y\geq 0$ .
## Graph
It's difficult to plot a multivariable function accurately, but the main idea doesn't change.

**e.g.** Plot the graph of $f(x,y)=-y$ .
Consider the $yz$ plane, it's just a line through origin. And now we move the value of $x$ , and it doesn't depend on the value $x$ , so it will be a plane.
![z=-y.png][1]

**e.g.** Plot the graph of $f(x,y)=1-x^2-y^2$ .
Consider the $yz$ plane, where $x=0$ , it will be a parabola with the quation $z=1-y^2$ . Similarly, the part on $xz$ plane is still a parabola with the quation $z=1-x^2$ .
But if we consider the graph on the $xy$ plane, where $z=0$ , we'll get a unit circle that is $x^2+y^2=1$ .
![1-x2-y2.png][2]

### Contour Plot
The process of a traditional plot is hard and not that easy to understand. Take the last example, we can draw a contour plot like the following
![contour.png][3]
which indicated where the function achieves the same value on the $xy$ plane.
We can feel the change of the function by observing the gap between curves and know how the function changes along some direction.

## Partial Derivatives
We care about the change rate of a multivariable function, but it has several variables. What we do is just convert the multivariable function into a single variable function, that is treat other variables as constants.
Given a function $f(x,y)$ , the partial derivative at point $(x_0,y_0)$ of $f$ with respect to $x$ is
$$
\frac{\partial f}{\partial x}(x_0,y_0)=\lim_{\Delta x\to 0}\frac{f(x_0+\Delta x, y_0)-f(x_0, y_0)}{\Delta x},
$$
and generally the partial derivative of $f$ with respect to $x$ is a multivariable function that is
$$
f_x=\frac{\partial f}{\partial x}=\lim_{\Delta x\to 0}\frac{f(x+\Delta x, y)-f(x, y)}{\Delta x}.
$$
## Approximation
Like the linear approximation in single variable function, a multivariable function also has approximation. That is
$$
\Delta f(x,y)\approx f_x\Delta x+f_y\Delta y.
$$
Why is it correct?
Thinking about the following assumption
$$
\left\{\begin{aligned}f_x(x_0,y_0)=a\\f_y(x_0,y_0)=b\end{aligned}\right.,
$$
and we have two tangent lines
$$
l_1:\left\{\begin{aligned}z&=z_0+a(x-x_0)\\y&=y_0\end{aligned}\right.,l_2:\left\{\begin{aligned}z&=z_0+b(y-y_0)\\x&=x_0\end{aligned}\right..
$$
And these two lines can determine a tangent plane $z=z_0+a(x-x_0)+b(y-y_0)$ .

## Maxima / Minima
At local maxima or minima, we have $f_x(x_0,y_0)=0$ and $f_y(x_0,y_0)=0$ , which means the point has a horizontal tangent plane.
### Critical Points
Point $(x,y)$ is a critical point of $f$ if $f_x(x_0,y_0)=0$ and $f_y(x_0,y_0)=0$ .

**e.g.** Find critical points for $f(x,y)=x^2-2xy+3y^2+2x-2y$ .

**Solution** According to definition, we get
$$
\left\{\begin{aligned}f_x&=2x-2y+2\\f_y&=-2x+6y-2=0\end{aligned}\right.,
$$
and we can solve the critical point that is $(-1,0)$ .
But what's the minima?
Notice that
$$
f(x,y)=x^2-2xy+3y^2+2x-2y=(x-y+1)+2y^2-1\geq -1,
$$
and we plug $(-1,0)$ into it, it's exactly $-1$ , so we get local and global minima at $(-1,0)$ .
### Saddle Points
Focus on the condition $f_x(x_0,y_0)=0$ and $f_y(x_0,y_0)=0$ , it's neccessary but not sufficient in terms of maxima or minima. Because we could have some examples that $f_x(x_0,y_0)=0$ and $f_y(x_0,y_0)=0$ where the function doesn't have local minima or maxima at $(x_0,y_0)$ .
For example, the function $f(x,y)=x^2-y^2$ .
![x2-y2.png][4]
It's easy to validate that $f_x(0,0)=0,f_y(0,0)=0$ , anyhow, it doesn't achieve maxima or minima at the point, these points are called saddle points.
### Application
#### Least-square Interpolation
When we are given a lot of discrete data (often seen in scientific experiments), we want to find some line to approximate these data, and enable us to find the relation between variables and predict their value.
Considering the data set $(x_1,y_1),(x_2,y_2),\cdots,(x_n,y_n)$ and the target line $y=ax+b$ , how to optimize the line in order that the line become best for discrete data? Actually, it's a minima problem.
As a convention, the indicator we use here is the offset squared, for each data $(x_i,y_i)$ that is $(ax_i+b-y_i)^2$ , so the function we'd like to analyze is
$$
D(a,b)=\sum_1^n (ax_i+b-y_i)^2,
$$
whose minima we want to find.
We take the partial derivative with respect to $a,b$
$$
\frac{\partial D}{\partial a}=\sum_1^n [2(ax_i+b-y_i)x_i],\frac{\partial D}{\partial b}=\sum_1^n [2(ax_i+b-y_i)],
$$
and to get the critical point, we solve the system
$$
\left\{\begin{aligned}&\frac{\partial D}{\partial a}=0\\&\frac{\partial D}{\partial b}=0\end{aligned}\right.,
$$
namely
$$
\left\{\begin{aligned}&\left(\sum_1^nx_i^2\right)a+\left(\sum_1^nx_i\right)b=\sum_1^nx_iy_i\\&\left(\sum_1^nx_i\right)a+nb=\sum_1^ny_i\end{aligned}\right..
$$
## Validation by Second Derivatives
### Special Cases
#### Completing Squares
Consider the following function behavior at origin
$$
f(x,y)=ax^2+bxy+cy^2,
$$
and we try to complete the square here to judge whether the function can achieve maxima or minima at origin, namely
$$
\begin{aligned}f(x,y)&=a\left(x^2+\frac{b}{a}xy\right)+cy^2\\&=a\left(x+\frac{b}{2a}y\right)^2-\frac{b^2}{4a}y^2+cy^2\\&=a\left(x+\frac{b}{2a}y\right)^2+\frac{4ac-b^2}{4a}y^2\\&=\frac1{4a}\left[4a^2\left(x+\frac{b}{2a}y\right)^2+(4ac-b^2)y^2\right].\end{aligned}
$$
It's obvious that the origin is a critical point because
$$
\frac{\partial f}{\partial x}=2ax+by,\frac{\partial f}{\partial y}=2cy+bx.
$$
And plug the origin into these, easy to get they are $0$ , the problem here is can $f(0,0)$ be the true local maxima or minima?
Observe the completed part, the signs before two squared terms are interesting, $4a^2$ is always positive, and $4ac-b^2$ is not determined.
If $4ac-b^2>0$ , then the parts in bracket are two non-negative terms, and have to be non-negative. And $f(0,0)=0$ , then it has local maxima or minima (depending on the sign of $\frac1{4a}$ , namely $a$ ).
If $4ac-b^2=0$ , the function will depends on only one variable $x$ , and the behavior here cannot be concluded. In this special case, it will be local maxima or minima, where any point $(0,t)$ will achive.
If $4ac-b^2<0$ , then the parts in bracket are one non-negative, the other non-positive, so it's possible to get either positive or negative value. So $f(0,0)$ cannot be maxima or minima, it's a saddle point.

#### Homogenous Equation
We find that quadratic discriminant $b^2-4ac$ occur in the analysis above, is that a coincidence?
Still the example above, notice that each term is quadratic, so
$$
f(x,y)=y^2\left(a\left(\frac{x}{y}\right)^2+b\left(\frac{x}{y}\right)+c\right),
$$
and near the origin, $\frac{x}{y}$ can be any number.
If the equation $at^2+bt+c=0$ has two roots, namely, $b^2-4ac>0$ , it means that the function can achieve two sides of $0$ , and it keeps $0$ on some direction ( $\frac{x}{y}$ indicates the direction when approaching the origin).
![quad-root-up.png][5]![quad-root-down.png][6]
If the equation $at^2+bt+c=0$ has only one root, namely, $b^2-4ac=0$ , actually it can't be concluded, anyhow, it indicates that on some direction, the function keeps its value at origin.
If the equation $at^2+bt+c=0$ has no roots, namely, $b^2-4ac<0$ , it means that $f(0,0)=0$ will be exactly local maxima or minima (depending on the sign of $a$ ), because near the origin, the function value can't be zero.
![quad-noroot.png][7]

### Second Derivative Test
According to multivariable quadratic Taylor's formula
$$
\Delta f\approx f_x(x-x_0)+f_y(y-y_0)+\frac12f_{xx}(x-x_0)^2+f_{xy}(x-x_0)(y-y_0)+\frac12f_{yy}(y-y_0)^2,
$$
we can have a general test on other functions.
To test a critical point $(x_0,y_0)$ of $f$ , let
$$
A=f_{xx}(x_0,y_0),B=f_{xy}(x_0,y_0),C=f_{yy}(x_0,y_0),
$$
* if $AC-B^2>0$ 
    - if $A>0$ , we get local minima at $(x_0,y_0)$ 
    - if $A<0$ , we get local maxima at $(x_0,y_0)$ 
* if $AC-B^2<0$ , then it's a saddle point
* if $AC-B^2=0$ , no conclusion


  [1]: /old/uploads/2019/07/1909456760.png
  [2]: /old/uploads/2019/07/640288293.png
  [3]: /old/uploads/2019/07/1629113623.png
  [4]: /old/uploads/2019/07/2686925380.png
  [5]: /old/uploads/2019/08/3874810908.png
  [6]: /old/uploads/2019/08/444253504.png
  [7]: /old/uploads/2019/08/3259334859.png