# Bootstrap Resampling
Permanent Note
Created: 01-07-2022 11:13
#statistics 

When performing bootstrap resampling, make sure to reset the random seed to the time stamp when performing the resampling. This is SUPER important to make sure than any new bootstraps are different from previous resamples. 

Bootstrap resampling is straightforward as a concept. However, I am interested in identifying ways that the process can be sped up.

I am also interested in keeping track of bootstraps, so that a bootstrap process can be performed in steps, e.g. 200 today and 2000 tomorrow. To do this the program needs to keep track of the result of the previous bootstraps and to reset the randomization seed so that NEW bootstraps are created.

I also wonder if it is possible to restructure the linear regression equations so to be maximally efficient when calculating bootstraps. 


$\beta = \frac{X^T \cdot Y}{X^T \cdot X}$


## Resample with a matrix
It is possible to create a sparse matrix that can be pre-multiplied by a data/design matrix that will create a resampled version of it. This matrix B is (NxN) containing zeros, but a single one value in each row. 
X = [a e; b f; c g; d h]
B = [0 1 0 0; 1 0 0 0; 0 0 0 1; 0 1 0 0]
BX=[b f; a e; d h; b f]
Therefore, B is equivalent to [2 1 4 2] resamples.

Is the use of this resample matrix faster than the resample algorithms?







## References
1. 