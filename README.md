# Programming Assignment 1
#### Made by: Lazaro, Kyle Gabrielle A. | 2ECE-C
#### Date Submitted: August 27, 2026  

## Objectives:
1. use basic Python functions, operators, and string operations;
2. manipulate strings using indexing, slicing, and built-in string methods;
3. apply sequence unpacking to manipulate the elements of a list; and
4. construct simple Python functions that return a specified result.


#### A. Word Rotation Problem
The rotate_word(text) function takes a non-empty string and shifts its initial character to the end while maintaining the original order and casing of all remaining characters. This is accomplished by using Python string slicing to extract the trailing substring and concatenate the first character to the end.

```python
def rotate_word(word):
    return word[1:] + word[0]

print (rotate_word("python"))
print (rotate_word("logic"))
print (rotate_word("Code"))
print (rotate_word("A"))
print (rotate_word("smile"))
```

#### B. Username Builder Problem
The make_username(first_name, last_name) function accepts two name strings, strips out all internal spaces, converts every character to lowercase, and joins the processed names with a single period. It relies on built-in string methods like .lower() and .replace() alongside Python f-strings to format and return the final handle.

```python
def make_username(first_name, last_name):
    username = first_name.lower().replace(" ", "") + "." + last_name.lower().replace(" ", "")
    return (username)
    
print (make_username("Ada", "Lovelace"))
print (make_username("Alan", "Turing"))
print (make_username("Ana Maria", "De Leon"))
```

#### C. Bookend Swap Problem
The swap_bookends(items) function takes a list of at least two items and returns a new list where the first and last elements have swapped positions while leaving the middle elements untouched. It utilizes extended sequence unpacking (first, *middle, last) to break down the input list and construct the modified sequence without altering the original input.

```python
def swap_bookend(var):
    first, *middle, last = var 
    return [last, *middle, first]

numbers = [1, 2, 3, 4, 5, 6]
print (swap_bookend(numbers))

colors = ["red", "green", "blue"]
print (swap_bookend(colors))

n2 = [8, 3]
print (swap_bookend(n2))
```

## READMe File Version History
August 27, 2026 - Update READMe output uploaded


# Programming Assignment 2
## Objectives:
1. create and reshape NumPy arrays using appropriate NumPy functions;
2. perform vectorized numerical operations on an ndarray;
3. compute array statistics and use Boolean conditions to select elements; and
4. save computed NumPy arrays as .npy files.

#### A. Reproducible Normalization Problem
- This task requires generating a reproducible $5\times 5$ matrix of random integers from 10 to 100 using the fixed random seed 2112, normalizing its elements using standard score scaling based on the population mean and standard deviation, displaying the required array statistics, and exporting the resulting array to X_normalized.npy

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

x_bar = np.mean(X)

sigma = np.std(X)

X_normalized = (X - x_bar) / sigma

np.save('X_normalized.npy', X_normalized)
```

#### B. Cubes Divisible by 4 Problem
- This task involves creating a $10\times 10$ array containing the cubed values of the first 100 positive integers, applying Boolean filtering to select only the cubed values divisible by 4, displaying the output shape and selected elements, and saving the filtered array to div_by_4.npy.

```python
C = np.arange(1, 101)
C.resize(10, 10)

div_by_4 = C[C % 4 == 0]

div_by_4.size

np.save('div_by_4.npy', div_by_4)
```

#### C. Above-Mean Squares Problem
- This task asks to construct a $6\times 6$ matrix filled with the squared values of the first 36 positive integers, calculate the mean of all matrix elements, use Boolean filtering to extract elements strictly greater than the mean, display the required verification metrics, and save the array as above_mean.npy. 
```python
S = (np.arange(1, 37) ** 2).reshape(6, 6)

S_mean = np.mean(S)

above_mean = S[S > S_mean]

above_mean.size

np.save('above_mean.npy', above_mean)
```

## READMe File Version History
September 3, 2026 - Update READMe output uploaded
