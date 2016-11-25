## ChangeLog
1. forked from jen20/libuv-cmake
2. remove macro ${LIBUVDIR}
3. Fix windows Visual Studio building error.

## CMake build for libuv

**This is not officically supported by the libuv project, and issues encountered using this should NOT be reported to the libuv upstream project - instead report issues here.**

This repository contains a CMakeLists.txt capable of building libuv without requiring the use of Autotools or GYP. It may be of use to projects which use CMake and want to take a dependency on libuv without requiring switching build systems to GYP, or using an `ExternalProject` in CMake. It is of particular use for people wanting completion from an IDE such as CLion, which relies on CMake as the project file format.

It is currently known to work on Mac OS X, Linux and Solaris, though it may also work on Windows (untested as I don't have easy access to a Windows box).

The position from the UV maintainers appears to be that there will not be a supported CMake build added. I will try to maintain this as new stable versions of libuv are released, as it is used in my own projects. The current version is **v1.6.1**.

### Usage

- Copy CmakeLists.txt to {your-source-directory-of-libuv}
- Just CMake the project.

```
- The `uv` target is produced by the `CMakeLists.txt` file - it can be linked using the following:

```cmake
target_link_libraries(my_target uv)
```

- By default the tests and benchmarks for libuv are not built. To enable them, set the `LIBUV_BUILD_TESTS` option to `ON`.

### Contributing

- Please report issues to the issue tracker on this repository, and NOT to the upstream project.
- Please open pull requests on this repository.
