# `lu`

The LU factorization of a square matrix


## Description

`lu` computes the LU factorization of a matrix.


## Usage

```r
lu(x)
list(list("lu"), list("default"))(x)
list(list("solve"), list("lu"))(a, b, list())
is.lu(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a square numeric matrix whose LU factorization is to be computed.
`a`     |     an LU factorization of a square matrix.
`b`     |     a vector or matrix of right-hand sides of equations.
`list()`     |     further arguments passed to or from other methods


## Details

The LU factorization plays an important role in many numerical procedures. In
 particular it is the basic method to solve the equation $\mathbf{Ax} = \mathbf{b}$ 
 for given matrix $\mathbf{A}$ , and vector $\mathbf{b}$ .
 
  `solve.lu` is the method for [`solve`](#solve) for `lu` objects.
 
  `is.lu` returns `TRUE` if `x` is a [`list`](#list) 
 and [`inherits`](#inherits) from `"lu"` . % not more checks, for speed. 
 
 Unsuccessful results from the underlying LAPACK code will result in an
 error giving a positive error code: these can only be interpreted by
 detailed study of the `Fortran` code.


## Value

The LU factorization of the matrix as computed by LAPACK. The components in
 the returned value correspond directly to the values returned by `DGETRF` .
  


Value      |Description
------------- |----------------
`lu`     |  a matrix with the same dimensions as $x$. The upper triangle contains the $\mathbf{U}$ of the decomposition and the strict lower triangle contains information on the $\mathbf{L}$ of the factorization. 
`pivot`     |  information on the pivoting strategy used during the factorization.




## Seealso

[`extractL`](#extractl) , [`extractU`](#extractu) , [`constructX`](#constructx) for
 reconstruction of the matrices,
  [`lu2inv`](#lu2inv)


## Note

To compute the determinant of a matrix (do you really need it?),
 the LU factorization is much more efficient than using eigenvalues
 ( [`eigen`](#eigen) ).  See [`det`](#det) .
 
 LAPACK uses column pivoting and does not attempt to detect rank-deficient matrices.


## References

Anderson. E., Bai, Z., Bischof, C., Blackford, S., Demmel, J., Dongarra, J.,
 Du Croz, J., Greenbaum, A., Hammarling, S., McKenney, A. Sorensen, D. (1999).
  LAPACK Users' Guide , 3rd Edition. SIAM.
 (Available at [http://www.netlib.org/lapack/lug/lapack_lug.html](http://www.netlib.org/lapack/lug/lapack_lug.html) ).
 
 Golub, G.H., Van Loan, C.F. (1996).
  Matrix Computations , 3rd Edition.
 John Hopkins University Press.


## Examples

```r
a <- matrix(c(3,2,6,17,4,18,10,-2,-12), ncol = 3)
z <- lu(a)
z # information of LU factorization

# computing det(a)
prod(diag(z$lu)) # product of diagonal elements of U

# solve linear equations
b <- matrix(1:6, ncol = 2)
solve(z, b)
```


