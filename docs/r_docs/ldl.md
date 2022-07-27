# `ldl`

The LDL decomposition


## Description

Compute the LDL decomposition of a real symmetric matrix.


## Usage

```r
ldl(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a symmetric numeric matrix whose LDL decomposition is to be computed.


## Value

The factorization has the form $\mathbf{X} = \mathbf{LDL}^T$ , where $\mathbf{D}$ 
 is a diagonal matrix and $\mathbf{L}$ is unitary lower triangular.
 
The LDL decomposition of `x` is returned as a list with components:
  


Value      |Description
------------- |----------------
`lower`     |  the unitary lower triangular factor $\mathbf{L}$.
`d`     |   a vector containing the diagonal elements of $\mathbf{D}$.


## Seealso

[`chol`](#chol)


## References

Golub, G.H., Van Loan, C.F. (1996).
  Matrix Computations , 3rd Edition.
 John Hopkins University Press.


## Examples

```r
a <- matrix(c(2,-1,0,-1,2,-1,0,-1,1), ncol = 3)
z <- ldl(a)
z # information of LDL factorization

# computing det(a)
prod(z$d) # product of diagonal elements of D

# a non-positive-definite matrix
m <- matrix(c(5,-5,-5,3), ncol = 2)
try(chol(m)) # fails
ldl(m)
```


