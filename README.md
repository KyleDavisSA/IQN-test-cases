# IQN-test-cases

This repository contains ready to run test cases to reproduce the results for studying the quasi-Newton improvements in [preCICE](https://github.com/precice/precice). The improvements are made in the [iqnUpdates](https://github.com/precice/precice/tree/iqnUpdates) branch. The test cases contain all solver settings and meshes, as well as run scripts for all solvers.

In order to reproduce the results, the necessary preCICE configuration files are provided `configuration-files`. The configuration files are organised into `Table-1`, `Table-1`, and `Table-3`. The configuration files from `Table-3` reproduces the results for `Table-4` and `Table-5` as well. Inside each folder, the folders are further divided into which set of data it reproduces: 

baseline, prescale freeze or weight-monitoring .
