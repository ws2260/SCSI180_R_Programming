---
title: "Introduction to R Programing"
output:
  html_document:
    output_file: "Section4_4.html"
    toc: true
    toc_depth: 3
    toc_float: true
---



---

# **4. Glossary**

Here’s a quick reference to key terms we’ve covered in this session:

---

## **Interfaces**

- **Graphical User Interface (GUI)**: Interaction with the computer using visual elements like buttons and menus.
  - Example: Clicking “File > Open File” in RStudio.
- **Command-Line Interface (CLI)**: Interaction with the computer by typing commands instead of using graphical elements.
  - Example: Typing `getwd()` in RStudio to print the current working directory.

---

## **R Programming Basics**

- **Variable**: A named container that stores data in R.
  - Example: `x <- 10`
- **Function**:  A block of reusable code that performs a specific task. Functions take inputs (arguments) and return outputs.
  - Example: `sqrt(16)` calculates the square root of 16.
- **Parameter**: A placeholder in a function definition that accepts input values. Parameters are defined in the function header.
  - Example: In the function `mean(x, na.rm = FALSE`), `x` and `na.rm` are parameters.
- **Argument**: The actual values provided to a function when it is called. Arguments are passed to the parameters.
  - Example: In `mean(x = c(1, 2, 3), na.rm = TRUE`), `c(1, 2, 3)` is the argument for the parameter `x`, and `TRUE` is the argument for the parameter `na.rm`.
- **Package**: A collection of pre-built R functions, datasets, and documentation designed for specific tasks. Packages extend R's capabilities.
  - Example: `ggplot2` for advanced data visualization.

---

## **Directories**

- **Home Directory**: The default starting location on your computer for files.
  - Example: `C:/Users/YourName/Documents`
- **Working Directory**: The folder R is currently using to read or save files.
  - Example: Set with `setwd("path/to/folder")`.

---

## **Data Types**

- **Numeric**: Represents numbers (e.g., integers or doubles).
- **Character**: Text or strings enclosed in quotes.
  - Example: `"Hello, World!"`
- **Logical**: Two-valued/binary/Boolean variables - either `TRUE` or `FALSE`, often used in conditions or comparisons
- **Factor**: Categorical data with fixed levels.
  - Example: `factor(c("Male", "Female"))`

---

## **Data Structures**

- **Vector**: A one-dimensional collection of data of the same type.
  - Example: `c(1, 2, 3)`
- **Dataframe**: A two-dimensional structure with rows (observations) and columns (variables).
  - Example:
```r
data.frame(Name = c("Alice", "Bob"), Age = c(25, 30))
```
- **List**: A flexible collection that can store data of different types.
  - Example: `list(Name = "Alice", Scores = c(90, 85))`

---

## **Dataframe Terminology**

- **Observation**: A row in a dataframe representing an individual entry.
- **Variable/Feature**: A column in a dataframe representing a specific characteristic.

---

## **Operators**

- **`<-`**: Used to assign values to variables (preferred over `=`).
- **`=`**: Also used for assignment or to specify arguments in functions.
- **`==`**: Comparison operator to check equality.

---

## **Exercise**

**1. You downloaded a file called `data.csv` from the internet and ran the following code:**  
   

``` r
read.csv("data.csv")
```

**However, you get an error saying `file not found`. What might be causing this issue, and how can you fix it?**

<details>
<summary>Click for Answer</summary>

**Possible causes**:
  
  - The file `data.csv` is not in your current working directory. Check with `getwd()` and move the file there or specify the full path.
  - The filename may have a typo or incorrect capitalization.
  - The file extension `.csv` might be missing or incorrect.

**Solutions**:
  
  - Use `getwd()` to confirm the working directory.
  - Verify the filename and path.
  - If the file is in another location, use `setwd()` or provide the full path, e.g., `read.csv("C:/Users/YourName/Documents/data.csv")`.
   </details>
   
<br>

**2. In the function `mean(x = c(1, 3, 5), na.rm = TRUE)`:**

   - Identify the **parameters**.
   - Identify the **arguments**.

<details>
<summary>Click for Answer</summary>
   
- **Parameters**: `x`, `na.rm`  
- **Arguments**: `c(1, 3, 5)` is the argument for `x`; `TRUE` is the argument for `na.rm`.
   </details>
   
<br>

**3. What is the data structure of `c(12.5, 15.0, 20.0)` and what will be the output of the following code?**  


``` r
typeof(c(12.5, 15.0, 20.0))
```

<details>
<summary>Click for Answer</summary>
   
- The data structure is a **numeric vector**.  
- The output of `typeof(c(12.5, 15.0, 20.0))` will be `"double"`.
   </details>

<br>

**4. What will be the output of the following code?**
   

``` r
fruits <- c("apple", "banana", "cherry")
fruits[4] <- "date"
print(fruits)
```

<details>
<summary>Click for Answer</summary>

The output will be:

```
[1] "apple" "banana" "cherry" "date"
```

Explanation: The `fruits` vector was extended to include "date" at index 4.
</details>

<br>

**5. What’s the output of the following code and what are the differences of x as variables in these two different contexts?**


``` r
x <- c(1, 2, 3)
df <- data.frame(x = c(4, 5, 6))
print(x)
print(df$x)
```

<details>
<summary>Click for Answer</summary>

The output will be:

`print(x)`

```
[1] 1 2 3
```

`print(df$x)`

```
[1] 4 5 6
```

Explanation:

- **`x` as a variable in R**:  
  
  - A named container that stores data in R. Here, `x` is a standalone vector holding three numeric values: `1`, `2`, and `3`.  

- **`x` as a variable/feature in a dataframe**:  

  - A column in the dataframe `df` that represents a specific characteristic. It is tied to the dataframe and must be accessed with `df$x`.  

- **Key Difference**:  
  
  - `x` as a standalone variable and `x` as a column in a dataframe are both referred to as variables but differ in context.  
  - In a dataframe, **variables** or **features** are stored in **columns**, which collectively describe given characteristics in a dataset.  

</details>

<br>

**6. What will the following code output and what's the difference between `=` and `==` here?**  


``` r
x = 3
print(x)
print(x = 4)
print(x == 3)
```

<details>
<summary>Click for Answer</summary>

Output:  

- `print(x)`:  

```
[1] 3
```
    
- `print(x = 4)`:  

```
[1] 4
```
    
- `print(x == 3)`:  
    
```
[1] TRUE
```

Explanation:  

- **`=` for assignment (though `<-` is preferred in R)**:  
    
  - `x = 3` assigns the value `3` to the variable `x`.  
  - `x = 4` inside `print()` temporarily assigns `4` to `x` and returns it, but this does not persist. After this line, `x` still holds the value `3`.  

- **`==` for comparison**:  
    
  - `x == 3` checks whether the value of `x` is equal to `3` and returns `TRUE` since `x` was assigned `3` earlier.  

- **Key Difference**:  
    
  - `=` is used to assign a value to a variable.  
  - `==` is used to compare values, returning `TRUE` if they are equal or `FALSE` otherwise.  
</details>

---

[Table of Contents](index.html) | [Previous: 3. Exploring R Basics](exploring-r-basics.html)
