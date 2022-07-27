# `dupl.prod`

Matrix multiplication envolving the duplication matrix


## Description

Given the order of a duplication and matrix `x` , performs one of the matrix-matrix
 operations:
    

* $\mathbf{Y} = \mathbf{DX}$ , if `side = "left"` and `transposed = FALSE` , or
* $\mathbf{Y} = \mathbf{D}^T\mathbf{X}$ , if `side = "left"` and `transposed = TRUE` , or
* $\mathbf{Y} = \mathbf{XD}$ , if `side = "right"` and `transposed = FALSE` , or
* $\mathbf{Y} = \mathbf{XD}^T$ , if `side = "right"` and `transposed = TRUE` ,  

where $\mathbf{D}$ is the duplication matrix of order $n$ . The main aim of
  `dupl.prod` is to do this matrix multiplication without forming the
 duplication matrix.


## Usage

```r
dupl.prod(n = 1, x, transposed = FALSE, side = "left")
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the duplication matrix.
`x`     |     numeric matrix (or vector).
`transposed`     |     logical. Duplication matrix should be transposed?
`side`     |     a string selecting if duplication matrix is pre-multiplying `x` , that is  `side = "left"` or post-multiplying `x` , by using `side = "right"` .


## Details

Underlying `C` code only uses information provided by [`dupl.info`](#dupl.info) to
 performs the matrix multiplication. The duplication matrix is never created.


## Seealso

[`duplication`](#duplication)


## Examples

```r
D4 <- duplication(n = 4, matrix = TRUE)
x <- matrix(1, nrow = 16, ncol = 2)
y <- crossprod(D4, x)

z <- dupl.prod(n = 4, x, transposed = TRUE) # D4 is not stored
all(z == y) # matrices y and z are equal!
```


