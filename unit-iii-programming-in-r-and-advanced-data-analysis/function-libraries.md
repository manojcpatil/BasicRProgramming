# Function Libraries

Function libraries, also known as collections of functions or utility libraries, are sets of related functions bundled together for specific tasks or analyses. They help organize and modularize code, making it easier to manage and reuse across projects.

**Creating a Function Library**

To create a function library in R, follow these steps:

1.  **Define Functions:**

    * Write R functions that perform specific tasks or computations.
    * Save these functions in a `.R` script file (e.g., `my_functions.R`).

    ```r
    # my_functions.R

    # Function to calculate factorial of a number
    calculate_factorial <- function(n) {
      if (n == 0) {
        return(1)
      } else {
        return(n * calculate_factorial(n - 1))
      }
    }

    # Function to generate Fibonacci sequence
    generate_fibonacci <- function(n) {
      sequence <- numeric(n)
      sequence[1] <- 1
      sequence[2] <- 1
      for (i in 3:n) {
        sequence[i] <- sequence[i - 1] + sequence[i - 2]
      }
      return(sequence)
    }
    ```
2. **Organize Functions:**
   * Group related functions together in the same script file based on their purpose or functionality.

**Using a Function Library**

To use functions from a library in your R script or interactive session:

1.  **Load the Library:**

    * Source the script file containing your functions using `source()`.

    ```r
    source("path/to/my_functions.R")
    ```
2.  **Call Functions:**

    * Use the functions from the library in your R code.

    ```r
    # Calculate factorial of 5 using the library function
    factorial_5 <- calculate_factorial(5)
    print(factorial_5)  # Output: 120

    # Generate Fibonacci sequence of length 10 using the library function
    fib_sequence <- generate_fibonacci(10)
    print(fib_sequence)  # Output: 1 1 2 3 5 8 13 21 34 55
    ```
