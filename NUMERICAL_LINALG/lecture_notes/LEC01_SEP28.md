# Matirx and Vector Multiplication

## Matrix multiply vector
### Row expansion
b = Ax

### Column expansion
$$
\boldsymbol{b} = \sum_j \boldsymbol{a}_j x_j
$$

## Matrix Multiplication
$$
\mathbf{b} = \mathbf{A}\mathbf{C}\\
\boldsymbol{b}_j = \mathbf{A}\boldsymbol{c}_j
$$

## Properties of Matrix
**Range and Null space of matrix A**
$$
\text{range}(\mathbf{A}) := \{\boldsymbol{b} : \boldsymbol{b} = \mathbf{A}\boldsymbol{x}, \boldsymbol{x}\in\Complex^n\}
$$
range(A) is the space spanned by the columns of A

**Nullspace of A**
$$
\text{null}(\mathbf{A}) := \{\boldsymbol{x}: \mathbf{A}\boldsymbol{x} = 0\}
$$


**Rank of a matrix**

column rank : dimension of the column space
row rank : dimension of the row space

```{prf:theorem}
row rank = column rank
```

**Full Rank**
A full rank matrix $\mathbf{A}\in \Complex^{m\times n}$ and  $m\ge n$, then $\text{rank}(\mathbf{A}) = n$.


```{prf:theorem}
A matrix $\mathbf{A} \in \Complex^{m\times n}$ has full rank <=> $\mathbf{A}$ maps no two vectors to the same vector.
````{prf:example}
$$
\mathbf{A} = \begin{bmatrix}
1 & 5\\
0 & 0\\
0 & 0
\end{bmatrix}
$$

maps $\boldsymbol{x}_1 = \[1; 0\]$ and $\boldsymbol{x}_2 = \[-4;, 1\]$ onto the same vector.
````
```

```{note}
A full rank 3*1 matrix has only rank=1 so that it can only span in one dimension.
```


## Soluability of Ax = b
Definition : A non-singular or invertible matrix is a square matrix of full rank.

=> If $\mathbf{A}\in\Complex^{m\times m}$ is full rank, then the columns of $\mathbf{A}$ form a basis of $\Complex^m$.


## Inverse
x = A^-1b => the coefficients needed to span b in the columns of A

```{prf:theorem}
For $\mathbf{A}\in\Complex^{m\times m}$, the following are equivalent:
- $\mathbf{A}$ has inverse $\mathbf{A}^{-1}$
- $\text{rank}(\mathbf{A}) = m$
- $\text{range}(\mathbf{A}) = \Complex^m$
- $\text{null}(\mathbf{A}) = \{0\}$
- 0 is not an eigenvalues of $\mathbf{A}$
- 0 is not a singular value of $\mathbf{A}$
- $\text{det}(\mathbf{A}) \neq 0$

```