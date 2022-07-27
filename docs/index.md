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
* **URL**: [https://faosorios.github.io/fastmatrix/ ](https://faosorios.github.io/fastmatrix/ )
* **NeedsCompilation**: yes 
* **LazyLoad**: yes 
* **Repository**: CRAN 
* **Date/Publication**: 2022-07-05 19:00:02 UTC
* **Documentation**: [fralfaro/fastmatrix-book](https://github.com/fralfaro/fastmatrix-book) 

## Table Of Contents

1. [R topics documented](r_docs/array.mult.md)
    * [array.mult](r_docs/array.mult.md)
    * [asSymmetric ](r_docs/asSymmetric.md)
    * [bezier](r_docs/bezier.md)
    * [bracket.prod](r_docs/bracket.prod.md)
    * [cg](r_docs/cg.md)
    * [cholupdate](r_docs/cholupdate.md)
    * [circulant](r_docs/circulant.md)
    * [comm.info]( r_docs/comm.info.md)
    * [comm.prod](r_docs/comm.prod.md)
    * [commutation](r_docs/commutation.md)
    * [corAR1](r_docs/corAR1.md)
    * [corCS](r_docs/corCS.md)
    * [cov.MSSD](r_docs/cov.MSSD.md)
    * [cov.weighted](r_docs/cov.weighted.md)
    * [dupl.cross](r_docs/dupl.cross.md)
    * [dupl.info](r_docs/dupl.info.md)
    * [dupl.prod](r_docs/dupl.prod.md)
    * [duplication](r_docs/duplication.md)
    * [equilibrate](r_docs/equilibrate.md)
    * [geomean]( r_docs/geomean.md)
    * [hadamard.prod](r_docs/hadamard.prod.md)
    * [harris.test](r_docs/harris.test.md)
    * [helmert](r_docs/helmert.md)
    * [is.lower.tri](r_docs/is.lower.tri.md)
    * [jacobi](r_docs/jacobi.md)
    * [kronecker.prod](r_docs/kronecker.prod.md)
    * [kurtosis](r_docs/kurtosis.md)
    * [ldl](r_docs/ldl.md)
    * [lu-methods](r_docs/lu-methods.md)
    * [lu](r_docs/lu.md)
    * [lu2inv](r_docs/lu2inv.md)
    * [Mahalanobis](r_docs/Mahalanobis.md)
    * [matrix.inner](r_docs/matrix.inner.md)
    * [matrix.norm](r_docs/matrix.norm.md)
    * [matrix.polynomial](r_docs/matrix.polynomial.md)
    * [mediancenter]( r_docs/mediancenter.md)
    * [minkowski](r_docs/minkowski.md)
    * [moments](r_docs/moments.md)
    * [ols.fit-methods]( r_docs/ols.fit-methods.md)
    * [ols.fit](r_docs/ols.fit.md)
    * [ols]( r_docs/ols.md)
    * [power.method](r_docs/power.method.md)
    * [ridge](r_docs/ridge.md)
    * [seidel](r_docs/seidel.md)
    * [sherman.morrison]( r_docs/sherman.morrison.md)
    * [sweep.operator](r_docs/sweep.operator.md)
    * [symm.info](r_docs/symm.info.md)
    * [symm.prod]( r_docs/symm.prod.md)
    * [symmetrizer](r_docs/symmetrizer.md)
    * [vec](r_docs/vec.md)
    * [vech]( r_docs/vech.md)
    * [whitening]( r_docs/whitening.md)
    * [wilson.hilferty](r_docs/wilson.hilferty.md)
2. [References](reference.md)