# `dupl.cross`

Matrix crossproduct envolving the duplication matrix


## Description

Given the order of two duplication matrices and matrix `x` , this function performs
 the operation: $\mathbf{Y} = \mathbf{D}_n^T\mathbf{X}\mathbf{D}_k$ , where $\mathbf{D}_n$ 
 and $\mathbf{D}_k$ are duplication matrices of order $n$ and $k$ , respectively.


## Usage

```r
dupl.cross(n = 1, k = n, x = NULL)
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the duplication matrix used pre-multiplying `x` .
`k`     |     order of the duplication matrix used post-multiplying `x` . By default  `k = n` is used.
`x`     |     numeric matrix, this argument is required.


## Details

This function calls [`dupl.prod`](#dupl.prod) to performs the matrix multiplications required
 but without forming any duplication matrices.


## Seealso

[`dupl.prod`](#dupl.prod)


## Examples

```r
D2 <- duplication(n = 2, matrix = TRUE)
D3 <- duplication(n = 3, matrix = TRUE)
x <- matrix(1, nrow = 9, ncol = 4)
y <- t(D3) %*% x %*% D2

z <- dupl.cross(n = 3, k = 2, x) # D2 and D3 are not stored
all(z == y) # matrices y and z are equal!

x <- matrix(1, nrow = 9, ncol = 9)
z <- dupl.cross(n = 3, x = x) # same matrix is used to pre- and post-multiplying x
z # print result
```


