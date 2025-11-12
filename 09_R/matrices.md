# Matrix
indexatioon using rows and columns
A[1,2]
A[1,] whole row
A[,2] whole column
Creating a matrix:
1. using 2 vectors = rbind(v1,v2) & cbind(v1,v2) and assign colnames() and rownames()
2. matrix() - generally not used as you dont often create from scratch
   matrix(data, row, column, byrow = T/F) By default it goes by column byrow = F

# Naming
vector
names(vector)
names(vector) = NULL

# Visualize
matplot()
tables in R = t(matrix)
