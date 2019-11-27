<!DOCTYPE html>
<html>
  <head>
    <title>SPH Introduction with SWIFT</title>
    <meta charset="utf-8">
    <style>
      @import url(https://fonts.googleapis.com/css?family=Open+Sans:400,700,400italic);
      @import url(https://fonts.googleapis.com/css?family=Inconsolata:400,700,400italic);

      body { font-family: 'Open Sans'; }

      .remark-slide-content { font-size: 30px; }

      h1, h2, h3 {
        font-family: 'Inconsolata';
        font-weight: 700;
        font-size: 40px;
      }
      .remark-code, .remark-inline-code { font-family: 'Inconsolata'; font-size: 30px; }
    </style>
  </head>
  <body>
    <textarea id="source">


class: center, middle

# Introduction to SPH with SWIFT
## Josh Borrow
### 28 November 2019

---

# Agenda

1. Introduction (to the introduction?)
2. Getting set up
3. The examples


---

# Introduction

+ SWIFT is an astrophysics simulation code
+ Used for cosmology, planetary impacts, and even engineering
+ It generally uses compressible SPH, but can be configured to use many different models.

---

# Getting set up

Head over to:

```
github.com/swiftsim/swiftsim/swiftsim-tutorials
```

This tutorial is there! (SPH Introduction folder).

---

# Getting set up

SWIFT requires:

+ GNU autotools
+ A reasonably modern C compiler, such as GCC
+ An installation of the HDF5 library
+ An installation of the GSL library
+ An installation of the FFTW library

If you need help please just ask!

---

# Special cases

Note there are some special cases for getting set up:

+ If you do not have an MPI install, configure the code with `--disable-mpi`
+ If you are on a Mac running Catalina, take care to read the Getting Started section carefully!

---

# The examples

1. Sod Shock
2. Sedov Blast
3. Kelvin-Helmholtz
4. An Isolated Galaxy
5. Anything?

We're here to help, so just ask us if you have any questions!

---

# Get going!

```
github.com/swiftsim/swiftsim/swiftsim-tutorials
```

Please ask any and all questions!

```
@JBorrow
```
```
joshua.borrow@durham.ac.uk
```




    </textarea>
    <script src="https://remarkjs.com/downloads/remark-latest.min.js">
    </script>
    <script>
      var slideshow = remark.create();
    </script>
  </body>
</html>
