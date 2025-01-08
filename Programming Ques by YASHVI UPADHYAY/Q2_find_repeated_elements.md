---
title: Find Repeated Elements
tags: ['set', 'filtering','lambda','data-processing']
---

# Problem Statement

Given a list, return a str list containing elements **which are repeated**. (case, type sensistive ==, ascending order)

**Example:**
```python
input list -> [1, 2, 3, '2', 3, 3, 4,'A','b','B','A'] #here 3,'A' have repetitions
output list -> [3, 'A']
```
**Refrain from for/while loops. Use functional programming like lambda/mapping etc...**

# Solution

```python test.py  -r 'python test.py'
<template>
def find_repeated_elements(data: list) -> list:
    '''
    Find elements that are repeated in the input list.
    Argument:
    - data: List of items (any type)

    Return:
    - A list of repeated elements (strings of ascending order)
    '''
    <los>return ...</los>
    <sol>
    repeated = list(filter(lambda item: data.count(item) > 1, set(data)))
    repeated.sort(key=lambda x: (str(x), x))    
    return repeated
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
        order_repr(find_repeated_elements([1, 2, 3, 2, 4, 5, 3, 6, 1])),
        order_repr([1, 2, 3])
        )
```

## Output 1

```
'[1, 2, 3]'
```

## Input 2

```
if not check_for_loops(find_repeated_elements):
    is_equal(
        order_repr(find_repeated_elements(['apple', 'banana', 'apple', 'cherry', 'banana'])),
        order_repr(['apple', 'banana'])
        )        
```
## Output 2

```
"['apple', 'banana']"
```

## Input 3

```
if not check_for_loops(find_repeated_elements):
    is_equal(
        order_repr(find_repeated_elements([10, 20, 30, 40])),
        order_repr([])
        )
```

## Output 3

```
'[]'
```

# Private Test Cases

## Input 1

```
if not check_for_loops(find_repeated_elements):
    is_equal(
        order_repr(find_repeated_elements([7, 7, 7, 7, 7])),
        order_repr([7])
        )
    is_equal(
        order_repr(find_repeated_elements([1, 2, 'apple', 2, 'banana', 'apple', 'bAnana'])),
        order_repr([2, 'apple'])
        )
    is_equal(
        order_repr(find_repeated_elements([])),
        order_repr([])
        )
```

## Output 1

```
'[7]'
"[2, 'apple']"
'[]'
```
