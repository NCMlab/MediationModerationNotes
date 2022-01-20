# Mediation and Moderation for Brain Imaging
Permanent Note
Created: 01-10-2022 13:53


Mediation and moderaion for brain imaging is different because of the need to apply the model across thousands of voxels, data points, in the brain. Any of the variables in the model can be brain maps; however, the most likely is the use brain maps as the mediating variables. 

There are tricks that are used to make analysis of brain imaging data faster. In standard statistical parametric mapping, the brain imaging data is the outcome variable. Therefore, the design matrix/model is the same for every data point in the brain. This allows the design matrix to be inverted once, then multiplied by the data from every data point in the brain. Since the inversion step is the most computaionally intensive, this makes the process quick. 

When the brain imaging data is a predictor variable, the inversion is required for every data point making the process quite long. It becomes even longer when it needs to be bootstrapped for every voxel.


## References
1. 