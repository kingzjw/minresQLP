# minresQLP
c++ version based on the eigen

 MINRES-QLP: Sparse Symmetric Equations or Least-Squares Problems

    AUTHORS: S.-C. T. Choi, M. A. Saunders.
    CONTRIBUTORS: C. C. Paige.
    CONTENTS: Implementation of a conjugate-gradient type method for solving sparse linear equations: \begin{align*} \text{Solve } & Ax=b \\ \text{or } & (A - sI)x = b \\ \text{or minimize } & \|Ax-b\|^2 \\ \text{or minimize } & \|(A - sI)x-b\|^2 \end{align*} The matrix \(A - sI\) must be symmetric or Hermitian, but it may be definite or indefinite, singular or nonsingular. The scalar \(s\) is a shifting parameter – it may be any real number. The method is based on Lanczos tridiagonalization. You may provide a preconditioner, but it must be symmetric positive definite.

    If \((A - sI)\) is nonsingular, use SYMMLQ or MINRES.

    If \((A - sI)x = b\) is singular and compatible, use MINRES or MINRES-QLP (this routine).

    If \((A - sI)x = b\) is singular and incompatible, use MINRES-QLP (this routine).

    If \(A\) is unsymmetric or rectangular, use LSQR or LSMR.


    Special application: To find a null vector of a singular symmetric or Hermitian matrix \(A\), apply MINRES-QLP to the system \( \min \|Ax - b\| \) with any nonzero vector \(b\) (e.g. a random \(b\)). At a minimizer, the residual vector \(r = b - Ax \) will satisfy \( Ar=0 \). See [1] for examples.

    If an eigenvalue \( \lambda \) is known, the associated eigenvector may be obtained by applying MINRES-QLP to \((A - \lambda I)x = b\). The residual \(r = b - (A - \lambda I)x \) is an eigenvector because \( (A - \lambda I)r = 0 \).

    If \( \lambda \) is not exact, use a loose stopping tolerance and Rayleigh-quotient iteration to refine \( \lambda \).

    REFERENCES:
    [1] S.-C. T. Choi (2006). Iterative Methods for Singular Linear Equations and Least-Squares Problems, PhD thesis, ICME, Stanford University.

    [2] S.-C. T. Choi, C. C. Paige and M. A. Saunders. MINRES-QLP: A Krylov subspace method for indefinite or singular symmetric systems, SIAM J. Sci. Comput. 33:4, 1810-1836, published electronically Aug 4, 2011.

    [3] S.-C. T. Choi and M. A. Saunders. Algorithm 937: MINRES-QLP for symmetric and Hermitian linear equations and least-squares problems, ACM Trans. Math. Softw. 40:2, Article 16 (Feb 2014), 12 pp. (pdf)
    RELEASE:

    02 May 2010: MATLAB implementation

    12 Sep 2013: f90 implementations (real and complex) version 27

    07 Jun 2018: Python implementation available from Yang Liu et al. 
