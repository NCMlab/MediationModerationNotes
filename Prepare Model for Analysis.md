# Prepare Model for Analysis 



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
Out = list(length = number of variables)
In = list(length = number of variables)
count = 0
for r in (Rows of Direct):
	F = find(r not equal to zero)
	if length(F) > 0:
		Out.append(variable in row r)
		CurrentModel = list
		 for j in F:
			CurrentModel.append(variable in column(F(j)))
		In.append(CurrentModel)
	count += 1
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
			
