---
title: "[Naive Set Theory] Section 2 The Axiom of Specification"
categories:
- mathematics
- set-theory
tags:
- "Naive Set Theory"
date: 2018-07-23 15:22:00
mathjax: true
draft: false
---
# *Naive Set Theory* Section 2 The Axiom of Specification 分类公理
<!--more-->

## 前置要点 Highlights
> **P. 4 Para. 1**: All the basic principles of set theory, except only the axiom of extension, are designed to make new sets out of old ones.
* 根据已有集合构造新的集合.

----------

> **P. 4 Para. 2**: Warning: a box that contains a hat and nothing else is not the same thing as a hat.
* 某个单元素集合和这个元素本身是有区别的.

----------

## 阐明 Exposition
* **断言**
    - 基本类型（原子性语句）
        * (属于 belonging) $x\in A$ ,
        * (相等 equality) $A=B$ .
* 逻辑运算符
    - $\wedge$ 与(且),
    - $\vee$ 或,
    - $\neg$ 非,
    - $\Leftarrow$ 蕴含,
    - $\Leftrightarrow$ 双条件(当且仅当),
    - $\exists$ 存在,
    - $\forall$ 任意.

* 语句构造规则
    1. 将非( $\neg$ )放于语句前时，可考虑使用小括号包住语句（防止歧义，但往往是多余的）.
    2. 将与( $\wedge$ ),或( $\vee$ ),双条件( $\Leftrightarrow$ )置于语句间时，可考虑使用小括号包住语句.

* **分类公理**
    - **分类公理**. 对于每一个集合 $A$ 和每一个条件 $S(x)$ 而言，总有一个对应的集合 $B$ ，使得 $B$ 中都是 $A$ 的元素而满足条件 $S(x)$ .
    - 这样一种生成 $B$ 的过程，可记作 $B=\{x\in A:S(x)\}$ 