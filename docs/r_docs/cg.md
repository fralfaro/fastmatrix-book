# `cg`

Solve linear systems using the conjugate gradients method


## Description

Conjugate gradients (CG) method is an iterative algorithm for solving linear systems
 with positive definite coefficient matrices.


## Usage

```r
cg(a, b, maxiter = 200, tol = 1e-7)
```


## Arguments

Argument      |Description
------------- |----------------
`a`     |     a symmetric positive definite matrix containing the coefficients of the linear system.
`b`     |     a vector of right-hand sides of the linear system.
`maxiter`     |     the maximum number of iterations. Defaults to `200`
`tol`     |     tolerance level for stopping iterations.


## Value

a vector with the approximate solution, the iterations performed are returned
 as the attribute 'iterations'.


## Seealso

[`jacobi`](#jacobi) , [`seidel`](#seidel) , [`solve`](#solve)


## References

Golub, G.H., Van Loan, C.F. (1996).
  Matrix Computations , 3rd Edition.
 John Hopkins University Press.
 
 Hestenes, M.R., Stiefel, E. (1952).
 Methods of conjugate gradients for solving linear equations.
  Journal of Research of the National Bureau of Standards  49 , 409-436.


## Examples

```r
a <- matrix(c(4,3,0,3,4,-1,0,-1,4), ncol = 3)
b <- c(24,30,-24)
z <- cg(a, b)
z # converged in 3 iterations
```


