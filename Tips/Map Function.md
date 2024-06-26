### `map` Function in Python

The `map` function in Python is a built-in function used to apply a given function to all items in an input list (or any iterable). It returns a map object (which is an iterator) of the results. The syntax for `map` is:

```python
map(function, iterable, ...)
```

**function**: The function to apply to each item in the iterable.
**iterable**: One or more iterables (e.g., lists, tuples, sets).

The map function applies the given function to each item of the iterable(s) and returns a map object. If multiple iterables are passed, the function should take that many arguments and is applied to the items from all iterables **in parallel**.

### Example
Here is an example to demonstrate how map works:

# Function to square a number
def square(x):
    return x * x

# List of numbers
numbers = [1, 2, 3, 4, 5]

# Use map to apply the square function to each item in the numbers list
squared_numbers = map(square, numbers)

# Convert the map object to a list and print it
print(list(squared_numbers))
```

[1, 4, 9, 16, 25]
```
