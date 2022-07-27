# `lu-methods`

Reconstruct the L, U, or X Matrices from an LU object


## Description

Returns the original matrix from which the object was constructed or
 the components of the factorization.


## Usage

```r
constructX(x)
extractL(x)
extractU(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     object representing an LU factorization. This will typically have come from a previous call to [`lu`](#lu) .


## Value

`constructX` returns $\mathbf{X}$ , the original matrix from which the `lu` 
 object was constructed (because of the pivoting the $\mathbf{X}$ matrix is not exactly
 the product between $\mathbf{L}$ and $\mathbf{U}$ ).
 
  `extractL` returns $\mathbf{L}$ . This may be pivoted.
 
  `extractU` returns $\mathbf{U}$ .


## Seealso

[`lu`](#lu) .


## Examples

```r
a <- matrix(c(10,-3,5,-7,2,-1,0,6,5), ncol = 3)
z <- lu(a)
L <- extractL(z)
L
U <- extractU(z)
U
X <- constructX(z)
all(a == X)
```


