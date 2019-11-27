## Getting Started

To get started, you will need to download and compile a version of SWIFT. It
will also help to install the tools that we use to analyse the outputs,
however files are provided such that SWIFT outputs can be read with Paraview.

To get started with SWIFT, you will need (working versions) of the following:

+ GNU autotools.
+ A reasonably modern C compiler, such as GCC.
+ An installation of the HDF5 library.
+ An installation of the GSL library.
+ An installation of the FFTW library.

The following are useful to have, but are not strictly necessary for the
demonstrations below:

+ An installation of some other allocator, such as tbbmalloc.

You can learn how to install these with your specific package manager
by searching the name of your operating system combined with the name of
the package.

### Downloading and Building SWIFT

Begin by cloning the SWIFT master:

```
git clone https://gitlab.cosma.dur.ac.uk/swift/swiftsim.git
```

To create your first build of SWIFT (this process will need to be repeated
when changing any of the many compile-time options in SWIFT):

```
cd swiftsim
./autogen.sh
./configure
make
```

After configure has finished, you should check the output to make sure that
the script has found all of your libraries correctly. If not, then you can
specify paths for individual libraries; `./configure --help` will provide help
with this.

Note that the `main.c` and the SWIFT binary are stored in the examples
directory for historical reasons. Should you wish, you can also create an
out-of-source build.

Finally, note that you will have to pass `CFLAGS="-fno-stack-check"` to the
configure script should you wish to compile SWIFT on a Mac running MacOS
Catalina (due to a bug in the shipped version of `clang`). You can do this
by adding it as another command line argument, i.e.

```
./configure CFLAGS=-fno-stack-check
```

### Installing the SWIFT python tools

To install the python tools, all you need to do is use the python package
manager, `pip`,

```
pip install swiftsimio matplotlib scipy
```

This should install all necessary components for reading the output files.
You will need modern python (3). Legacy python (2) is not supported by the
SWIFT project.

You will probably find it useful to install the `numba` python library
at the same time should you wish to visualise your outputs as images
and movies. This significantly decreases the post-processing computation
time.

Next: [Your First Example](your_first_example.md)
