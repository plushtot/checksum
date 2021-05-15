# Installing Checksum

## What You Need

- GCC [>= 7] or Clang [>= 5].
- Git [>= 2.18].
- CMake [>= 3.16].
- GNU Make [>= 4.2.1]
- OpenSSL [>= 1.1.1]
- Internet connection.

The following list of software is optional such that you should only download it
if you wish to contribute:

- GDB [>= 9].
- Doxygen [>= 1.8.18].
- Clang format [>= 10].
- Clang tidy [>= 10].
- CMake tidy [>= 0.5.0].

## Stick With a Release Version

The `main` branch is generally considered to always be in a volatile state.
Thus, there is a high chance that directly cloning `main` may leave you with a
broken build. Thus, you should stick with the tagged release versions if you
just want to use Checksum.

However, if you plan on contributing, then go on ahead and clone away. I highly
recommend that you read through the provided [contributing file](CONTRIBUTING.md),
and read through the code base documentation to gain a better understanding of
the project's internals. You don't wanna go in blind do you?

## The General Process

1. `mkdir build && cd build`
1. `cmake ..`
1. `make`
1. `sudo make install`

_You can also use -j[CORES] to speed up the build, where CORES is the number of
CPU cores your machine has!_

## Build System Options

The following information will only be useful if you plan on contributing (or
just curious). Otherwise, you can just ignore this section.

You can generate the code base documentation via the _-DENABLE_DOXYGEN_ option to
ON. This is disabled by default, because it increases the build time and
constantly regenerates documentation after typing `make`.

Checksum uses Git submodules to manage its dependancies. The project's build
system manages these submodules automatically so you do not need to constantly
type `git submodule --init --update` for every build you create. However, if you
want manual control over submodule management, then you can just set
_-DMANAGE_SUBMODULES_ to OFF.

By default, Checksum uses the `Release` build type. However, if you want to
change you can use the _-DCMAKE_BUILD_TYPE_. Here are the following build types:

- Release
- Debug
- MinSizeRel
- RelWithDebInfo

Finally, if you do not want the build system to treat warnings as errors, then
just set the _-DWARNINGS_AS_ERRORS_ option to OFF.
