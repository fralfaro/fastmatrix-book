# `symm.info`

Compact information to construct the symmetrizer matrix


## Description

This function provides the information required to create the symmetrizer matrix.


## Usage

```r
symm.info(n = 1)
```


## Arguments

Argument      |Description
------------- |----------------
`n`     |     order of the symmetrizer matrix.


## Details

This function returns a list containing vectors that represent an element of the
 symmetrizer matrix and is accesed by the indexes in vectors `row` , `col` 
 and values contained in `val` . This information is used by function [`symm.prod`](#symm.prod) 
 to do some operations involving the symmetrizer matrix without forming it. This
 information also can be obtained using function [`symmetrizer`](#symmetrizer) .


## Value

A list containing the following elements:
  

Value      |Description
------------- |----------------
`row`     |   vector of indexes, each entry represents the row index of the symmetrizer matrix.
`col`     |   vector of indexes, each entry represents the column index of the symmetrizer matrix.
`val`     |   vector of values, each entry represents the value of the symmetrizer matrix at element given by row and col indexes.
`order`     |    order of the symmetrizer matrix.

 


## Seealso

[`symmetrizer`](#symmetrizer) , [`symm.prod`](#symm.prod)


## Examples

```r
z <- symm.info(n = 3)
z # elements in symmetrizer matrix of order 3

N3 <- symmetrizer(n = 3, matrix = TRUE)
N3 # only recommended if n is very small
```


