---
title: "[MIT OCW] 18.02 Multivariable Calculus - 14, 15 笔记"
categories:
- "mooc-notes"
tags:
- "MIT 18.02"
date: 2019-08-09 03:56:00
mathjax: true
draft: false
---
# MIT OCW 18.02 Multivariable Calculus
<!--more-->
## Non-independent Variables
### Review of Implicit Differentiation
Like the implicit differentiation in single variable calculus, there are times we cannot solve a variable as a function dependent on others (especially the powers are larger than $2$ ).

**e.g.** Given the implicit function $y^3+xy+5=0$ , what is $\frac{\mathrm{d}y}{\mathrm{d}x}$ ?

**Solution** Apply derivatives at both sides we get
$$
3y^2\cdot\frac{\mathrm{d}y}{\mathrm{d}x}+\left(1\cdot y+x\cdot\frac{\mathrm{d}y}{\mathrm{d}x}\right)=0,
$$
and the answer is
$$
\frac{\mathrm{d}y}{\mathrm{d}x}=-\frac{y}{3y^2+x}.
$$
### Multivariable Function
When there are not only two variables in a formula, and it's not easy to solve a variable as a function dependent on others, is there similar tricks? The answer is to use the total differential.

**e.g.** Given an equation $x^3+yz+z^3=8$ , find $\frac{\partial z}{\partial x}$ and $\frac{\partial z}{\partial y}$ at point $(2,3,1)$ .

**Solution** Consider a function $f(x,y,z)=x^2+yz+z^3=8$ and its total differential
$$
\mathrm{d}f=2x\mathrm{d}x+z\mathrm{d}y+(y+3z^2)\mathrm{d}z,
$$
since $f(x,y,z)=8$ so
$$
\mathrm{d}f=2x\mathrm{d}x+z\mathrm{d}y+(y+3z^2)\mathrm{d}z=0.
$$
And let's think about the actual meaning of partial derivatives $\frac{\partial z}{\partial x}$ and $\frac{\partial z}{\partial y}$ , it keeps a variable active and others constant, so to get $\frac{\partial z}{\partial x}$ , we can set $\mathrm{d}y=0$ , since $y$ is considered constant and get
$$
3x^2\mathrm{d}x+(y+3z^2)\mathrm{d}z=0,
$$
so plug the point into it and we have
$$
4\mathrm{d}x+6\mathrm{d}z=0,
$$
so
$$
\frac{\partial z}{\partial x}=-\frac23,
$$
and similarly
$$
\frac{\partial z}{\partial y}=-\frac16.
$$
#### Relationship with Implicit Differentiation
When I carefully reviewed the equation above, I was ignited by the meaning of the partial derivative and find a bridge between the method and implicit differentiation.
When we are computing $\frac{\partial z}{\partial x}$ , we only care about the variation of $x$ and $z$ , so we can treat anything else as constants and the problem is again solved by implicit differentiation that is
$$
\frac{\mathrm{d}}{\mathrm{d}x}(x^2+yz+z^3)=\frac{\mathrm{d}}{\mathrm{d}x}8,
$$
and here $y$ is a number not a variable, we can get
$$
2x+yz'+3z^2z'=0,
$$
so
$$
z'=-\frac{2x}{3z^2+y},
$$
namely
$$
\frac{\partial z}{\partial x}=-\frac{2x}{3z^2+y}.
$$
### Notation Traps
Consider a function $f(x,y)=x+y$ and set $x=u,y=u+v$ , so $f(u,v)=2u+v$ . Compute $\frac{\partial f}{\partial x}=1,\frac{\partial f}{\partial u}=2$ , but $x=u$ , what is the contradiction?
Actually it's a trap from notation, because when we write $\frac{\partial f}{\partial x}$ , we are assuming that $x$ is active and $y$ is constant. On the other hand, when we write $\frac{\partial f}{\partial u}$ , we are assuming that $u$ is active and $v$ is constant. The common variation of $x=u$ is the same, but what we keep constant is different in these two notations. So here are another notation to clearify what we keep constant: $\left(\frac{\partial f}{\partial x}\right)_y$ indicates that $x$ is active and $y$ is constant.
### Application

**e.g.** Given a *right* triangle with area $A$ , like the following:
![right-triangle.png][1]
find $\frac{\partial A}{\partial \theta}$ .

**Solution** We can write the expression
$$
A=\frac12ab\sin(\theta),
$$
the key point here is that we have a constraint: a *right* triangle. So here exist the notation traps.
* Treat $a,b$ are independent variables
Then the answer is just the partial derivative which keeps both $a$ and $b$ constant: $\left(\frac{\partial A}{\partial \theta}\right)_{a,b}=\frac12ab\cos(\theta).$ 
* Treat $a,b$ are non-independent
The constraint here is exactly $a=b\cos(\theta)$ , and there are another two ways: either $a$ or $b$ is constant.
- Treat $a$ constant

**Method 1 (Total Differential)** Now we compute the differential
$$
\begin{aligned}\mathrm{d}A&=\frac{\partial A}{\partial a}\mathrm{d}a+\frac{\partial A}{\partial b}\mathrm{d}b+\frac{\partial A}{\partial \theta}\mathrm{d}\theta\\&=\frac12b\sin(\theta)\mathrm{d}a+\frac12a\sin(\theta)\mathrm{d}b+\frac12ab\cos(\theta)\mathrm{d}\theta,\end{aligned}
$$
and another differential derived from the constraint
$$
\begin{aligned}\mathrm{d}a&=\frac{\partial a}{\partial b}\mathrm{d}b+\frac{\partial a}{\partial \theta}\mathrm{d}\theta\\&=\cos(\theta)\mathrm{d}b-b\sin(\theta)\mathrm{d}\theta.\end{aligned}
$$
Here we're keeping $a$ constant, so $\mathrm{d}a=0$ , and get the differential relationship between $b$ and $\theta$ that is
$$
\cos(\theta)\mathrm{d}b-b\sin(\theta)\mathrm{d}\theta=0,
$$
namely
$$
\mathrm{d}b=b\tan(\theta)\mathrm{d}\theta.
$$
Substitute $\mathrm{d}b$ and $\mathrm{d}a=0$ into the previous differential, we can get
$$
\mathrm{d}A=\frac12ab\sin(\theta)\tan(\theta)\mathrm{d}\theta+\frac12ab\cos(\theta)\mathrm{d}\theta,
$$
so we have
$$
\mathrm{d}A=\frac12ab\left(\sin(\theta)\tan(\theta)+\cos(\theta)\right)\mathrm{d}\theta,
$$
therefore
$$
\left(\frac{\partial A}{\partial \theta}\right)_{a}=\frac12ab\sec(\theta).
$$

**Method 2 (Chain Rule)** We can have
$$
\begin{aligned}\left(\frac{\partial A}{\partial \theta}\right)_{a}&=\left(\frac{\partial A}{\partial \theta}\right)_{a}\left(\frac{\partial \theta}{\partial \theta}\right)_{a}+\left(\frac{\partial A}{\partial a}\right)_{a}\left(\frac{\partial a}{\partial \theta}\right)_{a}+\left(\frac{\partial A}{\partial b}\right)_{a}\left(\frac{\partial b}{\partial \theta}\right)_{a}\\&=\frac{\partial A}{\partial \theta}+\frac{\partial A}{\partial b}\frac{\partial b}{\partial \theta}=\frac12ab\cos(\theta)+\left(\frac12a\sin(\theta)\right)\cdot\left(a\tan(\theta)\sec(\theta)\right)\\&=\frac12ab\cos(\theta)+\frac12a\sec(\theta)\cdot\sin(\theta)\tan(\theta)\\&=\frac12ab\sec(\theta).\end{aligned}
$$
- Treat $b$ constant 
Omitted.

## Partial Differential Equations
Phenomenon in reality is generally governed by partial differential equations, like heat equation in 3D space
$$
\frac {\partial u}{\partial t}=\alpha \left({\frac {\partial ^{2}u}{\partial x^{2}}}+{\frac {\partial ^{2}u}{\partial y^{2}}}+{\frac {\partial ^{2}u}{\partial z^{2}}}\right).
$$
[1]: /old/uploads/2019/08/1060013086.png