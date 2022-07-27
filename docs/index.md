# Welcome to fastmatrix’s documentation!

## Description

Small set of functions to fast computation of some matrices and operations useful in 
statistics and econometrics. Currently, there are functions for efficient computation of duplication,
commutation and symmetrizer matrices with minimal storage requirements. Some commonly used matrix decompositions (LU and LDL),
basic matrix operations (for instance, Hadamard, Kronecker products and the Sherman-Morrison formula) and iterative solvers for
linear systems are also available.

In addition, the package includes a number of common statistical procedures such as the sweep operator, 
weighted mean and covariance matrix using an online algorithm, linear regression (using Cholesky, QR, SVD, sweep operator and conjugate gradients methods),
ridge regression (with optimal selection of the ridge parameter considering the GCV procedure), functions to compute the multivariate skewness, 
kurtosis, Mahalanobis distance (checking the positive defineteness) and the Wilson-Hilferty transformation of chi squared variables.

## About package

* **Type**: Package
* **Title**: Fast Computation of some Matrices Useful in Statistics 
* **Version**: 0.4-12 Date 2022-07-05
* **Author**:
     * [Felipe Osorio](http://fosorios.mat.utfsm.cl/) [aut, cre] (<https://orcid.org/0000-0002-4675-5201>), 
     * [Alonso Ogueda](https://aoguedao.github.io/) [aut] 
* **Maintainer**: Felipe Osorio <felipe.osorios@usm.cl>
* **Depends**: R(>= 3.5.0)
* **License**: GPL-3 
* **URL**: https://faosorios.github.io/fastmatrix/ 
* **NeedsCompilation**: yes 
* **LazyLoad**: yes 
* **Repository**: CRAN 
* **Date/Publication**: 2022-07-05 19:00:02 UTC