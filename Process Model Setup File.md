# Process Model Setup File
Permanent Note
Created: 01-20-2022 13:36


The setup file needs to have the following items in it:
- Number of boostrap resampling
- [[The direct effects matrix]]
- [[The interaction terms|Interaction effects matrix]]
	- Not all models will have interactions so if there are none, then this can be omitted
		- The code needs to react appropriately if it is omitted
- Path matrix


- Size of the data for each variable in the model
	- This may be used in the [[Mediation-moderation efficient coding|decisions made by the code]].



## References
1. 