
## What is Jupyter Lab 

***JupyterLab is a next-generation web-based user interface for Project Jupyter.*** 

***JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals.*** 

* text editor and jupyter includes syntax highlighting and configurable indentation. 

* terminals in jupyter provide full support for system shells on mac linux and powerShell on windows. 

* jupyter notebookes like spreadsheets or presentations it is work easily with data and code it has 2 modes : 

*command mode : is designed for easily navigating and changing framework of your book that framework is composed of cells which keep your data thoughts and code in little containers* 

*edit mode : to edit* 

## Numpy Tutorial 

***NumPy is a commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem, like scikit-learn, that use NumPy under the hood.*** 

### Numpy 2-Dimensional Arrays 

**A 2-dimensional array is also known as a matrix, and is something you should be familiar with. In fact, it’s just a different way of thinking about a list of lists. A matrix has rows and columns. By specifying a row number and a column number, we’re able to extract an element from a matrix.** 

### Creating A NumPy Array

**to create a NumPy array use the numpy.array function. If pass in a list of lists, it will automatically create a NumPy array with the same number of rows and columns** 

### Alternative NumPy Array Creation Methods 

* There are a variety of methods that you can use to create NumPy arrays. To start with, you can create an array where every element is zero, using numpy.zeros 

* You can also create an array where each element is a random number using numpy.random.rand 

### Using NumPy To Read In Files

**to use NumPy to directly read csv or other files into arrays. We can do this using the numpy.genfromtxt function.** 

### Indexing NumPy Arrays 

**can use array indexing to select individual elements, groups of elements, or entire rows and columns. One important thing to keep in mind is that just like Python lists, NumPy is zero-indexed, meaning that the index of the first row is 0, and the index of the first column is 0. If we want to work with the fourth row, we’d use index 3, if we want to work with the second row, we’d use index 1, and so on.** 

### NumPy Data Types 

***each NumPy array can store elements of a single data type.*** 


1. float — numeric floating point data.
2. int — integer data.
3. string — character data.
4. object — Python objects.

### Converting Data Types

**use the numpy.ndarray.astype method to convert an array to a different type.** 

### NumPy Array Operations 

**NumPy makes it simple to perform mathematical operations on arrays. This is one of the primary advantages of NumPy, and makes it quite easy to do computations.** 

> Single Array Math 
**If you do any of the basic mathematical operations (/ , * , - , + , ^) with an array and a value, it will apply the operation to each of the elements in the array.** 


> Multiple Array Math 
**It’s also possible to do mathematical operations between arrays. This will apply the operation to pairs of elements. For example** 

> NumPy Array Methods 
**NumPy also has several methods that you can use for more complex calculations on arrays.** 

### NumPy Array Comparisons 

**NumPy makes it possible to test to see if rows match certain values using mathematical comparison operations like <, >, >=, <=, and ==.** 

### Subsetting 

**One of the powerful things we can do with a Boolean array and a NumPy array is select only certain rows or columns in the NumPy array.** 

### Reshaping NumPy Arrays

**can change the shape of arrays while still preserving all of their elements. This often can make it easier to access array elements. The simplest reshaping is to flip the axes, so rows become columns, and vice versa. We can accomplish this with the numpy.transpose function**

### Combining NumPy Arrays

**With NumPy, it’s very common to combine multiple arrays into a single unified array. can use numpy.vstack to vertically stack multiple arrays. Think of it like the second arrays’s items being added as new rows to the first array. can read in the winequality-white.csv dataset that contains information on the quality of white wines, then combine it with our existing dataset, wines, which contains information on red wines.**
