# `is.lower.tri`

Check if a matrix is lower or upper triangular


## Description

Returns `TRUE` if the given matrix is lower or upper triangular matrix.


## Usage

```r
is.lower.tri(x, diag = FALSE)
is.upper.tri(x, diag = FALSE)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a matrix of other list() object with `length(dim(x)) == 2` .
`diag`     |     logical. Should the diagonal be included?


## Value

Check if a matrix is lower or upper triangular. You can also include diagonal to the check.


## Seealso

[`lower.tri`](#lower.tri) , [`upper.tri`](#upper.tri)


## Examples

```r
x <- matrix(rnorm(10 * 3), ncol = 3)
R <- chol(crossprod(x))

is.lower.tri(R)
is.upper.tri(R)
```


