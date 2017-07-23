# Charpter 2 Overview of Supervised Learning
## 2.2 Variable Types and Terminology
This distinction in output type has led to a naming convention for the<br>
prediction tasks: `regression` when we predict quantitative outputs, and<br> 
`classification` when we predict qualitative outputs.<br>
**Notation**<br>
*X*--n input variable/a vector<br>
*X*<sub>*j*</sub>--components in *X*<br>
*Y*--quantitative outputs<br>
*G*--qualitative outputs
*x*<sub>*i*</sub>--the ith observed value of *X*<br>
**X**--N x p matrix, N input p-vectors *x*<sub>*i*</sub>, *i*=1,2,...,N<br>
Since all vectors are assumed to be column vectors, the *i*th row of **X** is *x*<sup>T</sup><sub>i</sub>, the vector transpose of *x*<sub>i</sub>.
## 2.3 Two Simple Approaches to Prediction: Least Squares and Nearest Neighbors
### 2.3.1 Linear Models and Least Squares
Given a vector of inputs *X*<sup>T</sup> = (X1,X2, . . . ,Xp), we predict the output *Y*  via the model<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20\hat{Y}=\hat{\beta_o}+%20\sum_{j=1}^{p}{X_j}{\hat\beta_j}">


