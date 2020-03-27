complex_bessel
==============

[![Join the chat at https://gitter.im/valandil/complex_bessel](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/valandil/complex_bessel?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![DOI](https://zenodo.org/badge/5354/valandil/complex_bessel.svg)](https://zenodo.org/badge/latestdoi/5354/valandil/complex_bessel)

A C++ library to evaluate Bessel functions of all kinds. More information can 
be found on the [website](http://joeydumont.github.io/complex_bessel).

## Introduction

C++ library that acts as a wrapper for the Fortran subroutines developed by D.E. Amos.
The library provides functionality to compute the Bessel, Hankel and Airy functions of
complex argument and real order. Negative orders are implemented via the standard formulae.

We provide a shared object library and header files to be included.

## Compilation instructions

The library uses CMake for compilation. The user should thus install CMake
on their machine. On Ubuntu and other Debian-based OSes, this can be done
by running
  ```bash
  sudo apt-get install cmake
  ```
On Arch Linux
  ```bash
  sudo pacman -S cmake
  ```

The user should then run
  ```bash
  bash build.sh
  ```
which will create a `build/` directory and run make automatically. When
you are ready to install the files, just run 
  ```bash
  cd build
  sudo make install
  ```
The library will be installed to `/usr` by default. To change
it, you will have to run `cmake` manually like so:
  ```bash
  cmake -DCMAKE_INSTALL_PREFIX=/path/of/install/dir
 ```
 
 ## Other similar libraries
 
 The FORTRAN library that is used as the main driver for the computation of Bessel functions is also used in
   * [`scipy.special`](https://docs.scipy.org/doc/scipy/reference/special.html)
   * MATLAB
   
[Boost](https://www.boost.org/doc/libs/1_72_0/libs/math/doc/html/math_toolkit/bessel/bessel_first.html) has its own implementation of the Bessel functions, but only supports real values for the argument.

If arbitrary precision is needed, the [`arb`](http://arblib.org/acb_hypgeom.html#bessel-functions) library supports the computation of many special functions, including Bessel functions.

## Example
![Contours of Hankel function](/tests/contours.png)
