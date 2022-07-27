# `comm.prod`

Matrix multiplication envolving the commutation matrix


## Description

Given the row and column dimension of a commutation and matrix `x` , performs
 one of the matrix-matrix operations:
    

* $\mathbf{Y} = \mathbf{KX}$ , if `side = "left"` and `transposed = FALSE` , or
* $\mathbf{Y} = \mathbf{K}^T\mathbf{X}$ , if `side = "left"` and `transposed = TRUE` , or
* $\mathbf{Y} = \mathbf{XK}$ , if `side = "right"` and `transposed = FALSE` , or
* $\mathbf{Y} = \mathbf{XK}^T$ , if `side = "right"` and `transposed = TRUE` ,  
 
where $\mathbf{K}$ is the commutation matrix of order $mn$ . The main aim of
  `comm.prod` is to do this matrix multiplication without forming the
 commutation matrix.


## Usage

```r
comm.prod(m = 1, n = m, x = NULL, transposed = FALSE, side = "left")
```


## Arguments

Argument      |Description
------------- |----------------
`m`     |     a positive integer row dimension.
`n`     |     a positive integer column dimension.
`x`     |     numeric matrix (or vector).
`transposed`     |     logical. Commutation matrix should be transposed?
`side`     |     a string selecting if commutation matrix is pre-multiplying `x` , that is  `side = "left"` or post-multiplying `x` , by using `side = "right"` .


## Details

Underlying `Fortran` code only uses information provided by [`comm.info`](#comm.info) 
 to performs the matrix multiplication. The commutation matrix is never created.


## Seealso

[`commutation`](#commutation)


## Examples

```r
K42 <- commutation(m = 4, n = 2, matrix = TRUE)
x <- matrix(1:24, ncol = 3)
y <- K42 %*% x

z <- comm.prod(m = 4, n = 2, x) # K42 is not stored
all(z == y) # matrices y and z are equal!
```


