## Module 1 Quiz

#### Q1. Susan asks Joe for his data shared according to the data sharing plan discussed in the lectures. Which of the following are reasons the study may be reproducible, but not replicable?
<p><b>Answer:</b> The identified effect can be reproduced from Joe's code and data, but may be due only to random variation and not appear in future studies.</p>

#### Q2. Put the following code chunk at the top of an R markdown document called test.Rmd but set eval=TRUE
<p><b>Answer:</b> The plot is random the first time you knit the document. It is identical to the first time the second time you knit the document. After removing the folders test_cache and test_files they generate new random versions.</p>

#### Q3. Create a summarizedExperiment object with the following code 
#### library(Biobase)
#### library(GenomicRanges)
#### data(sample.ExpressionSet, package = "Biobase")
#### se = makeSummarizedExperimentFromExpressionSet(sample.ExpressionSet)
<p><b>Answer:</b> Get the genomic table with assay(se) assay(se), get the phenotype table with colData(se) colData(se), get the feature data with rowData(se) rowData(se). rowRanges(se) rowRanges(se) gives information on the genomic location and structure of the measured features.</p>

#### Q4. Suppose that you have measured ChIP-Seq data from 10 healthy individuals and 10 metastatic cancer patients. For each individual you split the sample into two identical sub-samples and perform the ChIP-Seq experiment on each sub-sample. How can you measure (a) biological variability, (b) technical variability and (c) phenotype variability.
<p><b>Answer:</b> A) By looking at variation across samples from 10 different individuals with cancer
B) By looking at variability between the measurements on the two sub-samples from the same sample and
C) by comparing the average measurements on the healthy individuals to the measurements on the individuals with cancer.</p>

#### Q5. Just considering the phenotype data what are some reasons that the Bottomly data set is likely a better experimental design than the Bodymap data? Imagine the question of interest in the Bottomly data is to compare strains and in the Bodymap data it is to compare tissues.
<p><b>Answer:</b>  The covariates in the Bottomly data set (experiment number, lane number)  are balanced with respect to strain. The covariates in the Bodymap data set (gender, age, number of technical replicates) are not balanced with respect to tissue.</p>

#### Q6. What are some reasons why this plot is not useful for comparing the number of technical replicates by tissue (you may need to install the plotrix package).
<p><b>Answer:</b> The “mixture” category is split across multiple wedges.</p>

#### Q7. Which of the following code chunks will make a heatmap of the 500 most highly expressed genes (as defined by total count), without re-ordering due to clustering? Are the highly expressed samples next to each other in sample order?
<p><b>Answer:</b> row_sums = rowSums(edata)
  
edata = edata[order(-row_sums),]

index = 1:500

heatmap(edata[index,],Rowv=NA,Colv=NA)</p>

#### Q8. Make an MA-plot of the first sample versus the second sample using the log2 transform (hint: you may have to add 1 first) and the rlog transform from the DESeq2 package. How are the two MA-plots different? Which kind of genes appear most different in each plot?
<p><b>Answer:</b> The plots look pretty similar, but there are two strong diagonal stripes (corresponding to the zero count genes) in the 
log2
log2 plot. In both cases, the genes in the middle of the expression distribution show the biggest differences, but the low abundance genes seem to show smaller differences with the 
rlog
rlog transform.</p>

#### Q9. Cluster the data in three ways: With no changes to the data After filtering all genes with rowMeans less than 100 After taking the log2 transform of the data without filtering Color the samples by which study they came from (Hint: consider using the function myplclust.R in the package rafalib available from CRAN and looking at the argument lab.col.) How do the methods compare in terms of how well they cluster the data by study? Why do you think that is?
<p><b>Answer:</b> Clustering with or without filtering is about the same. Clustering after the log2 transform shows better clustering with respect to the study variable. The likely reason is that the highly skewed distribution doesn't match the Euclidean distance metric being used in the clustering example.</p>

#### Q10. Cluster the samples using k-means clustering after applying the log2 transform (be sure to add 1). Set a seed for reproducible results (use set.seed(1235)). If you choose two clusters, do you get the same two clusters as you get if you use the cutree function to cluster the samples into two groups? Which cluster matches most closely to the study labels?
<p><b>Answer:</b> They produce different answers. The k-means clustering matches study better. Hierarchical clustering would look better if we went farther down the tree but the top split doesn’t perfectly describe the study variable.</p>
