---
title: Kaprekar's constant  
tags: ['I/O', 'while loop', 'sort', 'join']  
---

# Problem Statement

1. Take any **four-digit number**, using at least two different digits (*check for same for a given input*).
2. Arrange the digits in **descending** and then in **ascending order** to get two four-digit numbers.
3. **Subtract** the smaller number from the bigger number.
4. Go back to **step 2** and repeat until you reach 6174 (Kaprekar's constant).
5. Return the **number of steps (int) it took until the difference is 6174.**

**Example:**
```
1459 #3
```
largest - smallest =
9541 – 1459 = 8082\
8820 – 0288 = 8532\
8532 – 2358 = 6174\
Hence, it took 4 steps to reach 6174. (If the input was 6174, then 0 steps)\

# Solution

```python test.py  -r 'python test.py'
<template>
def check_step(Num:str):
    '''
    Perform one step of the Kaprekar's process:
    1. Sort the digits of Num to get the largest and smallest numbers. (hint: we can't sort int)
    2. return the difference between them
    '''
    Lar_Num = <sol>int(''.join(sorted(Num)[::-1]))</sol>
    Small_Num = <sol>int(''.join(sorted(Num)))</sol>
    <sol>
    return f"{Lar_Num - Small_Num:04d}"
    </sol>

def Kaprekar():
    Num = input().strip()
    <sol>
    steps=0
    if len(Num) != 4 or not Num.isdigit() or len(set(Num)) < 2:
        return None  # Return None if invalid input (non-4 digits or all digits the same)
    if int(Num) == 6174:
        return 0
    
    while int(Num) != 6174:
        Num = check_step(Num)
        steps += 1
    return steps
    </sol>
print(Kaprekar())
</template>
```

# Public Test Cases

## Input 1

```
1631
```

## Output 1

```
7
```

## Input 2

```
2468
```

## Output 2

```
1
```

## Input 3

```
3839
```

## Output 3

```
5
```

# Private Test Cases

## Input 1

```
6174
```

## Output 1

```
0
```

## Input 2

```
24Ab
```

## Output 2

```
None
```

## Input 3

```
1111
```

## Output 3

```
None
```

## Input 4

```
21
```

## Output 4

```
None
```  