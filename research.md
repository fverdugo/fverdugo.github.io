# Research

\toc

## Post-doctoral research at CIMNE (2016-present)

### Objectives

This part of my research career starts in January 2016 and it extends up
to the present. I joined CIMNE as a post-doc researcher in 2016 and I
was promoted to Assistant Research Professor in view of my academic
results in 2019. In CIMNE, I am pursuing a research agenda, whose main
objectives are:

> -   Developing novel parallel finite element (FE) techniques for the simulation of complex problems in science an engineering using modern supercomputers
> -   Helping application experts to adopt these novel computational techniques to solve real-world problems
> -   Implementing these computer tools in open-source software projects in order to foster their adoption by the scientific community

### Research lines

In order to address these global objectives, my current research agenda
includes the following main research lines:

-   Simplify mesh generation in large-scale parallel computations via
    embedded FE methods

-   Software design of scientific applications and open-source codes
    (the Gridap.jl project)

#### Simplify mesh generation in large-scale parallel computations via embedded FE methods

##### Research line description

Mesh generation is known to be one of the main bottlenecks in real-world
industrial FE simulations. Conventional FE methods require so-called
body-fitted meshes, i.e., grids that conform to the geometrical
boundaries of the computational domain (see Figure 1). Constructing such grids is not
obvious for complex geometries. It often requires skilled humans, and it
is time consuming as mesh generation is estimated to be 80% of total
simulation time in industrial applications [^cottrell_2009]. The goal of
so-called embedded FE methods [^burman_2015] (also known as unfitted or
immersed methods) is to change this situation by allowing one to work on
background Cartesian meshes that do not necessarily conform to the
geometrical boundaries (see Figure 1). Generating such unfitted Cartesian
grids is much simpler and more efficient that constructing body fitted
meshes, specially in large parallel computations. One can use highly
scalable octree-based mesh generators like the p4est package, which has
shown excellent scaling properties up to thousands of hundreds of CPU
cores.

@@im-100
![](/assets/fig1.png)
*Figure 1: Body-fitted vs. unfitted meshes*
@@

However, embedded methods have known drawbacks. One of the most
notorious, still an open question today, is the so-called *small cut
cell problem*. Some cells of the unfitted mesh can be intersected by a
very small part of the domain, which can lead to arbitrarily large
condition numbers in the underlying discrete FE operators. This is a
major issue, when dealing with large-scale simulations that require
Krylov sub-space iterative linear solvers because they are very
sensitive to the conditioning and spectral properties of the underlying
operators. The result is that embedded methods are mainly used in small
to medium problems, which can be handled with direct linear solvers
(i.e., Gaussian elimination) instead of iterative procedures. One of my
main research goals at CIMNE is to address the conditioning problems of
embedded methods in order to allow their usage in large-scale real-world
computations.
