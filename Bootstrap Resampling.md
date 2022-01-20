# Bootstrap Resampling
Permanent Note
Created: 01-07-2022 11:13
#statistics 


Bootstrap resampling is straightforward as a concept. However, I am interested in identifying ways that the process can be sped up.

I am also interested in keeping track of bootstraps, so that a bootstrap process can be performed in steps, e.g. 200 today and 2000 tomorrow. To do this the program needs to keep track of the result of the previous bootstraps and to rset the randomization seed so that NEW bootstraps are created.

I also wonder if it is possible to restructure the linear regression equations so to be maximally efficient when calculating bootstraps. 


$\beta = \frac{X^T \cdot Y}{X^T \cdot X}$


## References
1. 