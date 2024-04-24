# Exercises 1

#### 1. Write an R program to find the factors of a given number.

```R
find_factors <- function(num) {
  factors <- c()
  for (i in 1:num) {
    if (num %% i == 0) {
      factors <- c(factors, i)
    }
  }
  return(factors)
}

# Example usage:
number <- 36
result <- find_factors(number)
print(paste("Factors of", number, "are:", result))
```

#### 2. Write an R program to create a two-dimensional 5×3 array of sequence of even integers greater than 50.

```R
start <- 52
end <- 70  # 52 + (5*3) - 1 = 70
even_seq <- seq(start, end, by = 2)
matrix_5x3 <- matrix(even_seq, nrow = 5, ncol = 3, byrow = TRUE)
print(matrix_5x3)
```

#### 3. Write an R program to find row and column index of maximum and minimum value in a given matrix.

```R
find_max_min_indices <- function(mat) {
  max_val <- max(mat)
  min_val <- min(mat)
  
  max_index <- which(mat == max_val, arr.ind = TRUE)
  min_index <- which(mat == min_val, arr.ind = TRUE)
  
  return(list(max_value = max_val,
              max_row = max_index[,1],
              max_col = max_index[,2],
              min_value = min_val,
              min_row = min_index[,1],
              min_col = min_index[,2]))
}

# Example usage:
matrix_example <- matrix(c(3, 8, 12, 5, 7, 9), nrow = 2, byrow = TRUE)
result_indices <- find_max_min_indices(matrix_example)
print(result_indices)
```

#### 4. Write an R program to create a vector using : operator and `seq()` function.

```R
# Using : operator
vector_using_colon <- 1:10

# Using seq() function
vector_using_seq <- seq(from = 1, to = 10, by = 1)

print(vector_using_colon)
print(vector_using_seq)
```

#### 5. Write an R program to reverse the order of a given vector.

```R
reverse_vector <- function(vec) {
  return(rev(vec))
}

# Example usage:
original_vector <- c(1, 2, 3, 4, 5)
reversed_vector <- reverse_vector(original_vector)
print(reversed_vector)
```

#### 6. Write an R program to find the second highest value in a given vector.

```R
find_second_highest <- function(vec) {
  sorted_vec <- sort(unique(vec), decreasing = TRUE)
  return(sorted_vec[2])  # Second highest value
}

# Example usage:
input_vector <- c(10, 20, 5, 30, 15)
second_highest <- find_second_highest(input_vector)
print(paste("Second highest value is:", second_highest))
```

#### 7. Uses of `scan()` function:

The `scan()` function in R is used to read data values interactively from the console or from a file. It is useful for quickly inputting data elements, particularly for smaller datasets. Examples:

*   **Reading from Console**:

    ```R
    data_input <- scan(prompt = "Enter data values (space-separated): ")
    print(data_input)
    ```
*   **Reading from File**:

    ```R
    data_file <- "data.txt"
    data_from_file <- scan(data_file, what = numeric(), quiet = TRUE)
    print(data_from_file)
    ```

#### 8. Difference between data frame and a matrix in R:

* **Matrix**:
  * Represents a homogeneous data structure where all elements must be of the same data type (e.g., numeric, character).
  * Has dimensions (`nrow` x `ncol`) and can store data in a 2-dimensional array format.
  * Elements are accessed using row and column indices.
  * Suitable for mathematical operations and computations.
* **Data Frame**:
  * Represents a heterogeneous data structure where each column can contain different data types.
  * Can be seen as a special case of a list where each element (column) has the same length.
  * Supports handling and manipulation of tabular data, similar to a database table.
  * Ideal for data analysis and manipulation tasks, especially with mixed data types.

In summary, matrices are more rigid in structure (homogeneous) and are used primarily for mathematical operations, while data frames provide flexibility (heterogeneous) and are commonly used in data analysis and statistics tasks within R.
