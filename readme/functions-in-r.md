# Functions in R

Let's elaborate on functions in R, covering elementary functions and applying functions to subsets, with examples for each:

### 1. Elementary Functions

R provides a wide range of built-in **elementary functions** that perform common mathematical and statistical operations on data. These functions can be used directly or in combination with other functions to perform complex analyses.

#### Examples of Elementary Functions:

* **Arithmetic Functions**: `sum()`, `mean()`, `median()`, `max()`, `min()`

```R
# Using arithmetic functions
numbers <- c(10, 20, 30, 40, 50)
total_sum <- sum(numbers)      # Calculates the sum of numbers
average <- mean(numbers)       # Calculates the mean of numbers
middle_value <- median(numbers) # Calculates the median of numbers
```

* **Statistical Functions**: `sd()` (standard deviation), `var()` (variance), `cor()` (correlation)

```R
# Using statistical functions
data <- c(10, 20, 30, 40, 50)
standard_deviation <- sd(data)  # Calculates the standard deviation
variance <- var(data)           # Calculates the variance
```

* **Mathematical Functions**: `sqrt()` (square root), `abs()` (absolute value), `log()` (natural logarithm)

```R
# Using mathematical functions
x <- 16
square_root <- sqrt(x)          # Calculates the square root of x
absolute_value <- abs(-10)      # Calculates the absolute value
natural_logarithm <- log(10)    # Calculates the natural logarithm of 10
```

### 2. Applying Functions to Subsets

In R, functions can be applied to subsets of data using techniques like indexing, logical subsetting, or grouping operations. This allows for targeted analysis and manipulation of specific parts of a dataset.

#### Examples of Applying Functions to Subsets:

* **Using Indexing**:

```R
# Applying a function to a subset using indexing
data <- c(10, 20, 30, 40, 50)
subset <- data[1:3]             # Selects the first three elements
subset_sum <- sum(subset)       # Calculates the sum of the subset
```

* **Using Logical Subsetting**:

```R
# Applying a function to a subset using logical subsetting
data <- c(10, 20, 30, 40, 50)
subset <- data[data > 20]       # Selects elements greater than 20
subset_mean <- mean(subset)     # Calculates the mean of the subset
```

* **Using Grouping Operations (e.g., `apply()` or `tapply()`)**:

```R
# Applying a function to subsets based on grouping
categories <- c("A", "A", "B", "B", "C")
values <- c(10, 20, 30, 40, 50)
category_mean <- tapply(values, categories, mean)  # Calculates mean by category
```

### Summary

Functions in R are powerful tools for performing computations, transformations, and analyses on data. Elementary functions provide essential mathematical and statistical operations, while applying functions to subsets enables targeted analysis of specific parts of a dataset.

By mastering these concepts, students can leverage functions effectively to manipulate data and derive insights from datasets in various applications of data analysis and statistical programming.
