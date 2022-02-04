# Create regression equations from the setup file
## Assume we are working with this model:
ModelName = 'Model 5'
Direct=
	['A', 'B', 'C';
	0,0,0;
	1,0,0;
	1,1,0]

Interaction=
	['A','B','C';
	0,0,0;
	0,0,0;
	1,1,0]

Path=['A','B','C';
	0,0,0;
	1,0,0;
	0,2,0]


The direct matrix needs to be of size (MxM), where M is the number of variables in the model
The Interaction is of size (MxMxI), where the dimension I can be 1 or more.
The Path is of size (MxMxI), where the dimension I can be 1 or more.

This setup assumes that the columns and rows correspond with each other. The variable in column 1 corresponds to the variable in row 1, etc.

## Step one, set up the direct effects
This needs some though because som variables may be brain imaging data and require another loop

for r in (Rows of Direct)
	F = find(r not equal to zero)
	if length(F) > 0
		Out = data of row r
		In = data in the non-zero columns as found in F
	end
end