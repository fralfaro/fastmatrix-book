# `moments`

Central moments


## Description

It calculates up to fourth central moments (or moments about the mean), and the
 skewness and kurtosis coefficients using an online algorithm.


## Usage

```r
moments(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric vector containing the sample observations.


## Details

The $k$ -th central moment is defined as
  
$$m_k = \frac{1}{n}\sum_{i=1}^n (x_i - \overline{x})^k.$$
 
 In particular, the second central moment is the variance of the sample. The sample
 skewness and kurtosis are defined, respectively, as
  
$$b_1 = \frac{m_3}{s^3}, \qquad b_2 = \frac{m_4}{s^4} - 3,$$
 
 where $s$ denotes de standard deviation.


## Value

A list containing `second` , `third` and `fourth` central moments,
 and `skewness` and `kurtosis` coefficients.


## Seealso

[`var`](#var) .


## References

Spicer, C.C. (1972).
 Algorithm AS 52: Calculation of power sums of deviations about the mean.
  Applied Statistics  21 , 226-227.


## Examples

```r
set.seed(149)
x <- rnorm(1000)
z <- moments(x)
z
```


