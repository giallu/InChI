[Upstream README](README-upstream.md)

# InChI unofficial repository

This is a fork of the [InChI library official repository](https://github.com/IUPAC-InChI/InChI) where I work on my changes before submitting them as PRs

As such, there should be no need to use it unless you want to test some specific work in progress or artifact before it lands upstream

Right now, the main work going on here is the port of the build system to cmake (originally on branch `giallu/port_to_cmake`, later rebased and expanded on branch `build_matrix`):

## Compiling from source

InChI library and demo binaries can be easily compiled with cmake out of tree. 
For instance, the following will build everything in the `builddir` directory:

```
cmake -B builddir
cmake --build builddir
```

tested on Linux/GCC, Windows/MSVC, OSX/LLVM [and others](https://github.com/giallu/InChI/actions/workflows/build.yml)

### Compilation options

the default build creates a shared library, it is possible to have a static library instead by setting `BUILD_SHARED_LIBS` to `OFF` like this:

```
cmake -B builddir -D BUILD_SHARED_LIBS=OFF
```