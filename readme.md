# Testing and Estimation of Social Network Dependence With Time to Event Data

# Author Contributions Checklist Form

## Data

### Abstract 

The data set contains two parts. One records the network/friendship information by pairs of nodes. Another contains some attributes (age, gender etc.) and responses (survival time and censoring indicator) of each subject. 

### Availability

The real Tencent QQ Game Data will not be publicly available because of business confidentiality.

Example data is included in this repo.

## Code

### Abstract

There are 8 files, which contain functions for the proposed test, parameter estimation and asymptotic variance estimation, as well as code to reproduce the simulation study in the paper. There is also an example code file which instructs how to run the code on the example data step by step.

### Description 

All code is available at https://github.com/lsu3/social_network_dependence (master+ commit 4)

Contents:

1. attributes.csv, a generated data set using the same setting as described in the Simulation section, where \rho=0.05, censoring rate about 30%. Columns X1, X2 are the two covariates, tildeT is the observed survival time, delta is the indicator of censoring. This file is of the same format as for our real data set.
2. network.csv, a generated network data set using the same setting as described in the Simulation section, where K=5. Columns V1 and V2 are the ID of connected pairs. This file is of the same format as for our real data set.
3. data_prep.R, an R file containing functions to transform the raw data to the format we need.
4. fun_test.R, an R file containing functions for the proposed test method in Section 3.1.
5. fun_estimation.R, an R file containing functions for the parameter estimation for the proposed model as described in Section 3.2.
6. fun_variance.R, an R file containing functions for estimating the asymptotic variance for the proposed model as described in Section 3.2.
7. example.R, an example of how to run the code step by step on the data.
8. data_generator.R, an R file containing functions to generate data used in simulation.
9. test_simulation.R, code to run simulation for the proposed testing.
10. estimation_simulation.R, code to run simulation for the proposed estimation methods.

Main file: example.R

1. Read in data from attributes.csv and network.csv. Prepare the data for further use.
2. Run the proposed test. First set up the grid for \gamma, then calculate the test statistic, and finally obtain the critical value based on the proposed resampling method.
3. Run the proposed algorithm for the parameter estimation.
4. Run to get the standard error.

### Optional Information

Version information:
R version: 3.4.1 (2017-06-30) -- "Single Candle"
survival: survival_2.41-3
parallel: parallel
foreach: foreach_1.4.3
doParallel: doParallel_1.0.11

Run time information:
These results are based on MacBook pro(Retina, 13-inch, Late 2013), 2.4 GHz Intel Core i5, 8 GB 1600 MHz DDR3, macOS Sierra(version 10.12.6)
1. Single run of testing: 39.02286 secs
2. 100 replicates of testing simulation: 49.05856 mins
3. Single run of estimation: 18.30699 secs
4. 100 replicates of estimation simulation: 35.75173 mins

## Instructions for use

### Reproducibility 

Results of a data set that is similar to the real data example from paper can be reproduced by following the same steps as showed in example.R:

*	Read in data from attributes.csv and network.csv. Prepare the data for further use.
*	Run the proposed test. First set up the grid for \gamma, then calculate the test statistic, and finally obtain the critical value based on the proposed resampling method.
*	 Run the proposed algorithm for the parameter estimation.
*	Run to get the standard error.

Simulation results for the proposed test as presented in the paper can be reproduced by running test_simulation.R

Simulation results for the proposed estimation method as presented in the paper can be reproduced by running estimation_simulation.R
