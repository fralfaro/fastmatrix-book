# `Mahalanobis`

Mahalanobis distance


## Description

Returns the squared Mahalanobis distance of all rows in `x` and the
 vector $\mathbf{\mu}$ = `center` with respect to $\mathbf{\Sigma}$ = `cov` .
 This is (for vector `x` ) defined as
  
$$D^2 = (\mathbf{x} - \mathbf{\mu})^T \mathbf{\Sigma}^{-1} (\mathbf{x} - \mathbf{\mu})$$


## Usage

```r
Mahalanobis(x, center, cov, inverted = FALSE)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     vector or matrix of data. As usual, rows are observations and columns are variables.
`center`     |     mean vector of the distribution.
`cov`     |     covariance matrix ( $p \times p$ ) of the distribution, must be positive definite.
`inverted`     |     logical. If `TRUE` , `cov` is supposed to contain the  inverse of the covariance matrix.


## Details

Unlike function `mahalanobis` , the covariance matrix is factorized using the
 Cholesky decomposition, which allows to assess if `cov` is positive definite.
 Unsuccessful results from the underlying LAPACK code will result in an error message.


## Seealso

[`cov`](#cov) , [`mahalanobis`](#mahalanobis)


## Examples

```r
x <- cbind(1:6, 1:3)
xbar <- colMeans(x)
S <- matrix(c(1,4,4,1), ncol = 2) # is negative definite
D2 <- mahalanobis(x, center = xbar, S)
all(D2 >= 0) # several distances are negative

## next command produces the following error:
## Covariance matrix is possibly not positive-definite
D2 <- Mahalanobis(x, center = xbar, S)
```


