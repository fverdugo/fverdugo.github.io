# Software

\toc

## Projects I created

### The Gridap.jl Project

@@im-100
![](/assets/gridap-banner.png)

![](/assets/fig_gridap_intro.png)
@@

#### Overview
[Gridap](https://github.com/gridap/Gridap.jl) is a free and open source finite element (FE) library exclusivelly written in [Julia](https://julialang.org/). It is a general-purpose library that, rather than providing pre-bluid solvers for particular equations and methods, it makes available a feature-rich set of tools that allows users to build advanced solvers for their particular needs. With Gridap, one can easily prototype FE methods in a laptop and eventually deploy them in large HPC clusters, with virtually no modifications of the high-level user code, and without departing from Julia code (i.e., no knowledge of C/C++ or fortran required at any point of the workflow).

The library currently supports linear and nonlinear PDE systems for scalar and vector fields, single and multi-field problems, conforming and nonconforming finite element (FE) discretizations, on structured and unstructured meshes of simplices and n-cubes. Gridap is extensible and modular. One can implement new FE spaces, new reference elements, use external mesh generators, linear solvers, post-processing tools, etc. See, e.g., the list of available [Gridap plugins](https://github.com/gridap/Gridap.jl#plugins).

> **More info:**
> - Visit the official Gridap [Github repository](https://github.com/gridap/Gridap.jl).
> - To get started, take a look at the [Gridap Tutorials](https://gridap.github.io/Tutorials/stable/).
> - Ask us anything in our [Gitter chat](https://gitter.im/Gridap-jl/community).

#### My role

I have created this library in a collaboration with Prof. Santiago Badia (Monash University) in order to make more productive the research on computational methods for solving PDEs and also to simplify the access to stat-of-the-art simulation tools to application experts willing to solve challenging problems on a wide range of hardware types, from laptops to supercomputers. I am the principal software architect and maintainer of the library and I am happy to help others to use and contribute to the library. See related research [here](/research/#rl2_software_design_of_scientific_applications_and_open-source_projects).


### PartitionedArrays.jl

@@im-100
![](/assets/parrays-banner.png)
@@

#### Overview

The [PartitionedArrays.jl](https://github.com/fverdugo/PartitionedArrays.jl) package provides a data-oriented parallel implementation of partitioned vectors and sparse matrices needed in a wide range of simulation codes including finite differences, finite volumes, and FE libraries. The long-term goal of this package is to provide (when combined with other Julia packages as [IterativeSolvers.jl](https://github.com/JuliaLinearAlgebra/IterativeSolvers.jl) and [AlgebraicMultigrid.jl](https://github.com/JuliaLinearAlgebra/AlgebraicMultigrid.jl)) a Julia alternative to well-known distributed algebra back ends such as [PETSc](https://petsc.org/).

PartitionedArrays.jl is the distributed linear algebra backed powering the [GridapDistributed.jl](https://github.com/gridap/GridapDistributed.jl) package, the extension of Gridap for large-scale parallel distributed memory computations. In collaboration with my colleagues Prof. Santiago Badia and Alberto F. Martín, we plan to implement scalable multi-level domain decomposition solvers within this framework to efficiently solve in parallel the systems of linear algebraic equations arising from the discretization of complex PDE-based models.

> **More info:**
> - Visit the official PartitionedArrays.jl [Github repository](https://github.com/fverdugo/PartitionedArrays.jl).

#### My role

I am the creator and maintainer of this library. I am ready to help programmers to implement new
linear solvers and preconditioners within this framework.

## Projects I contributed to

### FEMPAR

@@im-100
[![](/assets/fempar.jpg)](https://github.com/fempar/fempar)
@@

#### Overview

[FEMPAR](https://github.com/fempar/fempar) is a object-oriented fortran-based library for the simulation of problems governed by partial differential equations (PDEs). It provides a set of state-of-the-art numerical discretizations, including finite element methods, discontinuous Galerkin methods, XFEM, and spline-based functional spaces. The library was originally designed to efficiently exploit distributed-memory supercomputers and easily handle multiphysics problems. It also provides a set of highly scalable numerical linear algebra solvers based on multilevel domain decomposition for the systems of equations that arise from PDE discretizations. Some applications of FEMPAR include the simulation of metal additive manufacturing processes, superconductor devices, breeding blankets in fusion reactors, and nuclear waste repositories. FEMPAR was able to exploit the full scale of the largest supercomputers in Europe for which it was included in the [high-Q club](https://www.fz-juelich.de/ias/jsc/EN/Expertise/High-Q-Club/FEMPAR/_node.html) of the most scalable scientific European codes.

#### My contribution

During the first years as post-doc at CIMNE, I have lead the implementation of embedded finite element methods within FEMPAR for both serial and parallel distributed-memory implementations based on MPI. This has served as the main infrastructure for developing new embedded finite element methods in my research team and was eventually used in the FEMPAR-AM module for additive manufacturing simulations. See related research [here](/research/#rl1_simplify_mesh_generation_in_large-scale_parallel_computations_via_embedded_fe_methods).

### BACI

@@im-100
[![](/assets/baci_wing.png)](https://www.epc.ed.tum.de/en/lnm/home-en/)
@@

#### Overview

[BACI](https://baci.pages.gitlab.lrz.de/website/) (“Bavarian Advanced Computational Initiative”) is a parallel multi-physics research code to analyze and solve a plethora of physical problems by means of computational mechanics. BACI provides simulation capabilities for a variety of physical models, including

- single fields such as solids and structures, fluids, scalar transport, or porous media
- multiphysics coupling and interactions between several fields
- advanced analysis capabilities such as uncertainty quantification, parameter estimation, or optimization

Large parts of BACI are based on finite element methods (FEM, CutFEM), but alternative discretization methods such as discontinuous Galerkin methods (DG), particle methods and mesh-free methods have also been successfully integrated. BACI leverages the Trilinos project for sparse linear algebra, nonlinear solvers, and linear solvers and preconditioners. The research software is fully implemented in C++ using an object-oriented and modular software design. BACI is parallelized with MPI for distributed memory hardware architectures.

#### My contribution

During my post-doc stay at TUM, I have developed a general computational framework based on monolithic AMG techniques for the solution of strongly coupled problems. It allows users to easily build complex AMG preconditioners taylored to specific needs from input files in xml format. This framework has been used at TUM since then, and it
has been considered by several papers in top international journals
with a wide range of
applications including simulation of vascular tumor growth and
simulations of lithium ion cells. See related research [here](/research/#post-doctoral_research_at_tum_2013-2015).

### EUROPLEXUS

@@im-100
[![](/assets/europlexus.png)](https://ec.europa.eu/jrc/en/scientific-tool/europlexus-simulation-software)
@@

#### Overview

[EUROPLEXUS](https://ec.europa.eu/jrc/en/scientific-tool/europlexus-simulation-software) is a computer code for the simulation of fast transient fluid-structure interaction problems. It is co-owned by JRC and CEA and is developed jointly by the co-owners plus the members of a Consortium (currently including EDF, ONERA and Safran), and a number of Universities. Its application field ranges from blast analysis to assess strategic building vulnerability, to safety of power plants, chemical plants, transportation (blast in tunnels, crash), maritime (under-water explosions and impacts), design of the protection of public spaces and critical infrastructure against terrorist attacks. The code is also used these days to simulate the behaviour of vehicles ramming attacks and the possible protection solutions.

#### My contribution

As PhD student, I collaborated with Dr. Folco Casadei to implement adaptive mesh refinement and error assessment capabilities into the code.


