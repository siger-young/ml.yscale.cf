---
title: "[Naive Set Theory] Section 6 Ordered Pairs"
categories:
- mathematics
- set-theory
tags:
- "Naive Set Theory"
date: 2018-08-10 11:46:00
mathjax: true
draft: false
---
# *Naive Set Theory* Section 6 Ordered Pairs 有序对
<!--more-->

## 前置要点 Highlights
> **P. 22 Para. 1**: Even without a precise definition of what this means, we can do something set-theoretically intelligent with it. We can, namely, consider, for each particular spot in the ordering, the set of all those elements that occur at or before that spot; we obtain in this way the sets {c} {c, b} {c, b, d} {c, b, d, a}.
* 将会用**集合**去定义有序对，并且基本思路是逐一确定位置.

----------

## 阐明 Exposition
* **有序对** (ordered pairs)
    - 考虑一个简单情况，即元素 $a,b$ 的有序对，其中第一维是 $a$ ，第二维是 $b$ ，该有序对记作 $(a,b)$ 被定义为 $(a,b)=\{\{a\},\{a,b\}\}$ .

* **笛卡儿积** (Cartesian product)
    - 二元形式的**笛卡儿积**被表示为 $A\times B = \{x:x=(a,b), a\in A\land b\in B\}$ .
    - 若 $R$ 是一些有序对的集合，那么必存在集合 $A,B$ ，使得 $R\subset A\times B$ .

* **投影**
    - $A=\{a:\exists b,(a,b)\in R\}$ 是 $R$ 在第一维上的**投影**.
    - $B=\{b:\exists a,(a,b)\in R\}$ 是 $R$ 在第二维上的**投影**.
----------

## 习题 Exercise
* 证明 $(A\cup B)\times X = (A\times X)\cup(B\times X)$ .
$$
\begin{aligned}
&\forall x \in (A\cup B)\times X, x = (a,b) ,\\
& a\in A\cup B, b\in X\\
\Leftrightarrow & a\in A \lor a\in B, b\in X\\
\Leftrightarrow & (a\in A\land b\in X)\lor (a\in B\land b\in X)\\
\Leftrightarrow & (a,b)\in A\times X\lor (a,b)\in B\times X\\
\Leftrightarrow & (a,b)\in (A\times X)\cup (B\times X)\\
& \mathrm{Q.E.D.}
\end{aligned}
$$
* 证明 $(A\cap B)\times (X\cap Y) = (A\times X)\cap(B\times X)$ .
$$
\begin{aligned}
&\forall x \in (A\cap B)\times (X\cap Y), x = (a,b) ,\\
& a\in A\cap B, b\in X\cap Y\\
\Leftrightarrow & a\in A\land a\in B \land b\in X \land b\in Y\\
\Leftrightarrow & (a\in A\land b\in X)\land(a\in B\land b\in Y)\\
\Leftrightarrow & (a,b)\in (A\times X)\land(a,b)\in(B\times Y)\\
\Leftrightarrow & (a,b)\in (A\times X)\cap (B\times Y)\\
& \mathrm{Q.E.D.}
\end{aligned}
$$
* 证明 $(A-B)\times X =(A\times X) - (B\times X)$ .
$$
\begin{aligned}
&\forall x \in (A-B)\times X, x = (a,b) ,\\
& a\in A-B, b\in X\\
\Leftrightarrow & (a\in A\land a\notin B)\land b\in X\\
\Leftrightarrow & (a\in A\land b\in X)\land(a\notin B\land b\in X)\\
\Leftrightarrow & (a,b)\in A\times X\land (a,b)\notin B\times X\\
\Leftrightarrow & (a,b)\in (A\times X)-(B\times X)\\
& \mathrm{Q.E.D.}
\end{aligned}
$$
* 证明 $A=\varnothing\lor B=\varnothing \Leftrightarrow A\times B=\varnothing$ .
定义法或反证法易证得.
* 证明 $A\subset X\land B\subset Y \Leftrightarrow A\times B\subset X\times Y$ .
$$
\begin{aligned}
&\forall x \in A\times B, x = (a,b) ,\\
& a\in A, b\in B, A\subset X, B\subset Y\\
\Rightarrow & a\in X, b\in Y\\
\Leftrightarrow & (a,b)\in X\times Y\\
\Leftrightarrow & A\times B\subset X\times Y \\
& \mathrm{Q.E.D.}
\end{aligned}
$$
