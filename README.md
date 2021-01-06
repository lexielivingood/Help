# (PART) DataCamp {-} 

# Introduction to R

<https://learn.datacamp.com/courses/free-introduction-to-r>

## Intro to basics

#HOW IT WORKS

#Use # to add comments that aren't run as R code

#Math W/ R

#Addition: 
3 + 4
#Subtraction: 
5 - 5 
#Multiplication:
3 * 5
#Division: (w/ parentheses)
(5 + 5) / 2
#Exponentiation: 
2^5
#Modulo:(remainder of division)
28 %% 6

#STORE A VALUE AS A VARIABLE

#Assign a value 4 to the variable my_var:
my_var <- 4

#type name of variable to print to show value 
my_var

#Add 2 variables together 
my_apples <- 4
my_oranges <- 4
my_apples + my_oranges 

#BASIC DATA TYPES

#adding different data types together won't work
4 + six

#Decimal values like 4.5 are called numerics.
#Whole numbers like 4 are called integers. Integers are also numerics.
#Boolean values (TRUE or FALSE) are called logical.
#Text (or string) values are called characters.
#quotation marks indicate that "some text" is a string
my_character <- "universe"
my_character 

#CHECK DATA TYPE TO AVOID ERRORS 
class(my_character)


## Vectors

#Vectors = one-dimension arrays that can hold data
#CREATE A VECTOR 
numeric_vector <- c(1, 2, 3)
character_vector <- c("a", "b", "c")

#NAMING A VECTOR
#Give names to the elements of a vector 
some_vector <- c("Element1", "Element2")
names(some_vector) <- c("Name1", "Name2")
some_vector

#You can create a variable for names for elements of a vector 
poker_vector <- c(140, -50, 20, -120, 240)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
poker_vector

#Calculate totals from vectors
#if you sum 2 vectors, it takes the element-wise sum
c(1, 2, 3) + c(4, 5, 6)
c(1 + 4, 2 + 5, 3 + 6)

#Calculations can be done with variables
a <- c(1, 2, 3) 
b <- c(4, 5, 6)
c <- a + b

#Calculate sum of all elements of a vector 
sum(poker_vector)

#Check if one sum is greater than another
roulette_vector <- c(-24, -50, 100, -350, 10)
sum(poker_vector) > sum(roulette_vector)

#Select specific elements of a vector 
#type name of vector than number of element in [] (first element is 1)
poker_vector[1]

#Select multiple elements of a vector with c() inside brackets
poker_vector[c(1,5)]

#c(2, 3, 4) can be abbreviated to 2:4
poker_vector[2:4]

#Assigned names can be used instead of numerical values
poker_vector["Monday"]
poker_vector [c("Monday", "Friday")]

#Calculate average values
mean(poker_vector)

#SELECTION BY COMPARISON
#The (logical) comparison operators known to R are:
#< less than 
poker_vector < roulette_vector
#> greater than 
poker_vector > roulette_vector
#<= less than or equal to
poker_vector <= roulette_vector
#>= greater than or equal to
poker_vector >= roulette_vector
#== equal to each other
poker_vector == roulette_vector
#!= not equal to each other
poker_vector != roulette_vector

#Comparison operators can also be used on vectors
c(4, 5, 6) > 5

#Find which elements are greater than 0
poker_vector > 0
#Assign a variable
selection_vector <- poker_vector > 0
#Select desired elements
poker_vector[selection_vector]
#R will only select elements that are TRUE in selection_vector]

## Matrices

#A matrix is a group of elements of the same data type arranged into rows and columns.
#use matrix() function

#Example:
matrix(1:9, byrow = TRUE, nrow = 3)
# 1:9 = elements that R will arrange into the rows and columns of the matrix.
# byrow = TRUE the matrix is filled by the rows.
# byrow = FALSE = the matrix is filled by the columns
# nrow = number of rows.

#Analyze matrices
#Three given vectors
new_hope <- c(460.998, 314.4)
empire_strikes <- c(290.475, 247.900)
return_jedi <- c(309.306, 165.8)
#Combine multiple vectors into a single one
box_office <- c(new_hope, empire_strikes, return_jedi)
#Contruct a matrix from vector 
star_wars_matrix <- matrix(box_office, byrow = TRUE, nrow = 3)
star_wars_matrix

#Naming a matrix 
#You can add names for the rows and the columns of a matrix
#Vectors used for naming:
region <- c("US", "non-US")
titles <- c("A New Hope", "The Empire Strikes Back", "Return of the Jedi")
#Name the columns with colnames()
colnames(star_wars_matrix) <- region
#Name the rows with rownames() then print
rownames(star_wars_matrix) <- titles
star_wars_matrix

#Calculate totals for each row of matrix 
worldwide_vector <- rowSums(star_wars_matrix)

#Merge matrices/vectors by column
all_wars_matrix <- cbind(star_wars_matrix, worldwide_vector)

## Factors


## Data frames


## Lists