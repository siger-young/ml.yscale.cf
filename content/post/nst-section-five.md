---
title: "[Naive Set Theory] Section 5 Complements and Powers"
categories:
- mathematics
- set-theory
tags:
- "Naive Set Theory"
date: 2018-08-07 11:01:00
mathjax: true
draft: false
---
# *Naive Set Theory* Section 5 Complements and Powers 补集和幂集
<!--more-->

## 阐明 Exposition
* **差集**及**相对补集**
    - 集合 $A,B$ 的**差集** $A-B$ 被定义为 $A-B=\{x\in A: x\notin B\}$ .
    - 上式的定义不一定要满足 $B\subset A$ .

* **绝对补集**
    - 假设此处提到的集合是**全集** $U$ 的子集.
    - 集合 $A$ 的绝对补集 $A'$ .
    - (其它记号[<sup>1</sup>][1]如 $A^\complement,\bar A,\complement_{U}A,\complement A$ etc.)

* **绝对补集**的一些性质
    - $(A')'=A$ .(对合 involution)
    - $\varnothing '=U, U' = \varnothing$ .
    - $A\cap A' = \varnothing, A\cup A' = U$ .
    - $A\subset B \Leftrightarrow B' \subset A'$ .
    - $(A\cup B)' = A' \cap B', (A\cap B)' = A' \cup B'$ .(De Morgan's laws)

* 二元性
    - 对于已知成立的关于若干个集合且由交、并、补、包含组成的一个等式或命题，我们可将每个集合替换为其补集，交并互换，颠倒包含关系，则原等式或原命题仍成立.

* **对称差**
    - 集合 $A,B$ 的对称差 $A+B$ 被定义为 $A+B=(A-B)\cup(B-A)$ .
    - 该运算对应逻辑运算中的**异或**(xor).
* **对称差**的一些性质
    - $A+B = B+A$ .(交换律)
    - $A+\varnothing=A$ .
    - $A+A=\varnothing$ .

* **零元交集**( $\bigcap$ )的完善
    - 在 [Section 4][2] 中**零元交集**的第一次定义曾提到，**零元交集**所操作的集合不能是空集，这是由于考虑其反面情况来思考结果，会发现任意元素都可满足，也就是说空集的交集是一切组成的集合.
    - 现在我们重新定义**零元交集**，使之与之前的定义兼容，且可对空集操作.
    - 实际上想法也很简单，我们框定一个“宇宙”即可，即将操作限制在全集 $U$ 中.
    - 假定 $A$ 是全集 $U$ 的子集，那么 $\bigcap A=\{x\in U: \forall X \in A, x\in X\}$ .

* **幂集公理**
    - **幂集公理**. 对于一个集合 $A$ ，总存在一个由 $A$ 的所有子集组成的集合.
    - 规范化描述： $\forall A,\exists \;{{\mathcal  {P}}(A)},\forall x:x\in {{\mathcal  {P}}(A)}\Leftrightarrow x\subset A$ .
    - $\mathcal{P}(A) = \{X:X\subset A\}$ .
    - 由**外延公理**可知，这样的集合 $\mathcal {P}$ 是唯一的，被称为 $A$ 的**幂集**(power set).

* 特殊集合的**幂集**例举
    - $\mathcal{P}(\varnothing) = \{\varnothing\}$ .
    - $\mathcal{P}(\{a,b\}) = \{\varnothing,\{a\},\{b\},\{a,b\}\}$ .

* **一般化的 De Morgan's laws**
    - 若集合 $A$ 由全集 $U$ 的子集组成( $A$ 是 $\mathcal{P}(U)$ 的子集)，不妨设 $D=\{X\in P(U): X'\in A\}$ ,
    - 则集合 $D$ 的并可写为 $\bigcup_{X\in A} X'$ ，则 $D$ 的交可写为 $\bigcap_{X\in A} X'$ .
    - 则一般化的 De Morgan's laws 可写为
        * $(\bigcup_{X\in A}X)' = \bigcap_{X\in A}X'$ ,
        * $(\bigcap_{X\in A}X)' = \bigcup_{X\in A}X'$ .

----------

## 习题 Exercise
1. 证明 $\mathcal{P}(E)\cap\mathcal{P}(F) = \mathcal{P}(E\cap F)$ .
思路是使用**外延公理**，证明两个集合拥有相同的元素.
$$
\begin{aligned}
&\forall x\in \mathcal{P}(E)\cap \mathcal{P}(F), \\
& x\in \mathcal{P}(E) \ \mathrm{and} \ x\in \mathcal{P}(F)\\
\Leftrightarrow & x\subset E \ \mathrm{and} \ x\subset F \\
\Leftrightarrow & x\subset E\cap F\\
\Leftrightarrow & x\in P(E\cap F)\\
& \mathrm{Q.E.D.}
 \end{aligned}
$$
----------

## 参考 Reference
[1] https://en.wikipedia.org/wiki/Complement_(set_theory)


  [1]: https://en.wikipedia.org/wiki/Complement_(set_theory)
  [2]: https://blog.sigeryoung.ml/2018/08/05/nst-section-four.html