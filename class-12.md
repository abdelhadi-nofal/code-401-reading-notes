## Pandas for Data Science

![image](https://user-images.githubusercontent.com/79086986/122688541-801ded80-d225-11eb-8a4a-ae8b8e7d8066.png)


Pandas is an open source Python package that is most widely used for data science/data analysis and machine learning tasks. It is built on top of another package named Numpy, which provides support for multi-dimensional arrays. As one of the most popular data wrangling packages, Pandas works well with many other data science modules inside the Python ecosystem, and is typically included in every Python distribution, from those that come with your operating system to commercial vendor distributions like ActiveState’s ActivePython.

Import the package » import pandas as pd
A table of data is stored as a pandas DataFrame.The columns of the resulting DataFrame have different dtypes.
Each column in a DataFrame is a Series
You can do things by applying a method to a DataFrame or Series.

DataFrame.to_numpy() gives a NumPy representation of the underlying data. Note that this can be an expensive operation when your DataFrame has columns with different data types, which comes down to a fundamental difference between pandas and NumPy: NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column. When you call DataFrame.to_numpy(), pandas will find the NumPy dtype that can hold all of the dtypes in the DataFrame. This may end up being object, which requires casting every value to a Python object.

DataFrame.to_numpy() does not include the index or column labels in the output.
describe() shows a quick statistic summary of your data.

When selecting subsets of data, square brackets [] are used. Inside these brackets, you can use a single column/row label, a list of column/row labels, a slice of labels, a conditional expression or a colon.
Select specific rows and/or columns using loc when using the row and column names
Select specific rows and/or columns using iloc when using the positions in the table
You can assign new values to a selection based on loc/iloc.
Getting data in to pandas from many different file formats or data sources is supported by read_* functions.
Exporting data out of pandas is provided by different to_*methods.
The head/tail/info methods and the dtypes attribute are convenient for a first check.

pandas primarily uses the value np.nanto represent missing data. It is by default not included in computations.
Reindexing allows you to change/add/delete the index on a specified axis. This returns a copy of the data.

Series is equipped with a set of string processing methods in the str attribute that make it easy to operate on each element of the array, as in the code snippet below. Note that pattern-matching in str generally uses regular expressions by default (and in some cases always uses them).

Pandas uses the plot() method to create diagrams.Also , we can use Pyplot, a submodule of the Matplotlib library to visualize the diagram on the screen.
