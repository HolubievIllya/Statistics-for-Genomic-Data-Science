## Module 4 Quiz

#### Q1. When performing gene set analysis it is critical to use the same annotation as was used in pre-processing steps. Read the paper behind the Bottomly data set on the ReCount database: http://www.ncbi.nlm.nih.gov/pubmed?term=21455293 Using the paper and the function: supportedGenomes() in the goseq package can you figure out which of the Mouse genome builds they aligned the reads to.
<p><b>Answer:</b> UCSC mm9</p>

#### Q2. Load the Bottomly data with the following code and perform a differential expression analysis using limma with only the strain variable as an outcome. How many genes are differentially expressed at the 5% FDR level using Benjamini-Hochberg correction? What is the gene identifier of the first gene differentially expressed at this level (just in order, not the smallest FDR) ? (hint: the featureNames function may be useful)
<p><b>Answer:</b> 223 at FDR 5%; 
ENSMUSG00000000402 first DE gene</p>

#### Q3. Use the nullp and goseq functions in the goseq package to perform a gene ontology analysis. What is the top category that comes up as over represented? (hint: you will need to use the genome information on the genome from question 1 and the differential expression analysis from question 2.
<p><b>Answer:</b> GO:0004888</p>

#### Q4. Look up the GO category that was the top category from the previous question. What is the name of the category?
<p><b>Answer:</b> transmembrane signaling receptor activity</p>


#### Q5. Load the Bottomly data with the following code and perform a differential expression analysis using limma and treating strain as the outcome but adjusting for lane as a factor. Then find genes significant at the 5% FDR rate using the Benjamini Hochberg correction and perform the gene set analysis with goseq following the protocol from the first 4 questions. How many of the top 10 overrepresented categories are the same for the adjusted and unadjusted analysis?
<p><b>Answer:</b> 3</p>




