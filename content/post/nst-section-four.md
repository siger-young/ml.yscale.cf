---
title: "[Naive Set Theory] Section 4 Unions and Intersections"
categories:
- mathematics
- set-theory
tags:
- "Naive Set Theory"
date: 2018-08-05 04:31:00
mathjax: true
draft: false
---
# *Naive Set Theory* Section 4 Unions and Intersections 并集交集
<!--more-->


## 阐明 Exposition
* **并集公理**与**并集**
    - **并集公理**. 对于任意的 集的集合 $A$ ，总存在一个集合 $U$ 拥有所有至少属于 $A$ 中一个集合 $X$ 的元素. (讲道理如果用书上的语言变成中文，我自己觉得别扭，英语更适合阐述这样的语句.)
    - $\displaystyle \forall A,\exists U,\forall x:x\in U\iff (\exists X:x\in X\land X\in A)$ 
    - 可能是我第一次贴较为标准化的数学语言叙述，理解一下并不难. (实际上此处有些地方没有加括号，若理解有困难，可看 Wikipedia 并集公理[<sup>1</sup>][1]的写法.)
    - $U$ 叫做 $A$ 的**并集**.
    - 使用**分类公理**我们可表达成 $U = \{x:\exists X\in A, x\in X\}$ ，
    - **并集公理**旨在阐明一个集合的并集是一个集合.

* **并集**记号
    - 若使用 $A$ 来表示集合 $U$ ，可写为 $\bigcup A$ .
    - 若使用 $A$ 中的集合 $X$ 来表示集合 $U$ ，可写为 $\bigcup_{X\in A} X$ .
    - 一般地，对于 $U$ 中若只有两个集合 $A,B$ ，那么此时 $U$ 的并集可写为 $\big\{X:X\in \{A,B\}\} = A\cup B = \{x: x\in A \lor x\in B\}$ 

* **并集**的一些性质
    - $\bigcup \{X:X\in \varnothing\}=\varnothing$ 即 $\bigcup \varnothing = \varnothing$ .
    - $\bigcup \{X:X\in \{A\}\} = A$ 即 $\bigcup \{A\} = A$ .
    - $A\cup \varnothing = A$ 
    - $A\cup B = B \cup A$ . (交换律)
    - $A\cup(B\cup C) = (A\cup B)\cup C$ = $A\cup B\cup C$ . (结合律)
    - $A\cup A = A$ . (幂等性)
    - $A\subset B \Leftrightarrow A\cup B = B$ 

* 一般化**对**
    - 一个事实 $\{a\}\cup \{b\} = \{a, b\}$ 
    - 将 $\{a, b, c\}$ 定义为 $\{a,b,c\} = \{a\}\cup\{b\}\cup\{c\}$ 
    - 证得 $\{a,b,c\} = \{x:x=a \lor x=b \lor x=c\}$ .这样的**无序多元组**是确定的.

* **交集**
    - 集合 $A, B$ 的**交集**定义为 $A\cap B = \{x\in A:x\in B\}$ .
    - 自然有 $A\cap B = \{x: x\in A \land x\in B\}$ .

* **交集**的一些性质
    - $A\cap \varnothing = \varnothing$ 
    - $A\cap B = B \cap A$ . (交换律)
    - $A\cap(B\cap C) = (A\cap B)\cap C$ = $A\cap B\cap C$ . (结合律)
    - $A\cap A = A$ . (幂等性)
    - $A\subset B \Leftrightarrow A\cap B = A$ 

* **不交**和**不交集**
    - 如果 $A\cap B = \varnothing$ ，则集合 $A,B$ **不交**，是一对**不交集**.

* 并集和交集的分配律
    - $A\cap(B\cup C) = (A\cap B)\cup (A\cap C)$ .
    - $A\cup(B\cap C) = (A\cup B)\cap (A\cup C)$ .

***思考***: 并集由并集公理导出，而交集是直接定义的原因.
根据**分类公理**，我们能够直接定义二元关系的交集，即 $\{x\in A: x\in B\}$ . 注意到**分类公理**能够构造子集，而我们所需要的**并集**，它是一个更大的集合，因此需要有**并集公理**.

* 模仿**并集公理**审视**交集**
    - $V = \{x: \forall X \in A, x\in X\}$ .

* **零元交集**( $\bigcap$ )
    - $V$ 可被记作 $\bigcap A$ 或 $\bigcap \{X: X\in A\}$ 或 $\bigcap_{X\in A} X$ .

----------

## 习题 Exercise
1. 证明 $(A\cap B)\cup C=A\cap(B\cup C)\Leftrightarrow C\subset A$ .
$$
\begin{aligned}
\mathbf{i.} \ & (A\cap B)\cup C = A\cap(B\cup C) \Rightarrow C \subset A\\
& \because C \subset (A\cap B)\cup C = A\cap(B\cup C) \subset A \\
& \therefore C \subset A\\
\mathbf{ii.} \ & (A\cap B)\cup C = A\cap(B\cup C) \Leftarrow C \subset A\\
& \because C\subset A \Leftrightarrow A\cup C = A\\
& \therefore(A\cap B)\cup C = (A\cup C)\cap(B\cup C) = A\cap(B\cup C)\\\\
& \mathrm{Q.E.D} \\
\end{aligned}
$$
----------

## 参考 Reference
[1] https://en.wikipedia.org/wiki/Axiom_of_union


  [1]: https://en.wikipedia.org/wiki/Axiom_of_union