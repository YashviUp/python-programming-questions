---
title: Price into Rupees
tags: ['formatted-string', 'index', 'data-type']
---

# Problem Statement

Given a list of grocery items and their prices in paise (1 rupee = 100 paise), **return price in rupees** and remaining part in **paise** for the item *at the given index*. If the index is out of range, return **None**.

**Example:**
```python
GroceryList = ['sugar', 'flour']
PriceList = [4000, 7000]
get_price_in_rupees(GroceryList, PriceList, 1) # Flour:70 rupees 0 paise
get_price_in_rupees(['tablet', 'baking soda', 'milk', 'detergent'],[142, 841, 7621, 2221],1) # Baking Soda:8 rupees 41 paise
```
First case: is in __00 form fully converts into rupees\
Second case: baking soda is at index=1 and corresponds to `841` i.e. `8 rupees (800 paise) +41 paise`\


# Solution

```python test.py -r 'python test.py'
<template>
def get_price_in_rupees(grocery_list: list, price_list: list, index: int) -> str:
    <sol>
    if 0 <= index < len(price_list):
        return f"{grocery_list[index].title()}:{price_list[index]//100} rupees {price_list[index]%100} paise"
    return None
    </sol>
</template>
<suffix_invisible>
{% include '../function_type_and_modify_check_suffix.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1

```
GroceryList = ['apples', 'bread', 'carrots', 'detergent']
PriceList = [1201, 2500, 7502, 4080]
is_equal(
    get_price_in_rupees(GroceryList,PriceList,2), "Carrots:75 rupees 2 paise"
    )
```

## Output 1

```
'Carrots:75 rupees 2 paise'
```

## Input 2

```
GroceryList = ['mango', 'milk', 'eggs']
PriceList = [1500, 5000, 999]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, 0), "Mango:15 rupees 0 paise"
    )
```

## Output 2

```
'Mango:15 rupees 0 paise'
```

## Input 3

```
GroceryList = ['onions', 'potatoes', 'tomatoes']
PriceList = [450, 1050, 2300]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, 1), "Potatoes:10 rupees 50 paise"
    )
```

## Output 3

```
'Potatoes:10 rupees 50 paise'
```

## Input 4

```
GroceryList = ['mango', 'milk', 'eggs']
PriceList = [1500, 5000, 999]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, 2), "Eggs:9 rupees 99 paise"
    )
```

## Output 4

```
'Eggs:9 rupees 99 paise'
```

## Input 5

```
GroceryList = ['onions', 'potatoes', 'tomatoes']
PriceList = [450, 1050, 2300]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, -1), None
    )
```

## Output 5

```
None
```

# Private Test Cases

## Input 1

```
GroceryList = ['onions', 'potatoes', 'tomatoes']
PriceList = [450, 1050, 2300]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, 3), None
    )
```

## Output 1

```
None
```

## Input 2

```
is_equal(
    get_price_in_rupees([], [], 0),
    None
)
```

## Output 2

```
None
```

## Input 3

```
GroceryList = ['tea']
PriceList = [905]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, 0), "Tea:9 rupees 5 paise"
    )
```

## Output 3

```
'Tea:9 rupees 5 paise'
```

## Input 4

```
GroceryList = ['chocolate-chip-cookies']
PriceList = [2501]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, 0), "Chocolate-Chip-Cookies:25 rupees 1 paise"
    )
```

## Output 4

```
'Chocolate-Chip-Cookies:25 rupees 1 paise'
```

## Input 5

```
GroceryList = ['rice', 'wheat']
PriceList = [1200, 3400]
is_equal(
    get_price_in_rupees(GroceryList, PriceList, 5), None
)
```

## Output 5

```
None
```
    
