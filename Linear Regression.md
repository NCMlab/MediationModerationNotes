# Linear Regression
Permanent Note
Created: 01-20-2022 13:40


Linear regression is modeling a variable as a linear function of other variables.

$Y = \beta_0 + \beta_1 \cdot x_1 + \beta_2 \cdot x_2 + ...+ \epsilon$
 
This reads as Y is a weight linear combination of the x variables.
The equation may also be written in matrix format.
$$
X=[x_1 \space x_2 \space x_3]
$$
$$ 
b=[\beta_1 \space \beta_2 \space \beta_3]
$$
$$
Y=Xb
$$
This equation is solved for b
$$
X^T Y = X^T X b
$$
$X^TX$ is now a square matrix.

$$
(X^TX)^{-1}X^T Y = (X^TX)^{-1}X^T X b
$$
$$
(X^TX)^{-1}X^T Y = b
$$
## Precalculation
If the independent varivale $Y$ is brain imaging data, then the following is allowed:
```python
	Nvoxels
	transX = transpose(X)
	pX = inverse(X*transX)*transX
	beta = size(Nvoxels, NcolumnsInX)
	for i in Y:
		beta = pX*i
```

The pX variable is also called the pseudoinverse of X
## References
1. 