# Markdown notes

A markdown file is made by using .md file extension

## 1. Headings

The level is indicated bt the number of hashtags
```
# A first-level heading
## A second level heading
### A third level heading
```

## 2. Quoting code

To make a code block use triple backticks. The language is indicated after the triple backticks. 
````
```python
print('Hello world')
```
````
```python
print('Hello world')
```
They can also be used in line 
````
`*`
````
`*`
## 3. Tables

Tables are made with pipes `|` and hyphens `-`. There must be at least three hyphens in each column of the header row.
```
| Section 1 | Section 2 |
| --- | --- |
| Cell 1 | Cell 2 |
```
| Section 1 | Section 2 |
| --- | --- |
| Cell 1 | Cell 2 |
## 4. Lists
Unordered lists:
```
- Line 1
+ Line 2
* Line 3
```
- Line 1
+ Line 2
* Line 3

Ordered lists:
```
1. Line 1
2. Line 2
3. Line 3
```
1. Line 1
2. Line 2
3. Line 3

Nested lists:
```
- Line 1
  - Line 2
    - Line 3
```
- Line 1
  - Line 2
    - Line 3

## 5. A collapsed section
A dropdown menu until the reader clicks
````
<details>

<summary>Label goes here</summary>

### Sample header

Text here

```python
print('Sample code block')
```

</details>
````
<details>

<summary>Label goes here</summary>

### Sample header

Text here

```python
print('Sample code block')
```

</details>
