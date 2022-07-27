# `sherman.morrison`

Sherman-Morrison formula


## Description

The Sherman-Morrison formula gives a convenient expression for the inverse of the
 rank 1 update $(\mathbf{A} + \mathbf{bd}^T)$ where $\mathbf{A}$ is a $n\times n$ 
 matrix and $\mathbf{b}$ , $\mathbf{d}$ are $n$ -dimensional vectors. Thus
  
$$(\mathbf{A} + \mathbf{bd}^T)^{-1} = \mathbf{A}^{-1} - \frac{\mathbf{A}^{-1}\mathbf{bd}^T\mathbf{A}^{-1}}{1 + \mathbf{d}^T\mathbf{A}^{-1}\mathbf{b}}.$$


## Usage

```r
sherman.morrison(a, b, d = b, inverted = FALSE)
```


## Arguments

Argument      |Description
------------- |----------------
`a`     |     a numeric matrix.
`b`     |     a numeric vector.
`d`     |     a numeric vector.
`inverted`     |     logical. If `TRUE` , `a` is supposed to contain its inverse .


## Details

Method of `sherman.morrison` calls BLAS level 2 subroutines `DGEMV` and
  `DGER` for computational efficiency.


## Value

a square matrix of the same order as `a` .


## Examples

```r
n <- 10
ones <- rep(1, n)
a <- 0.5 * diag(n)
z <- sherman.morrison(a, ones, 0.5 * ones)
z
```


