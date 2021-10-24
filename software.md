# Software

\toc

## The Gridap.jl Project

@@im-100
![](/assets/gridap-banner.png)

![](/assets/fig_gridap_intro.png)
@@

### Overview
[Gridap](https://github.com/gridap/Gridap.jl) is a free and open source finite element (FE) library exclusivelly written in [Julia](https://julialang.org/). It is a general-purpose library that, rather than providing pre-bluid solvers for particular equations and methods, it makes available a feature-rich set of tools that allows users to build advanced solvers for their particular needs. With Gridap, one can easily prototype FE methods in a laptop and eventually deploy them in large HPC clusters, with virtually no modifications of the high-level user code, and without departing from Julia code (i.e., no knowledge of C/C++ or fortran required at any point of the workflow).

The library currently supports linear and nonlinear PDE systems for scalar and vector fields, single and multi-field problems, conforming and nonconforming finite element (FE) discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available [Gridap plugins](https://github.com/gridap/Gridap.jl#plugins).

> **More info:**
> - Visit the official Gridap [Github repository](https://github.com/gridap/Gridap.jl).
> - To get started, take a look at the [Gridap Tutorials](https://gridap.github.io/Tutorials/stable/).
> - Ask us anything in our [Gitter chat](https://gitter.im/Gridap-jl/community).

### My role

I have created this library in a collaboration with Prof. Santiago Badia (Monash University) in order to make more productive the research on computational methods for solving PDEs and also to simplify the access to stat-of-the-art simulation tools to application experts willing to solve challenging problems on a wide range of hardware types, from laptops to supercomputers. I am the principal software architect and maintainer of the library and I am happy to help others to use and contribute to the library.


## PartitionedArrays.jl

@@im-100
![](/assets/parrays-banner.png)
@@

### Overview

The [PartitionedArrays.jl](https://github.com/fverdugo/PartitionedArrays.jl) package provides a data-oriented parallel implementation of partitioned vectors and sparse matrices needed in a wide range of simulation codes including finite differences, finite volumes, and FE libraries. The long-term goal of this package is to provide (when combined with other Julia packages as [IterativeSolvers.jl](https://github.com/JuliaLinearAlgebra/IterativeSolvers.jl) and [AlgebraicMultigrid.jl](https://github.com/JuliaLinearAlgebra/AlgebraicMultigrid.jl)) a Julia alternative to well-known distributed algebra back ends such as [PETSc](https://petsc.org/).



PartitionedArrays.jl is planned to be the distributed linear algebra backed powering the [GridapDistributed.jl](https://github.com/gridap/GridapDistributed.jl) package, the extension of Gridap.jl for large-scale parallel distributed memory computations. In collaboration with my colleagues Prof. Santiago Badia and Alberto F. Martín, we plan to implement scalable multi-level domain decomposition solvers to efficiently solve the systems of linear algebraic equations arising from the discretization of complex PDE-based models.
