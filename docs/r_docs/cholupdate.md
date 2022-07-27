# `cholupdate`

Rank 1 update to Cholesky factorization


## Description

function `chol.update` , where `R = chol(A)` is the original Cholesky
 factorization of $\mathbf{A}$ , returns the upper triangular Cholesky factor of
  $\mathbf{A} + \mathbf{xx}^T$ , with `x` a column vector of appropriate dimension.


## Usage

```r
cholupdate(r, x)
```


## Arguments

Argument      |Description
------------- |----------------
`r`     |     a upper triangular matrix, the Cholesky factor of matrix a.
`x`     |     vector defining the rank one update.


## Seealso

[`chol`](#chol)


## References

Golub, G.H., Van Loan, C.F. (2013).
  Matrix Computations , 4th Edition.
 John Hopkins University Press.


## Examples

```r
a <- matrix(c(1,1,1,1,2,3,1,3,6), ncol = 3)
r <- chol(a)
x <- c(0,0,1)
b <- a + outer(x,x)
r1 <- cholupdate(r, x)
r1
all(r1 == chol(b)) # TRUE
```


