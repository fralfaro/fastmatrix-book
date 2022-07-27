# `matrix.norm`

Compute the norm of a rectangular matrix


## Description

Computes a matrix norm of `x` using LAPACK. The norm can be the one ( `"1"` )
 norm, the infinity ( `"inf"` ) norm, the Frobenius norm, the maximum modulus
 ( `"maximum"` ) among elements of a matrix, as determined by the value of `type`.


## Usage

```r
matrix.norm(x, type = "Frobenius")
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     a numeric matrix.
`type`     |     character string, specifying the type of matrix norm to be computed. A character indicating the type of norm desired.
| "$1$" specifies the **one** norm, (maximum absolute column sum);
| "$Inf$" specifies the **infinity** norm (maximum absolute row sum);
| "$Frobenius$" specifies the **Frobenius** norm (the Euclidean norm of x treated as if it were a vector);
| "$maximum$" specifies the **maximum** modulus of all the elements in x.

## Details

As function `norm` in package base , method of `matrix.norm` calls the LAPACK function `DLANGE`.
Note that the 1-, `Inf` - and maximum norm is faster to calculate than the Frobenius one.


## Value

The matrix norm, a non-negative number.


## Examples

```r
# a tiny example
x <- matrix(c(1, 1, 1,
1, 2, 1,
1, 3, 1,
1, 1,-1,
1, 2,-1,
1, 3,-1), ncol = 3, byrow = TRUE)
matrix.norm(x, type = "Frobenius")
matrix.norm(x, type = "1")
matrix.norm(x, type = "Inf")

# an example not that small
n <- 1000
x <- .5 * diag(n) + 0.5 * matrix(1, nrow = n, ncol = n)
matrix.norm(x, type = "Frobenius")
matrix.norm(x, type = "1")
matrix.norm(x, type = "Inf")
matrix.norm(x, type = "maximum") # equal to 1
```


