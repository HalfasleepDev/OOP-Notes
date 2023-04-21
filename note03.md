# Data Structures
### Sections
1) Matrices & List Comprehension
2) Map & Filter
3) Tuples
4) Sets
5) Dictionary

<details>

<summary>1) Matrices & List Comprehension</summary>
 
## 1. Matrices & List Comprehension
### Matrices
- **A matrix** is a representations of numbers, symbols, or expressions in a 2-Dimensional Array.
  - Mathematical matrix diagram example:

$$
A =
\left(\begin{array}{cc} 
1 & 2 & 3 & 4\\ 
5 & 6 & 7 & 8
\end{array}\right)
$$ 

  - Row 1 has values of 1 2 3 4
  - Column 2 has values of 2 6
- In python it can be used to create data structures that have values in rows and columns. Creating a matrix in standalone python is done by utilizing a list within a list. External libraries/modules can be used to simplify and extend this process.
  - Example:
  ```python
  matrix_A = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
  ]
  ```
### List Comprehension
- List Comprehension is a concise method to create list. The technique is commonly used when:
  - The list is a result of some operations applied to all its items
  - It is a made from another sequence/iterable data
  - The list is member of another list/sequence/iterable data that satisfies a certain condition
#### Format
- A **Square Bracket** `[]` containing an expression that describes the list
- One or more **For clause** to explain its members
- Then a zero or more **if clauses** depending on the complexity of the list
#### Examples:
1) A list which squares all the numbers from [0,10)

    Before:
    ```python
    squares = []
    for i in range(10):
        squares.append(i ** 2)

    print('Our result: %s' % squares)
    ```
    After using list comprehension:
    ```python
    squares = [i**2 for i in range(10)]

    print('Our new result: %s' % squares)
    ```
    Both output: `Our result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]`

2) Using list comprehension, create the list: [[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]] From

    A = [1,2,3]
    
    B = [3,1,4]
    
    ```python
    a = [1,2,3]
    b = [3,1,4]

    result = [[x, y] for x in a for y in b if x != y]
    print(result)
    ```
    Which outputs: `[[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]`
    
    This works where `x` comes from `a` and `y` comes from `b` as long as `x` does not equal `y`
  
3) Using list comprehension to turn a 2D array called vec to a single list

    vec = [[1,2,3], [4,5,6], [7,8,9]]
    
    Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
    
    ```python
    vec = [[1,2,3], [4,5,6], [7,8,9]]

    result = [value for row in vec for value in row]
    print('Vec as a single list of values: %s' % result)
    ```
    Which outputs: `Vec as a single list of values: [1, 2, 3, 4, 5, 6, 7, 8, 9]`
    
    A vec is an example of a matrix in Python 3 by using list of lists
    
    It grabs each `value`, from where it comes from `row` inside the `vec`. Finally the last for clause to denote that value comes from the row.
  
</details>

<details>

<summary>2) Map & Filter</summary>

## 2. Map & Filter
### The Map Function
- The general idea of a map function is to apply a function to an iterable data.
- Formatting is as follows:
  ```python
  map(function_name, sequence)
  ```
  -- `function_name`: any function (built-in or selfmade) that returns a desired value of choice
  
  -- `sequence`: any iterable data type
  
  To demonstrate the map function, it will be used to square an array:
  ```python
  def square(num):
    ''' squares the given num argument '''
    return num ** 2
  # end of square

  array = list(range(1,11))
  square_array = list(map(square, array))

  print('Original Array:', array)
  print('Array Squared:', square_array)
  ```
  Output:
  ```
  Original Array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  Array Squared: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
  ```
- The map function is that it doesn’t return a specific data type, but rather, an python iterable data.
  - To resolve this, execute a list function after the map function. 
    - For example: 
    ```python
    def upper(x):
        ''' upper() turns string x into its uppercased counter part '''
        return x.upper()

    word = 'hello world!'
    upper_word = ''.join(list(map(upper, word)))

    print(word)
    print(upper_word)

    # simpler way:
    print(word.upper())
    ```
    Output:
    ```
    hello world!
    HELLO WORLD!
    HELLO WORLD!
    ```
    Although the map function works here, there is a lot of unnessesary work turning the variable to uppercase. It is an example not to use `map()` for little change to a string. 
### The Filter Function
- The general idea of a filter function is to filter out items from a data set that meets a certain condition.
- Formatting is as follows:
  ```python
  filter(bool_returning_function, sequence)
  ```
  -- `bool_returning_function`: the function name we provide for `filter()` must be return a boolean value, and should also be able handle the items inside the sequence as its arguments
  
  -- `sequence`: any iterable data type
  To demonstrate the filter function, it will be used to filter odd numbers from 1 to 100:
  ```python
  def isOdd(x):
      ''' isOdd() returns True if x is odd.'''
      return x % 2 != 0

  array = list(range(1,101))
  odds = list(filter(isOdd, array))

  print('Odd Numbers from 1 to 100:', odds)
  ```
  Output: 
  ```
  Odd Numbers from 1 to 100: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99]
  ```
### Example Problem: List of Palindromic Numbers
This program creates a list of palindromic numbers (numbers that are palindromes) from 1 to 10,000.
```python
  
```
**Explanation**:
1. string version of the array --> `map(str, array)`
2. filter out the palindrome --> `filter(isPalindrome, string version of the array)`
3. remap all values back to integers --> `map(int, palindromes)`
4. turn the mapped integers iterable back inside a list --> `list(palindromicIterables)`
