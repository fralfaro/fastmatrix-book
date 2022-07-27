# `sweep.operator`

Gauss-Jordan sweep operator for symmetric matrices


## Description

Perform the sweep operation (or reverse sweep) on the diagonal elements of a
 symmetric matrix.


## Usage

```r
sweep.operator(x, k = 1, reverse = FALSE)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a symmetric matrix.
`k`     |     elements (if `k` is vector) of the diagonal which will be sweeped.
`reverse`     |     logical. If `reverse = TRUE` the reverse sweep is performed.


## Details

The symmetric sweep operator is a powerful tool in computational statistics with
 uses in stepwise regression, conditional multivariate normal distributions, MANOVA,
 and more.


## Value

a square matrix of the same order as `x` .


## References

Goodnight, J.H. (1979).
 A tutorial on the SWEEP operator.
  The American Statistician  33 , 149-158.


## Examples

```r
# tiny example of regression, last column contains 'y'
xy <- matrix(c(1, 1, 1, 1,
1, 2, 1, 3,
1, 3, 1, 3,
1, 1,-1, 2,
1, 2,-1, 2,
1, 3,-1, 1), ncol = 4, byrow = TRUE)
z <- crossprod(xy)
z <- sweep.operator(z, k = 1:3)
cf <- z[1:3,4] # regression coefficients
RSS <- z[4,4]  # residual sum of squares

# an example not that small
x <- matrix(rnorm(1000 * 100), ncol = 100)
xx <- crossprod(x)
z <- sweep.operator(xx, k = 1)
```


