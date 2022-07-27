# `mediancenter`

Mediancenter


## Description

It calculates the mediancenter (or geometric median) of multivariate data.


## Usage

```r
mediancenter(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a matrix or data frame. As usual, rows are observations and columns are variables.


## Details

The mediancenter for a sample of multivariate observations is computed using a
 steepest descend method combined with bisection. The mediancenter invariant to
 rotations of axes and is useful as a multivariate generalization of the median
 of univariate sample.


## Value

A list containing the following named components:
  
Value      |Description
------------- |----------------
`median`     |  an estimate for the mediancenter of the data.
`iter`     |   the number of iterations performed, it is negative if a degenerate solution is found.


## Seealso

[`cov.wt`](#cov.wt) , [`median`](#median) .


## References

Gower, J.C. (1974).
 Algorithm AS 78: The mediancentre.
  Applied Statistics  23 , 466-470.


## Examples

```r
x <- cbind(1:10, c(1:3, 8:5, 8:10))
z <- mediancenter(x)$median # degenerate solution
xbar <- colMeans(x)
plot(x, xlab = "", ylab = "")
points(x = xbar[1], y = xbar[2], pch = 16, col = "red")
points(x = z[1], y = z[2], pch = 3, col = "blue", lwd = 2)
```


