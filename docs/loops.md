---
title: loops
tags: 
date created: 23.01.03, 09:36:23
date modified: 23.01.05, 09:28:04
---

## types of loops

### for loops

- loops over a set of items and does something to each item

```python
for <temporary variable> in <list variable>:
  <action statement>
  <action statement>

nums = [1,2,3,4,5]
for num in nums:     # assigns the variable 'num' to each item that goes into this 'for loop'
  print(num)         # prints that 'num' and grabs another 'num' from 'nums'

# output:

# 1
# 2
# 3
# 4
# 5
```

### while loops

- loops as long as a given condition is met

```python
hungry = True
while hungry:            #as long as 'hungry' is set to True, the loop will run
  print("Time to eat!")
  hungry = False         #the loop changes 'hungry' to False, so the loop will end after only one go around

i = 1
while i < 6:             #as long as 'i' is less than 6, the loop will continue to run
  print(i)
  i = i + 1              #the loop adds 1 to 'i' and so eventually 'i' will equal 6, ending the loop

# output:

#Time to eat!            #loops one time
#1                       #loops five times
#2
#3
#4
#5
```

## nested loops

- you can put a loop inside another loop!

```python
groups = [["Jobs", "Gates"], ["Newton", "Euclid"], ["Einstein", "Feynman"]]

for group in groups:  # this outer loop will iterate over each list in the groups list
  for name in group:  # this inner loop will go through each name in each list
    print(name)

# output:

#Jobs
#Gates   
#Newton  
#Euclid  
#Einstein
#Feynman
```

## list comprehension

- *i have a bit of trouble with this topic*
- list comprehensions create lists with a loop
- list comprehensions always return a list
- `[EXPRESSION for ITEM in LIST <if CONDITIONAL>]`

```python
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

## other

### infinite loops and getting stuck

- if the program is taking forever, it may be in an infinite loop
- an infinite loop occurs when there's nothing preventing the program from terminating
- pressing `ctrl` + `c` will terminate the program and end the infinite loop

### break

- escapes a loop

```python
numbers = [0, 254, 2, -1, 3]

for num in numbers:
	if (num < 0):                           # the number '-1' will pop into this 'if-statement' ...
		print("Negative number detected!")
		break                               # ... and break the 'for loop' here
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

- similar to break in that it skips the rest of the loop, but it doesn't break the loop completely

```python
big_number_list = [1, 2, -1, 4, -5, 5, 2, -9]  # a bunch of numbers
for i in big_number_list:                      # assigns 'i' for a single number in list
  if i < 0:                                    # if 'i' is negative it goes into this 'if-statement' ...
    continue                                   # ... and it skips the rest of the 'for loop' ...
  print(i)                                     # ... otherwise, it gets printed

# output                                       # and thus only positive (and zero) numbers get printed!

#1
#2
#4
#5
#2
```

### for i in range()

- takes a number (i.e. `for i in range(3)` takes `3`) and does something that many times in a row
	- can use the number `i` like in the first example below
	- or can ignore `i` like in the second example

```python
for i in range(3):   #three numbers, starting with zero
  print(i)

for i in range(3):   #three iterations
  print("WARNING")

# output

#0
#1
#2

#WARNING
#WARNING
#WARNING
```
