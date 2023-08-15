## Module 2 Quiz

#### Q1. What percentage of variation is explained by the 1st principal component in the data set if you: 1) Do no transformations? 2) log2(data + 1) transform? 2) log2(data + 1) transform and subtract row means?
<p><b>Answer:</b> a. 0.89 b. 0.97 c. 0.35</p>

#### Q2. Perform the log2(data + 1) transform and subtract row means from the samples. Set the seed to 333 and use k-means to cluster the samples into two clusters. Use svd to calculate the singular vectors. What is the correlation between the first singular vector and the sample clustering indicator?
<p><b>Answer:</b> 0.87</p>

#### Q3. Fit a linear model relating the first gene’s counts to the number of technical replicates, treating the number of replicates as a factor. Plot the data for this gene versus the covariate. Can you think of why this model might not fit well?
<p><b>Answer:</b> There are very few samples with more than 2 replicates so the estimates for those values will not be very good.</p>

#### Q4. Fit a linear model relating he first gene’s counts to the age of the person and the sex of the samples. What is the value and interpretation of the coefficient for age?
<p><b>Answer:</b> -23.91. This coefficient means that for each additional year of age, the count goes down by an average of 23.91 for a fixed sex.</p>

#### Q5. Perform the log2(data + 1) transform. Then fit a regression model to each sample using population as the outcome. Do this using the lm.fit function (hint: don’t forget the intercept). What is the dimension of the residual matrix, the effects matrix and the coefficients matrix?
<p><b>Answer:</b> Residual matrix:  129 x 52580 

Effects matrix: 129 x 52580

Coefficients matrix: 2 x 52580 </p>

#### Q6. Perform the log2(data + 1) transform. Then fit a regression model to each sample using population as the outcome. Do this using the lm.fit function (hint: don’t forget the intercept). What is the effects matrix?
<p><b>Answer:</b> </p>

#### Q7. Fit many regression models to the expression data where age is the outcome variable using the lmFit function from the limma package (hint: you may have to subset the expression data to the samples without missing values of age to get the model to fit). What is the coefficient for age for the 1,000th gene? Make a plot of the data and fitted values for this gene. Does the model fit well?
<p><b>Answer:</b> -27.61. The model doesn't fit well since there are two large outlying values and the rest of the values are near zero.</p>

#### Q8. Fit many regression models to the expression data where age is the outcome variable and tissue.type is an adjustment variable using the lmFit function from the limma package (hint: you may have to subset the expression data to the samples without missing values of age to get the model to fit). What is wrong with this model?
<p><b>Answer:</b> Since tissue.type tissue.type is a factor variable with many levels, this model has more coefficients to estimate per gene (18) than data points per gene (16).</p>

#### Q9. Why is it difficult to distinguish the study effect from the population effect in the Montgomery Pickrell dataset from ReCount?
<p><b>Answer:</b> The effects are difficult to distinguish because each study only measured one population. </p>

#### Q10. Set the seed using the command set.seed(33353) then estimate a single surrogate variable using the sva function after log2(data + 1) transforming the expression data, removing rows with rowMeans less than 1, and treating age as the outcome (hint: you may have to subset the expression data to the samples without missing values of age to get the model to fit). What is the correlation between the estimated surrogate for batch and age? Is the surrogate more highly correlated with race or gender?
<p><b>Answer:</b> 
Correlation with age: 0.20

More highly correlated with race.</p>
