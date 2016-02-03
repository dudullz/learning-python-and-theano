# learning-python-and-theano

## Python
#### Basics
(1) The slice operation will make a new copy, 
from [More Control Flow Tools](https://docs.python.org/2/tutorial/controlflow.html#for-statements)
```python
>>> for w in words[:]:  # Loop over a slice copy of the entire list.
...     if len(w) > 6:
...         words.insert(0, w)
...
>>> words
['defenestrate', 'cat', 'window', 'defenestrate']
```
(2) 9 method of list
> - list.append(x)
> - list.extend(L)
> - list.insert(i, x)
> - list.remove(x)
> - list.pop([i])
> - list.index(x)
> - list.count(x)
> - list.sort(cmp=None, key=None, reverse=False)
> - list.reverse()

(3) [Nested List Comprehensions](https://docs.python.org/2/tutorial/datastructures.html#nested-list-comprehensions)
```python
>>> [[row[i] for row in matrix] for i in range(4)]
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```
```python
>>> transposed = []
>>> for i in range(4):
...     # the following 3 lines implement the nested listcomp
...     transposed_row = []
...     for row in matrix:
...         transposed_row.append(row[i])
...     transposed.append(transposed_row)
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
```

(4) sequence unpacking, from [Tuples and Sequences](https://docs.python.org/2/tutorial/datastructures.html#tuples-and-sequences)
```ptyhon
 t = 12345, 54321, 'hello!' # example of tuple packing
>>> x, y, z = t
```
> - This is called, appropriately enough, sequence unpacking and works for **any sequence** on the right-hand side. 
> - Sequence unpacking requires the list of variables on the left to have the same number of elements as the length of the sequence.
> - **Note that multiple assignment is really just a combination of _tuple packing_ and _sequence unpacking_.**

(5) list and tuple and zip, from [zip](https://docs.python.org/2/library/functions.html#zip)
> - **NOTE the list(x2), list(y2) in below to convert tuple to list**
```python
>>> x = [1, 2, 3]
>>> y = [4, 5, 6]
>>> zipped = zip(x, y)
>>> zipped
[(1, 4), (2, 5), (3, 6)]
>>> x2, y2 = zip(*zipped)
>>> x == list(x2) and y == list(y2)
True
```

#### basic tensor functionality
> `>>> x = T.fmatrix()`
> -  the x is a TensorVariable instance
> - The T.fmatrix object itself is an instance of TensorType
> - Theano knows what type of variable x is because x.type points back to T.fmatrix

