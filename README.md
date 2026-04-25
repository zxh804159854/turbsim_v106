
# NREL TurbSim source with CMake build

This is a fork of the [NREL TurbSim](https://nwtc.nrel.gov/TurbSim) source code
to adapt it to use CMake for the build system. The source formatting has been
rearranged slightly, but otherwise no source files have been modified from the
base source downloadable at the NWTC download portal.

## Installation instructions

### Vs2015+INTEL_Fortran_2016_U1
```
git clone https://github.com/zxh804159854/turbsim_v106
cd turbsim_v106/build                   # Change into the build directory
cmake ../src -G "Visual Studio 14 2015" -A x64
cmake --build . --config Release
cmake --install . --config Release
```

### vs2022和oneapi2025
```
git clone https://github.com/zxh804159854/turbsim_v106
cd turbsim_v106/build                   # Change into the build directory
cmake ../src -G "Visual Studio 17 2022" -T fortran=ifx           # 必须这样子写，否则无法正确识别oneapi
cmake --build . --config Release                               # Build sources 
cmake --install . --config Release
```

## Current CMake options

* `DOUBLE_PRECISION`     - Enable double precision for REAL
* `CMAKE_BUILD_TYPE`     - RELEASE or DEBUG
* `CMAKE_INSTALL_PREFIX` - Directory where the executable is installed
* `BUILD_SHARED_LIBS`    - Enable building of shared libraries

## Other information

Please consult the official NWTC download portal for License, Disclaimer, and
documentation.

# Version Information

* NWTC_Library v1.07.02a-mlb, 21-May-2013
* TurbSim v1.06.00, 21-Sep-2012