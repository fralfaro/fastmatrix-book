# `whitening`

Whitening transformation


## Description

Applies the whitening transformation to a data matrix based on the Cholesky decomposition
 of the empirical covariance matrix.


## Usage

```r
whitening(x, Scatter = NULL)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     vector or matrix of data with, say, $p$ columns.
`Scatter`     |     covariance (or scatter) matrix ( $p \times p$ ) of the distribution, must be positive definite. If `NULL` , the covariance matrix is estimated from the data.


## Value

Returns the whitened data matrix $\mathbf{Z} = \mathbf{X W}^T$ , where
  
$$\mathbf{W}^T\mathbf{W} = \mathbf{S}^{-1},$$
 
 with $\mathbf{S}$ the empirical covariance matrix.


## References

Kessy, A., Lewin, A., Strimmer, K. (2018).
 Optimal whitening and decorrelation.
  The American Statistician  72 , 309-314.


## Examples

```r
x <- iris[,1:4]
species <- iris[,5]
pairs(x, col = species) # plot of Iris

# whitened data
z <- whitening(x)
pairs(z, col = species) # plot of
```


