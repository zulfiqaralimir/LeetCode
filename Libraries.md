## Collections in LeetCode Python

In the context of LeetCode and Python, a "collection" generally refers to a variety of data structures provided by the `collections` module in Python. The `collections` module implements specialized container datatypes providing alternatives to Python’s general-purpose built-in containers like `dict`, `list`, `set`, and `tuple`.

Here are some of the most commonly used collections from the `collections` module that you might encounter or find useful in solving LeetCode problems:

### `Counter`
A dictionary subclass for counting *hashable objects*. It's useful for counting occurrences of elements in an iterable.
```python
from collections import Counter

cnt = Counter(['red', 'blue', 'red', 'green', 'blue', 'blue'])
print(cnt)  # Output: Counter({'blue': 3, 'red': 2, 'green': 1})

### `defaultdict`
A dictionary subclass that calls a *factory function* to supply *missing values*.
