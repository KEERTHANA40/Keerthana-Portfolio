# how to check functions
?func()

# Packages and libraries
libraries - set of functions
packages - folder to store libraries
CRAN - Comprehensive R Archive network

# Reading a file from outside
filename = read.csv(file.choose())

# Visualizing the data
ggplot2

# Assigning a value
x <- 2L # L not given number by default is stored as double, with L its integer 
typeof(x) = integer, double, complex, character, logical (boolean)

# Operations
Add, sub, multiply *, Div /, sqrt, < > ! == != >= <= / & isTrue(variable)

# Loops
while()
for()

# Vector same datatype
If there is even one character in the vectore, then the complete typeof(vector) is character
1:5 = 1 2 3 4 5
Similar to array in other languages
indexation starts from 1
c() = creating a vector, combine
a = seq(1,15,2) along with start and end third number is about the difference between numbers
replicate = rep(3,50) - repeats 3 number 50 times, it can be number/character/vector
[] - indexing starts with 1 in R
[1] = first, [2] = second and so on
[-1] = all others except first, same for all
for PRINTING no for loop needed, use indexing and print the vectors.

# Type checks
is.numeric()
is.integer()
is.double()

# Conditions
if() else() elseif

# Random variables - Statistical knowledge
rnorm() - set of numbers randomly distributed.
The likelihood of the number generated percentages are shown in the bell curve.

# Law of large numbers (LLN):
eg : coin tosses
n = 100 count tosses, x = check measure of heads and tails, 1 if heads, 0 if tails
xn -> E(x) when n -> infinity
when n is approaching infinity, actually measured value meets/converges the expected value.
