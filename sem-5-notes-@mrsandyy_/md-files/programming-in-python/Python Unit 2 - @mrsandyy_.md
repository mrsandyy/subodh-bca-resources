# Unit 2: Lists and Dictionaries

## 1. Lists

A list in Python is a collection of items that are **ordered**, **mutable** (can be changed), and allow **duplicate elements**. Lists are one of the most commonly used data types in Python and are defined using square brackets `[]`.

### 1.1 Key Features of Lists

- **Ordered**: The items have a defined order that will not change unless you explicitly modify the list.
- **Mutable**: You can add, remove, or change elements after the list is created.
- **Heterogeneous**: A list can contain elements of different data types (e.g., integers, strings, floats, or even other lists).
- **Dynamic**: Lists in Python can grow or shrink dynamically as you add or remove elements.
- **Indexed**: Each element in a list can be accessed using its index, starting from `0` for the first element.

### 1.2 Creating a List

You can create a list by placing a comma-separated sequence of elements inside square brackets.

```python
# Examples of lists
empty_list = []               # An empty list
fruits = ["apple", "banana", "cherry"]  # A list of strings
numbers = [1, 2, 3, 4, 5]     # A list of integers
mixed = [1, "hello", 3.14, True]  # A mixed data type list
nested_list = [[1, 2], [3, 4]]  # A nested list
```

### 1.3 Accessing Elements

You can access list elements using their index. Negative indexing allows you to access elements from the end of the list.

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])  # Output: apple (first element)
print(fruits[-1]) # Output: cherry (last element)
```

### 1.4 Modifying a List

Since lists are mutable, you can modify their contents.

#### 1.4.1 Adding Elements:

- **`append()`**: Adds a single element to the end.
- **`extend()`**: Adds multiple elements to the end.
- **`insert()`**: Adds an element at a specific index.

```python
numbers = [1, 2, 3]
numbers.append(4)         # [1, 2, 3, 4]
numbers.extend([5, 6])    # [1, 2, 3, 4, 5, 6]
numbers.insert(2, 99)     # [1, 2, 99, 3, 4, 5, 6]
```

#### 1.4.2 Removing Elements:

- **`remove()`**: Removes the first occurrence of a specific value.
- **`pop()`**: Removes an element at a specified index (or the last element if no index is provided).
- **`clear()`**: Removes all elements from the list.

```python
numbers = [1, 2, 3, 4, 5]
numbers.remove(3)    # [1, 2, 4, 5]
numbers.pop()        # [1, 2, 4] (removes the last element)
numbers.pop(1)       # [1, 4] (removes element at index 1)
numbers.clear()      # [] (empty list)
```

### 1.5 List Built-in Methods

| **Method**                      | **Description**                                                                                   | **Example**                                                 |
| ------------------------------- | ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| `append(item)`                  | Adds an item to the end of the list.                                                              | `numbers = [1, 2, 3]; numbers.append(4)` → `[1, 2, 3, 4]`   |
| `extend(iterable)`              | Adds all elements of an iterable (e.g., another list) to the end of the list.                     | `numbers = [1, 2]; numbers.extend([3, 4])` → `[1, 2, 3, 4]` |
| `insert(index, item)`           | Inserts an item at the specified index.                                                           | `numbers = [1, 3]; numbers.insert(1, 2)` → `[1, 2, 3]`      |
| `remove(item)`                  | Removes the first occurrence of the specified item.                                               | `numbers = [1, 2, 3, 2]; numbers.remove(2)` → `[1, 3, 2]`   |
| `pop(index=-1)`                 | Removes and returns the item at the specified index (default is the last item).                   | `numbers = [1, 2, 3]; numbers.pop()` → `[1, 2]`             |
| `clear()`                       | Removes all items from the list.                                                                  | `numbers = [1, 2, 3]; numbers.clear()` → `[]`               |
| `index(item, start, end)`       | Returns the index of the first occurrence of the item between optional `start` and `end` indices. | `numbers = [1, 2, 3]; numbers.index(2)` → `1`               |
| `count(item)`                   | Returns the number of occurrences of the specified item.                                          | `numbers = [1, 2, 2, 3]; numbers.count(2)` → `2`            |
| `sort(key=None, reverse=False)` | Sorts the list in ascending order (or descending if `reverse=True`).                              | `numbers = [3, 1, 2]; numbers.sort()` → `[1, 2, 3]`         |
| `reverse()`                     | Reverses the order of the list.                                                                   | `numbers = [1, 2, 3]; numbers.reverse()` → `[3, 2, 1]`      |
| `copy()`                        | Returns a shallow copy of the list.                                                               | `numbers = [1, 2, 3]; copy = numbers.copy()` → `[1, 2, 3]`  |

```python
numbers = [5, 3, 8]
numbers.append(10)   # [5, 3, 8, 10]
numbers.sort()        # [3, 5, 8, 10]
print(numbers.pop())  # Output: 10
```

#### 1.5.1 Special Features of Lists

- **Slicing**: Extract sublists. Extract a portion of a sequence (like a list or string) using indices. It's done using the colon (:) operator.

```python
nums = [10, 20, 30, 40, 50]
print(nums[1:4])  # Output: [20, 30, 40]
```

- **Negative Indexing**: Negative indexing allows you to access elements from the end of a sequence. The last element is -1, the second-to-last is -2, and so on.

```python
print(nums[-1])  # Output: 50
```

## 2. Tuples

#### Tuple Operators and Built-in Functions

Tuples are immutable sequences in Python.

```python
# Example of tuple creation
coordinates = (10, 20, 30)
```

- **Operators**:
  - Concatenation: `+`
  - Repetition: `*`

```python
a = (1, 2)
b = (3, 4)
print(a + b)  # Output: (1, 2, 3, 4)
print(a * 2)  # Output: (1, 2, 1, 2)
```

- **Built-in Functions**:
  - `len(tuple)`: Returns the number of elements.
  - `max(tuple)`: Returns the largest element.
  - `min(tuple)`: Returns the smallest element.
  - `tuple(iterable)`: Converts an iterable to a tuple.

```python
nums = (5, 10, 15)
print(len(nums))  # Output: 3
```

#### Special Features of Tuples

- Can be used as keys in dictionaries because they are hashable.
- Packing and unpacking:

```python
# Tuple packing
point = 3, 4
# Tuple unpacking
x, y = point
print(x, y)  # Output: 3 4
```

## 3. Dictionaries

#### Introduction to Dictionaries

Dictionaries store data as key-value pairs, where keys must be unique and immutable.

```python
# Example dictionary
student = {"name": "John", "age": 20}
print(student["name"])  # Output: John
```

#### Built-in Functions

- **`len(dict)`**: Returns the number of key-value pairs.
- **`dict.keys()`**: Returns a view object of keys.
- **`dict.values()`**: Returns a view object of values.
- **`dict.items()`**: Returns a view object of key-value pairs.

```python
print(student.keys())   # Output: dict_keys(['name', 'age'])
print(student.values()) # Output: dict_values(['John', 20])
```

#### Built-in Methods

- **`get(key, default)`**: Returns the value for `key` or `default` if the key does not exist.
- **`update(other_dict)`**: Merges another dictionary.
- **`pop(key)`**: Removes and returns the value for `key`.
- **`clear()`**: Removes all items.

```python
student.update({"grade": "A"})
print(student)  # {'name': 'John', 'age': 20, 'grade': 'A'}
```

#### Dictionary Keys

Keys must be:

- Unique
- Immutable types (e.g., strings, numbers, tuples)

```python
# Valid keys
d = {1: "one", (2, 3): "tuple"}
```

## 4. Sets

#### Introduction to Sets

Sets are unordered collections of unique elements.

```python
# Example of a set
numbers = {1, 2, 3, 3}
print(numbers)  # Output: {1, 2, 3}
```

#### Comparing Sets

- **Subset**: `<=`
- **Superset**: `>=`
- **Equality**: `==`

```python
a = {1, 2}
b = {1, 2, 3}
print(a <= b)  # Output: True
```

#### Mathematical Set Operations

- **Union**: `|` or `set.union()`
- **Intersection**: `&` or `set.intersection()`
- **Difference**: `-` or `set.difference()`
- **Symmetric Difference**: `^` or `set.symmetric_difference()`

```python
a = {1, 2, 3}
b = {3, 4, 5}
print(a | b)  # Output: {1, 2, 3, 4, 5}
print(a & b)  # Output: {3}
```

#### Set Comprehensions

Set comprehensions allow concise set creation.

```python
# Example: Set of squares
squares = {x**2 for x in range(5)}
print(squares)  # Output: {0, 1, 4, 9, 16}
```
