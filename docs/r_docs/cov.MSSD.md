# `cov.MSSD`

Mean Square Successive Difference (MSSD) estimator of the covariance matrix


## Description

Returns a list containing the mean and covariance matrix of the data.


## Usage

```r
cov.MSSD(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a matrix or data frame. As usual, rows are observations and columns are variables.


## Details

This procedure uses the Holmes-Mergen method using the difference between each
 successive pairs of observations also known as Mean Square Successive Method (MSSD)
 to estimate the covariance matrix.


## Value

A list containing the following named components:

Value      |Description
------------- |----------------
`mean`     |    an estimate for the center (mean) of the data.
`cov`     |   the estimated covariance matrix.



## Seealso

[`cov`](#cov) and [`var`](#var) .


## References

Holmes, D.S., Mergen, A.E. (1993).
 Improving the performance of the $T^2$ control chart.
  Quality Engineering  5 , 619-625.


## Examples

```r
x <- cbind(1:10, c(1:3, 8:5, 8:10))
z0 <- cov(x)
z0
z1 <- cov.MSSD(x)
z1
```


