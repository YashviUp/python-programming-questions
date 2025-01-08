---
title: Price into Dollars
tags: ['formatted-string', 'index', 'data-type']
---

# Problem Statement

Given a list of prices of items in ruppes (1 dollar = 85 rupees), **modify in place the price to dollars and cents(1 dollar = 100 cents)** for the item *at the given index* (don't modify other indices). If the index is out of range, return **None**.
Assume the `price_list` is list of valid **integers**.\
String output has no decimal points (as the remaining rupees is written as cents)
**Don't use any loops**
**Example:**
```python
PriceList = [4000, 7000]
get_price_in_dollars(PriceList, 1) # list modified [4000, '82 dollars 35 cents']
get_price_in_dollars([142, 841, 7621, 2221],1) #list modified [142, '9 dollars 89 cents',7621,1)
```
First case: 7000 rupeess -> 82 dollars 35 cents\
Second case: at index=1 is `841` i.e. `9 dollars 89 cents` (85 rupees -> 1 dollar & 1 dollar -> 100 cents)


# Solution

```python test.py -r 'python test.py'
<template>
def get_price_in_dollars(price_list: list, index: int) -> str:
    <sol>
    if 0 <= index < len(price_list):
        price_list[index] = f"{price_list[index]//85} dollars {price_list[index]%85 *100//85} cents"
    return None
    </sol>
</template>
<suffix_invisible>
{% include '../is_equal_forloop_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```python
PriceList = [1201, 2500, 7502, 4080]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 0), PriceList, ['14 dollars 12 cents', 2500, 7502, 4080], should_modify=True
    )
```

## Output 1

```
['14 dollars 12 cents', 2500, 7502, 4080]
```

## Input 2

```python
PriceList = [1500, 5000, 999]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 0), PriceList, ['17 dollars 64 cents', 5000, 999], should_modify=True
    )
```

## Output 2

```
['17 dollars 64 cents', 5000, 999]
```

## Input 3

```python
PriceList = [450, 1050, 2300]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 1), PriceList, [450, '12 dollars 35 cents', 2300], should_modify=True
    )
```

## Output 3

```
[450, '12 dollars 35 cents', 2300]
```

## Input 4

```python
PriceList = [1500, 5000, 999]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 2), PriceList, [1500, 5000, '11 dollars 75 cents'], should_modify=True
    )
```

## Output 4

```
[1500, 5000, '11 dollars 75 cents']
```

## Input 5

```python
PriceList = [450, 1050, 2300]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, -1), PriceList, None, should_modify=False
    )
```

## Output 5

```
None
```


# Private Test Cases

## Input 1 (out of range index)

```python
PriceList = [450, 1050, 2300]
if not check_for_loops(get_price_in_dollars): #if for loop found prints "Found a 'for' loop in the function {func.__name__}.")
    modify_check(
        lambda x: get_price_in_dollars(x, 3), PriceList, None, should_modify=False
    )
```

## Output 1

```
None
```

## Input 2 (empty list)

```python
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 0),
        [],
        None,
        should_modify=False
    )
```

## Output 2

```
None
```

## Input 3 (1 item list)

```python
PriceList = [905]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 0), PriceList, ['10 dollars 64 cents'], should_modify=True
    )
```

## Output 3

```
['10 dollars 64 cents']
```

## Input 4 (1 item list)

```python
PriceList = [2501]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 0), PriceList, ['29 dollars 42 cents'], should_modify=True
    )
```

## Output 4

```
['29 dollars 42 cents']
```

## Input 5 (out of range index)

```python
PriceList = [1200, 3400]
if not check_for_loops(get_price_in_dollars):
    modify_check(
        lambda x: get_price_in_dollars(x, 5), PriceList, None, should_modify=False
    )
```

## Output 5

```
None
```
    
