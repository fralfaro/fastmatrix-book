# `duplication`

Duplication matrix


## Description

This function returns the duplication matrix of order $n$ which transforms,
 for a symmetric matrix $\mathbf{A}$ , `vech` $(\mathbf{A})$ into `vec` $(\mathbf{A})$ .


## Usage

```r
duplication(n = 1, matrix = FALSE, condensed = FALSE)
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the duplication matrix.
`matrix`     |     a logical indicating whether the duplication matrix will be returned.
`condensed`     |     logical. Information should be returned in compact form?.


## Details

This function is a wrapper function for the function `dupl.info` . This function
 provides the minimum information required to create the duplication matrix. If option
  `matrix = FALSE` the duplication matrix is stored in two vectors containing the
 coordinate list of indexes for rows and columns. Option `condensed = TRUE` only
 returns vector of indexes for the columns of duplication matrix.
 
  Warning:  `matrix = TRUE` is not recommended, unless the order `n` 
 be small. This matrix can require a huge amount of storage.


## Value

Returns an $n^2$ by $n(n + 1)/2$ matrix (if requested).


## Seealso

[`dupl.info`](#dupl.info)


## References

Magnus, J.R., Neudecker, H. (1980).
 The elimination matrix, some lemmas and applications.
  SIAM Journal on Algebraic Discrete Methods  1 , 422-449.
 
 Magnus, J.R., Neudecker, H. (2007).
  Matrix Differential Calculus with Applications in Statistics and Econometrics , 3rd Edition.
 Wiley, New York.


## Examples

```r
z <- duplication(n = 100, condensed = TRUE)
object.size(z) # 40.5 Kb of storage

z <- duplication(n = 100, condensed = FALSE)
object.size(z) # 80.6 Kb of storage

D100 <- duplication(n = 100, matrix = TRUE)
object.size(D100) # 202 Mb of storage, do not request this matrix!

# a small example
D3 <- duplication(n = 3, matrix = TRUE)
a <- matrix(c( 1, 2, 3,
2, 3, 4,
3, 4, 5), nrow = 3)
upper <- vech(a)
v <- D3 %*% upper
all(vec(a) == as.vector(v)) # vectors are equal!
```


