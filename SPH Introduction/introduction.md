# Introduction to SWIFT

### Josh Borrow

### Thursday, November 7, 2019
 
## What is SWIFT?

SWIFT is a new SPH code, developed at Durham, to run large-scale cosmological
simulations. State-of-the-art cosmological simulations use around a hundred
billion SPH particles, and as such this code needs to be able to scale to
tens of thousands of cores – just to hold the particles in memory!

SWIFT achieves this though a three-tier parallelism approach. It uses:

+ MPI communication between nodes
+ Threads on a single node (using pthreads, not OpenMP)
+ SIMD-level parallelism (with some explicit vectorization) within a single
  core.

With this, SWIFT has been shown to weak-scale almost perfectly up to tens of
thousands of cores. Strong scaling cosmological problems is a huge
challenge[^1], and is not something that is covered in this tutorial.

SWIFT is fully open source[^2] and is in open development. It also has
numerous tools available to analyse data using the python programming
language[^3]. These tools will be used in this tutorial, but you can be very
brave and read the HDF5 outputs by yourself should you wish. They are well
described, with each output containing extra metadata.

Full documentation for SWIFT is available online[^4]. Please consult this for
more technical information than is available in this document.

Because SWIFT is designed to run compressible ideal gas simulations, it
requires multiple time-stepping. More information on this is available in the
documentation, but briefly: each particle carries its own time-step, which is
not global. Each particle is integrated only when it needs to be; integrating
all particles on a global time-step would represent an increase of over 100x
in run-time for cosmological problems.

SWIFT includes several hydrodynamics models, with most of these not including
Riemann solvers. In the information below, each model will be explored in
turn.

Next: [Getting Started](getting_started.md)

[^1]: Borrow et al. 2018, SPHERIC; https://ui.adsabs.harvard.edu/abs/2018arXiv180701341B/abstract.

[^2]: Available at gitlab.cosma.dur.ac.uk/swift/swiftsim or mirrored at github.com/swiftsim/swiftsim.

[^3]: These are available on our GitHub, github.com/swiftsim/swiftsimio. You can also install them with pip.

[^4]: Documentation is available at swiftism.com/docs.