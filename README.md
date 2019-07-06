# System-programming-notes

## 1. Boost build on Windows OS platform for VC++:

### 1.1 Build the Boost.Build tool
```
> .\bootstrap.bat
```

### 1.2 Build Boost libraries

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
