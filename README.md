OpenFOAM Workshop 2023 - DAFoam Tutorial
========================================

These tutorial files are part of the tutorial _DAFoam: A Discrete-Adjoint for OpenFOAM to Enable Gradient-Based Multidisciplinary Design Optimization_, presented at the 2023 OpenFOAM Workshop in Genoa, Italy. Additional DAFoam tutorials, expanding on the ones presented here, are available on the [DAFoam website](https://dafoam.github.io/index.html).

These tutorials can be run with an installation of DAFoam v3.0.6 and the corresponding MACH / MPhys tools, or with the provided Docker container, explained below.

DAFoam Docker Container
-----------------------

DAFoam is packaged as a Docker image to easily run cases on nearly any operating system, without compatibility or installation issues. Before downloading the image, ensure that you have a working Docker installation. Once Docker is installed and up to date, pull the DAFoam image:

```
docker pull dafoam/opt-packages:v3.0.6 
```

Once the image is downloaded, navigate to the root diretory of this tutorial and instantiate the Docker image using the commands below for Linux, MacOS, or Windows systems:

Linux:

```
docker run -it --rm -u dafoamuser --mount "type=bind,src=$(pwd),target=/home/dafoamuser/mount" -w /home/dafoamuser/mount dafoam/opt-packages:v3.0.6 bash
```

MacOS:

```
docker run -it --rm -u dafoamuser --mount "type=bind,src=$(pwd),target=/home/dafoamuser/mount" -w /home/dafoamuser/mount dafoam/opt-packages:v3.0.6 bash
```

Windows:

```
docker run -it --rm -u dafoamuser --mount "type=bind,src=%cd%,target=/home/dafoamuser/mount" -w /home/dafoamuser/mount dafoam/opt-packages:v3.0.6 bash
```

This command will start the image and the terminal session will convert into the DAFoam container. The DAFoam (and OpenFOAM) commands are now available on this environment.

Part 1 - Airfoil Optimization
-----------------------------

This is an example of airfoil optimization with DAFoam and the simpleFoam incompressible solver. To run the case, navigate to the directory and run the runscript:

```
cd Part1/
cp -r 0.orig 0
mpirun -np <number of cores> python runScript.py
```
Part 2 - Wing Aerodynamic Optimization
--------------------------------------

This is an example of wing aerodynamic optimization with DAFoam and the rhoSimpleFoam compressible solver. To run the case, navigate to the directory and run the runscript:

```
cd Part2/
cp -r 0.orig 0
mpirun -np <number of cores> python runScript.py
```

Part 3 - Wing Aerostructural Optimization
-----------------------------------------

This is an example of wing aerostructural optimization with DAFoam and the rhoSimpleFoam compressible solver. This case also requires the finite element solver TACS and the load and displacement transfer toolbox MELD. To run the case, navigate to the directory and run the runscript:

```
cd Part3/
cp -r 0.orig 0
mpirun -np <number of cores> python runScript.py
```
