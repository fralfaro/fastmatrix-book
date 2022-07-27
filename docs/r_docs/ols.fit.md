# `ols.fit`

Fitter Functions for Linear Models


## Description

This function is a switcher among various numerical fitting functions
 ( [`ols.fit.cg`](#ols.fit.cg) , [`ols.fit.chol`](#ols.fit.chol) , [`ols.fit.qr`](#ols.fit.qr) ,
  [`ols.fit.svd`](#ols.fit.svd) and [`ols.fit.sweep`](#ols.fit.sweep) ). The argument `method` 
 does the switching: `"qr"` for [`ols.fit.qr`](#ols.fit.qr) , etc. This should usually
  not be used directly unless by experienced users.


## Usage

```r
ols.fit(x, y, method = "qr", tol = 1e-7, maxiter = 100)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     design matrix of dimension $n\times q$ .
`y`     |     vector of observations of length $n$ .
`method`     |     currently, methods `"cg"` , `"chol"` , `"qr"` (default),  `"svd"` and `"sweep"` are supported.
`tol`     |     tolerance for the conjugate gradients ( `gc` ) method. Default is  `tol = 1e-7` .
`maxiter`     |     The maximum number of iterations for the conjugate gradients ( `gc` ) method. Defaults to 100.


## Value

a [`list`](#list) with components:
  
Value      |Description
------------- |----------------
`coefficients`     |  a named vector of coefficients.
`residuals`     |   the residuals, that is response minus fitted values.
`fitted.values`     |   the fitted mean values.
`RSS`     |  the residual sum of squares.
`cov.unscaled`     |   a $p \times p$ matrix of (unscaled) covariances of the $\hat{\beta}_{j}$, $j = 1,...,p$.




## Seealso

[`ols.fit.cg`](#ols.fit.cg) , [`ols.fit.chol`](#ols.fit.chol) , [`ols.fit.qr`](#ols.fit.qr) ,
  [`ols.fit.svd`](#ols.fit.svd) , [`ols.fit.sweep`](#ols.fit.sweep) .


## Examples

```r
set.seed(151)
n <- 100
p <- 2
x <- matrix(rnorm(n * p), n, p) # no intercept!
y <- rnorm(n)
fm <- ols.fit(x = x, y = y, method = "chol")
fm
```


