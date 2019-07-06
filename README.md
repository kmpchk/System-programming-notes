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
