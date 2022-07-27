# `dupl.info`

Compact information to construct the duplication matrix


## Description

This function provides the minimum information required to create the duplication matrix.


## Usage

```r
dupl.info(n = 1, condensed = TRUE)
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the duplication matrix.
`condensed`     |     logical. Information should be returned in compact form?


## Details

This function returns a list containing two vectors that represent an element of
 the duplication matrix and is accesed by the indexes in vectors `row` and `col` .
 This information is used by function [`dupl.prod`](#dupl.prod) to do some operations
 involving the duplication matrix without forming it. This information also can be
 obtained using function [`duplication`](#duplication)


## Value

A list containing the following elements:

Value      |Description
------------- |----------------
`row`     |  vector of indexes, each entry represents the row index of the duplication matrix. Only present if `condensed = FALSE`.
`col`     |   vector of indexes, each entry represents the column index of the duplication matrix.
`order`     |    order of the duplication matrix.



## Seealso

[`duplication`](#duplication) , [`dupl.prod`](#dupl.prod)


## Examples

```r
z <- dupl.info(n = 3, condensed = FALSE)
z # where are the ones in duplication of order 3?

D3 <- duplication(n = 3, matrix = TRUE)
D3 # only recommended if n is very small
```


