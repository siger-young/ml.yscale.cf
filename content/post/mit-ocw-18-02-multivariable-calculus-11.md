---
title: "[MIT OCW] 18.02 Multivariable Calculus - 11 笔记"
categories:
- "mooc-notes"
tags:
- "MIT 18.02"
date: 2019-08-01 15:48:00
mathjax: true
draft: false
---
# MIT OCW 18.02 Multivariable Calculus
<!--more-->
## Total Differentials
When we are considering a multivariable function, is there a way to hold changes of all components?
Well there's the total differential defined for $f(x,y,z)$ that is
$$
\mathrm{d}f=\frac{\partial f}{\partial x}\mathrm{d}x+\frac{\partial f}{\partial y}\mathrm{d}y+\frac{\partial f}{\partial z}\mathrm{d}z.
$$

**Notice** I've been confusing the derivatives and differentials, but I'm now clearing the edge between them. In single variable situation, when apply "differential" to some function $f(x)$ , we get actually another function
$$
\mathrm{d}f(x,\Delta x)\overset{\Delta}{=}f'(x)\Delta x.
$$
We often write something like
$$
\mathrm{d}f=\boxed{}\mathrm{d}x
$$
because according to definition
$$
\mathrm{d}(x,\Delta x)=\Delta x.
$$
## Chain Rule
If we have some multivariable function $f(x,y,z)$ , where $x=x(t),y=y(t),z=z(t)$ , we can get
$$
\frac{\mathrm{d}f}{\mathrm{d}t}=\frac{\partial f}{\partial x}\frac{\mathrm{d}x}{\mathrm{d}t}+\frac{\partial f}{\partial y}\frac{\mathrm{d}y}{\mathrm{d}t}+\frac{\partial f}{\partial z}\frac{\mathrm{d}z}{\mathrm{d}t}.
$$
### Validation for Product and Quotient Rule
Treat product of two functions $u=u(t),v=v(t)$ as a multivariable function $f(u,v)=uv$ , and apply the chain rule
$$
\begin{aligned}\frac{\mathrm{d}f}{\mathrm{d}t}&=\frac{\partial f}{\partial u}\frac{\mathrm{d}u}{\mathrm{d}t}+\frac{\partial f}{\partial v}\frac{\mathrm{d}v}{\mathrm{d}t}\\&=v\frac{\mathrm{d}u}{\mathrm{d}t}+u\frac{\mathrm{d}v}{\mathrm{d}t}.\end{aligned}
$$
The quotient rule can be validated similarly, omitted.

## Chain Rule for Several Variables
Given a function $f(x,y)$ where $x=x(u,v),y=y(u,v)$ , how to get $\frac{\partial f}{\partial u}$ and $\frac{\partial f}{\partial v}$ without plugging $x=x(u,v)$ and $y=y(u,v)$ in?
Let's calculate the total differential of $f$ , that is
$$
\begin{aligned}\mathrm{d}f&=\frac{\partial f}{\partial x}\mathrm{d}x+\frac{\partial f}{\partial y}\mathrm{d}y\\&=\frac{\partial f}{\partial x}\left(\frac{\partial x}{\partial u}\mathrm{d}u+\frac{\partial x}{\partial v}\mathrm{d}v\right)+\frac{\partial f}{\partial y}\left(\frac{\partial y}{\partial u}\mathrm{d}u+\frac{\partial y}{\partial v}\mathrm{d}v\right)\\&=\left(\frac{\partial f}{\partial x}\frac{\partial x}{\partial u}+\frac{\partial f}{\partial y}\frac{\partial y}{\partial u}\right)\mathrm{d}u+\left(\frac{\partial f}{\partial x}\frac{\partial x}{\partial v}+\frac{\partial f}{\partial y}\frac{\partial y}{\partial v}\right)\mathrm{d}v.\end{aligned}
$$
And notice that
$$
\mathrm{d}f=\frac{\partial f}{\partial u}\mathrm{d}u+\frac{\partial f}{\partial v}\mathrm{d}v,
$$
therefore we get
$$
\left\{\begin{aligned}\frac{\partial f}{\partial u}&=\frac{\partial f}{\partial x}\frac{\partial x}{\partial u}+\frac{\partial f}{\partial y}\frac{\partial y}{\partial u}\\\frac{\partial f}{\partial v}&=\frac{\partial f}{\partial x}\frac{\partial x}{\partial v}+\frac{\partial f}{\partial y}\frac{\partial y}{\partial v}.\end{aligned}\right.
$$
