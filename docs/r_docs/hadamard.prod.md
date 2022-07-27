# `hadamard`

Hadamard product of two matrices


## Description

This function returns the Hadamard or element-wise product of two matrices `x` 
 and `y` , that have the same dimensions.


## Usage

```r
hadamard(x, y = x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric matrix or vector.
`y`     |     a numeric matrix or vector.


## Value

A matrix with the same dimension of `x` (and `y` ) which corresponds to the
 element-by-element product of the two matrices.


## References

Styan, G.P.H. (1973).
 Hadamard products and multivariate statistical analysis,
  Linear Algebra and Its Applications  6 , 217-240.


## Examples

```r
x <- matrix(rep(1:10, times = 5), ncol = 5)
y <- matrix(rep(1:5, each = 10), ncol = 5)
z <- hadamard(x, y)
z
```


