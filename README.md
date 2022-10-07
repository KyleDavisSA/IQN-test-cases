# IQN-test-cases

This repository contains ready to run test cases to reproduce the results for studying the [quasi-Newton enhancements]{https://www.mdpi.com/2297-8747/27/3/40} in [preCICE](https://github.com/precice/precice). The `elastic-tube-3d-quad` is the elastic tube test case from the preCICE [tutorials](https://github.com/precice/tutorials). The test cases contain all solver settings and meshes, as well as run scripts for all solvers.

In order to reproduce the results, the necessary preCICE configuration files are provided in the folder `configuration-files` within each test case. The four test cases are: 
1. elastice-tube-3d-linear
2. elastice-tube-3d-quad
3. breaking-dam-2d
4. breaking-dam-3d

The configuration files are organised into `Table-1`, `Table-2`, and `Table-3`. The configuration files from `Table-3` reproduces the results for `Table-4` and `Table-5` as well. Inside each folder, the folders are further divided into which set of data it reproduces: 

1. `Table-1`: baseline, prescale freeze and weight-monitoring
2. `Table-2`: weight-monitoring
3. `Table-3`: baseline and QR3.

The `baseline` and `prescale freeze` folders are to be run with preCICE [v2.3.0](https://github.com/precice/precice/releases/tag/v2.3.0), `weight-monitoring` and `QR3` are to be run with [iqnUpdates](https://github.com/precice/precice/tree/iqnUpdates). The folders are further divided into:
1. `TSR-10_MIR-100` to reproduce test data for time steps reused = 10 and maximum number of iterations = 100
2. `TSR-20_MIR-200` to reproduce test data for time steps reused = 20 and maximum number of iterations = 200.

Within the folders, are the precice configuration files. Each file is named `precice-config_FilterType-FilterLimit.xml`. Here, the `FilterType` is either the `QR2` filter, or the `QR3` filter, which utilises the new preconditioner weight monitoring. The `FilterLimit` is either `= 0.001`, `= 0.01` or `= 0.1` depending on the test case.

Each file must be copied into the test case folder (i.e. into `IQN-test-cases/breaking-dam-2d/` or `IQN-test-cases/elastice-tube-3d-linear/` ) and renamed to `precice-config-xml` to reproduce the simulation results. A default configuration file is currently in each test case folder.

The following software version were used in the study:
1. Ubuntu 20.04.3 LTS - 64 bit
2. Boost 1.17.0
3. Eigen 3.3.7
4. PETSc 3.13.3
5. Python 3.8.10
6. openMPI v4.0.3
