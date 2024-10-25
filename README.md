# PythonTutorial
Random Topics in Basic Python
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


# Missing values in a dataframe
df.isnull().sum()  // return the sum of all missing values in a column
 
# CSV
pd.read_csv('input.csv')
df.into_csv('output.csv',index=False)
# Lambda Function in python

# Try Except in Python

