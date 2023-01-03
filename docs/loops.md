---
title: loops
tags: 
date created: 23.01.03, 09:36:23
date modified: 23.01.03, 10:00:10
---

## types of loops

### for loops

### while loops

## nested loops

## other

### infinite loops

### break

- escapes a loop

```
numbers = [0, 254, 2, -1, 3]

for num in numbers:
	if (num < 0):
		print("Negative number detected!")
		break
	print(num)

# output:

# 0
# 254
# 2
# Negative number detected!
```

- the for loop is broken in the above example
- notice how `-1` is not printed and the loop skips over `3` entirely

### continue

### for i in range()

## list comprehension

- *i have a bit of trouble with this topic*
- list comprehensions create lists with a loop
- list comprehensions always return a list
- `[EXPRESSION for ITEM in LIST <if CONDITIONAL>]`

```
result = [x**2 for x in range(10) if x % 2 == 0]
print(result)

# output:

# [0, 4, 16, 36, 64]
```

- x$^2$ for x in 0 -> 9
- and if the remainder when divided by 2 is 0 (when the number is even)

so it takes a list of numbers from 0 to 9: `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`

squares them all: `[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]`

and returns the even ones: `[0, 4, 16, 36, 64]`
