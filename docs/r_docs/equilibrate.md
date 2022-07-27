# `equilibrate`

Equilibration of a rectangular or symmetric matrix


## Description

Equilibrate a rectangular or symmetric matrix using 2-norm.


## Usage

```r
equilibrate(x, scale = TRUE)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric matrix.
`scale`     |     a logical value, `x` must be scaled to norm unity?


## Value

For `scale = TRUE` , the equilibrated matrix. The scalings and an approximation
 of the condition number, are returned as attributes `"scales"` and `"condition"` .
 If `x` is a rectangular matrix, only the columns are equilibrated.


## Examples

```r
x <- matrix(c(1, 1, 1,
1, 2, 1,
1, 3, 1,
1, 1,-1,
1, 2,-1,
1, 3,-1), ncol = 3, byrow = TRUE)
z <- equilibrate(x)
apply(z, 2, function(x) sum(x^2)) # all 1

xx <- crossprod(x)
equilibrate(xx)
```


