# `ridge`

Ridge regression


## Description

Fit a linear model by ridge regression, returning an object of class `"ridge"` .


## Usage

```r
ridge(formula, data, subset, lambda = 1.0, method = "GCV", ngrid = 200, tol = 1e-07,
  maxiter = 50, na.action, model = FALSE, x = FALSE, y = FALSE, contrasts = NULL, ...)
```


## Arguments

Argument      |Description
------------- |----------------
`formula`     |     an object of class `"` (or one that can be coerced to that class): a symbolic description of the model to be fitted.
`data`     |     an optional data frame, list or environment (or object coercible by [`as.data.frame`](#as.data.frame) to a data frame) containing the variables in the model. If not found in `data` , the variables are taken from  `environment(formula)` , typically the environment from which `ridge`  is called.
`subset`     |     an optional vector specifying a subset of observations to be used in the fitting process.
`na.action`     |     a function which indicates what should happen when the data contain `NA` s. The default is set by the `na.action` setting of  [`options`](#options) , and is [`na.fail`](#na.fail) if that is unset.
`lambda`     |     a scalar or vector of ridge constants. A value of 0 corresponds to ordinary least squares.
`method`     |     the method for choosing the ridge parameter lambda. If `method = "none"` , then lambda is 'fixed'. If `method = "GCV"` (the default) then the ridge parameter is chosen automatically using the generalized cross validation (GCV) criterion. For `method = "grid"` , optimal value of lambda is selected computing the GCV criterion over a grid. If `method = "MSE"` the optimal ridge parameter is selected minimizing the mean squared estimation error criterion, this is the `ORPS1`  subroutine by Lee (1987).
`ngrid`     |     number of elements in the grid used to compute the GCV criterion. Only required if `method = "grid"` and `lambda` is a scalar.
`tol`     |     tolerance for the optimization of the GCV criterion. Default is `1e-7` .
`maxiter`     |     maximum number of iterations. The default is 50.
`model, x, y`     |     logicals.  If `TRUE` the corresponding components of the fit (the model frame, the model matrix, the response) are returned.
`contrasts`     |     an optional list. See the `contrasts.arg` of  [`model.matrix.default`](#model.matrix.default) .
`list()`     |     additional arguments to be passed to the low level regression fitting functions (not implemented).


## Details

`ridge` function fits in linear ridge regression without scaling or centering
 the regressors and the response. In addition, If an intercept is present in the model, its
 coefficient is penalized.)


## Value

A list with the following components:

Value      |Description
------------- |----------------
`dims`     |  dimensions of model matrix.
`coefficients`     |   a named vector of coefficients.
`scale`     |  a named vector of coefficients.
`fitted.values`     | the fitted mean values.
`residuals`     |   the residuals, that is response minus fitted values.
`RSS`     |  the residual sum of squares.
`edf`     | the effective number of parameters.
`GCV`     | vector (if method = "grid") of GCV values.
`HKB`     | HKBestimate of the ridge constant.
`LW`     | LW estimate of the ridge constant.
`lambda`     | vector (if `method = "grid"`) of lambda values; otherwise, for methods `method = "none"`, `"GCV"` or `"MSE"`, the value of ridge parameter used by the algorithm.
`optimal`     | value of lambda with the minimum GCV (only relevant if `method = "grid"`).
`iterations`     | number of iterations performed by the algorithm (only relevant if `method = "MSE"`).
`call`     | the matched call.
`terms`     | the terms object used.
`contrasts`     | (only where relevant) the contrasts used.
`y`     | if requested, the response used.
`x`     | if requested, the model matrix used.
`model`     |  if requested, the model frame used.




## Seealso

[`lm`](#lm) , [`ols`](#ols)


## References

Golub, G.H., Heath, M., Wahba, G. (1979).
 Generalized cross-validation as a method for choosing a good ridge parameter.
  Technometrics  21 , 215-223.
 
 Hoerl, A.E., Kennard, R.W., Baldwin, K.F. (1975).
 Ridge regression: Some simulations.
  Communication in Statistics  4 , 105-123.
 
 Hoerl, A.E., Kennard, R.W. (1970).
 Ridge regression: Biased estimation of nonorthogonal problems.
  Technometrics  12 , 55-67.
 
 Lawless, J.F., Wang, P. (1976).
 A simulation study of ridge and other regression estimators.
  Communications in Statistics  5 , 307-323.
 
 Lee, T.S (1987).
 Algorithm AS 223: Optimum ridge parameter selection.
  Applied Statistics  36 , 112-118.


## Examples

```r
z <- ridge(GNP.deflator ~ ., data = longley, lambda = 4, method = "grid")
z # ridge regression on a grid over seq(0, 4, length = 200)

z <- ridge(GNP.deflator ~ ., data = longley)
z # ridge parameter selected using GCV (default)
```


