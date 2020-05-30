---
title: "[Naive Set Theory] Section 1 The Axiom of Extension"
categories:
- mathematics
- set-theory
tags:
- "Naive Set Theory"
date: 2018-07-22 05:39:00
mathjax: true
draft: false
---
# *Naive Set Theory* Section 1 The Axiom of Extension 外延公理
<!--more-->

## 前置要点 Highlights
> **P. 1 Para. 1**: The word "class" is also used in this context, but there is a slight danger in doing so. The reason is that in some approaches to set theory "class" has a special technical meaning.
* 慎用类一词叙述

**类**在集合论中有特殊含义.

----------

> **P. 1 Para. 2**: One thing that the development will not include is a definition of sets. The situation is analogous to the familiar axiomatic approach to elementary geometry.
> **P. 1 Para. 2**: The semi-axiomatic point of view adopted here assumes that the reader has the ordinary, human, intuitive (and frequently erroneous) understanding of what sets are.
* 集合的定义实际并不明确.

----------

> **P. 1 Para. 3**: Sets, as they are usually conceived, have *elements* or *members*.
* 集合中有元素.

----------

> **P. 1 Para. 3**: It is important to know that a set itself may also be an element of some other set.
* 一个集合可以是*另一个*集合的元素.
* 隐含了有关[**第三次数学危机**][1]的内容，也是朴素集合论的缺陷.

----------

## 阐明 Exposition
* 关于字母的一些约定俗成惯例
字母表靠前的字母表示元素，字母表靠后的字母表示元素所在的集合；或者，小写字母表示元素，大写字母表示元素所在的集合.

* **属于** belonging
若 $x$ 属于 $A$ （ $x$ 是 $A$ 的一个元素），则写作 $x\in A$ .

* **相等** equality
    - 集合之间可能的比**属于**更基本的关系就是**相等**.
    - $A$ 和 $B$ 相等仍然是以熟悉的记号表示为 $A=B$ ;
    - 同样地， $A$ 和 $B$ 不相等表示为 $A\neq B$ .

* **属于**与**相等**的联系
    - **外延公理**. *两个集合相等当且仅当它们拥有相同的元素*.
    - <del>**稍微有逼格一点**，集合由其外延确定.</del>
* **子集**和**包含** subset & inclusion
    - 若 $A$ 和 $B$ 为集合，且 $A$ 的每个元素同样也是 $B$ 的元素之一，那么 $A$ 是 $B$ 的一个**子集**，即 $B$ 包含 $A$ ，表示为 $A\subset B$ 或者 $B \supset A$ .
    - 若 $A$ 和 $B$ 为集合，且 $A\subset B, A \neq B$ ，那么 $A$ 是 $B$ 的**真子集**.

* 一些性质
 1. (自反性 reflexive) $A\subset A$ .
 2. (传递性 transitive) $A, B, C$ 都是集合且 $A\subset B, B\subset C$ ，那么 $A\subset C$ .
 3. (对称性 symmetric) $A=B \Leftrightarrow B=A$ .

* **外延公理**的重新叙述
    - **外延公理**. 若 $A$ 和 $B$ 为集合， $A = B \Leftrightarrow A\subset B, B\subset A$ .
    - 要证明集合 $A$ 和 $B$ 相等，也一般从 $A\subset B$ 和 $B\subset A$ 两个部分入手.

* 辨析
    - **属于**( $\in$ )和**包含**( $\subset$ )其实是截然不同的东西，但需要注意**包含**具有自反性，即 $A\subset A$ 恒成立；反观**属于**， $A\in A$ ，这是不可能的.
    - 相关内容可延伸至[**第三次数学危机**][1].

  [1]: https://en.wikipedia.org/wiki/Russell%27s_paradox