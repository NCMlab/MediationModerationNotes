# Defing data for mediation and moderation
Permanent Note
Created: 01-11-2022 12:25


The data input can be set up to only have one column per variable that will be used. Therefore, there needs to be a function that "setups" the data.

This is important because one variable will typically be thousands of variables that all need to be tested. 
1. One program can extract the data one by one and send it to the model to be analyzed.  
2. Or, the full dataset can be sent and the analysis function can cycle over the data
	1. I like this idea better for the following reason.
		1. If the outcome variable is the brain imaging data (with lots of variables), and the inpout model is teh same for each variable, then the model only needs inversion once. 
		2. See here for a description:[[Mediation and Moderation for Brain Imaging]]


## References
1. 