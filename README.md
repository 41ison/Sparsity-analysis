# Sparsity analysis and imputation of missing values in proteomics data
Some quick tips for sparsity analysis, including reduction in a matrix of abundance

# How does it work?
1. Load the matrix with the protein abundance
2. Apply the protein_missingness() function to the matrix
3. Remove the proteins with more than, let's say, 20% of missing values
4. Save the matrix with the missingness column
5. Plot a histogram of the protein missing values

In order to facilitate the analysis, we can create some functions to be used in the analysis.
Your matrix must have the genes or proteins in the rows and the samples in the columns. After running the `protein_missingness()` function, the column `prot_miss` will be created in the matrix. This column will store the percentage of missing values for each protein. The `remove_missing()` function will remove the proteins with more than a specific percentage of missing values.

# Important assumptions about the abundance matrix: 
1. you have the proteins in the rows and the samples in the columns.
2. naturally, the matrix has some missing values.

# Steps to follow to reduce sparsity on the matrix
You can apply this method regardless the orgin of the matrix with abundance of proteins (DIANN, FragPipe, MaxQuant, etc).

# Check whether the missing values are missing at random (MAR)
This function computes the Little's MCAR test to check whether the missing values are missing at random (MAR).
If the p-value is less than 0.05, the missing values are not missing at random.
You need the {naniar} package to run this function.

# We will follow the steps below to impute the missing values using random forest regression.
We are assuming reasonable that the missing values are missing at random (MAR).
If you have a different assumption, you can change the method of imputation accordingly.
Here the {mice} package is used to impute the missing values.
