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
If X<sup>T</sup>X is nonsingular, then the unique solution is given by<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20\hat{\beta}=(X^TX)^{-1}X^Ty"><br>
<font color=#0099ff>Scenario 1</font>: The training data in each class were generated from bivariate
Gaussian distributions with uncorrelated components and different
means.<br>
<font color=#0099ff>Scenario 2</font>: The training data in each class came from a mixture of 10 low-
variance Gaussian distributions, with individual means themselves
distributed as Gaussian.<br>
### 2.3.2 Nearest-Neighbor Methods
Nearest-neighbor methods use those observations in the training set T closest in input space to x to form Y-hat . Specifically, the k-nearest neighbor fit for Y-hat is defined as follows:<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20\hat{Y}(x)%20=\frac{1}{2}\sum_{x_i%20\in%20N_k(x)}y_i"><br>
It is also clear that we cannot use sum-of-squared errors on the training
set as a criterion for picking k, since we would always pick k = 1! It would
seem that k-nearest-neighbor methods would be more appropriate for the
mixture Scenario 2 described above, `while for Gaussian data the decision
boundaries of k-nearest neighbors would be unnecessarily noisy.`<br>
### 2.3.3 From Least Squares to Nearest Neighbors
The following list describes some ways in which these simple procedures have been enhanced:<br>
* Kernel methods use weights that decrease smoothly to zero with dis-
tance from the target point, rather than the effective 0/1 weights used
by k-nearest neighbors.<br>
* In high-dimensional spaces the distance kernels are modified to emphasize some variable more than others.
* Local regression fits linear models by locally weighted least squares, rather than fitting constants locally.
* Linear models fit to a basis expansion of the original inputs allow arbitrarily complex models.
* Projection pursuit and neural network models consist of sums of non-linearly transformed linear models.
### 2.4 Statistical Decision Theory
Statistical Decision Theory requires a loss function L(Y, f(X)) for penalizing errors in prediction, and by far the most
common and convenient is squared error loss:<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20\L(Y,%20f(x))=(Y-f(x))^2"><br>
This leads us to a criterion for choosing f,<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20EPE(f)=E(Y-f(x))^2=\int{[y-f(x)]^2Pr(dx,dy)}"><br>
By conditioning on X, we can write EPE as:<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20EPE(f)=E(Y-f(x))^2=E_XE_Y_|_X([Y-f(x)]^2|X)"><br>
and we see that it suffices to minimize EPE pointwise:<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20f(x)=argmin_cE_Y_|_X([Y-c]^2|X=x)"><br>
The solution is<br>
<img src="http://latex.codecogs.com/gif.latexx?\%20f(x)=E(Y|X=x)"><br>
So both k-nearest neighbors and least squares end up approximating conditional expectations by averages. But they differ dramatically in terms of model assumptions:<br>
* Least squares assumes f(x) is well approximated by a globally linear function.<br>
* k-nearest neighbors assumes f(x) is well approximated by a locally constant function.<br>

p39





