# `symm.prod`

Matrix multiplication envolving the symmetrizer matrix


## Description

Given the order of a symmetrizer and matrix `x` , performs one of the matrix-matrix
 operations:
    

* $\mathbf{Y} = \mathbf{NX}$ , if `side = "left"` , or
* $\mathbf{Y} = \mathbf{XN}$ , if `side = "right"` ,  

where $\mathbf{N}$ is the symmetrizer matrix of order $n$ . The main aim of
  `symm.prod` is to do this matrix multiplication without forming the
 symmetrizer matrix.


## Usage

```r
symm.prod(n = 1, x = NULL, side = "left")
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the symmetrizer matrix.
`x`     |     numeric matrix (or vector).
`side`     |     a string selecting if symmetrizer matrix is pre-multiplying `x` , that is  `side = "left"` or post-multiplying `x` , by using `side = "right"` .


## Details

Underlying `C` code only uses information provided by [`symm.info`](#symm.info) to
 performs the matrix multiplication. The symmetrizer matrix is never created.


## Seealso

[`symmetrizer`](#symmetrizer)


## Examples

```r
N4 <- symmetrizer(n = 4, matrix = TRUE)
x <- matrix(1:32, ncol = 2)
y <- N4 %*% x

z <- symm.prod(n = 4, x) # N4 is not stored
all(z == y) # matrices y and z are equal!
```


