# `harris.test`

Test for variance homogeneity of correlated variables


## Description

Performs large-sample methods for testing equality of $p \ge 2$ correlated variables.


## Usage

```r
harris.test(x, test = "Wald")
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a matrix or data frame. As usual, rows are observations and columns are variables.
`test`     |     test statistic to be used. One of "Wald" (default), "log", "robust" or "log-robust".


## Value

A list of class 'harris.test' with the following elements:
 
  

Value      |Description
------------- |----------------
`statistic`     |  value of the statistic, i.e. the value of either Wald test, using the log-transformation, or distribution-robust versions of the test (robust and log-robust).
`parameter`     |  the degrees of freedom for the test statistic, which is chi-square distributed.
`p.value`     |    the p-value for the test.
`estimate`     |   the estimated covariance matrix.
`method`     |    a character string indicating what type of test was performed.



## References

Harris, P. (1985).
 Testing the variance homogeneity of correlated variables.
  Biometrika  72 , 103-107.


## Examples

```r
x <- iris[,1:4]
z <- harris.test(x, test = "robust")
z
```


