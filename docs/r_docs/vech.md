# `vech`

Vectorization the lower triangular part of a square matrix


## Description

This function returns a vector obtained by stacking the lower triangular part of a
 square matrix.


## Usage

```r
vech(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a square matrix.


## Value

Let `x` be a $n$ by $n$ matrix, then `vech(x)` is a $n(n+1)/2$ -dimensional
 vector.


## Examples

```r
x <- matrix(rep(1:10, each = 10), ncol = 10)
x
y <- vech(x)
y
```


