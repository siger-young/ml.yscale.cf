---
title: "2020 大学物理（上）知识梳理"
date: 2020-05-31T17:34:10+08:00
draft: true
---
2020 大学物理（上）知识梳理
<!--more-->
# 第 6 章 静电场

## 电荷和库仑定律

### 基本概念

**库仑定律** 两个点电荷 $q_1,q_2$， 则 $q_1$ 对 $q_2$ 的作用力为
$$
\begin{equation}
\mathbf{F}=\frac{q_1q_2}{4\pi\epsilon_0r^2}\hat{\mathbf{r}}=\frac{q_1q_2}{4\pi\epsilon_0r^3}\mathbf{r}
\label{eqn:6-coulomb-law}
\end{equation}
$$
其中 $\mathbf{r}$ 是从 $q_1$ 指向 $q_2$ 的向量，$\hat{\mathbf{r}}$ 是 $\mathbf{r}$ 的单位向量，当 $q_1$ 与 $q_2$ 同号时，两者相斥；异号时，两者相吸；$\epsilon_0$ 是一个常量，叫做**真空电容率**或**真空介电常数**

**电力叠加原理** 多个点电荷 $q_1,q_2,\cdots,q_n$ 对另一电荷 $q$ 的作用力为
$$
\mathbf{F}=\sum_{i=1}^n \mathbf{F}_i
$$
其中 $\mathbf{F}_i$ 是 $q_i$ 对 $q$ 的作用力，可用 $\eqref{eqn:6-coulomb-law}$ 计算，当电荷连续分布时，则有积分式
$$
\mathbf{F}=\int_{t_1}^{t_2} d\mathbf{F}
$$

## 电场

### 基本概念

**电场强度** 电场强度实际上是归一化的一种电场性质
$$
\mathbf{E}=\frac{\mathbf{F}}{q}
$$

**电场叠加原理** 因为电场力可以叠加，因此电场强度也可以叠加。

### 电偶极子

{{% figure class="center" src="/images/2020-physics-a-review/dipole.png" alt="电偶极子示意图" caption="电偶极子示意图" %}}

**电偶极子** 如上图所示，两个等量异种电荷 $+q,-q$ 间距为 $l$，构成一个体系，称为电偶极子.

**电偶极子中垂线的场强** 中垂线上，设某点到两个电荷中点的距离为 $d$，则该点场强大小为
$$
E=\dfrac{ql}{4\pi\epsilon_0(d^2+\frac{l^2}4)^{3/2}}
$$
显然根据几何关系可以知道电场力向左，故场强也向左.

当 $d\gg l$ 时，注意到有
$$
\begin{equation}
E=\frac{ql}{4\pi\epsilon_0d^3}
\label{eqn:6-dipole-strength}
\end{equation}
$$

**电偶极矩** 在式 $\eqref{eqn:6-dipole-strength}$ 场强中有一项 $ql$，这一项反映电偶极子的特性，一般记为
$$
\mathbf{p}=q\mathbf{l}
$$
称为电偶极矩，其中 $\mathbf{l}$ 由 $-q$ 指向 $+q$，故电偶极子中垂线的场强可写为
$$
E=-\frac{\mathbf{p}}{4\pi\epsilon_0d^3}
$$
