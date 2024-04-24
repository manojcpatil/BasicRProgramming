# Exercises 5

#### Questions and Answers:

1. **Listing Color Combinations**:
   * **Question**: You have a set of colors to choose from: (red, blue, green, white, black, yellow). You have to pick 3 colors, and you can't pick the same color more than once. List all possible combinations with and without replacement.
   *   **Answer**:

       ```R
       library(gtools)

       colors <- c("red", "blue", "green", "white", "black", "yellow")

       # Combinations without Replacement
       combinations_without_replacement <- combinations(6, 3, colors, repeats.allowed = FALSE)
       print(combinations_without_replacement)

       # Combinations with Replacement
       combinations_with_replacement <- combinations(6 + 3 - 1, 3, colors, repeats.allowed = TRUE)
       print(combinations_with_replacement)
       ```
2. **R Function to Check Prime Number**:
   * **Question**: Write an R function to check whether a given number is prime or not.
   *   **Answer**:

       ```R
       is_prime <- function(n) {
         if (n <= 1) return(FALSE)
         for (i in 2:sqrt(n)) {
           if (n %% i == 0) return(FALSE)
         }
         return(TRUE)
       }

       # Example usage
       num <- 17
       result <- is_prime(num)
       print(result)  # Output: TRUE
       ```
3. **Function to Replace Missing Values with Mean**:
   * **Question**: Write an R function to replace missing values in a vector with the mean of that vector.
   *   **Answer**:

       ```R
       replace_missing_with_mean <- function(vec) {
         mean_val <- mean(vec, na.rm = TRUE)
         vec[is.na(vec)] <- mean_val
         return(vec)
       }

       # Example usage
       vec <- c(1, NA, 3, NA, 5)
       result <- replace_missing_with_mean(vec)
       print(result)  # Output: 1.0 3.0 3.0 3.0 5.0
       ```
4. **Probability Density Function and Realizations**:
   * **Question**: Let $X$ be a random variable with probability density function $f(x) = \frac{4}{3}x(2 - x^2)$ for $0 \leq x \leq 1$. Write R code to i) verify that the area under $f(x)$ is 1. ii) generate 100 realizations of $X$.
   *   **Answer**:

       ```R
       # Probability density function f(x)
       f <- function(x) {
         return((4/3) * x * (2 - x^2))
       }

       # Verify area under f(x) is 1
       area <- integrate(f, 0, 1)
       print(area$value)  # Should be close to 1

       # Generate 100 realizations of X
       set.seed(123)  # Set seed for reproducibility
       realizations <- runif(100, 0, 1)
       ```
5. **Creating Data Frame using Matrix and Adding Rows/Columns**:
   * **Question**: How to create a data frame using a matrix in R? Also, how do you add a row and a column to data objects like a matrix or a data frame?
   *   **Answer**:

       ```R
       # Create a matrix
       mat <- matrix(1:9, nrow = 3, ncol = 3)

       # Convert matrix to data frame
       df <- as.data.frame(mat)

       # Adding a row to data frame 'df'
       new_row <- c(10, 11, 12)
       df <- rbind(df, new_row)

       # Adding a column to data frame 'df'
       new_col <- c(13, 14, 15, 16)
       df <- cbind(df, new_col)
       ```
6. **Function to Obtain Minimum Value of Three Variables**:
   * **Question**: Write an R function to obtain the minimum value out of three variables.
   *   **Answer**:

       ```R
       min_of_three <- function(a, b, c) {
         return(min(a, b, c))
       }

       # Example usage
       result <- min_of_three(5, 3, 8)
       print(result)  # Output: 3
       ```
