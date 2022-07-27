# `minkowski`

Computes the p-norm of a vector


## Description

Computes a `p` -norm of vector `x` .  The norm can be the one ( `p = 1` )
 norm, Euclidean ( `p = 2` ) norm, the infinity ( `p = Inf` ) norm. The underlying
  `C` or `Fortran` code is inspired on ideas of BLAS Level 1.


## Usage

```r
minkowski(x, p = 2)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric vector.
`p`     |     a number, specifying the type of norm desired. Possible values include real number greater or equal to 1, or Inf, Default value is `p = 2` .


## Details

Method of `minkowski` for `p = Inf` calls `idamax` BLAS function.
 For other values, `C` or `Fortran` subroutines using unrolled cycles are
 called.


## Value

The vector `p` -norm, a non-negative number.


## Examples

```r
# a tiny example
x <- rnorm(1000)
minkowski(x, p = 1)
minkowski(x, p = 1.5)
minkowski(x, p = 2)
minkowski(x, p = Inf)

x <- x / minkowski(x)
minkowski(x, p = 2) # equal to 1
```


