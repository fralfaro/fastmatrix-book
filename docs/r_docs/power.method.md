# `power.method`

Power method to approximate dominant eigenvalue and eigenvector


## Description

The power method seeks to determine the eigenvalue of maximum modulus, and a corresponding
 eigenvector.


## Usage

```r
power.method(x, only.value = FALSE, maxiter = 100, tol = 1e-8)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a symmetric matrix.
`only.value`     |     if `TRUE` , only the dominant eigenvalue is returned, otherwise both dominant eigenvalue and eigenvector are returned.
`maxiter`     |     the maximum number of iterations. Defaults to `100`
`tol`     |     a numeric tolerance.


## Value

When `only.value` is not true, as by default, the result is a list with components
  `"value"` and `"vector"` . Otherwise only the dominan eigenvalue is returned.
 The performed number of iterations to reach convergence is returned as attribute `"iterations"` .


## Seealso

[`eigen`](#eigen) for eigenvalues and eigenvectors computation.


## Examples

```r
n <- 1000
x <- .5 * diag(n) + 0.5 * matrix(1, nrow = n, ncol = n)

# dominant eigenvalue must be (n + 1) / 2
z <- power.method(x, only.value = TRUE)
```


