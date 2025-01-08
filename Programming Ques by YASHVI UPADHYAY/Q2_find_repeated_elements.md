---
title: Find Repeated Elements
tags: ['set', 'filtering','lambda']
---

# Problem Statement

Given a list, return a list containing elements which are repeated, equal. (case, type sensistive)

**Example:**
```python
input list -> [1, 2, 3, 2, 3, 3, 4,'A','b','B','A'] #here 2,3,'A' have repetitions
output list -> [2, 3, 'A']
```
**Don't use loops. Use functional programming like lambda/map etc...**

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
{% include '../is_equal_loops_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
if not check_for_loops(find_repeated_elements):
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
if not check_for_loops(find_repeated_elements):
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
if not check_for_loops(find_repeated_elements):
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
if not check_for_loops(find_repeated_elements):
    is_equal(
        find_repeated_elements([7, 7, 7, 7, 7]),
        [7]
    )
    is_equal(
        find_repeated_elements([1, 2, 'apple', 2, 'banana', 'apple','bAnana']), 
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
