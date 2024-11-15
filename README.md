# Vector Operations Library Using Makefile (CSAPP)

## Note:
### Using Dynamic Linking：
1. Set up the LD_LIBRARY_PATH environment variable to include the build directory:
```shell
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$(pwd)/build
```
2. Run the program:
```shell
./prog21
```
### Alternative: Using Absolute Path Linking

If you prefer to use the absolute path for the shared library, uncomment the corresponding lines in the Makefile under the “Compile main program and link with shared library” section. This will allow the program to locate the shared library without modifying LD_LIBRARY_PATH.