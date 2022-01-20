# Using the flexible modeling approach
Permanent Note
Created: 01-10-2022 12:42

In order to use the flexible modeling approach, the different matrices need to be defined, then used as inputs. Therefore, a function could be defined as:

function(data, direct, paths, interact, names)

**direct:** a square matrix with size equal to the number of columns in the data matrix.
**names**: a list of names that correspond to the variable names in the dataFrame of the data variable. The variables in "names" are in the same order as in the direct matrix. This allows the data to be in any order and the direct and names to specify the order. This also allows the input data to have unused columns, which are those NOT specified in the names vector/list.

---
When this function is called there needs to be a check to make sure that all variables listed in **names** are in the dataFrame **data** and to make sure that all path steps in **paths** have direct effects listed.

---
## Function list
* Linear regression
	* input: predictors, outcome
	* output beta weights
* Calculate path
	* input: beta weights, path matrix
	* output: path value
* Bootstrap
	* input: predictors, outcome, BootstrapMatrix
	* output: beta weights from each bootstrap
* MakeBootStrapMatrix
	* input: Number of bootstraps, length of data (N)
	* output: matrix of size NBoot x N
	* The create matriix needs to be saved and used repeatedly
* CalculateCI
	* input: vector of values, CI type
	* output: CI values
	* CI types: percentile, BC
* Create interaction term
	* input: data, interaction matrix
	* output: vector 
	* The data vectors are demeaned and then multiplied and teh result is returned
* Probing a Moderation
	* to define
* Setup files 
	* There are setup files for the different designs, with NO data specified. Therefore, we can have a battery of common analysis models, like Hayes. But there is also the flexibility to specify your own model.
		* It would be nice to be able to convert the design files into figures, like Mermaid markdown, that allow the user to see what they are going to test graphically.
	* There is also a setup file specifying the data sources. 
## References
1. 