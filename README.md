# Sparsity-analysis
Some quick tips for sparsity analysis, including reduction in a matrix of abundance

# How does it work?
# 1. Load the matrix with the protein abundance
# 2. Apply the protein_missingness() function to the matrix
# 3. Remove the proteins with more than, let's say, 20% of missing values
# 4. Save the matrix with the missingness column
# 5. Plot a histogram of the protein missing values
