# `corCS`

Compound Symmetry Correlation Structure


## Description

This function is a constructor for the `corCS` correlation matrix representing
 a compound symmetry structure corresponding to uniform correlation.


## Usage

```r
corCS(rho, p = 2)
```


## Arguments

Argument      |Description
------------- |----------------
`rho`     |     the value of the correlation between any two correlated observations, which must be between -1 and 1.
`p`     |     dimension of the requested correlation matrix.


## Value

Returns a $p$ by $p$ matrix.


## Examples

```r
R <- corCS(rho = 0.8, p = 5)
```


