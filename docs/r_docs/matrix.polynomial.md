# `matrix.polynomial`

Evaluates a real general matrix polynomial


## Description

Given $c_0,c_1,\dots,c_n$ coefficients of the polynomial and $\mathbf{A}$ 
 an $n$ by $n$ matrix. This function computes the matrix polynomial
  
$$\mathbf{B} = \sum\limits_{k=0}^n c_k\mathbf{A}^k,$$
 
 using Horner's scheme, where $\mathbf{A}^0 = \mathbf{I}$ is the $n$ by $n$ identity matrix.


## Usage

```r
matrix.polynomial(a, coef = rep(1, power + 1), power = length(coef))
```


## Arguments

Argument      |Description
------------- |----------------
`a`     |     a numeric square matrix of order $n$ by $n$ for which the polinomial is to be computed.
`coef`     |     numeric vector containing the coefficients of the polinomial in order of increasing power.
`power`     |     a numeric exponent (which is forced to be an integer). If the exponent is zero, a multiple of the identity matrix is returned.


## Value

Returns an $n$ by $n$ matrix.


## Examples

```r
a <- matrix(c(1, 3, 2, -5, 1, 7, 1, 5, -4), ncol = 3, byrow = TRUE)
cf <- c(3, 1, 2)
b <- matrix.polynomial(a, cf)
b # 3 * diag(3) + a + 2 * a %*% a
b <- matrix.polynomial(a, power = 2)
b # diag(3) + a + a %*% a
```


