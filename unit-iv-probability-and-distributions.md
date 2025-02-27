# Probability and Distributions

In the realm of probability and distributions in R, there are various functions and techniques available to work with random variables, probability distributions, and visualizing their properties. Here is a detailed overview of key functions and tasks related to probability and distributions in R:

#### Random Sampling

1.  **`sample()`**

    * Generate random samples from a given set of elements or a specified range of numbers.

    Example:

    ```R
    # Sample from a vector
    sample(c("A", "B", "C", "D"), size = 10, replace = TRUE)

    # Sample integers from 1 to 100
    sample(1:100, size = 20, replace = TRUE)
    ```
2.  **`runif()`**, **`rnorm()`**, **`rbinom()`**, etc.

    * Generate random numbers from uniform, normal, binomial, or other specified distributions.

    Example:

    ```R
    # Generate 100 random numbers from a uniform distribution between 0 and 1
    runif(100)

    # Generate 50 random numbers from a normal distribution with mean 0 and standard deviation 1
    rnorm(50, mean = 0, sd = 1)

    # Generate 30 random numbers from a binomial distribution with size 10 and probability 0.5
    rbinom(30, size = 10, prob = 0.5)
    ```

#### Probability Distributions

1.  **Density and Cumulative Density Functions (PDF and CDF)**

    * **`dnorm()`, `dbinom()`, `dpois()`, etc.**
      * Compute the probability density function (PDF) for specific distributions like normal, binomial, Poisson, etc.
    * **`pnorm()`, `pbinom()`, `ppois()`, etc.**
      * Compute the cumulative distribution function (CDF) for specific distributions.

    Example:

    ```R
    # Compute PDF and CDF of a standard normal distribution
    dnorm(0)  # PDF at x = 0
    pnorm(0)  # CDF at x = 0

    # Compute PDF and CDF of a binomial distribution
    dbinom(2, size = 10, prob = 0.5)  # PDF at x = 2 for Binomial(10, 0.5)
    pbinom(2, size = 10, prob = 0.5)  # CDF at x = 2 for Binomial(10, 0.5)
    ```
2.  **Quantile Values**

    * **`qnorm()`, `qbinom()`, `qpois()`, etc.**
      * Compute quantile values (inverse CDF) for specific distributions.

    Example:

    ```R
    # Compute the 95th percentile of a standard normal distribution
    qnorm(0.95)

    # Compute the 80th percentile of a Poisson distribution with mean 5
    qpois(0.8, lambda = 5)
    ```

#### Plotting Probability Distributions

1.  **Density Plots**

    * Use **`plot()`** and **`lines()`** with computed densities (`density()`) to plot density curves.

    Example:

    ```R
    # Generate random data from a normal distribution
    x <- rnorm(1000, mean = 0, sd = 1)

    # Plot the density curve
    plot(density(x), main = "Density Plot of Normal Distribution")
    ```
2.  **Q-Q Plots (Quantile-Quantile Plots)**

    * Use **`qqnorm()`** and **`qqline()`** to create Q-Q plots for assessing distributional assumptions.

    Example:

    ```R
    # Generate random data from a normal distribution
    x <- rnorm(100)

    # Create Q-Q plot
    qqnorm(x)
    qqline(x)
    ```

#### Additional Functions and Techniques

1.  **`hist()`**

    * Create histograms to visualize the distribution of data.

    Example:

    ```R
    # Generate random data from a Poisson distribution
    x <- rpois(100, lambda = 3)

    # Plot a histogram
    hist(x, breaks = 10, main = "Histogram of Poisson Distribution")
    ```
2.  **`ecdf()`**

    * Compute and plot empirical cumulative distribution functions.

    Example:

    ```R
    # Generate random data from a uniform distribution
    x <- runif(100)

    # Plot empirical CDF
    plot(ecdf(x), main = "Empirical CDF of Uniform Distribution")
    ```

These functions and techniques provide a comprehensive toolkit for working with probability distributions, conducting random sampling, and visualizing data distribution characteristics in R. By mastering these tools, you can efficiently analyze data and gain insights into underlying probabilistic structures.
