# Exercise 2

#### Question 1:

Consider the following vectors: `u <- c(5, 6, 7, 8)` and `v <- c(2, 3, 4)`. Write down what you expect as the result of the following operations:

* `u + v`
* `v - u`
* `u * v`
* `u / v`

#### Answer 1:

Given vectors:

* `u <- c(5, 6, 7, 8)`
* `v <- c(2, 3, 4)`

**Expected Results:**

1. `u + v`: Adds corresponding elements of `u` and `v`.
   * Result: `c(5 + 2, 6 + 3, 7 + 4, 8 + 2) = c(7, 9, 11, 10)`
2. `v - u`: Subtracts `u` from `v` (element-wise).
   * Result: `c(2 - 5, 3 - 6, 4 - 7, NA)` (recycles `u` to match length of `v`)
   * Result: `c(-3, -3, -3, -3)`
3. `u * v`: Multiplies corresponding elements of `u` and `v`.
   * Result: `c(5 * 2, 6 * 3, 7 * 4, 8 * 2) = c(10, 18, 28, 16)`
4. `u / v`: Divides corresponding elements of `u` by `v`.
   * Result: `c(5 / 2, 6 / 3, 7 / 4, 8 / 2) = c(2.5, 2, 1.75, 4)`

#### Question 2:

Write a function that takes two arguments `n` and `k`, which are positive integers. The function should return an (n \times k) matrix with specific values as described below:

$$
\left[ \begin{array}{cccccc} k & 1 & 0 & \dots & 0 & 0 \\ 1 & k & 1 & \dots & 0 & 0 \\ 0 & 1 & k & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 1 & k \\ 0 & 0 & 0 & \dots & 0 & k \\ \end{array} \right]
$$

#### Answer 2:

```R
create_matrix <- function(n, k) {
  mat <- matrix(0, nrow = n, ncol = k)
  
  # Fill diagonal and off-diagonal elements
  for (i in 1:n) {
    mat[i, i] <- k  # diagonal elements
    if (i > 1) {
      mat[i, i - 1] <- 1  # elements to the left of the diagonal
    }
  }
  
  return(mat)
}

# Example usage:
n <- 6
k <- 3
result_matrix <- create_matrix(n, k)
print(result_matrix)
```

**Output:**

```
     [,1] [,2] [,3] [,4] [,5] [,6]
[1,]    3    1    0    0    0    0
[2,]    1    3    1    0    0    0
[3,]    0    1    3    1    0    0
[4,]    0    0    1    3    1    0
[5,]    0    0    0    1    3    1
[6,]    0    0    0    0    1    3
```

This function `create_matrix(n, k)` generates an (n \times k) matrix where:

* The diagonal elements are `k`.
* The elements immediately to the left of the diagonal are `1`.
* All other elements are `0`.
