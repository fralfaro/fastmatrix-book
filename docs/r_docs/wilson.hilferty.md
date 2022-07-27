# `wilson.hilferty`

Wilson-Hilferty transformation


## Description

Returns the Wilson-Hilferty transformation of random variables with chi-squared distribution.


## Usage

```r
wilson.hilferty(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     vector or matrix of data with, say, $p$ columns.


## Details

Let $F = D^2/p$ be a random variable, where $D^2$ denotes the squared Mahalanobis
 distance defined as
  
$$D^2 = (\mathbf{x} - \mathbf{\mu})^T \mathbf{\Sigma}^{-1} (\mathbf{x} - \mathbf{\mu})$$
 
 
 Thus the Wilson-Hilferty transformation is given by
  
$$z = \frac{F^{1/3} - (1 - \frac{2}{9p})}{(\frac{2}{9p})^{1/2}}$$
 
 and $z$ is approximately distributed as a standard normal distribution. This
 is useful, for instance, in the construction of QQ-plots.


## Seealso

[`cov`](#cov) , [`Mahalanobis`](#mahalanobis)


## References

Wilson, E.B., and Hilferty, M.M. (1931).
 The distribution of chi-square.
  Proceedings of the National Academy of Sciences of the United States of America  17 , 684-688.


## Examples

```r
x <- iris[,1:4]
z <- wilson.hilferty(x)
par(pty = "s")
qqnorm(z, main = "Transformed distances Q-Q plot")
abline(c(0,1), col = "red", lwd = 2, lty = 2)
```


