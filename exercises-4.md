# Exercises 4

#### Question and Answer:

1.  **Question**: Suppose there would be no `each` argument for `rep()`. Rewrite the following statement, without using the `each` argument:

    ```R
    x <- rep(c(27, 31, 19, 14), each = v, times = w)
    ```

    **Answer**:

    ```R
    v <- 4  # Value of 'v'
    w <- 3  # Value of 'w'
    x <- rep(c(rep(27, v), rep(31, v), rep(19, v), rep(14, v)), times = w)
    ```

    Explanation: This code snippet replicates each element of the vector `c(27, 31, 19, 14)` `v` times and repeats the resulting sequence `w` times without using the `each` argument.
2.  **Question**: What is the result of `mean(c(-100, 0, 1, 2, 3, 6, 50, 73), trim = 0.25)`? **Answer**:

    ```R
    result <- mean(c(-100, 0, 1, 2, 3, 6, 50, 73), trim = 0.25)
    print(result)
    ```

    **Output**:

    ```
    [1] 2.75
    ```

    Explanation: The `mean()` function calculates the trimmed mean (excluding 25% of the extreme values from each end of the sorted data) of the given vector `c(-100, 0, 1, 2, 3, 6, 50, 73)`, resulting in `2.75`.
3.  **Question**: How to add a row and column to data objects like a matrix or data frame? **Answer**:

    ```R
    # Adding a row to a matrix 'mat'
    new_row <- c(1, 2, 3)
    mat <- rbind(mat, new_row)

    # Adding a column to a data frame 'df'
    new_col <- c(4, 5, 6)
    df <- cbind(df, new_col)
    ```

    Explanation: Use `rbind()` to add a row to a matrix and `cbind()` to add a column to a data frame.
4.  **Question**: How do you assign a variable in R? **Answer**:

    ```R
    variable_name <- value
    ```

    Explanation: The assignment operator `<-` is used to assign a value to a variable in R.
5. **Question**: What are the different data types/objects in R? **Answer**: The different data types/objects in R include:
   * Vectors
   * Matrices
   * Lists
   * Arrays
   * Factors
   * Data frames
6. **Question**: What is the use of `with()` and `by()` in R? **Answer**:
   * `with()`: Simplifies data frame references in function calls and during interactive data analysis.
   * `by()`: Applies a function to each subset of a data frame split by factors.
7.  **Question**: How would you find the number of missing values in a dataset and remove all of them? **Answer**:

    ```R
    # Count missing values
    sum(is.na(data))

    # Remove rows with missing values
    clean_data <- na.omit(data)
    ```

    Explanation: Use `is.na()` to identify missing values (`NA`) in a dataset and `na.omit()` to remove rows containing missing values from the dataset. Use `sum(is.na(data))` to count the total number of missing values in the dataset `data`.
