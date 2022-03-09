# References to MatLab Code

## [FitProcessModel](https://github.com/NCMlab/ProcessModelsNeuroImage/blob/master/FinalCode/FitProcessModel.m)

* This is the function that performs the regression
* It cycles over the Direct and Interaction matrices to create the regression equations.
* It then fits the regresson equations using the function [ProcessRegStats](https://github.com/NCMlab/ProcessModelsNeuroImage/blob/master/FinalCode/ProcessRegStats.m)
	* This function performs the actual beta value estimation on lines 15 to 17 as follows:
		`design = x2fx(design);`
		`[Q,R] = qr(design,0);`
		`beta = R\(Q'*y);`
	* The rest of the file performs a lot of statistical values using the beta values
* The function contains a lot of info about handling the output files. 
* It then calculates the path values. 
	* It also calculates the standard error of the path values using this function: [subfnCalculatePathSE](https://github.com/NCMlab/ProcessModelsNeuroImage/blob/master/FinalCode/subfnCalculatePathSE.m)

## [testerOneVoxelProcessBootstrap](https://github.com/NCMlab/ProcessModelsNeuroImage/blob/master/FinalCode/testerOneVoxelProcessBootstrap.m)
This function performs all analyses on a single data location.
* It calculates the point estimate first on line 14.
	* The point estimate is the model fit BEFORE any bootstrap resampling is done
* It also performs the bootstrapping here:
	* [BootStrapFunction](https://github.com/NCMlab/ProcessModelsNeuroImage/blob/master/FinalCode/BootStrapFunction.m)
