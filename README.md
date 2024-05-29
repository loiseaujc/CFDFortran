# CFD Fortran

Inspired by Lorena Barba's [**CFD Python**](https://github.com/barbagroup/CFDPython) (also known as the **12 steps to Navier-Stokes**), **CFD Fortran** is a practical module for learning both the foundations of *computational fluid dynamics* (CFD) as well as of *modern Fortran*. While conceptually similar to **CFD Python**, **CFD Fortran** extends the scope of the latter by putting additional emphasis on *computational performances*. These performances not only come from the use of a compiled language specifically designed for scientific computing, but also by gradually introducing more efficient algorithms and paying attention to the interplay between their implementations and the optimizations offered by current compilers.

## For who is this module and how to use it?

This module is intended for anyone interested in `Fortran` and *computational fluid dynamics*. The teaching material and accompanying source codes being released under a [Creative Common](https://creativecommons.org/) and **to-be-decided** license, respectively, it can be used for self study, as as part of a regular university course in scientific computing or for an intensive training course in industry.

**University course:** As an introductory course to scientific computing at university, the **CFD Fortran** lessons can be completed in 4 to 5 weeks if the advanced (optional) material is excluded. Although we try to cover the gist of it, prior knowledge of standard numerical methods (mainly finite differences and Jacobi-like iterative solvers for linear equations) should be consider a pre-requisite for such a class. Some programming experience with another language can also be beneficial.

### Lessons

- **Lesson 0: Setting up your Fortran environment** -- `Fortran` is a programming language targeting scientific computing which has been around for nearly sixty years. It has lost some momentum in the past decade in favor of seemingly more modern languages such as `C++`, `Python`, `Julia` or `Rust`, and is often considered an "old" language mostly due to the prominence of out-dated `Fortran 77` codes. Yet, `Fortran` remains just as relevant as ever for developing new high-performance scientific softwares and its "old language" image often results from a lack of knowledge of its modern capabilities. In the past few years, this observation lead to a community-wide effort to restore `Fortran`'s letters of nobility and equip it with a modern scientific computing ecosystem, not only including modernized versions of widespread libraries but also a brand new package manager. In this pre-lesson, we will give a whirlwind tour of this on-going effort gathered around the [fortran-lang](https://fortran-lang.org/) initiative.
  - Installing your first `Fortran` compiler (i.e. `gfortran` or `LFortran`) and the [Fortran Package Manager](https://github.com/fortran-lang/fpm) `fpm`.
  - The basics of `Fortran`.
  - (Optional) Setting up a modern integrated development environment (IDE) for `Fortran`.
- **Lesson 1: the Helmholtz equation** -- This equation, of which the well-known [Poisson equation]() is a special case, is ubiquitous in physics and engineering. It is the `Hello World!` of partial differential equations. Discretizing it with standard finite-difference schemes, this lesson illustrates how to solve the resulting linear system of equations using a variety of iterative solvers. We will discuss how these solvers can be written in a readable, maintainable and generic way in `Fortran` while making sure to have implementations as high-performing as possible.
  - Jacobi, Gauss-Seidel and SOR iterative solvers.
  - (Optional) Cache-blocking and OpenMP parallelization strategies for Jacobi-like iterative solvers.
  - (Optional) Multigrid and conjugate gradient.
- **Lesson 2: Time-stepping and the unsteady Heat equation** -- Solving the unsteady heat equation is just as important as solving its steady counterpart. It illustrates some of the key challenges one has to face when simulating spatio-temporal systems. Whenever possible (i.e. for implicit schemes) we will re-use the iterative solvers developed in the previous lessons, thus highlighting the benefits of having written them in a fairly modular way to begin with. We will also discuss the pros and cons of implicit vs. explicit time-stepping, not only from the classical point of view of the [Courant-Friedrichs-Lewy](https://en.wikipedia.org/wiki/Courant%E2%80%93Friedrichs%E2%80%93Lewy_condition) condition, but also implementation-wise.
  - Single-step Explicit [Runge-Kutta](https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods) schemes with fixed time steps.
  - Implicit scheme: The [Crank-Nicholson](https://en.wikipedia.org/wiki/Crank%E2%80%93Nicolson_method) method.
  - (Optional) Runge-Kutta schemes with variable time steps and error control.
  - (Optional) Using [ADI](https://en.wikipedia.org/wiki/Alternating-direction_implicit_method) iterations for the implicit phase.
- **Lesson 3: Linear and nonlinear advection-diffusion equations** -- While being integral parts of CFD, the steady and unsteady heat equations are elliptic/parabolic partial differential equations and thus do not capture a fundamental process in fluid flows: transport. In this lesson, we will thus look at the linear advection equation and its nonlinear counterpart, the Burgers' equation. Relying once more on the finite-differences method, we will see why special care needs to be taken when discretizing the differential operator associated to this physical process and how it can be efficiently implemented in `Fortran`.
  - The linear advection equation in 1D with an updwind scheme.
  - Combining advection and diffusion.
  - Extension to the nonlinear viscous [Burgers](https://en.wikipedia.org/wiki/Burgers%27_equation)' equation with no shocks.
  - (Optional) Extension of the linear advection-diffusion equation in 2D.
  - (Optional) Shock-capturing schemes for the Burgers' equation in the presence of shocks.
- **Lesson 4: The incompressible Navier-Stokes equations** -- In this last-to-final lesson, we are now ready to tackle the main goal of this module: simulating the incompressible Navier-Stokes equations. In particular, we will implement a full CFD solver capable of simulating two canonical flow configurations, namely the plane Poiseuille and the lid-driven cavity flows. Building on the previous lessons, we will implement an incompressible CFD solver with excellent serial performances. By the end of this lesson, students shall not only have a good understanding of the basics of computational fluid dynamics but also be able to write high-quality `Fortran` code using some its more modern features.
  - Simulating the plane Poiseuille flow in 2D.
  - Simulating the two-dimensional lid-driven cavity flow using a vorticity-streamfunction formulation.
- **Lesson 5: To go further** -- In this last lesson, we will discuss some important features targeting high-performance computing at scale. This will not only include a discussion about modern `Fortran` features such as `do concurrent` constructs or `coarray`, but also elements of an [MPI](https://en.wikipedia.org/wiki/Message_Passing_Interface)-based parallelization strategy as well as the state of `Fortran` and GPU computing.

### Dependencies

This module has close to no dependencies except for having access to a `Fortran` compiler. If you need to setup your computer for using `Fortran`, please refer to [this guide](https://fortran-lang.org/learn/os_setup/) on the [fortran-lang](https://fortran-lang.org) website.

## How to contribute to CFD Fortran?

TBA
