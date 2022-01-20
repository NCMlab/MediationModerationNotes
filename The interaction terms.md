# The interaction terms
Permanent Note
Created: 01-10-2022 12:47


An interaction between A and B when predicting C is specified as:

| |A|B|C|
|---|---|---|---|
|A|0|0|0|
|B|0|0|0|
|C|1|1|0|

Each row in the interaction matrix is either all zeros or has at least two ones. Having to ones means there is a two-way interaction. It is also possible to have a three way interaction which would have three ones. In that case all two way interactions need to be specified in the model also. 


```mermaid
graph LR;
A-->{ }-->C;
W-->{ }--C;

```
## References
1. 