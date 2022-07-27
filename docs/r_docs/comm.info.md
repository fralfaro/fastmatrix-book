# `comm.info`

Compact information to construct the commutation matrix


## Description

This function provides the minimum information required to create the commutation matrix.
 
 The commutation matrix is a square matrix of order $mn$ that, for an $m\times n$ 
 matrix $\mathbf{A}$ , transform `vec` $(\mathbf{A}$ ) to `vec` $(\mathbf{A}^T)$ .


## Usage

```r
comm.info(m = 1, n = m, condensed = TRUE)
```


## Arguments

Argument      |Description
------------- |----------------
`m`     |     a positive integer row dimension.
`n`     |     a positive integer column dimension.
`condensed`     |     logical. Information should be returned in compact form?


## Details

This function returns a list containing two vectors that represent an element of
 the commutation matrix and is accesed by the indexes in vectors `row` and `col` .
 This information is used by function [`comm.prod`](#comm.prod) to do some operations
 involving the commutation matrix without forming it. This information also can be
 obtained using function [`commutation`](#commutation) .


## Value

A list containing the following elements:
  

Value      |Description
------------- |----------------
`row`     |     vector of indexes, each entry represents the row index of the commutation matrix.
`col`     |    vector of indexes, each entry represents the column index of the commutation matrix. Only present if `condensed = FALSE`.
`m`     |     positive integer, row dimension.
`n`     |     positive integer, column dimension.



## Seealso

[`commutation`](#commutation) , [`comm.prod`](#comm.prod)


## References

Magnus, J.R., Neudecker, H. (1979).
 The commutation matrix: some properties and applications.
  The Annals of Statistics  7 , 381-394.


## Examples

```r
z <- comm.info(m = 3, n = 2, condensed = FALSE)
z # where are the ones in commutation matrix of order '3,2'?

K32 <- commutation(m = 3, n = 2, matrix = TRUE)
K32 # only recommended if m and n are very small
```


