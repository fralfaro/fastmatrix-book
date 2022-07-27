# `vec`

Vectorization of a matrix


## Description

This function returns a vector obtained by stacking the columns of x


## Usage

```r
vec(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric matrix.


## Value

Let `x` be a $n$ by $m$ matrix, then `vec(x)` is a $nm$ -dimensional
 vector.


## Examples

```r
x <- matrix(rep(1:10, each = 10), ncol = 10)
x
y <- vec(x)
y
```


