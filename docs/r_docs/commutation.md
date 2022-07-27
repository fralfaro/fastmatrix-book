# `commutation`

Commutation matrix


## Description

This function returns the commutation matrix of order $mn$ which transforms,
 for an $m\times n$ matrix $\mathbf{A}$ , `vec` $(\mathbf{A})$ to
  `vec` $(\mathbf{A}^T)$ .


## Usage

```r
commutation(m = 1, n = m, matrix = FALSE, condensed = FALSE)
```


## Arguments

Argument      |Description
------------- |----------------
`m`     |     a positive integer row dimension.
`n`     |     a positive integer column dimension.
`matrix`     |     a logical indicating whether the commutation matrix will be returned.
`condensed`     |     logical. Information should be returned in compact form?


## Details

This function is a wrapper function for the function `comm.info` . This function
 provides the minimum information required to create the commutation matrix. If option
  `matrix = FALSE` the commutation matrix is stored in two vectors containing the
 coordinate list of indexes for rows and columns. Option `condensed = TRUE` only
 returns vector of indexes for the rows of commutation matrix.
 
  Warning:  `matrix = TRUE` is not recommended, unless the order `m` 
  and  `n` be small. This matrix can require a huge amount of storage.


## Value

Returns an $mn$ by $mn$ matrix (if requested).


## Seealso

[`comm.info`](#comm.info)


## References

Magnus, J.R., Neudecker, H. (1979).
 The commutation matrix: some properties and applications.
  The Annals of Statistics  7 , 381-394.
 
 Magnus, J.R., Neudecker, H. (2007).
  Matrix Differential Calculus with Applications in Statistics and Econometrics , 3rd Edition.
 Wiley, New York.


## Examples

```r
z <- commutation(m = 100, condensed = TRUE)
object.size(z) # 40.6 Kb of storage

z <- commutation(m = 100, condensed = FALSE)
object.size(z) # 80.7 Kb of storage

K100 <- commutation(m = 100, matrix = TRUE) # time: < 2 secs
object.size(K100) # 400 Mb of storage, do not request this matrix!

# a small example
K32 <- commutation(m = 3, n = 2, matrix = TRUE)
a <- matrix(1:6, ncol = 2)
v <- K32 %*% vec(a)
all(vec(t(a)) == as.vector(v)) # vectors are equal!
```


