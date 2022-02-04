# Mediation and Moderation
Map of Content #MOC
Created: 01-07-2022 10:07

1. [[Cognitive Reserve]] can only be identified through some factor moderating the effect of age or pathology on cognition.
2. The effects of age on cognition are mediated through [[Age related diseases]].
3. Mediation models range from the simple [[Three Variable Mediation Model]] to more sophisticated parallel and serial mediation models.
4. [[Parallel mediation]]
5. [[Serial Mediation]]
6. [[Simple Moderation]]
7. [[Flexible modeling of Mediation]]
8. [[Mediation and Moderation for Brain Imaging]]
9. [[Library of Mediation-Moderation Models]]
10. 


## Subproject list
- Generic setup file
	- This includes the direct, interaction, and path matrices
	- There will eventually be a library of these files
		- Examples
			- [[Model 4]], see its figure [[Model4Figure|here]].
			- [[Model 5]], see its figure [[Model5Figure|here]].
			- [[Model 6]], see its figure [[Model6Figure|here]].
* Analysis setup procedure
	* Select generic setup file
		* Check the file for the number of variables that are used
	* Select data to be used for the model
		* This selection procedure will be based on how many variables are needed for the model
		* Data can be  imaging data
		* Data can be CSV file
			* If CSV data is used, then check to see if there is a header row
			* Check to see how many columns are in the file.
				* If there are more than one variable in the file, then ask the user which variable to use.
	* Parameters to ask of the user
		* Number of bootstraps
			* Type of confidence intervals to calculate
				* Selection from a menu/list
		* Whether to apply TFCE
			* Yes/No
		* What correction for multiple comparisons to use
			 * Selection from a menu/list
		* Output from this step will be an analysis setup file specifically for processing the data

			
- Read setup file
- Create equations using the data/variables as defined in the setup file
- Process data/equations
- Create path values as defined in the setup file, based on results
- Run bootstrapping on all parameters
- Calculate confidence intervals on bootstrap results
- Create a results summary page
- Create a library of setup files of the most common designs.

# References
1. https://arxiv.org/abs/2106.02482
