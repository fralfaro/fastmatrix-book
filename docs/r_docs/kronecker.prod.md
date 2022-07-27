# `kronecker.prod`

Kronecker product on matrices


## Description

Computes the kronecker product of two matrices, `x` and `y` .


## Usage

```r
kronecker.prod(x, y = x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric matrix or vector.
`y`     |     a numeric matrix or vector.


## Details

Let $\mathbf{X}$ be an $m\times n$ and $\mathbf{Y}$ a $p\times q$ matrix.
 The $mp\times nq$ matrix defined by
  
$$\left[{\begin{array}{*{20}{c}}x_{11}\mathbf{Y} & \dots & x_{1n}\mathbf{Y} \\\vdots & & \vdots \\x_{m1}\mathbf{Y} & \dots & x_{mn}\mathbf{Y}\end{array}}\right],$$
 
 is called the Kronecker product of $\mathbf{X}$ and $\mathbf{Y}$ .


## Value

An array with dimensions `dim(x) * dim(y)` .


## Seealso

[`kronecker`](#kronecker) function from `base` package is based on [`outer`](#outer) .
 Our `C` version is slightly faster.


## References

Magnus, J.R., Neudecker, H. (2007).
  Matrix Differential Calculus with Applications in Statistics and Econometrics , 3rd Edition.
 Wiley, New York.


## Examples

```r
# block diagonal matrix:
a <- diag(1:3)
b <- matrix(1:4, ncol = 2)
kronecker.prod(a, b)

# examples with vectors
ones <- rep(1, 4)
y <- 1:3
kronecker.prod(ones, y) # 12-dimensional vector
kronecker.prod(ones, t(y)) # 3 x 3 matrix
```


