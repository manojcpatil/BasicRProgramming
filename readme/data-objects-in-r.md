---
description: >-
  Let's elaborate on the data objects in R, covering basic data objects,
  matrices, arrays, lists, and factors, with examples for each:
---

# Data Objects in R

###

#### 1. Basic Data Objects

In R, basic data objects include scalars, vectors, arrays, matrices, lists, and data frames. These objects serve as fundamental building blocks for organizing and manipulating data.

**Scalars and Vectors**

A **scalar** in R represents a single value, while a **vector** is a sequence of values of the same data type. Vectors can be numeric, character, logical, or complex.

```R
# Scalar
scalar <- 10

# Numeric vector
numeric_vector <- c(10, 20, 30, 40)

# Character vector
character_vector <- c("apple", "banana", "orange")

# Logical vector
logical_vector <- c(TRUE, FALSE, TRUE, TRUE)
```

#### 2. Matrices

A **matrix** is a 2-dimensional array where each element must be of the same data type. Matrices are created using the `matrix()` function.

```R
# Creating a matrix
matrix_data <- matrix(data = c(1, 2, 3, 4, 5, 6), nrow = 2, ncol = 3, byrow = TRUE)
print(matrix_data)
#      [,1] [,2] [,3]
# [1,]    1    2    3
# [2,]    4    5    6
```

#### 3. Arrays

An **array** is a multi-dimensional extension of a matrix where each element must be of the same data type. Arrays are created using the `array()` function.

```R
# Creating an array
array_data <- array(data = c(1, 2, 3, 4, 5, 6), dim = c(2, 3, 1))
print(array_data)
# , , 1
#
#      [,1] [,2] [,3]
# [1,]    1    3    5
# [2,]    2    4    6
```

#### 4. Lists

A **list** is a versatile data structure in R that can hold elements of different data types (e.g., vectors, matrices, or even other lists). Lists are created using the `list()` function.

```R
# Creating a list
list_data <- list(
  numeric_vector = c(10, 20, 30),
  character_vector = c("apple", "banana", "orange"),
  matrix_data = matrix(data = c(1, 2, 3, 4), nrow = 2, ncol = 2)
)
print(list_data)
# $numeric_vector
# [1] 10 20 30
#
# $character_vector
# [1] "apple"  "banana" "orange"
#
# $matrix_data
#      [,1] [,2]
# [1,]    1    3
# [2,]    2    4
```

#### 5. Factors

A **factor** is a special data object used to represent categorical data. Factors are created using the `factor()` function.

```R
# Creating a factor
gender <- c("Male", "Female", "Male", "Female", "Male")
factor_gender <- factor(gender)
print(factor_gender)
# [1] Male   Female Male   Female Male  
# Levels: Female Male
```

#### Summary

Understanding different data objects in R is essential for effective data manipulation and analysis. Each data object has its purpose and can be used in various ways to organize and process data efficiently.

By mastering these data objects, students can leverage R's capabilities to handle different types of data and perform complex analyses in fields like statistics, data science, and machine learning.

