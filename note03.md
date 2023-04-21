# Data Structures
### Sections
- Matrices & List Comprehension
- Map & Filter
- Tuples
- Sets
- Dictionary

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
