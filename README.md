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

## Matrices


## Factors


## Data frames


## Lists