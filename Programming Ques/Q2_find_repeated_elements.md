---
title: Find Repeated Elements
tags: ['set', 'filtering']
---

# Problem Statement

Given a list, return a list of elements which are repeated in the input list.

**Example**
```python
input list -> [1, 2, 3, 2, 3, 3, 4, 5, 6, 5] #here 2,3,5 have repetitions
output modified list -> [2, 3, 5]
```

# Solution

```python test.py  -r 'python test.py'
<template>
def find_repeated_elements(data: list) -> list:
    '''
    Find elements that are repeated in the input list.
    Parameters:
    - data: List of items (any type)

    Returns:
    - A list of repeated elements (in order of first occurrence)'''
    <los>return ...</los>
    <sol>
    seen = set()
    return list(
        filter(
            lambda x: data.count(x) > 1 and x not in seen and not seen.add(x),
            data
        )
    )
    </sol>
</template>
<suffix_invisible>
{% include '../function_type_and_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
is_equal(
    find_repeated_elements([1, 2, 3, 2, 4, 5, 3, 6, 1]), [1, 2, 3]
    )
```

## Output 1

```
[1, 2, 3]
```

## Input 2

```
is_equal(
    find_repeated_elements(['apple', 'banana', 'apple', 'cherry', 'banana']), ['apple', 'banana']
    )
```
## Output 2

```
['apple', 'banana']
```

## Input 3

```
is_equal(
    find_repeated_elements([10, 20, 30, 40]), []
    )
```

## Output 3

```
[]
```

# Private Test Cases

## Input 1

```
is_equal(
    find_repeated_elements([7, 7, 7, 7, 7]),
    [7]
)
is_equal(
    find_repeated_elements([1, 2, 'apple', 2, 'banana', 'apple']), 
    [2, 'apple']
)
is_equal(
    find_repeated_elements([]), 
    []
)
```

## Output 1

```
[7]
[2, 'apple']
[]
```