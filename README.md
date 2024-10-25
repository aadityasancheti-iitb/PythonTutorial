# PythonTutorial
Random Topics in Basic Python
***
# loc and iloc-
In Python's pandas library, .loc and .iloc are two important methods for selecting data from DataFrames. They’re commonly used for accessing rows, columns, or a subset of data, but each has different indexing conventions.

Here's a detailed explanation:

1. .loc - Label-Based Indexing
Definition: .loc is used to select data by label or conditional selection.
Usage: Access rows and columns based on labels or boolean conditions.
Range Inclusion: When slicing with labels, the end label is included in the result.
Syntax: df.loc[row_label, column_label]
Example Usage
python
Copy code
import pandas as pd

Sample DataFrame
data = {'A': [10, 20, 30], 'B': [40, 50, 60]}
df = pd.DataFrame(data, index=['x', 'y', 'z'])

 Selecting a single row by label
df.loc['x']           Returns row with index label 'x'

 Selecting multiple rows and columns by label
df.loc[['x', 'z'], ['A', 'B']]  # Returns specified rows and columns

 Using a conditional selection
df.loc[df['A'] > 15]  # Returns rows where column A has values greater than 15
Key Points
.loc allows label-based indexing, which means it looks at the index or column labels.
Useful for conditional filtering (e.g., df.loc[df['A'] > 10]).
It includes both the start and end labels when slicing.
2. .iloc - Integer-Based Indexing
Definition: .iloc is used for selection based on integer position.
Usage: Access rows and columns based on numerical index positions.
Range Inclusion: When slicing with positions, the end position is excluded.
Syntax: df.iloc[row_position, column_position]
Example Usage
python
Copy code
 Selecting a single row by position
df.iloc[0]            # Returns the first row (index position 0)

 Selecting a range of rows and columns by position
df.iloc[0:2, 0:2]     # Returns the first two rows and columns (0 and 1)

 Using integer position indexing with a specific row and column
df.iloc[2, 1]         # Returns the value at 3rd row, 2nd column (position-based)
Key Points
.iloc uses position-based indexing, meaning it looks at the numerical index of rows and columns.
Suitable for slicing ranges using index numbers, where the end position is not included.
Comparison Table
Feature	.loc	.iloc
Indexing Type	Label-based	Integer-based
Range Inclusion	End label included	End position excluded
Slicing with Step	Yes	Yes
Conditional Select	Supported	Not directly supported
Common Use	Named columns or index labels	Numerical indexing
Choosing Between .loc and .iloc
Use .loc when your DataFrame has meaningful labels, and you need to access data by specific labels or with conditions.
Use .iloc for purely numerical indexing, often useful when the structure of the DataFrame is numeric-based or when labels aren’t meaningful.
This distinction makes it easy to navigate and extract the desired rows and columns based on the indexing approach you need. 

***
# Missing values in a dataframe
df.isnull().sum()  // return the sum of all missing values in a column
*** 
# CSV
pd.read_csv('input.csv')
df.into_csv('output.csv',index=False)
***
# Lambda Function in python
## What is a Lambda Function?

A **lambda function** is an anonymous function defined with the keyword `lambda`, followed by input parameters, a colon, and a single expression. Lambda functions are often used for short, simple operations that are only needed once or temporarily, making them convenient in situations where a full function definition would be excessive.

### Syntax
```python
lambda arguments: expression
```

- **arguments**: The input parameters, which can be any number of arguments (like a regular function).
- **expression**: A single statement that the lambda function returns.

### Example
Here’s a simple example of a lambda function that adds two numbers:

```python
add = lambda x, y: x + y
print(add(3, 4))  # Output: 7
```

## Why Use Lambda Functions?

1. **Conciseness**: Lambda functions allow you to create small functions without formal definitions, keeping code shorter.
2. **Convenience**: They’re ideal when you need a simple function temporarily within other functions or methods, like `map()`, `filter()`, and `apply()`.

## Using Lambda Functions with Built-in Functions

### 1. **With `map()`**

The `map()` function applies a lambda function to each element of an iterable (like a list).

```python
numbers = [1, 2, 3, 4]
squared = map(lambda x: x ** 2, numbers)
print(list(squared))  # Output: [1, 4, 9, 16]
```

### 2. **With `filter()`**

The `filter()` function filters elements based on a condition defined by a lambda function.

```python
numbers = [1, 2, 3, 4, 5]
even_numbers = filter(lambda x: x % 2 == 0, numbers)
print(list(even_numbers))  # Output: [2, 4]
```

### 3. **With `apply()` in Pandas**

In Pandas, lambda functions are often used with `.apply()` to apply transformations across dataframes.

```python
import pandas as pd

df = pd.DataFrame({'numbers': [1, 2, 3, 4]})
df['squared'] = df['numbers'].apply(lambda x: x ** 2)
print(df)
# Output:
#    numbers  squared
# 0        1        1
# 1        2        4
# 2        3        9
# 3        4       16
```

## Lambda Function vs Regular Function

Lambda functions are best suited for simple operations and are typically one-liners, whereas regular functions defined with `def` are more versatile and can include multiple expressions, statements, and return values.

### Example: Lambda Function vs Regular Function

**Lambda Function**

```python
multiply = lambda x, y: x * y
print(multiply(5, 3))  # Output: 15
```

**Regular Function**

```python
def multiply(x, y):
    result = x * y
    return result

print(multiply(5, 3))  # Output: 15
```

## Limitations of Lambda Functions

- **Single Expression**: Lambda functions are limited to a single expression, so they cannot include multiple statements or complex logic.
- **Readability**: Overusing lambda functions or using them for complex operations can reduce readability.
- **No Name**: Since they are anonymous, debugging can be harder if errors arise.

## When to Use Lambda Functions

1. **Short, temporary functions** for simple operations.
2. **With built-in functions** like `map()`, `filter()`, or `apply()` for concise, inline functionality.
3. When a **regular function definition** (`def`) would be unnecessarily verbose for a single-use operation.

By understanding these aspects of lambda functions, you can write more efficient and concise code while maintaining readability.

# Try Except in Python

