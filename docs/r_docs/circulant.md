# `circulant`

Form a symmetric circulant matrix


## Description

Forms a symmetric circulant matrix using a backwards shift of its first column


## Usage

```r
circulant(x)
```


## Arguments

Argument      |Description
------------- |----------------
`x`     |     the first column to form the circulant matrix.


## Value

A symmetric circulant matrix.


## Examples

```r
x <- c(2,3,5,7,11,13)
circulant(x)
```


