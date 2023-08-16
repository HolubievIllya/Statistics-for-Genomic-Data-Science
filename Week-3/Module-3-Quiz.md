## Module 3 Quiz

#### Q1. Load the example SNP data with the following code: Fit a linear model and a logistic regression model to the data for the 3rd SNP. What are the coefficients for the SNP variable? How are they interpreted? (Hint: Don’t forget to recode the 0 values to NA for the SNP data)
<p><b>Answer:</b>         </p>

#### Q2. In the previous question why might the choice of logistic regression be better than the choice of linear regression?
<p><b>Answer:</b>         </p>

#### Q3. Load the example SNP data with the following code: Fit a logistic regression model on a recessive (need 2 copies of minor allele to confer risk) and additive scale for the 10th SNP. Make a table of the fitted values versus the case/control status. Does one model fit better than the other?
<p><b>Answer:</b>         </p>

#### Q4. Load the example SNP data with the following code: What is the average effect size? What is the max? What is the minimum?
<p><b>Answer:</b> Average effect size =  0.007, minimum = -4.25, maximum = 3.90</p>

#### Q5. Load the example SNP data with the following code: What is the correlation with the results from using snp.rhs.tests and chi.squared? Why does this make sense?
<p><b>Answer:</b> > 0.99. They are both testing for the same association using the same additive regression model on the logistic scale but using slightly different tests. </p>

#### Q6. Load the Montgomery and Pickrell eSet: Do the log2(data + 1) transform and fit calculate F-statistics for the difference between studies/populations using genefilter:rowFtests and using genefilter:rowttests. Do you get the same statistic? Do you get the same p-value?
<p><b>Answer:</b>             </p>

#### Q7. Load the Montgomery and Pickrell eSet: First test for differences between the studies using the DESeq2 package using the DESeq function. Then do the log2(data + 1) transform and do the test for differences between studies using the limma package and the lmFit, ebayes and topTable functions. What is the correlation in the statistics between the two analyses? Are there more differences for the large statistics or the small statistics (hint: Make an MA-plot).
<p><b>Answer:</b> 0.93. There are more differences for the small statistics.</p>

#### Q8. Apply the Benjamni-Hochberg correction to the P-values from the two previous analyses. How many results are statistically significant at an FDR of 0.05 in each analysis?
<p><b>Answer:</b> DESeq = 1995 significant; limma = 2807 significant</p>

#### Q9. Is the number of significant differences surprising for the analysis comparing studies from Question 8? Why or why not?
<p><b>Answer:</b> Yes and no. It is surprising because there is a large fraction of the genes that are significantly different, but it isn't that surprising because we would expect that when comparing measurements from very different batches. </p>

#### Q10. Suppose you observed the following P-values from the comparison of differences between studies. Why might you be suspicious of the analysis?
<p><b>Answer:</b> The p-values should have a spike near zero (the significant results) and be flat to the right hand side (the null results) so the distribution pushed toward one suggests something went wrong. </p>
