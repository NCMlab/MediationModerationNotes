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
The Interaction is of size (MxMxU), where the dimension U can be 1 or more.
The Path is of size (MxMxP), where the dimension P can be 1 or more.

This setup assumes that the columns and rows correspond with each other. The variable in column 1 corresponds to the variable in row 1, etc.

We will need to know the number of participants in the data and will call it **N**.

## Step one, set up the direct effects
This needs some thought because some variables may be brain imaging data and require another loop

Every regression model has two parts: the Outcome variable and the Input Variable(s).
For this model we will consider there being three variables named A, B, and C. 
```
Out = list
In = list
for r in (Rows of Direct):
	F = find(r not equal to zero)
	if length(F) > 0:
		Out.append(variable in row r)
		CurrentModel = list
		 for j in F:
			CurrentModel.append(variable in column(F(j)))
		In.append(CurrentModel)
```	

For this specific example we should now have
```
	Out = ['B', 'C']
	In = [['A'],['A','B']]
	Inter = [[],[],['B','C']]
```
Now we need to add interactions

```
Inter = list(size(M,1))
for t in size(Interaction,3):
	for r in (Rows of Interaction):
		if length(F) > 0:
			CurrentModel = list
			for j in F:
				CurrentModel.append(variable in column(F))
			Inter[row count].append(CurrentModel)
```
			
	