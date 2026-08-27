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

print(make_username("Ada", "Lovelace"))
print(make_username("Alan", "Turing"))
print(make_username("Ana Maria", "De Leon"))
```

#### C. Bookend Swap Problem
The swap_bookends(items) function takes a list of at least two items and returns a new list where the first and last elements have swapped positions while leaving the middle elements untouched. It utilizes extended sequence unpacking (first, *middle, last) to break down the input list and construct the modified sequence without altering the original input.

```python
def swap_bookends(items):
    first, *middle, last = items
    return [last, *middle, first]

print(swap_bookends([1, 2, 3, 4, 5, 6]))
print(swap_bookends(["red", "green", "blue"]))
print(swap_bookends([8, 3]))
```

## READMe File Version History
August 27, 2026 - Update READMe output uploaded
