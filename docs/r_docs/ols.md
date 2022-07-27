# `ols`

Fit linear regression model


## Description

Returns an object of class `"ols"` that represents a linear model fit.


## Usage

```r
ols(formula, data, subset, na.action, method = "qr", tol = 1e-7, maxiter = 100,
  model = FALSE, x = FALSE, y = FALSE, contrasts = NULL, ...)
```


## Arguments

Argument      |Description
------------- |----------------
`formula`     |     an object of class `"` (or one that can be coerced to that class): a symbolic description of the model to be fitted.
`data`     |     an optional data frame, list or environment (or object coercible by [`as.data.frame`](#as.data.frame) to a data frame) containing the variables in the model. If not found in `data` , the variables are taken from  `environment(formula)` , typically the environment from which `ols`  is called.
`subset`     |     an optional vector specifying a subset of observations to be used in the fitting process.
`na.action`     |     a function which indicates what should happen when the data contain `NA` s. The default is set by the `na.action` setting of  [`options`](#options) , and is [`na.fail`](#na.fail) if that is unset.
`method`     |     the least squares fitting method to be used; the options are `"cg"`  (conjugate gradients), `"chol"` , `"qr"` (the default), `"svd"` and  `"sweep"` .
`tol`     |     tolerance for the conjugate gradients ( `gc` ) method. Default is  `tol = 1e-7` .
`maxiter`     |     The maximum number of iterations for the conjugate gradients ( `gc` ) method. Defaults to 100.
`model, x, y`     |     logicals.  If `TRUE` the corresponding components of the fit (the model frame, the model matrix, the response) are returned.
`contrasts`     |     an optional list. See the `contrasts.arg` of  [`model.matrix.default`](#model.matrix.default) .
`list()`     |     additional arguments (currently disregarded).


## Value

`ols` returns an object of [`class`](#class)  `"ols"` .
 
 The function `summary` is used to obtain and print a summary of the
 results.  The generic accessor functions `coefficients` , `fitted.values` 
 and `residuals` extract various useful features of the value returned by `ols` .
 
 An object of class `"ols"` is a list containing at least the
 following components:
 
  
Value      |Description
------------- |----------------
`coefficients`     |  a named vector of coefficients.
`residuals`     |   the residuals, that is response minus fitted values.
`fitted.values`     |   the fitted mean values.
`RSS`     |  the residual sum of squares.
`cov.unscaled`     |   a $p \times p$ matrix of (unscaled) covariances of the $\hat{\beta}_{j}$, $j = 1,...,p$.
`call`     |  the matched call.
`terms`     |  the terms object used.
`contrasts`     | (only where relevant) the contrasts used.
`x`     |  if requested, the response used.
`y`     | if requested, the model matrix used.
`model`     |  if requested (the default), the model frame used.



## Seealso

[`ols.fit`](#ols.fit) , [`lm`](#lm) , [`lsfit`](#lsfit)


## Examples

```r
# tiny example of regression
y <- c(1, 3, 3, 2, 2, 1)
x <- matrix(c(1, 1,
2, 1,
3, 1,
1,-1,
2,-1,
3,-1), ncol = 2, byrow = TRUE)
f0 <- ols(y ~ x) # intercept is included by default
f0 # printing results (QR method was used)

f1 <- ols(y ~ x, method = "svd") # using SVD method instead
f1
```


