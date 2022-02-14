## Precalculating the Design Matrix
The following are the descriptions for calculating the parameters for Model 6. The following details should be sufficient to work out how to process the other models.

See [[Linear Regression]] for further explanation.
In the situation where the dependent (Out) variable is brain data and the independent variables are not, the pseudoinverse can be pre-calculated and then multiplied by every voxel in the dependent variable.
## Possible Situations
- ### No brain imaging data
 
```python
	size(A) --> [N,1]
	size(B) --> [N,1]
	size(C) --> [N,1]
	size(W) --> [N,1]	
	
	Out = ['',B', 'C','']
		 
	In = [[],['A','W'],['A','B','W'],[]]
	Inter = [ [[]], [['A','W']], [['B','W'], ['A','W']], [[]] ]

	b1 = regstats(B,[A W demean(A)*demean(W)])
	size(b1) --> [1,4]

	regstats(C, [A B W demean(B)*demean(W) demean(A)*demean(W)])
	size(b1) --> [1,6]

```

- ### One of the out variables is brain data

 ```python
	size(A) --> [N,1]
	size(B) --> [N,Nvoxels]
	size(C) --> [N,1]
	size(W) --> [N,1]	
	
	Out = ['',B', 'C','']
		 
	In = [[],['A','W'],['A','B','W'],[]]
	Inter = [ [[]], [['A','W']], [['B','W'], ['A','W']], [[]] ]

	pX = pseudoinverse([A W demean(A)*demean(W)])
	for i in B:
		b1(count,:) = pX*i
	size(b1) --> [Nvoxels,4]
	
	for i in B:
		b2(count,:) = regstats(C, [A i W demean(i)*demean(W) demean(A)*demean(W)])
	size(b2) --> [Nvoxels,6]
		   
```
- ### One In variable is brain data
 ```python
	size(A) --> [N,Nvoxels]
	size(B) --> [N,1]
	size(C) --> [N,1]
	size(W) --> [N,1]	
	
	Out = ['',B', 'C','']
		 
	In = [[],['A','W'],['A','B','W'],[]]
	Inter = [ [[]], [['A','W']], [['B','W'], ['A','W']], [[]] ]
	for i in A:
		   b1(count,:) = regstats(B,[i W demean(i)*demean(W)])
	size(b1) --> [Nvoxels,4]
	for i in A:
		b2(count,:) = regstats(C, [i B W demean(B)*demean(W) demean(i)*demean(W)])
	size(b2) --> [Nvoxels,6]
```

### One of the out variables is brain data
```python
	size(A) --> [N,1]
	size(B) --> [N,1]
	size(C) --> [Nvoxels,1]
	size(W) --> [N,1]	
	
	Out = ['',B', 'C','']
		 
	In = [[],['A','W'],['A','B','W'],[]]
	Inter = [ [[]], [['A','W']], [['B','W'], ['A','W']], [[]] ]

	b1 = regstats(B,[A W demean(A)*demean(W)])
	size(b1) --> [1,4]
		   
	pX = pseudoinverse([A B W demean(B)*demean(W) demean(A)*demean(W)])
	for i in C:
		b2(count,:) = pX*i
	size(b2) --> [Nvoxels,6]

```



	