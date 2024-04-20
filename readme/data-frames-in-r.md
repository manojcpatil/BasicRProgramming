---
description: >-
  Let's elaborate further on data frames in R, covering how to create, combine,
  add variables, add rows, and introduce key functions related to data frames.
---

# Data Frames in R

### 1. Creating Data Frames

A **data frame** in R is a tabular data structure consisting of rows and columns, where each column can be of a different data type (numeric, character, factor, etc.). You can create a data frame using the `data.frame()` function, specifying columns as vectors.

```R
# Creating a data frame from vectors
name <- c("Alice", "Bob", "Charlie")
age <- c(25, 30, 28)
city <- c("New York", "Los Angeles", "Chicago")

# Combine vectors into a data frame
df <- data.frame(Name = name, Age = age, City = city)
print(df)
#     Name Age         City
# 1  Alice  25     New York
# 2    Bob  30  Los Angeles
# 3 Charlie  28      Chicago
```

### 2. Combining Data Frames

### Combining by Rows (`rbind()`)

You can combine two or more data frames by rows using `rbind()` function.

```R
# Create two data frames
df1 <- data.frame(Name = c("David", "Eva"), Age = c(35, 40))
df2 <- data.frame(Name = c("Frank", "Grace"), Age = c(45, 50))

# Combine by rows
combined_df_rows <- rbind(df1, df2)
print(combined_df_rows)
#    Name Age
# 1 David  35
# 2   Eva  40
# 3 Frank  45
# 4 Grace  50
```

### Combining by Columns (`cbind()`)

You can combine two or more data frames by columns using `cbind()` function.

```R
# Combine by columns
combined_df_cols <- cbind(df, df1$Age, df2$Age)
colnames(combined_df_cols) <- c("Name", "Age", "City", "Age2", "Age3")
print(combined_df_cols)
#     Name Age         City Age2 Age3
# 1  Alice  25     New York   35   45
# 2    Bob  30  Los Angeles   40   50
# 3 Charlie  28      Chicago   NA   NA
```

### 3. Adding Variables to Data Frames

You can add new variables (columns) to an existing data frame using the assignment operator (`$`) or by directly assigning values to new columns.

```R
# Adding a new variable to the data frame
df$Gender <- c("Female", "Male", "Male")
print(df)
#     Name Age         City Gender
# 1  Alice  25     New York Female
# 2    Bob  30  Los Angeles   Male
# 3 Charlie  28      Chicago   Male
```

### 4. Adding Rows to Data Frames

You can add new rows to an existing data frame using the `rbind()` function.

```R
# Adding new rows to the data frame
new_row <- data.frame(Name = "Diana", Age = 33, City = "Miami", Gender = "Female")
df <- rbind(df, new_row)
print(df)
#     Name Age         City Gender
# 1  Alice  25     New York Female
# 2    Bob  30  Los Angeles   Male
# 3 Charlie  28      Chicago   Male
# 4  Diana  33        Miami Female
```

### 5. Key Functions Related to Data Frames

### Accessing Elements

* `head(df)`, `tail(df)`: View the first or last few rows of a data frame.
* `dim(df)`: Get the dimensions (rows, columns) of a data frame.
* `names(df)`: Get the column names of a data frame.
* `str(df)`: Display the structure of a data frame.

### Manipulating Data Frames

* `subset(df, condition)`: Extract a subset of rows based on a condition.
* `merge(df1, df2, by = "key_column")`: Merge two data frames based on a common key column.
* `transform(df, new_column = expression)`: Create a new column using expressions based on existing columns.

### Summary

Data frames are versatile data structures in R, widely used for storing and manipulating tabular data. Understanding how to create, combine, add variables, and perform operations on data frames using key functions is essential for data analysis and manipulation tasks in R.

By mastering these concepts and functions, students can effectively work with structured data and perform various analytical tasks using R programming.
