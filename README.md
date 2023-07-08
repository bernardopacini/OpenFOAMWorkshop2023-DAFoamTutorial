OpenFOAM Workshop 2023 - DAFoam Tutorial
========================================

DAFoam Docker Container
-----------------------

Linux:
```console
docker run -it --rm -u dafoamuser --mount "type=bind,src=$(pwd),target=/home/dafoamuser/mount" -w /home/dafoamuser/mount dafoam/opt-packages:v3.0.6 bash
```

MacOS:
```console
docker run -it --rm -u dafoamuser --mount "type=bind,src=$(pwd),target=/home/dafoamuser/mount" -w /home/dafoamuser/mount dafoam/opt-packages:v3.0.6 bash
```

Windows:

```console
docker run -it --rm -u dafoamuser --mount "type=bind,src=%cd%,target=/home/dafoamuser/mount" -w /home/dafoamuser/mount dafoam/opt-packages:v3.0.6 bash
```

Part 1 - Airfoil Optimization
-----------------------------

```
cd Part1/
mpirun -np <number of cores> python runScript.py
```
Part 2 - Wing Aerodynamic Optimization
--------------------------------------

```
cd Part2/
mpirun -np <number of cores> python runScript.py
```

Part 3 - Wing Aerostructural Optimization
-----------------------------------------

```
cd Part3/
mpirun -np <number of cores> python runScript.py
```