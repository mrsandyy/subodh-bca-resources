# Unit 2: Lists and Dictionaries

## 1. Lists

A list in Python is a collection of items that are **ordered**, **mutable** (can be changed), and allow **duplicate elements**. Lists are one of the most commonly used data types in Python and are defined using square brackets `[]`.

### 1.1 Key Features of Lists

- **Ordered**: The items have a defined order that will not change unless you explicitly modify the list.
- **Mutable**: You can add, remove, or change elements after the list is created.
- **Heterogeneous**: A list can contain elements of different data types (e.g., integers, strings, floats, or even other lists).
- **Dynamic**: Lists in Python can grow or shrink dynamically as you add or remove elements.
- **Indexed**: Each element in a list can be accessed using its index, starting from `0` for the first element.

### 1.2 Working with Lists

#### 1.2.1 Creating a List

You can create a list by placing a comma-separated sequence of elements inside square brackets.

```python
# Examples of lists
empty_list = []               # An empty list
fruits = ["apple", "banana", "cherry"]  # A list of strings
numbers = [1, 2, 3, 4, 5]     # A list of integers
mixed = [1, "hello", 3.14, True]  # A mixed data type list
nested_list = [[1, 2], [3, 4]]  # A nested list
```

#### 1.2.2 Accessing Elements

You can access list elements using their index. Negative indexing allows you to access elements from the end of the list.

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])  # Output: apple (first element)
print(fruits[-1]) # Output: cherry (last element)
```

#### 1.2.3 Adding Elements

- **`append()`**: Adds a single element to the end.
- **`extend()`**: Adds multiple elements to the end.
- **`insert()`**: Adds an element at a specific index.

```python
numbers = [1, 2, 3]
numbers.append(4)         # [1, 2, 3, 4]
numbers.extend([5, 6])    # [1, 2, 3, 4, 5, 6]
numbers.insert(2, 99)     # [1, 2, 99, 3, 4, 5, 6]
```

#### 1.2.4 Removing Elements

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

### 1.3 List Built-in Methods

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

#### 1.3.1 Special Features of Lists

- **Slicing**: Extract a portion of a sequence (like a list or string) using indices. It's done using the colon (:) operator.

```python
nums = [10, 20, 30, 40, 50]
print(nums[1:4])  # Output: [20, 30, 40]
```

- **Negative Indexing**: Negative indexing allows you to access elements from the end of a sequence. The last element is -1, the second-to-last is -2, and so on.

```python
print(nums[-1])  # Output: 50
```

## 2. Tuples

Tuples are a type of **sequence data structure** that are used to store collections of items. Unlike lists, tuples are **immutable**, meaning their contents cannot be changed after creation.

### 2.1 Key Features of Tuples

- **Immutable**: Once a tuple is created, you cannot add, remove, or modify its elements.
- **Ordered**: Elements in a tuple maintain their order.
- **Allows duplicates**: Tuples can contain duplicate elements.
- **Can hold multiple data types**: A tuple can store a mix of integers, strings, lists, other tuples, etc.
- **Parentheses `()`**: Tuples are defined using parentheses, although commas (`,`) are the actual tuple separators.

### 2.2 Tuple Operators

#### 2.2.1 Creating Tuples

You can create a tuple using parentheses `()` or the `tuple()` constructor.

```python
# Example of tuple creation
t1 = (1, 2, 3)
t2 = tuple([4, 5, 6])  # Using the tuple() constructor
```

#### 2.2.2 Accessing Elements

You can access elements using indexing and slicing.

- **Indexing:** Retrieves a single element.
- **Slicing:** Retrieves a sub-part of the tuple.

```python
t = (10, 20, 30, 40, 50)

# Accessing elements by index
print(t[0])  # Output: 10
print(t[-1]) # Output: 50

# Accessing a range of elements (slicing)
print(t[1:4])  # Output: (20, 30, 40)
```

#### 2.2.3 Concatenation ( `+` )

Tuples can be combined using the `+` operator.

```python
t1 = (1, 2)
t2 = (3, 4)
print(t1 + t2)  # Output: (1, 2, 3, 4)
```

#### 2.2.4 Repetition ( `*` )

You can repeat tuples using the `*` operator.

```python
print(t1 * 2)   # Output: (1, 2, 1, 2)
```

#### 2.2.5 Membership Testing

Check if an item exists in a tuple using the `in` or `not in` operators.

```python
print(2 in t1)  # Output: True
print(5 not in t2) # Output: True
```

#### 2.2.6 Iterating Through Tuples

You can iterate through a tuple using a `for` loop.

```python
for item in t1:
    print(item)
```

### 2.3 Tuples Built-in Functions

| **Function**  | **Description**                                                                                 | **Example**                        | **Output**                       |
| ------------- | ----------------------------------------------------------------------------------------------- | ---------------------------------- | -------------------------------- |
| `len()`       | Returns the number of elements in the tuple.                                                    | `len((1, 2, 3))`                   | `3`                              |
| `max()`       | Returns the maximum value in the tuple.                                                         | `max((10, 20, 30))`                | `30`                             |
| `min()`       | Returns the minimum value in the tuple.                                                         | `min((10, 20, 30))`                | `10`                             |
| `sum()`       | Returns the sum of all elements in the tuple (only for numeric elements).                       | `sum((1, 2, 3))`                   | `6`                              |
| `sorted()`    | Returns a sorted list of the tuple elements (does not modify the original tuple).               | `sorted((3, 1, 2))`                | `[1, 2, 3]`                      |
| `tuple()`     | Converts an iterable (like a list, string, or range) into a tuple.                              | `tuple([1, 2, 3])`                 | `(1, 2, 3)`                      |
| `all()`       | Returns `True` if all elements in the tuple are `True` (or the tuple is empty).                 | `all((True, 1, "text"))`           | `True`                           |
| `any()`       | Returns `True` if at least one element in the tuple is `True`.                                  | `any((False, 0, "text"))`          | `True`                           |
| `enumerate()` | Returns an enumerate object that yields pairs of index and value for each element in the tuple. | `list(enumerate(("a", "b", "c")))` | `[(0, 'a'), (1, 'b'), (2, 'c')]` |
| `reversed()`  | Returns a reverse iterator for the tuple.                                                       | `tuple(reversed((1, 2, 3)))`       | `(3, 2, 1)`                      |
| `zip()`       | Combines elements from multiple iterables into tuples.                                          | `list(zip((1, 2), ('a', 'b')))`    | `[(1, 'a'), (2, 'b')]`           |

#### Notes:

- These functions do not modify the tuple itself since tuples are immutable.
- Some functions (e.g., `max`, `min`, `sum`) are applicable only if all elements in the tuple are numeric or comparable.

### 2.4 Special Features of Tuples

| Feature                        | Description                                                                       |
| ------------------------------ | --------------------------------------------------------------------------------- |
| **Immutability**               | Tuples cannot be modified after creation, ensuring data integrity.                |
| **Faster Than Lists**          | Tuples are faster due to immutability and fixed size.                             |
| **Hashable**                   | Can be used as keys in dictionaries or elements in sets if elements are hashable. |
| **Heterogeneous Data**         | Can store elements of different data types.                                       |
| **Nested Tuples**              | Support for multi-level tuples.                                                   |
| **Memory Efficient**           | Consume less memory compared to lists.                                            |
| **Packing & Unpacking**        | Group multiple values or assign tuple elements to variables.                      |
| **Basic Operations**           | Support indexing, slicing, concatenation, repetition, and membership testing.     |
| **Readability**                | Often used to return multiple values from functions.                              |
| **Immutable Constants**        | Ideal for storing fixed, unchanging data.                                         |
| **Lexicographical Comparison** | Can be compared based on element order.                                           |

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
