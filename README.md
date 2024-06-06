# ddt_on_nesi

Showing how to use the debugger on NeSI platforms on a sample code

```
git clone https://github.com/pletzer/fidibench
```

## Platform dependent build

### Maui

Note: As of June 2024 `module load forge` will load version 22.1.1, which has a license issue.
```
module load forge/22.1.2
cd fidibench
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=debug ..
cmake --build .
```

### Mahuika

```
module load forge/22.1.2
cd fidibench
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=debug ..
cmake --build .
```


## Running the debugger

Documentation on how to use `ddt` on NeSI can be found [here](http://127.0.0.1:8000/nesi/support-docs/Scientific_Computing/Profiling_and_Debugging/Debugging/#ddt-offline-mode). 

Here we provide a Fortran code for you to debug (C++ executables are available under the `upwind/cxx` directory. In the build directory type
```
ddt upwind/fortran/upwindF08
```
Adjust the working directory. Set the queue (partition) parameters. Specify the command line arguments (e.g. 100 10) and click submit. You job will now be in the queue.

You should now be able to step through the code, set breakpoints and see the call stack. 

See [ARM DDT](https://developer.arm.com/documentation/101136/22-1-3/Arm-Forge/Introduction-to-Arm-Forge/Arm-DDT) to find out how to use ddt. 





