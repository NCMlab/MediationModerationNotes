
```python
N = XX # the number of rows in the data
results = []
regOut = []
for i in Out:
	if i is not empty:
		# Setup an equation
		[m, n] = size(i)
		if n > 1:
			# This is imaging data
		else:
			regOut.append(i)
regIn = []
for j in In:
	if j is not empty:
		[m, n] = size(j)
		if n > 1:
			# This is imaging data
		else:
			regIn.append(j)


for k in Inter:
	if k is not empty:
		for p in k:
			CurrentVar = ones(N,1)
			for q in p:
				CurrentVar = CurrentVar*(q - mean(q)) # remove the mean
			regIn.append(CurrentVar)
count = 0
for i in regOut:
	results.append(regstats(i, regIn[count]))
	count += 1
```



	