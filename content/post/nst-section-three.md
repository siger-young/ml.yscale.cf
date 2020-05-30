---
title: "[Naive Set Theory] Section 3 Unordered Pairs"
categories:
- mathematics
- set-theory
tags:
- "Naive Set Theory"
date: 2018-07-26 02:06:00
mathjax: true
draft: false
---
# *Naive Set Theory* Section 3 Unordered Pairs 配对公理
<!--more-->

## 前置要点 Highlights
> **P. 8 Para. 1**: The result is the set $\{x\in A:x\neq x\}$ , and that set, clearly, has no elements.

> **P. 8 Para. 1**: The axiom of extension implies that there can be only one set with no elements.
* 没有元素的集合即**空集** $\varnothing$ (empty set)的存在性.

----------

> **P. 4 Para. 2**: Warning: a box that contains a hat and nothing else is not the same thing as a hat.

> **P. 10 Para. 1**: Thus, for instance, $\varnothing$ and $\{\varnothing\}$ are very different sets.
* 某个单元素集合和这个元素本身是有区别的.

----------

## 阐明 Exposition
* **空集** $\varnothing$ 是任何集合的子集.
从反面来看，若 $A$ 为集合， $\varnothing \subset A$ 为假当且仅当 $\varnothing$ 有不属于 $A$ 的元素，而 $\varnothing$ 什么元素都没有，因此命题非假，则命题成立.

* **配对公理**
    - **配对公理**. 对于任意两个集合，总有一个集合，使得这两个集合都属于它.
    - 这样的集合 $A$ ，可以写成 $\{x\in A: x=a \ or \ x=b\}$ .

* **对** pairs
    - 外延公理说明了**配对公理**中这样的集合只有一个.
    - 可简记为 $\{a,b\}$ ，称为**对**（实际上此处没有强调顺序，因此是**无序对**）.
    - 而 $\{a,a\}$ 写为 $\{a\}$ 被称为 $a$ 的单元素集.

* 一些再定义
    - $a\in A \Leftrightarrow \{a\}\subset A$ 
    - $\{x: x=a \ or \ x=b\} = \{a,b\}$ 
    - $\{x: x\in A\} = A$ 
    - $\{x: x\neq x\} = \varnothing$ 
    - $\{x: x=a\} = \{a\}$ 

