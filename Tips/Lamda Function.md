# Lambda Functions in Python

Lambda functions, also known as anonymous functions, are small, unnamed functions defined using the `lambda` keyword. They are often used for short-term tasks and are defined in a single line. The syntax for a lambda function is:
```
lambda arguments: expression
```

# Lambda Functions in Python

Lambda functions, also known as anonymous functions, are small, unnamed functions defined using the `lambda` keyword. They are often used for short-term tasks and are defined in a single line. The syntax for a lambda function is:

- **arguments**: A comma-separated list of arguments.
- **expression**: An expression that is evaluated and returned.

## Characteristics of Lambda Functions

- **Anonymous**: Lambda functions are not bound to a name.
- **Single Expression**: They contain a single expression whose result is returned.
- **Short-term Use**: Commonly used as arguments to higher-order functions (like `map`, `filter`, and `sorted`).

## Example

Here’s an example of a simple lambda function that adds 10 to a given number:

```python
add_ten = lambda x: x + 10
print(add_ten(5))  # Output: 15
```

In this example, `lambda x: x + 10` is a lambda function that takes one argument `x` and returns `x + 10`.

## Using Lambda Functions with `map`

Lambda functions are often used with higher-order functions like `map`. Here’s an example:

```python
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

In this example, `lambda x: x * x` is a lambda function that squares each number in the `numbers` list.

## Using Lambda Functions with `filter`

Lambda functions can also be used with the `filter` function, which filters items in an iterable based on a condition. Here’s an example:

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # Output: [2, 4, 6, 8, 10]
```

In this example, `lambda x: x % 2 == 0` is a lambda function that returns `True` if a number is even and `False` otherwise.

## Using Lambda Functions with `sorted`

Lambda functions can also be used as the `key` argument in the `sorted` function to customize the sort order. Here’s an example:

```python
students = [
    {'name': 'John', 'age': 15},
    {'name': 'Jane', 'age': 12},
    {'name': 'Dave', 'age': 10}
]

sorted_students = sorted(students, key=lambda x: x['age'])
print(sorted_students)
# Output: [{'name': 'Dave', 'age': 10}, {'name': 'Jane', 'age': 12}, {'name': 'John', 'age': 15}]
```

## Summary

Lambda functions in Python are concise, unnamed functions defined using the `lambda` keyword. They are useful for short-term tasks and can be used as arguments to higher-order functions like `map`, `filter`, and `sorted`. Despite their brevity, they are powerful tools for creating small, quick functions without the need to formally define them using `def`.
