---
description: >-
  1. Explain the role of following functions with appropriate examples:
  cumsum(), cumprod(), cummin(), cummax() 2. Explain any two Loop Functions with
  appropriate examp
---

# Exercise 3

#### Explanation of Cumulative Functions:

1. **`cumsum()`**:
   * **Role**: Computes the cumulative sum of elements in a vector.
   *   **Example**:

       ```R
       x <- c(1, 2, 3, 4, 5)
       cumulative_sum <- cumsum(x)
       print(cumulative_sum)
       ```

       Output:

       ```
       [1]  1  3  6 10 15
       ```

       Explanation: The cumulative sum at each position is calculated as `[1, 1+2, 1+2+3, 1+2+3+4, 1+2+3+4+5]`.
2. **`cumprod()`**:
   * **Role**: Computes the cumulative product of elements in a vector.
   *   **Example**:

       ```R
       y <- c(2, 3, 4, 5)
       cumulative_product <- cumprod(y)
       print(cumulative_product)
       ```

       Output:

       ```
       [1]  2  6 24 120
       ```

       Explanation: The cumulative product at each position is calculated as `[2, 2*3, 2*3*4, 2*3*4*5]`.
3. **`cummin()`**:
   * **Role**: Computes the cumulative minimum of elements in a vector.
   *   **Example**:

       ```R
       z <- c(3, 1, 4, 2, 5)
       cumulative_min <- cummin(z)
       print(cumulative_min)
       ```

       Output:

       ```
       [1] 3 1 1 1 1
       ```

       Explanation: The cumulative minimum at each position is computed by taking the minimum value encountered up to that position.
4. **`cummax()`**:
   * **Role**: Computes the cumulative maximum of elements in a vector.
   *   **Example**:

       ```R
       w <- c(4, 2, 5, 1, 3)
       cumulative_max <- cummax(w)
       print(cumulative_max)
       ```

       Output:

       ```
       [1] 4 4 5 5 5
       ```

       Explanation: The cumulative maximum at each position is computed by taking the maximum value encountered up to that position.

#### Explanation of Loop Functions:

1. **`lapply()`**:
   * **Role**: Apply a function to each element of a list or vector.
   *   **Example**:

       ```R
       my_list <- list(a = 1:3, b = 4:6, c = 7:9)
       lapply(my_list, function(x) sum(x))
       ```

       Output:

       ```
       $a
       [1] 6

       $b
       [1] 15

       $c
       [1] 24
       ```

       Explanation: `lapply` applies the `sum()` function to each element of `my_list`.
2. **`sapply()`**:
   * **Role**: Simplify the output of `lapply()` into a vector or matrix if possible.
   *   **Example**:

       ```R
       my_list <- list(a = 1:3, b = 4:6, c = 7:9)
       sapply(my_list, function(x) sum(x))
       ```

       Output:

       ```
       a  b  c 
       6 15 24 
       ```

       Explanation: `sapply` applies the `sum()` function to each element of `my_list` and simplifies the result into a named vector. If the output can be simplified into a matrix, `sapply` will return a matrix instead of a vector.

These loop functions (`lapply` and `sapply`) are useful for applying a function to each element of a list or vector in R, providing flexibility and efficiency in data manipulation and analysis.
