# `jacobi`

Solve linear systems using the Jacobi method


## Description

Jacobi method is an iterative algorithm for solving a system of linear equations.


## Usage

```r
jacobi(a, b, start, maxiter = 200, tol = 1e-7)
```


## Arguments

Argument      |Description
------------- |----------------
`a`     |     a square numeric matrix containing the coefficients of the linear system.
`b`     |     a vector of right-hand sides of the linear system.
`start`     |     a vector for initial starting point.
`maxiter`     |     the maximum number of iterations. Defaults to `200`
`tol`     |     tolerance level for stopping iterations.


## Details

Let $\mathbf{D}$ , $\mathbf{L}$ , and $\mathbf{U}$ denote the diagonal, lower
 triangular and upper triangular parts of a matrix $\mathbf{A}$ . Jacobi's method
 solve the equation $\mathbf{Ax} = \mathbf{b}$ , iteratively by rewriting $\mathbf{Dx}$$  + (\mathbf{L} + \mathbf{U})\mathbf{x} = \mathbf{b}$ . Assuming that $\mathbf{D}$ is nonsingular
 leads to the iteration formula
  
$$\mathbf{x}^{(k+1)} = -\mathbf{D}^{-1}(\mathbf{L} + \mathbf{U})\mathbf{x}^{(k)} + \mathbf{D}^{-1}\mathbf{b}$$


## Value

a vector with the approximate solution, the iterations performed are returned
 as the attribute 'iterations'.


## Seealso

[`seidel`](#seidel)


## References

Golub, G.H., Van Loan, C.F. (1996).
  Matrix Computations , 3rd Edition.
 John Hopkins University Press.


## Examples

```r
a <- matrix(c(5,-3,2,-2,9,-1,3,1,-7), ncol = 3)
b <- c(-1,2,3)
start <- c(1,1,1)
z <- jacobi(a, b, start)
z # converged in 15 iterations
```


