---
title: "[MIT OCW] 18.02 Multivariable Calculus - 3 笔记"
categories:
- "mooc-notes"
tags:
- "MIT 18.02"
date: 2019-07-28 17:13:00
mathjax: true
draft: false
---
# MIT OCW 18.02 Multivariable Calculus
<!--more-->
## Matrices
### Linear Transformation
If we want apply some operation on a vector $\mathbf{x}=(x_1,x_2)$ to change it into $\mathbf{x'}=(-x_2,x_1)$ , the process can be described as a matrix.
Given a vector $\mathbf{x}=\begin{bmatrix}x_1\\x_2\end{bmatrix}$ and a matrix $\mathbf{R}=\begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}$ , a new vector will be generated after we apply the matrix $\mathbf{R}$ to $\mathbf{x}$ that is
$$
\mathbf{R}\mathbf{x}=\begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}\begin{bmatrix}x_1\\x_2\end{bmatrix}=\begin{bmatrix}-x_2\\x_1\end{bmatrix}.
$$
A more concrete example is that if we know how the target vector $\mathbf{u}=\begin{bmatrix}u_1\\u_2\\u_3\end{bmatrix}$ is derived from $\mathbf{x}=\begin{bmatrix}x_1\\x_2\\x_3\end{bmatrix}$, for instance
$$
\left\{\begin{aligned}u_1&=2x_1+3x_2+3x_3\\u_2&=2x_1+4x_2+5x_3\\u_3&=x_1+x_2+2x_3\end{aligned}\right.,
$$
then we can intermediately write such operation as a matrix that is
$$
\mathbf{A}=\begin{bmatrix}2&3&3\\2&4&5\\1&1&2\end{bmatrix}.
$$
We now have the following equation
$$
\mathbf{A}\mathbf{x}=\mathbf{u}.
$$
### Minor and Cofactor
For a matrix $\mathbf{A}$ , delete the row and the column where a specific element $a_{ij}$ exactly lies, and we get a smaller matrix. Treat it as a determinant, and that's called the **minor** of $a_{ij}$ .
The **cofactor** is almost the same as the minor, but have something to do with signs, which means that for the element $a_{ij}$ , we get the cofactor of it by multiplying $(-1)^{i+j}$ before the minor.
Write the cofactor of some element $a_{ij}$ as $A_{ij}$ , and compose a new matrix
$$
\mathbf{C}=\begin{bmatrix} A_{11} & A_{12} & A_{13} & \cdots \\ A_{21} & A_{22} & A_{23} & \cdots \\ A_{31} & A_{32} & A_{33} & \cdots \\ \vdots & \cdots & \cdots & \cdots \end{bmatrix},
$$
which is called the **cofactor matrix**, namely **comatrix**.

### Transpose
For a matrix $\mathbf{A}$ , the **transpose matrix** of it $\mathbf{A}^{\mathsf{T}}$ is derived from $\mathbf{A}$ where one's rows are the other's columns in the same order, vice versa.
Concretely, take $\mathbf{A}=\begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}$ as an example, the tranpose matrix $\mathbf{A}^{\mathsf{T}}=\begin{bmatrix} 1 & 4 & 7 \\ 2 & 5 & 8 \\ 3 & 6 & 9 \end{bmatrix}$ .

### Adjugate
For a matrix $\mathbf{A}$ , the **adjugate matrix** of it $\operatorname{adj}(\mathbf{a})=\mathbf{C}^{\mathsf{T}}$ , where $\mathbf{C}$ is the comatrix.

### Inverse
The **inverse** of a matrix $\mathbf{A}$ with the notation $\mathbf{A}^{-1}$ fulfills `
$$
\mathbf{A}\mathbf{A}^{-1}=\mathbf{I},\mathbf{A}^{-1}\mathbf{A}=\mathbf{I},
$$
` where $\mathbf{I}$ is an identity matrix.
For an equation $\mathbf{A}\mathbf{X}=\mathbf{B}$ , if we want to solve $\mathbf{X}$ , we just apply $\mathbf{A}^{-1}$ to the both sides thus get
$$
\mathbf{A}^{-1}(\mathbf{A}\mathbf{X})=\mathbf{A}^{-1}\mathbf{B},
$$
namely $\mathbf{X}=\mathbf{A}^{-1}\mathbf{B}$ .
To calculate the inverse of a matrix $A$ , we need to know the adjugate matrix $\operatorname{adj}(\mathbf{A})$ and the determinant of $\mathbf{A}$ to in the following formula
$$
\mathbf{A}^{-1}=\frac{\operatorname{adj}(\mathbf{A})}{\det(\mathbf{A})}.
$$

**e.g.** Calculate the inverse of $\mathbf{A}=\begin{bmatrix}2&3&3\\2&4&5\\1&1&2\end{bmatrix}$ .

**Solution**
First, we calculate the comatrix
$$
\mathbf{C}=\begin{bmatrix}
+\begin{vmatrix}4&5\\1&2\end{vmatrix}&
-\begin{vmatrix}2&5\\1&2\end{vmatrix}&
+\begin{vmatrix}2&4\\1&1\end{vmatrix}\\
-\begin{vmatrix}3&3\\1&2\end{vmatrix}&
+\begin{vmatrix}2&3\\1&2\end{vmatrix}&
-\begin{vmatrix}2&3\\1&1\end{vmatrix}\\
+\begin{vmatrix}3&3\\4&5\end{vmatrix}&
-\begin{vmatrix}2&3\\2&5\end{vmatrix}&
+\begin{vmatrix}2&3\\2&4\end{vmatrix}
\end{bmatrix}=\begin{bmatrix}
+3 & -(-1) & +(-2)\\
-3 & +1 & -(-1)\\
+3 & -4 & +(-2)
\end{bmatrix}=\begin{bmatrix}
3 & 1 & -2\\
-3 & 1 & 1\\
3 & -4 & 2
\end{bmatrix},
$$
and tranpose it
$$
\mathbf{C}^{\mathsf{T}}=\begin{bmatrix}
3 & -3 & 3\\
1 & 1 & -4\\
-2 & 1 & 2
\end{bmatrix}.
$$
Easy to get $\det(\mathbf{A})=3$ , therefore the inverse can be calculated
$$
\mathbf{A}^{-1}=\frac13\begin{bmatrix}
3 & -3 & 3\\
1 & 1 & -4\\
-2 & 1 & 2
\end{bmatrix}=\begin{bmatrix}
1 & -1 & 1\\
\frac13 & \frac13 & -\frac43\\
-\frac23 & \frac13 & \frac23
\end{bmatrix}.
$$
