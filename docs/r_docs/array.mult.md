# `array.mult`

Array multiplication


## Description

Multiplication of 3-dimensional arrays was first introduced by Bates and Watts (1980).
 More extensions and technical details can be found in Wei (1998).


## Usage

```r
array.mult(a, b, x)
```


## Arguments

Argument      |Description
------------- |----------------
`a`     |     a numeric matrix.
`b`     |     a numeric matrix.
`x`     |     a three-dimensional array.


## Details

Let $\mathbf{X} = (x_{tij})$ be a 3-dimensional $n\times p\times q$ where
 indices $t, i$ and $j$ indicate face, row and column, respectively. The
 product $\mathbf{Y} = \mathbf{AXB}$ is an $n\times r\times s$ array, with
  $\mathbf{A}$ and $\mathbf{B}$ are $r\times p$ and $q\times s$ matrices
 respectively. The elements of $\mathbf{Y}$ are defined as:
  
$$y_{tkl} = \sum\limits_{i=1}^p\sum\limits_{j=1}^q a_{ki}x_{tij}b_{jl}$$


## Value

`array.mult` returns a 3-dimensional array of dimension $n\times r\times s$ .


## Seealso

[`array`](#array) , [`matrix`](#matrix) , [`bracket.prod`](#bracket.prod) .


## References

Bates, D.M., Watts, D.G. (1980).
 Relative curvature measures of nonlinearity.
  Journal of the Royal Statistical Society, Series B  42 , 1-25.
 
 Wei, B.C. (1998).
  Exponential Family Nonlinear Models .
 Springer, New York.


## Examples

```r
x <- array(0, dim = c(2,3,3)) # 2 x 3 x 3 array
x[,,1] <- c(1,2,2,4,3,6)
x[,,2] <- c(2,4,4,8,6,12)
x[,,3] <- c(3,6,6,12,9,18)

a <- matrix(1, nrow = 2, ncol = 3)
b <- matrix(1, nrow = 3, ncol = 2)

y <- array.mult(a, b, x) # a 2 x 2 x 2 array
y
```


