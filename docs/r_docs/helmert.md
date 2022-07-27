# `helmert`

Helmert matrix


## Description

This function returns the Helmert matrix of order $n$ .


## Usage

```r
helmert(n = 1)
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the Helmert matrix.


## Details

A Helmert matrix of order $n$ is a square matrix defined as
  
$$\mathbf{H}_n = \left[{\begin{array}{*{20}{c}}1/\sqrt{n} & 1/\sqrt{n} & 1/\sqrt{n} & \dots & 1/\sqrt{n} \\1/\sqrt{2} & -1/\sqrt{2} & 0 & \dots & 0 \\1/\sqrt{6} & 1/\sqrt{6} & -2/\sqrt{6} & \dots & 0 \\\vdots & \vdots & \vdots & \ddots & \vdots \\\frac{1}{\sqrt{n(n-1)}} & \frac{1}{\sqrt{n(n-1)}} & \frac{1}{\sqrt{n(n-1)}} & \dots & -\frac{(n-1)}{\sqrt{n(n-1)}}\end{array}}\right].$$
 
 Helmert matrix is orthogonal and is frequently used in the analysis of variance (ANOVA).


## Value

Returns an $n$ by $n$ matrix.


## References

Lancaster, H.O. (1965).
 The Helmert matrices.
  The American Mathematical Monthly  72 , 4-12.
 
 Gentle, J.E. (2007).
  Matrix Algebra: Theory, Computations, and Applications in Statistics .
 Springer, New York.


## Examples

```r
n <- 1000
set.seed(149)
x <- rnorm(n)

H <- helmert(n)
object.size(H) # 7.63 Mb of storage
K <- H[2:n,]
z <- c(K %*% x)
sum(z^2) # 933.1736

# same that
(n - 1) * var(x)
```


