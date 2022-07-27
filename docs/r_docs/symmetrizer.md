# `symmetrizer`

Symmetrizer matrix


## Description

This function returns the symmetrizer matrix of order $n$ which transforms,
 for every $n\times n$ matrix $\mathbf{A}$ , `vec` $(\mathbf{A})$ into
  `vec` $((\mathbf{A} + \mathbf{A}^T)/2)$ .


## Usage

```r
symmetrizer(n = 1, matrix = FALSE)
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the symmetrizer matrix.
`matrix`     |     a logical indicating whether the symmetrizer matrix will be returned.


## Details

This function is a wrapper function for the function `symm.info` . This function
 provides the information required to create the symmetrizer matrix. If option `matrix = FALSE` 
 the symmetrizer matrix is stored in three vectors containing the coordinate list of
 indexes for rows, columns and the values.
 
  Warning:  `matrix = TRUE` is not recommended, unless the order `n` 
 be small. This matrix can require a huge amount of storage.


## Value

Returns an $n^2$ by $n^2$ matrix (if requested).


## Seealso

[`symm.info`](#symm.info)


## References

Abadir, K.M., Magnus, J.R. (2005).
  Matrix Algebra .
 Cambridge University Press.
 
 Magnus, J.R., Neudecker, H. (2007).
  Matrix Differential Calculus with Applications in Statistics and Econometrics , 3rd Edition.
 Wiley, New York.


## Examples

```r
z <- symmetrizer(n = 100)
object.size(z) # 319 Kb of storage

N100 <- symmetrizer(n = 100, matrix = TRUE) # time: < 2 secs
object.size(N100) # 800 Mb of storage, do not request this matrix!

# a small example
N3 <- symmetrizer(n = 3, matrix = TRUE)
a <- matrix(rep(c(2,4,6), each = 3), ncol = 3)
a
b <- 0.5 * (a + t(a))
b
v <- N3 %*% vec(a)
all(vec(b) == as.vector(v)) # vectors are equal!
```


