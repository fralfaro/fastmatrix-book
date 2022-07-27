# `matrix.inner`

Compute the inner product between two rectangular matrices


## Description

Computes the inner product between two rectangular matrices calling BLAS.


## Usage

```r
matrix.inner(x, y = x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric matrix.
`y`     |     a numeric matrix.


## Value

a real value, indicating the inner product between two matrices.


## Examples

```r
x <- matrix(c(1, 1, 1,
1, 2, 1,
1, 3, 1,
1, 1,-1,
1, 2,-1,
1, 3,-1), ncol = 3, byrow = TRUE)
y <- matrix(1, nrow = 6, ncol = 3)
matrix.inner(x, y)

# must be equal
matrix.norm(x, type = "Frobenius")^2
matrix.inner(x)
```


