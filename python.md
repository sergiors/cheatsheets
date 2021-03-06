---
title: Python
---

Python doesn't have type hint, is just for **semantics**, known as **annotations**. If you want static type, you need to use [MyPy](http://mypy-lang.org/).

```python
def foo(a: str) -> int:
    ...
```

## [Data Structures](https://docs.python.org/3.6/tutorial/datastructures.html)

```python
# list
# mutable

>>> [1, 2, 3, 1]
[1, 2, 3, 1]

```

```python
# tuple
# immutable

>>> (1, 2, 3, 1)
(1, 2, 3, 1)

```

```python
# dict

{'a': 1, 'b': 2}


# how to merge two dicts in Python 3.5+

>>> x = {'a': 1, 'b': 2}
>>> y = {'b': 3, 'c': 4}
>>> z = {**x, **y}
>>> z
{'a': 1, 'b': 3, 'c': 4}

```

```python
# set
# unordered collection
# no duplicate elements

>>> sorted({'apple', 'orange', 'apple', 'pear', 'orange', 'banana'})
['apple', 'banana', 'orange', 'pear']

```

Note: to create an empty set you have to use `set()`, not `{}`

---

```python
# if-else

>>> [a if a else 2 for a in [0, 1, 0, 3]]
[2, 1, 2, 3]

```

```python
# map

>>> list(map(lambda x: x+1, range(5)))
[1, 2, 3, 4, 5]

# filter
>>> list(filter(lambda x: x>5, range(10)))
[6, 7, 8, 9]

# reduce
>>> from functools import reduce
>>> reduce(lambda p, x: p+x, range(10))
45

```

```python
# function argument unpacking

>>> def myfunc(x, y, z):
...     print(x, y, z)
...

>>> tuple_vec = (1, 0, 1)
>>> dict_vec = {'x': 1, 'y': 0, 'z': 1}

>>> myfunc(*tuple_vec)
1 0 1

>>> myfunc(**dict_vec)
1 0 1

```

```python
# unpacking

>>> head, *rest = range(5)
>>> head
0
>>> rest
[1, 2, 3, 4]

>>> *rest, tail = range(5)
>>> rest
[0, 1, 2, 3]
>>> tail
4

>>> head, *rest, tail = range(5)
>>> head
0
>>> rest
[1, 2, 3]
>>> tail
4

```

```python
# keyword-only arguments
# it doesn't equal to use unpacking arguments

def compare(a, b, *, key=None):
    ...
```

```python
# f-strings

>>> name = 'Hendrix'
>>> age = 27
>>> f'Hello, {name}. You are {age}.'
'Hello, Hendrix. You are 27.'

>>> f'{2 * 37}'
'74'


# multiple lines
>>> lorem = 'Lorem ipsum'
>>> (f'{lorem} dolor sit amet, consectetur adipiscing elit.'
... f'Ut et tortor sollicitudin augue varius consequat.')
'Lorem ipsum dolor sit amet, consectetur adipiscing elit.Ut et tortor sollicitudin augue varius consequat.'

```

```python
# allow only keyword arguments after a bare `*`

def f(*, a, b):
  print(a + b)

f(1, 3)  # raises: "f() takes 0 positional arguments"
f(a=1, b=3)

```

```python
# the walrus operator
# https://docs.python.org/3/whatsnew/3.8.html#assignment-expressions

if (n := len(a)) > 10:
    print(f"List is too long ({n} elements, expected <= 10)")
```

## Refs

-   http://whypy3.com/
-   https://docs.python-guide.org/
-   https://gto76.github.io/python-cheatsheet/
-   https://dbader.org/blog/
-   https://realpython.com/inner-functions-what-are-they-good-for/
-   https://realpython.com/python-f-strings/
-   https://realpython.com/python-dicts/
-   https://treyhunner.com/2018/10/asterisks-in-python-what-they-are-and-how-to-use-them/
-   https://www.youtube.com/watch?v=--1MDx3IKac (Portuguese)
