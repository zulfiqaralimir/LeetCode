```markdown
## Collections in LeetCode Python

In the context of LeetCode and Python, a "collection" generally refers to a variety of data structures provided by the `collections` module in Python. The `collections` module implements specialized container datatypes providing alternatives to Python’s general-purpose built-in containers like `dict`, `list`, `set`, and `tuple`.

Here are some of the most commonly used collections from the `collections` module that you might encounter or find useful in solving LeetCode problems:

### `Counter`
A dictionary subclass for counting hashable objects. It's useful for counting occurrences of elements in an iterable.
```python
from collections import Counter

cnt = Counter(['red', 'blue', 'red', 'green', 'blue', 'blue'])
print(cnt)  # Output: Counter({'blue': 3, 'red': 2, 'green': 1})
```

### `defaultdict`
A dictionary subclass that calls a factory function to supply missing values.
```python
from collections import defaultdict

dd = defaultdict(int)
dd['key1'] += 1
print(dd)  # Output: defaultdict(<class 'int'>, {'key1': 1})
```

### `deque`
A list-like container with fast appends and pops on either end.
```python
from collections import deque

d = deque(['a', 'b', 'c'])
d.append('d')
d.appendleft('z')
print(d)  # Output: deque(['z', 'a', 'b', 'c', 'd'])
```

### `namedtuple`
A factory function for creating tuple subclasses with named fields.
```python
from collections import namedtuple

Point = namedtuple('Point', ['x', 'y'])
p = Point(1, 2)
print(p.x, p.y)  # Output: 1 2
```

### `OrderedDict`
A dictionary subclass that remembers the order entries were added.
```python
from collections import OrderedDict

od = OrderedDict()
od['a'] = 1
od['b'] = 2
od['c'] = 3
print(od)  # Output: OrderedDict([('a', 1), ('b', 2), ('c', 3)])
```

Using these specialized data structures can often make your solutions more efficient and readable, especially for problems involving counting elements, maintaining order, or implementing queues.

```
```
### defaultdict in Simple Terms
```
from collections import defaultdict

words = ['apple', 'banana', 'apple', 'orange', 'banana', 'apple']
word_count = defaultdict(int)

for word in words:
    word_count[word] += 1

print(word_count)  # Output: defaultdict(<class 'int'>, {'apple': 3, 'banana': 2, 'orange': 1})

```

Here, you don't need to worry about checking if the word is already in the dictionary. If it's not, defaultdict automatically creates it with a default value of 0.

In summary, defaultdict is a handy tool that simplifies working with dictionaries by automatically handling missing keys with default values you specify.


* In a defaultdict(int), if you access a key that doesn’t exist, it automatically creates that key and sets its value to 0 
* Without defaultdict, you would need to check if the key exists first:

### Visual Explanation
Regular Dictionary:

You must manually check if a key exists and create it if it doesn’t.
defaultdict:

Automatically creates a key with a default value if the key doesn’t exist.
### Summary
defaultdict simplifies your code by automatically creating keys with default values when you access or modify a missing key.
This avoids the need to check if the key exists before using it.
