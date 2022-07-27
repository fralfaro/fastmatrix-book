# `asSymmetric`

Force a matrix to be symmetric


## Description

Force a square matrix `x` to be symmetric


## Usage

```r
asSymmetric(x, lower = TRUE)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a square matrix to be forced to be symmetric.
`lower`     |     logical, should the upper (lower) triangle be replaced with the lower (upper) triangle?


## Value

a square symmetric matrix.


## Examples

```r
a <- matrix(1:16, ncol = 4)
isSymmetric(a) # FALSE
a <- asSymmetric(a) # copy lower triangle into upper triangle
```


