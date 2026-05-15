
# AMA Questions & Answers
---

# 1. Adhikya Edammala — What is a Class in Python?

A **class** is a blueprint used to create objects in Python.  
It defines attributes (variables) and methods (functions).

## Example

```python
class Student:
    def __init__(self, name):
        self.name = name

    def display(self):
        print(self.name)

s1 = Student("Naman")
s1.display()
```

## Output

```python
Naman
```

---

# 2. Allanki VV Manikanta Sai — What are Functions in Python?

Functions are reusable blocks of code used to perform a specific task.

## Example

```python
def add(a, b):
    return a + b

result = add(2, 3)
print(result)
```

## Output

```python
5
```

---

# 3. Arpit Yadav — How to Handle Exceptions?

Exceptions are runtime errors.  
Python handles them using `try`, `except`, `finally`.

## Example

```python
try:
    num = int(input("Enter number: "))
    print(10 / num)

except ZeroDivisionError:
    print("Cannot divide by zero")

except ValueError:
    print("Invalid input")

finally:
    print("Execution completed")
```

---

# 4. Boorle Sowmya Sri Lakshmi — Different Methods to Access Private Variables

Private variables are created using double underscore `__`.

## Example

```python
class Demo:
    def __init__(self):
        self.__x = 10

obj = Demo()
```

## Methods to Access

### 1. Using Getter Method

```python
class Demo:
    def __init__(self):
        self.__x = 10

    def get_x(self):
        return self.__x

obj = Demo()
print(obj.get_x())
```

### 2. Using Name Mangling

```python
print(obj._Demo__x)
```

---

# 5. Injamuri Arun Kumar — Mutable and Immutable Types in Python

## Mutable

Objects whose values can be changed after creation.

### Examples

```python
list
dict
set
```

```python
a = [1, 2]
a.append(3)
print(a)
```

## Immutable

Objects whose values cannot be changed.

### Examples

```python
int
float
tuple
string
```

```python
x = "hello"
# x[0] = 'H'  -> Error
```

---

# 6. Kamparapu Lakshman — What is the Return Type of `dict.items()`?

`dict.items()` returns a **dict_items** object.

## Example

```python
d = {"a": 1, "b": 2}

x = d.items()

print(type(x))
```

## Output

```python
<class 'dict_items'>
```

---

# 7. M Harivardhan Reddy — Difference Between Parameters and Arguments

| Parameters | Arguments |
|---|---|
| Variables in function definition | Actual values passed |
| Declared while creating function | Given while calling function |

## Example

```python
def add(a, b):   # Parameters
    return a + b

add(2, 3)        # Arguments
```

---

# 8. Md Musharaf — Method to Convert List to String

Use `join()`.

## Example

```python
lst = ["Python", "is", "easy"]

result = " ".join(lst)

print(result)
```

## Output

```python
Python is easy
```

---

# 9. Nayunipatruni Harsha Vardhan — Use of `pop()` and `remove()` in List

| pop() | remove() |
|---|---|
| Removes using index | Removes using value |
| Returns removed element | Does not return element |

## Example

```python
lst = [10, 20, 30]

lst.pop(1)
print(lst)
```

## Output

```python
[10, 30]
```

## Example

```python
lst = [10, 20, 30]

lst.remove(20)
print(lst)
```

## Output

```python
[10, 30]
```

---

# 10. Parlapalli Sulochana — Is Constructor Overloading Possible in Python?

Python does not support true constructor overloading directly.

But it can be achieved using:

- Default arguments
- `*args`

## Example

```python
class Demo:
    def __init__(self, a=None):
        if a:
            print(a)
        else:
            print("No value")

Demo()
Demo(10)
```

---

# 11. Rongala Vasu — What is Multiple Inheritance?

When one class inherits from more than one parent class.

## Example

```python
class A:
    def showA(self):
        print("Class A")

class B:
    def showB(self):
        print("Class B")

class C(A, B):
    pass

obj = C()

obj.showA()
obj.showB()
```

---

# 12. Rovinpal Udupi — Difference Between `.sort()` and `sorted()`

| `.sort()` | `sorted()` |
|---|---|
| Modifies original list | Creates new sorted list |
| Works only on lists | Works on all iterables |
| Returns `None` | Returns sorted list |

## Example

```python
a = [3, 1, 2]

a.sort()

print(a)
```

## Example

```python
a = [3, 1, 2]

b = sorted(a)

print(b)
```

---

# 13. Tumma Haritha — Difference Between `keys()`, `values()`, and `items()`

| Method | Returns |
|---|---|
| `keys()` | All keys |
| `values()` | All values |
| `items()` | Key-value pairs |

## Example

```python
d = {"a": 1, "b": 2}

print(d.keys())
print(d.values())
print(d.items())
```

---

# 14. Vikas Mehta — Time Complexity of Python List Sort Function

Python uses **Timsort** algorithm.

## Time Complexity

| Case | Complexity |
|---|---|
| Best Case | O(n) |
| Average Case | O(n log n) |
| Worst Case | O(n log n) |

## Example

```python
a = [5, 2, 1, 4]

a.sort()

print(a)
```

---

# 15. Yash Nitin Raut — Difference Between Options and Flags in Linux

| Options | Flags |
|---|---|
| Modify command behavior | Special type of option |
| Can have values | Usually boolean |
| May use single or double dash | Mostly single dash |

## Example

### Flag

```bash
ls -a
```

`-a` shows hidden files.

### Option with Value

```bash
grep -i "hello" file.txt
```

`-i` makes search case-insensitive.

### Long Option

```bash
ls --help
```

Displays help information.
