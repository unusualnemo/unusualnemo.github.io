---
title: functions
tags:
  - comp_sci
date created: 23.01.06, 08:03:04
date modified: 23.01.06, 08:39:14
---

functions allow you to run the same chunk of instructions multiple times

see also: [[don't repeat yourself]]

```python
print("i am printing this three times")  # so instead of writing this
print("i am printing this three times")  # three times in a row
print("i am printing this three times")

# output:

# i am printing this three times         # to get an output like this
# i am printing this three times
# i am printing this three times
```

```python
def print_three_times(string, times):    # you can put it in a function
	for i in range(times):               # to print as many times as you want
		print(string)                    # whatever string you want

print_three_times("i am printing this three times", 3)
print_three_times("this is a cool, new string!", 5)

# output

# i am printing this three times         # to get the same output
# i am printing this three times
# i am printing this three times

# this is a cool, new string!            # or a different one if you'd like!
# this is a cool, new string!
# this is a cool, new string!
# this is a cool, new string!
# this is a cool, new string!
```

for next time, FUTURE_NEMO:

```python
def function_name(parameter1, parameter2):  # def and function_name and parameters
	number = parameter1 + parameter2        # indentation
	return number                           # returning (returning multiple variables)

returned_number = function_name(2, 3)       # calling
print(returned_number)
```

## parameters

function parameters

function arguments

keyword arguments

multiple parameters

## scope

local

global
