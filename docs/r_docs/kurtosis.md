# `kurtosis`

Mardia's multivariate skewness and kurtosis coefficients


## Description

Functions to compute measures of multivariate skewness $(b_{1p})$ and kurtosis
  $(b_{2p})$ proposed by Mardia (1970),
  
$$b_{1p} = \frac{1}{n^2}\sum\limits_{i=1}^n\sum\limits_{j=1}^n ((\mathbf{x}_i -\overline{\mathbf{x}})^T\mathbf{S}^{-1}(\mathbf{x}_j - \overline{\mathbf{x}}))^3,$$
 
 and
  
$$b_{2p} = \frac{1}{n}\sum\limits_{i=1}^n ((\mathbf{x}_i - \overline{\mathbf{x}})^T\mathbf{S}^{-1}(\mathbf{x}_j - \overline{\mathbf{x}}))^2.$$


## Usage

```r
kurtosis(x)
skewness(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     matrix of data with, say, $p$ columns.


## References

Mardia, K.V. (1970).
 Measures of multivariate skewness and kurtosis with applications.
  Biometrika  57 , 519-530.
 
 Mardia, K.V., Zemroch, P.J. (1975).
 Algorithm AS 84: Measures of multivariate skewness and kurtosis.
  Applied Statistics  24 , 262-265.


## Examples

```r
setosa <- iris[1:50,1:4]
kurtosis(setosa)
skewness(setosa)
```


