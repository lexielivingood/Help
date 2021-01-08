# (PART) DataCamp {-} 

# Introduction to R

<https://learn.datacamp.com/courses/free-introduction-to-r>

# Intro to basics

### Use # to add comments that aren't run as R code

## Math 

### Addition: 
3 + 4
### Subtraction: 
5 - 5 
### Multiplication:
3 * 5
### Division: (w/ parentheses)
(5 + 5) / 2
### Exponentiation: 
2^5
### Modulo:(remainder of division)
28 %% 6

## Store a value as a variable 

### Assign a value 4 to the variable my_var using this command:
my_var <- 4

### Type the name of the variable to print to show value 
my_var

### Add 2 variables together 
my_apples <- 4
my_oranges <- 4
my_apples + my_oranges 

## Basic data types

#### adding different data types together won't work
4 + six

#### Decimal values like 4.5 are called numerics.Whole numbers like 4 are called integers. Integers are also numerics.Boolean values (TRUE or FALSE) are called logical.Text (or string) values are called characters.

### quotation marks indicate that "some text" is a string
my_character <- "universe"
my_character 

### Check data type to avoid errors with class()
class(my_character)

## Vectors
### Vectors = one-dimension arrays that can hold data

### Create a vector with c()
numeric_vector <- c(1, 2, 3)
character_vector <- c("a", "b", "c")
numeric_vector
character_vector

## Naming a vector

### Give names to the elements of a vector 
some_vector <- c("Element1", "Element2")
names(some_vector) <- c("Name1", "Name2")
some_vector

### You can create a variable for names for elements of a vector 
poker_vector <- c(140, -50, 20, -120, 240)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
poker_vector

### Calculate totals from vectors: if you sum 2 vectors, it takes the element-wise sum
c(1, 2, 3) + c(4, 5, 6)
c(1 + 4, 2 + 5, 3 + 6)

### Calculations can be done with variables
a <- c(1, 2, 3) 
b <- c(4, 5, 6)
c <- a + b
c

### Calculate sum of all elements of a vector with sum()
sum(poker_vector)

### Check if one sum is greater than another
roulette_vector <- c(-24, -50, 100, -350, 10)
sum(poker_vector) > sum(roulette_vector)

### Select specific elements of a vector: type name of vector then tyoe the number of the element in brackets (first element is 1)
poker_vector[1]

### Select multiple elements of a vector with c() inside brackets
poker_vector[c(1,5)]

### c(2, 3, 4) can be abbreviated to 2:4
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

#Merge matrices/vectors by row
rbind(star_wars_matrix, c(1,2))

#Calculate totals for each column of matrix
colSums(star_wars_matrix)

#You can use [] to select specific elements from a matrix. Use a comma to separate rows from columns with the rows on the left:
star_wars_matrix[1,2]

#Select all elements of a row or column by leaving out the number on the other side of the comma:
star_wars_matrix[,1]
star_wars_matrix[1,]

#Math w/ matrices
#Use standard operators (+, *, etc)
#Multiply matrix by 2
star_wars_matrix * 2

#Matrices can be multiplied by eachother where each element is the product of the cooresponding elements
star_wars_matrix * star_wars_matrix

## Factors
#Factor = statistical data type used to store catagorical variables 
#A catagorical variable can belong to a limited number of categories, as opposed to a continuous variable that can respon to an infinite number of values 

#Use the function factor() to create factors

#First, create a vector that contains limited number of categories 
sex_vector <- c("Male", "Female", "Female", "Male", "Male")
sex_vector
#(this vector has 2 categories)

#Encode vector as a factor:
factor_sex_vector <- factor(sex_vector)
factor_sex_vector

#There are 2 types of categorical variables: 
#1) Nominal categorical variables do not have an implied order
#2) Ordinal categorical variables do have an apparent order

#Factor levels:
#factors can contain specific factor levels. Use levels() to change names of these levels.
levels(factor_sex_vector) <- c("name1", "name2")
factor_sex_vector

#Pay attention to the order in which you assign levels; if you don;t specify the levels of the factor, they will be assigned alphabetically. Type: 
levels(factor_sex_vector)
#to see outputs in the order which you should type the corresponding names

#Summarizing a factor 
#The command summary() will give you an overview of the contents of a variable
summary(sex_vector)

#You can try to compare values in a factor...
female <- factor_sex_vector[2]
male <- factor_sex_vector[1]
male > female
#But it won't work b/c male and female are nominal factor levels

#Ordered factors
#example, first create a vector:
speed_vector <- c("medium", "slow", "slow", "medium", "fast")

#convert speed_vector from an unordered factor (defult using factor()) to an ordinal one
#Do this by adding two additional arguments: ordered and levels
factor_speed_vector <- factor(speed_vector,
ordered = TRUE,
levels = c("slow", "medium", "fast"))

#We can now compare elements as factor_speed_vector is ordered
#Compare second and fifth values
factor_speed_vector[2] > factor_speed_vector[5]

## Data frames
#Data frames have variables of a data set as columns and the observations as rows
#It can be useful to show a small part of a data set. Use function head() to show first observations of a data frame. Use function tail() to show last observations.
#Both functions print a "header" which has names of variables

#The function str() shows the structure of a data set

#Creating a data frame
#Use the data.frame() function
#You can use [] to select elements from a data frame

## Lists