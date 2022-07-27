# `cov.weighted`

Weighted covariance matrices


## Description

Returns a list containing estimates of the weighted mean and covariance matrix
 of the data.


## Usage

```r
cov.weighted(x, weights = rep(1, nrow(x)))
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a matrix or data frame. As usual, rows are observations and columns are variables.
`weights`     |     a non-negative and non-zero vector of weights for each observation. Its length must equal the number of rows of `x` .


## Details

The covariance matrix is divided by the number of observations, which arise for
 instance, when we use the class of elliptical contoured distributions. This differs
 from the behaviour of function [`cov.wt`](#cov.wt) .


## Value

A list containing the following named components:
  

Value      |Description
------------- |----------------
`mean`     |   an estimate for the center (mean) of the data.
`cov`     |   the estimated (weighted) covariance matrix.




## Seealso

[`cov.wt`](#cov.wt) , [`cov`](#cov) and [`var`](#var) .


## References

Clarke, M.R.B. (1971).
 Algorithm AS 41: Updating the sample mean and dispersion matrix.
  Applied Statistics  20 , 206-209.


## Examples

```r
x <- cbind(1:10, c(1:3, 8:5, 8:10))
z0 <- cov.weighted(x) # all weights are 1
D2 <- Mahalanobis(x, center = z0$mean, cov = z0$cov)
p <- ncol(x)
wts <- (p + 1) / (1 + D2) # nice weights!
z1 <- cov.weighted(x, weights = wts)
z1
```


