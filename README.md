# High Performance Conjugate Gradient Benchmark (HPCG)

This repository contains the Tech-X modifications of the HPCG benchmark.
HPCG is developed by Jack Dongarra, Michael Heroux, and Piotr Luszczek.
For more information on HPCG see 
[the official website of HPCG](https://software.sandia.gov/hpcg/default.php)

This repository is based on revision 2.1 of HPCG.


## Introduction

HPCG is a software package that performs a fixed number of symmetric
Gauss-Seidel preconditioned conjugate gradient iterations using double
precision (64 bit) floating point values.  Integer arrays have global
and local scope (global indices are unique across the entire distributed
memory system, local indices are unique within a memory image).  Integer
data for global/local indices have three modes:

- 32/32 - global and local integers are 32-bit
- 64/32 - global integers are 64-bit, local are 32-bit
- 64/64 - global and local are 64-bit.

These various modes are required in order to address sufficiently big
problems if the range of indexing goes above 2^31 (roughly 2.1B), or to
conserve storage costs if the range of indexing is less than 2^31.

The  HPCG  software  package requires the availability on your system of
an implementation of the  Message Passing Interface (MPI). An
implementation compliant with MPI version 1.1 is sufficient.


## Installation

See the file [INSTALL](INSTALL) in this directory.


## Documentation

The source code documentation can be generated with a Doxygen (version
1.8 or newer). In this directory type:

```
    doxygen tools/hpcg.dox
```

Doxygen will then generate various output formats in the `out` directory.


## Tuning

See the file [TUNING](TUNING) in this directory.


## Bugs

Known problems and bugs with this release are documented in the file
[BUGS](BUGS).


## Further information

Check out  the website
[http://software.sandia.gov/hpcg](http://software.sandia.gov/hpcg) for
the latest information.

