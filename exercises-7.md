# Exercises 7

#### Questions and Answers:

1.  **Question**: Define (X) as the space occupied by a certain device in a 1 (m^3) container. The probability density function of (X) is given by (f(x) = \frac{630}{56} x^4 (1 - x^4)) for (0 < x < 1). Write R code to find the mean, variance, and (P(0.2 < x < 0.8)) using the `integrate()` function. Also, plot the graph of the probability density function (f(x)). **Answer**:

    ```R
    # Define the probability density function
    f <- function(x) {
      return((630/56) * x^4 * (1 - x^4))
    }

    # Mean and variance using integrate()
    mean <- integrate(function(x) x * f(x), 0, 1)$value
    variance <- integrate(function(x) x^2 * f(x), 0, 1)$value - mean^2

    # Probability P(0.2 < x < 0.8)
    probability <- integrate(f, 0.2, 0.8)$value

    # Plotting the probability density function
    curve(f(x), from = 0, to = 1, xlab = "X", ylab = "Density", main = "Probability Density Function")
    ```
2.  **Question**: Construct R code to: i) Plot the probability mass function and the cumulative probability distribution of a binomial random variable (X \sim \text{Bin}(n=8, p=0.3)). ii) Find the smallest value of (k) such that (P(X \leq k) \geq 0.44) for (X \sim \text{Bin}(n=8, p=0.7)). iii) Calculate (P(Y \geq 3)) if (Y \sim \text{Bin}(20, 0.2)). **Answer**:

    ```R
    # i) Plotting PMF and CDF of Binomial distribution
    n <- 8
    p <- 0.3
    plot(0:n, dbinom(0:n, size = n, prob = p), type = "h", main = "Binomial PMF and CDF", xlab = "X", ylab = "Probability")
    lines(0:n, pbinom(0:n, size = n, prob = p), col = "red")

    # ii) Finding smallest k such that P(X ≤ k) ≥ 0.44
    k <- 0
    while (pbinom(k, size = 8, prob = 0.7) < 0.44) {
      k <- k + 1
    }
    smallest_k <- k

    # iii) Calculating P(Y ≥ 3) for Y ~ Bin(20, 0.2)
    probability_Y_ge_3 <- 1 - pbinom(2, size = 20, prob = 0.2)
    ```
3.  **Question**: Write commands in R to: i) Find the mode of the following observation: (1, 2, \ldots, 23). ii) Find (P\[X \leq 3]) where (X \sim \text{Pois}(\lambda = 2)). iii) Draw a systematic random sample of size 5 from a population of 65. iv) Simulate an experiment of tossing a coin 30 times and prepare its frequency distribution. **Answer**:

    ```R
    # i) Finding mode of observations
    mode <- function(x) {
      ux <- unique(x)
      ux[which.max(tabulate(match(x, ux)))]
    }
    mode(1:23)  # Mode of sequence 1 to 23

    # ii) Finding P[X ≤ 3] for X ~ Pois(lambda = 2)
    ppois(3, lambda = 2)

    # iii) Drawing systematic random sample of size 5 from a population of 65
    population <- 1:65
    sample_indices <- seq(1, length(population), length.out = 5)
    systematic_sample <- population[sample_indices]

    # iv) Simulating coin toss experiment and preparing frequency distribution
    coin_tosses <- sample(c("H", "T"), 30, replace = TRUE)
    table(coin_tosses)
    ```
4.  **Question**: An experiment was undertaken where 17 fresh and 17 one-week-old picked apples were randomly selected. Write R code to construct a 95% confidence interval for the mean difference between the hardness of fresh apples and the hardness for apples picked one week ago. Assume unequal variances. **Answer**:

    ```R
    # Assuming data for fresh and one-week-old apples
    fresh <- c(...)  # Data for fresh apples
    one_week_old <- c(...)  # Data for one-week-old apples

    # Constructing 95% confidence interval for mean difference
    t.test(fresh, one_week_old, var.equal = FALSE)
    ```
5.  **Question**: Create vectors (a) and (b) in R, where (a = (5, 10, \ldots, 160)) and (b = (87, 86, \ldots, 56)). Use vector arithmetic to multiply these vectors and call the result (d). Select subsets of (d) to identify: i) The 19th, 20th, and 21st elements of (d). ii) All elements of (d) which are less than 2000. iii) The number of elements of (d) that are greater than 6000. **Answer**:

    ```R
    # Creating vectors a and b
    a <- seq(5, 160, by = 5)
    b <- seq(87, 56, by = -1)

    # Vector arithmetic to multiply vectors a and b
    d <- a * b

    # Subsetting d
    element_19_21 <- d[19:21]
    elements_lt_2000 <- d[d < 2000]
    elements_gt_6000 <- sum(d > 6000)
    ```

6\. Question: Write a note on control statements in R.

**Answer:**

Control statements in R are essential for managing the flow of execution within a program. They enable conditional branching and repetitive execution, allowing you to control how your code responds to different conditions and iterate over data or tasks. Here's an overview of key control statements in R:

1.  **if-else Statements:**

    * `if(condition) { expr } else { expr }`: Executes `expr` if `condition` is `TRUE`, otherwise executes the `else` part.

    Example:

    ```R
    x <- 10
    if (x > 0) {
      print("Positive")
    } else {
      print("Non-positive")
    }
    ```
2.  **for Loops:**

    * `for(variable in sequence) { expr }`: Executes `expr` for each element in `sequence`.

    Example:

    ```R
    for (i in 1:5) {
      print(i)
    }
    ```
3.  **while Loops:**

    * `while(condition) { expr }`: Executes `expr` repeatedly as long as `condition` is `TRUE`.

    Example:

    ```R
    x <- 1
    while (x <= 5) {
      print(x)
      x <- x + 1
    }
    ```
4.  **repeat Loop:**

    * `repeat { expr; if(condition) { break } }`: Executes `expr` indefinitely until a `break` condition is met.

    Example:

    ```R
    x <- 1
    repeat {
      print(x)
      x <- x + 1
      if (x > 5) {
        break
      }
    }
    ```
5. **Control Flow Functions:**
   * `next`: Skips the current iteration of a loop.
   * `break`: Exits a loop prematurely.
   * `return`: Exits a function with a return value.

Control statements are powerful tools for implementing logic and algorithms in R. They enable you to handle various scenarios, make decisions based on conditions, and iterate over data efficiently. Understanding and using these control structures effectively can greatly enhance the flexibility and capability of your R programs.
