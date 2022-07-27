# `lu2inv`

Inverse from LU factorization


## Description

Invert a square matrix from its LU factorization.


## Usage

```r
lu2inv(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     object representing an LU factorization. This will typically have come from a previous call to [`lu`](#lu) .


## Value

The inverse of the matrix whose LU factorization was given.
 
 Unsuccessful results from the underlying LAPACK code will result in an
 error giving a positive error code: these can only be interpreted by
 detailed study of the `Fortran` code.


## Seealso

[`lu`](#lu) , [`solve`](#solve) .


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
a %*% lu2inv(z)
```


