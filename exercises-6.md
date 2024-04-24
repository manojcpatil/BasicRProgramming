# Exercises 6

#### Questions and Answers:

1. **Understanding `attach()`, `search()`, and `detach()`**:
   * **Question**: What are `attach()`, `search()`, and `detach()` functions in R?
   * **Answer**:
     *   `attach()`: Attaches a data frame to the search path. This allows you to refer to the columns of the attached data frame directly by their names. For example:

         ```R
         df <- data.frame(a = 1:3, b = 4:6)
         attach(df)
         print(a)  # Accessing 'a' directly
         detach(df)  # Detaching the data frame
         ```
     *   `search()`: Displays the search path in R, which includes attached data frames and other environments. For example:

         ```R
         search()
         ```
     *   `detach()`: Detaches a data frame from the search path. This removes the data frame from the search path, preventing direct access to its columns by name. For example:

         ```R
         detach(df)
         ```
2. **Subsetting a Data Frame**:
   * **Question**: For the data frame `df <- data.frame(a = 1:3, b = 4:6, c = 7:9)`, write R code to obtain subsets of `df` as i) `(4,5,6)`, ii) `1`, iii) `5`. Also, obtain the output of `df[,3]`, `df[1,]`, `df[2,2]`.
   *   **Answer**:

       ```R
       # Subsets of df
       subset_1 <- df$b  # (4,5,6)
       subset_2 <- df$a[1]  # 1
       subset_3 <- df$b[2]  # 5

       # Outputs
       output_1 <- df[,3]  # Column 'c'
       output_2 <- df[1,]  # Row 1 of df
       output_3 <- df[2,2]  # Element at row 2, column 2 (value: 5)
       ```
3. **Understanding `readline()`, `print()`, and `cat()`**:
   * **Question**: Explain about `readline()`, `print()`, and `cat()` functions in R with examples.
   * **Answer**:
     *   `readline()`: Reads a line from the console input as a character string. It is useful for interactive input. For example:

         ```R
         name <- readline(prompt = "Enter your name: ")
         print(name)
         ```
     *   `print()`: Prints its argument to the console or file. It is used to display values. For example:

         ```R
         x <- 10
         print(x)
         ```
     *   `cat()`: Concatenates and prints its arguments. It converts objects to character strings and concatenates them together. For example:

         ```R
         cat("Hello", "World!\n")
         ```
4. **Difference between `lapply` and `sapply`**:
   * **Question**: Differentiate between `lapply` and `sapply`.
   * **Answer**:
     *   `lapply()`: Applies a function to each element of a list or vector, and returns a list containing the results. It always returns a list, even if the input is a vector. Example:

         ```R
         x <- list(a = 1:3, b = 4:6)
         lapply(x, mean)
         ```
     *   `sapply()`: Simplifies the result of `lapply()` by attempting to simplify the output into a vector or matrix if possible. It returns a vector, matrix, or array. Example:

         ```R
         x <- list(a = 1:3, b = 4:6)
         sapply(x, mean)
         ```
5. **Mean, Variance, and Probability Calculation**:
   * **Question**: Define $X$ as a random variable with probability density function $f(x) = \frac{630}{56}x^4(1-x^4)$ for $0 < x < 1$. Write R code to find mean, variance, and $P(0.2 < x < 0.8)$ using `integrate()`.
   *   **Answer**:

       ```R
       # Define the probability density function
       f <- function(x) {
         return((630/56) * x^4 * (1 - x^4))
       }

       # Mean and variance
       mean <- integrate(function(x) x * f(x), 0, 1)$value
       variance <- integrate(function(x) x^2 * f(x), 0, 1)$value - mean^2

       # Probability P(0.2 < x < 0.8)
       probability
       ```
