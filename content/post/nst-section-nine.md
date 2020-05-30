---
title: "[Naïve Set Theory] Section 9 Families"
categories:
- mathematics
- set-theory
tags:
- "Naive Set Theory"
date: 2018-08-17 03:08:00
mathjax: true
draft: false
---
# *Naïve Set Theory* Section 9 Families 族
<del>这书名、章数、发布日期真的很配呢.<del>

## 阐明 Exposition
* **族**
    - 对于集合 $I,X$ ，如果 $x$ 是一个从 $I$ 到 $X$ 的函数，称 $x$ 是一个**族**，定义域 $I$ 的一个元素被称为**索引**(index)，定义域 $I$ 被称为**索引集**(index set)，函数 $x$ 的值域被称为**索引族**(indexed set).
    - 对于函数 $x$ 在索引为 $i$ 时的值叫族中的**项**(term)，记作 $x_i$ .
    - 对于上述族，我们可称其是 $X$ 中的族 $\{x_i\}$ .

* 族的并和交
    - 对于族 $\{A_i\}$ ，其值域的并叫做族 $\{A_i\}$ 的并，写作 $\bigcup_{i\in I}A_i$ 或是 $\bigcup_i A_i$ .
    - 如果该族非空，则其值域的交叫做 $\{A_i\}$ 的叫叫做族 $\{A_i\}$ 的交，写作 $\bigcap_{i\in I}A_i$ 或是 $\bigcap_i A_i$ .

* 一般化并集的结合律
    - 若 $\{I_j\}$ 是一个定义域为 $J$ 的集合族，令 $K=\bigcup_{j\in J}I_j$ ，令 $\{A_k\}$ 是一个定义域为 $K$ 的集合族，则有如下关系成立 $\bigcup_{k\in K}A_k=\bigcup_{j\in J}(\bigcup_{i\in I_j}A_i)$ .

* 一般化并集和交集的分配律
    - 若 $\{A_i\}$ 是 $X$ 子集中的族，且有 $B\subset X$ ，则有 $B\cap \bigcup_i A_i = \bigcup_i (B\cap A_i)$ 以及 $B\cup \bigcap_i A_i = \bigcap_i (B\cup A_i)$ .

* 一般化笛卡儿积
    - 考虑 $\{X_i\}$ 是一个定义域为 $I$ 的集合族，则该族的笛卡儿积即是所有集合族 $\{x_i\},x_i\in X_i, i\in I$ 的集合，写作 $\times_{i\in I}X_i$ 或 $\times_{i}X_i$ . (无法使用 ifsym 包，不能输出大" $\times$ ").
    - 观察到 $\times_i X_i = X^I$ ，我们得到了一般化的笛卡儿积，如高中常说的 $R^2, R^3$ ，可验证其正确性.

* 再谈**投影**和**函数**
    - 假使对于以上的 $I$ 有 $J\subset I$ ，那么自然产生上述笛卡儿积的一部分 $\times_{i\in J}X_i$ .
    - 如果使 $y_i=x_i, \forall i\in J$ ，那么 $x\rightarrow y$ 的对应关系被称为 $X$ 在 $\times_{i\in J}X_i$ 上的**投影**，记作 $f_J$ .
    - 如果 $x\in X$ ，则 $f_j$ 在 $x$ 时的值 $x_j$ 被称为 $x$ 在 $X_j$ 上的**投影**. (*此处需要与上一条的****投影****区分*)
    - 如果函数建立于上文的笛卡儿积 $X$ 上，称其为**多变量函数**，如果函数建立在笛卡儿积 $X_a\times X_b$ 上，称其为**单变量函数**.

----------

## 习题 Exercise
* 若 $\{A_i\},\{B_i\}$ 都是集合族，证明 $(\bigcup_i A_i)\cap(\bigcup_j B_j) = \bigcup_{i,j}(A_i\cap B_j)$ 并且 $(\bigcap_i A_i)\cup(\bigcap_j B_j) = \bigcap_{i,j}(A_i\cup B_j)$ .
( $\bigcup_{i,j}$ 表示 $\bigcup_{(i,j)\in I\times J}$ ，交集同理)
$$
\begin{aligned}
& \forall x\in (\bigcup_i A_i)\cap(\bigcup_j B_j),\\
& x\in (\bigcup_i A_i)\land x\in  (\bigcup_j B_j)\\
\Leftrightarrow & \exists i: x\in A_i \land\exists j: x\in B_j\\
\Leftrightarrow & \exists i,j: x\in A_i \land x\in B_j\\
\Leftrightarrow & \exists (i,j)\in I\times J \land (x\in A_i \land x\in B_j)\\
\Leftrightarrow & \exists (i,j)\in I\times J \land (x\in A_i\cap B_j)\\
\Leftrightarrow & x\in \bigcup_{i,j}(A_i\cap B_j)\\
&\mathrm{Q.E.D.}
\end{aligned}
$$
交集方法类似，留给读者作为习题（以 $0.18032c$ 的速度逃.

* 证明 $(\bigcup_i A_i)\times(\bigcup_j B_j)=\bigcup_{i,j}(A_i\times B_j)$ .
$$
\begin{aligned}
& \forall x\in(\bigcup_i A_i)\times(\bigcup_j B_j)\\
& x=(a,b), a\in (\bigcup_i A_i), b\in (\bigcup_j B_j)\\
\Leftrightarrow & \exists i: a\in A_i\land\exists j: b\in B_j\\
\Leftrightarrow & \exists i,j: a\in A_i \land b\in B_j\\
\Leftrightarrow & \exists (i,j)\in I\times J \land (a\in A_i \land b\in B_j)\\
\Leftrightarrow & \exists (i,j)\in I\times J \land (a,b)\in(A_i\times A_j)\\
\Leftrightarrow & x\in \bigcup_{i,j}(A_i\times B_j)\\
&\mathrm{Q.E.D.}
\end{aligned}
$$
* （不考虑空族）证明 $\forall j, \bigcap_i X_i\subset X_j\subset\bigcup_i X_i$ .
$$
\begin{aligned}
\mathbf{i.} \ &\forall x\in \bigcap_i X_i\\
\Rightarrow & \forall i, x\in X_i\\
\Rightarrow & i\leftarrow j \Rightarrow x\in X_j \\
\therefore& \forall j, \bigcap_i X_i\subset X_j\\
\mathbf{ii.} \ &\forall j, x\in X_j\\
\Rightarrow & \exists i, x\in X_i\\
\Rightarrow & x\in \bigcup_i X_i\\
\therefore& \forall j,X_j\subset\bigcup_i X_i\\
&\mathrm{Q.E.D.}
\end{aligned}
$$
