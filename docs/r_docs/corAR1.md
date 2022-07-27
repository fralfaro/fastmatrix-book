# `corAR1`

AR(1) Correlation Structure


## Description

This function is a constructor for the `corAR1` correlation matrix representing
 an autocorrelation structure of order 1.


## Usage

```r
corAR1(rho, p = 2)
```


## Arguments

Argument      |Description
------------- |----------------
`rho`     |     the value of the lag 1 autocorrelation, which must be between -1 and 1.
`p`     |     dimension of the requested correlation matrix.


## Value

Returns a $p$ by $p$ matrix.


## Examples

```r
R <- corAR1(rho = 0.8, p = 5)
```


