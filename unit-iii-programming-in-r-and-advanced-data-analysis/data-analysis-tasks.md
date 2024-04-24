# Data Analysis Tasks

In this chapter, we will explore essential techniques and methods for reading data into R, performing statistical computations, and gaining insights from data. Understanding these fundamental tasks is crucial for anyone working with data, whether you are a beginner or an experienced data analyst.

#### Introduction to Data Analysis

Data analysis is the process of inspecting, cleaning, transforming, and modeling data with the goal of discovering useful information, drawing conclusions, and supporting decision-making. In this chapter, we will focus on two key aspects of data analysis:

1. **Reading and Loading Data:**
   * Techniques for importing data into R from various sources such as CSV files, Excel spreadsheets, databases, APIs, and web scraping.
   * Exploring different R packages (e.g., `readr`, `readxl`, `data.table`, `DBI`) for efficient data loading and manipulation.
2. **Performing Statistical Computations:**
   * Basic and advanced statistical computations using built-in R functions and packages (`stats`, `dplyr`, `tidyr`, `ggplot2`, `caret`, `lme4`, etc.).
   * Conducting descriptive statistics, hypothesis testing, regression analysis, and more.

#### Reading and Loading Data

**Importing Data from Files**

R provides several methods for reading data from external files:

*   **CSV Files:**

    ```R
    data <- read.csv("data.csv")
    ```
*   **Excel Files:**

    ```R
    library(readxl)
    data <- read_excel("data.xlsx")
    ```
*   **Text Files:**

    ```R
    data <- read.table("data.txt", header = TRUE)
    ```

**Connecting to Databases**

R can connect to various databases (MySQL, SQLite, PostgreSQL, etc.) using packages like `DBI` and `RMySQL`:

```R
library(DBI)
con <- dbConnect(RMySQL::MySQL(), dbname = "mydb", user = "user", password = "password")
data <- dbGetQuery(con, "SELECT * FROM mytable")
dbDisconnect(con)
```

**Web Scraping**

Scraping data from websites is possible using packages like `rvest` and `httr`:

```R
library(rvest)
url <- "https://example.com"
web_data <- read_html(url) %>% html_table()
```

#### Performing Statistical Computations

**Descriptive Statistics**

Compute basic statistics (mean, median, variance, etc.) using R's built-in functions:

```R
# Descriptive statistics
summary(data)
mean(data$column)
var(data$column)
```

**Hypothesis Testing**

Perform hypothesis tests (t-tests, chi-squared tests, ANOVA, etc.) using R's statistical functions:

```R
# T-test example
t.test(data$group1, data$group2)
```

**Regression Analysis**

Fit regression models (linear, logistic, etc.) using packages like `lm` (linear model) or `glm` (generalized linear model):

```R
# Linear regression example
model <- lm(y ~ x1 + x2, data = mydata)
summary(model)
```

**Data Visualization**

Visualize data and results using plotting libraries like `ggplot2`:

```R
library(ggplot2)
ggplot(data, aes(x = x_var, y = y_var)) +
  geom_point() +
  geom_smooth(method = "lm")
```

#### List of function for Descriptive Statistics

1. **summary()**
   * Compute summary statistics (mean, median, min, max, quartiles) for numeric data.
2. **mean()**
   * Calculate the arithmetic mean of numeric vectors.
3. **median()**
   * Compute the median (middle value) of numeric data.
4. **var()**
   * Calculate the variance of numeric vectors.
5. **sd()**
   * Compute the standard deviation of numeric vectors.
6. **quantile()**
   * Compute sample quantiles (e.g., quartiles) of numeric data.
7. **range()**
   * Compute the range (min, max) of numeric vectors.
8. **summaryBy()** (from `doBy` package)
   * Generate descriptive statistics by group.

***

#### Other Useful Functions

1. **aggregate()**
   * Apply a function to subsets of data.
2. **apply()**
   * Apply a function over the margins of an array or matrix.
3. **lapply()** and **sapply()**
   * Apply functions to lists or vectors.
4. **dplyr** and **tidyr**
   * Packages for data manipulation and transformation (e.g., filtering, summarizing, reshaping).
