# `bezier`

Computation of Bezier curve


## Description

Computes the Bezier curve based on $n+1$ control points using the De Casteljau's method.


## Usage

```r
bezier(x, y, ngrid = 200)
```


## Arguments

Argument      |Description
------------- |----------------
`x, y`     |     vector giving the coordinates of the control points. Missing values are deleted.
`ngrid`     |     number of elements in the grid used to compute the smoother.


## Details

Given $\mathbf{p}_0,\mathbf{p}_1,\dots,\mathbf{p}_n$ control points the Bezier curve is given by
  $B(t)$ defined as
  
$$B(t) = \left({\begin{array}{c}x(t) \\y(t)\end{array}}\right) = \sum\limits_{k=0}^n {n \choose k} t^k (1 - t)^k\mathbf{p}_k$$
 
 where $t\in[0,1]$ . To evaluate the Bezier curve the De Casteljau's method is used.


## Value

A list containing `xgrid` and `ygrid` elements used to plot the Bezier curve.


## Examples

```r
# a tiny example
x <- c(1.0, 0.25, 1.25, 2.5, 4.00, 5.0)
y <- c(0.5, 2.00, 3.75, 4.0, 3.25, 1.0)
plot(x, y, type = "o")
z <- bezier(x, y, ngrid = 50)
lines(z$xgrid, z$ygrid, lwd = 2, lty = 2, col = "red")

# other simple example
x <- c(4,6,4,5,6,7)
y <- 1:6
plot(x, y, type = "o")
z <- bezier(x, y, ngrid = 50)
lines(z$xgrid, z$ygrid, lwd = 2, lty = 2, col = "red")
```


