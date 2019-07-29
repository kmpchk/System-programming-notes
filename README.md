# Bulatik's system programming notes

## 1. Boost build on Windows OS platform for VC++:

### 1.1. Build the Boost.Build tool
```
> .\bootstrap.bat
```

### 1.2. Build Boost libraries

```
> .\b2.exe toolset=msvc --build-type=complete --abbreviate-paths architecture=x86 address-model=64 install -j4
```
| Command-line options        | Meaning           |
| ------------- |:-------------:|
| toolset      | Use this to specify the Visual C++ compiler to use |
| architecture      | This is the processor architecture. Keep this x86 for both 32-bit and 64-bit builds     |
| address-model | Use this to specify whether you want 32 or 64 bit library to be built      |
| -j | Use this to specify how many cores to use for parallel compilation      |
| --abbreviate-paths | This option is useful to keep paths from becoming longer than the filesystem supports      |
| --build-type | This option determines which build types of the libraries are created. `minimal - only release builds, complete - both debug and release versions`     |

### 1.3. Resources
+ [Boost - Getting Started on Windows](https://www.boost.org/doc/libs/1_68_0/more/getting_started/windows.html)
+ [How to build Boost using Visual Studio](https://codeyarns.com/2014/06/06/how-to-build-boost-using-visual-studio/)
+ [Installation - Getting Started on Windows](https://theboostcpplibraries.com/introduction-installation)
+ [Boost libraries - build only what I need](https://stackoverflow.com/questions/4714289/boost-libraries-build-only-what-i-need)

## 2. CMake option to compile x86-32/64 bit executables using C++ compiler:

### 2.1. x86-32 bit executable
```
set(CMAKE_CXX_FLAGS -m32)
```
### 2.2. x86-64 bit executable
```
set(CMAKE_CXX_FLAGS -m64)
```

## 3. CMake option to compile STATIC library:

```
add_library(PROJECT_NAME LIB_SOURCES)
```

## 4. CMake option to compile SHARED (DYNAMIC) library:

```
add_library(PROJECT_NAME SHARED LIB_SOURCES)
```
## 5. Linking a STATIC(.a)/SHARED(.so) library with an executable:

```
target_link_libraries(PROJECT_NAME <STATIC_LIB_NAME>.(a/so))
```
## 6. Building an STATIC executable (no depends on libraries, example the `libstd++`):

```
target_link_libraries(PROJECT_NAME -static)
OR
set(CMAKE_EXE_LINKER_FLAGS "-static")
```
## 7. Showing linked shared libraries of an executable:

```
ldd EXECUTABLE_NAME
```
## 8. Determine the type of an executable or a shared library and showing additional information (32/64-bit, example):

```
file EXECUTABLE_NAME
```
