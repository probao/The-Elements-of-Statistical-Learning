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
**X**--N x p column matrix, N input p-vectors *x*<sub>*i*</sub>, *i*=1,2,...,N<br>
Since all vectors are assumed to be column vectors, the *i*th row of **X** is *x*<sup>T</sup><sub>i</sub>, the vector transpose of *x*<sub>i</sub>.
## 2.3 Two Simple Approaches to Prediction: Least Squares and Nearest Neighbors
### 2.3.1 Linear Models and Least Squares
Given a vector of inputs *X*<sup>T</sup> = (X1,X2, . . . ,Xp), we predict the output *Y*  via the model<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20\hat{Y}=\hat{\beta_o}+%20\sum_{j=1}^{p}{X_j}{\hat\beta_j}"><br>
It is convenient to include the constant variable 1 in *X*, and then write the linear model in vector form
as an inner product<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20\hat{Y}=X^T\hat{\beta}"><br>
We pick the coefficients β to minimize the residual sum of squares(RSS)<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20RSS(\beta)=%20\sum_{i=1}^{N}(y_i-x_i^T\beta)^2"><br>
<img src="http://latex.codecogs.com/gif.latexx?\%20RSS(\beta)=%20(y-X\beta)^T(y-X\beta)"><br>
Differentiating w.r.t. *β* we get the *normal equations*<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20X^T(y-X\beta)=0"><br>
If X<sup>T</sup>X is nonsingular, then the unique solution is given by
<img src="http://latex.codecogs.com/gif.latexx?\%20\hat{\beta}=(X^TX)^{-1}X^Ty"><br>


