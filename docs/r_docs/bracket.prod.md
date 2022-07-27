# `bracket.prod`

Bracket product


## Description

Bracket product of a matrix and a 3-dimensional array.


## Usage

```r
bracket.prod(a, x)
```


## Arguments

Argument      |Description
------------- |----------------
`a`     |     a numeric matrix.
`x`     |     a three-dimensional array.


## Details

Let $\mathbf{X} = (x_{tij})$ be a 3-dimensional $n\times p\times q$ array and
  $\mathbf{A}$ an $m\times n$ matrix, then $\mathbf{Y} = [\mathbf{A}][\mathbf{X}]$ 
 is called the bracket product of $\mathbf{A}$ and $\mathbf{X}$ , that is an $m$$  \times p\times q$ with elements
  
$$y_{tij} = \sum\limits_{k=1}^n a_{tk}x_{kij}$$


## Value

`bracket.prod` returns a 3-dimensional array of dimension $m\times p\times q$ .


## Seealso

[`array`](#array) , [`matrix`](#matrix) , [`array.mult`](#array.mult) .


## References

Wei, B.C. (1998).
  Exponential Family Nonlinear Models .
 Springer, New York.


## Examples

```r
x <- array(0, dim = c(2,3,3)) # 2 x 3 x 3 array
x[,,1] <- c(1,2,2,4,3,6)
x[,,2] <- c(2,4,4,8,6,12)
x[,,3] <- c(3,6,6,12,9,18)

a <- matrix(1, nrow = 3, ncol = 2)

y <- bracket.prod(a, x) # a 3 x 3 x 3 array
y
```


