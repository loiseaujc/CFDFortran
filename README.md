# CFD Fortran

Heavily inspired by Lorena Barba's [**CFD Python**](https://github.com/barbagroup/CFDPython) (also known as the **12 steps to Navier-Stokes**), **CFD Fortran** is a practical module for learning both the foundations of *computational fluid dynamics* (CFD) as well as of *modern Fortran*. While conceptually similar to **CFD Python**, **CFD Fortran** extends the scope of the latter by putting additional emphasis on *computational performances*. These performances not only come from the use of a compiled language specifically designed for scientific computing, but also by gradually introducing more efficient algorithms and implementations without compromising the pedagogical objectives of the original module.

## How to use this module?

## Lessons

- **Lesson 0: Setting up your Fortran environment** --
- **Lesson 1: the Helmholtz equation** -- This equation, of which the well-known [Poisson equation]() is a special case, is ubiquitous in physics. It is the `Hello World!` of partial differential equations. Discretizing it with standard finite-difference schemes, this lesson illustrates how to solve the resulting linear system of equations using a variety of iterative solvers. We will discuss how these solvers can be written in a readable, maintainable and generic way in `Fortran` while making sure to have implementations as high-performing as possible.
  - Jacobi, Gauss-Seidel and SOR iterative solvers.
  - (Optional) Cache-blocking and OpenMP parallelization strategies for Jacobi-like iterative solvers.
  - (Optional) Multigrid and conjugate gradient.
- **Lesson 2: Time-stepping and the unsteady Heat equation** -- Solving the unsteady heat equation is just as important as solving its steady counterpart. It illustrates some of the key challenges one has to face when simulating spatio-temporal systems. Whenever possible (i.e. for implicit schemes) we will re-use the iterative solvers developed in the previous lessons, thus highlighting the benefits of having written them in a fairly modular way to begin with. We will also discuss the pros and cons of implicit vs. explicit time-stepping, not only from the classical point of view of the [Courant-Friedrichs-Lewy](https://en.wikipedia.org/wiki/Courant%E2%80%93Friedrichs%E2%80%93Lewy_condition) condition, but also implementation-wise.
  - Single-step Explicit [Runge-Kutta](https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods) schemes with fixed time steps.
  - Implicit scheme: The [Crank-Nicholson](https://en.wikipedia.org/wiki/Crank%E2%80%93Nicolson_method) method.
  - (Optional) Runge-Kutta schemes with variable time steps and error control and/or low-storage variants.
  - (Optional) Using [ADI](https://en.wikipedia.org/wiki/Alternating-direction_implicit_method) iterations for the implicit phase.
- **Lesson 3: Linear advection-diffusion equation** --
- **Lesson 4: The incompressible Navier-Stokes equations** --
- **Lesson 5: To go further** --
