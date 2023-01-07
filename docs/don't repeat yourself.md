---
title: "don't repeat yourself"
tags:
  - comp_sci
date created: 23.01.06, 08:18:22
date modified: 23.01.06, 08:33:37
---

a principle of software development aimed at reducing repetition and redundancy

first used in *the pragmatic programmer*

```python
i = 5

while i < 10:    # this is the same as the one below it
	i += 1

while i < 10:    # they both add 1 to 'i' until 'i' is 10
	i += 1

# by the end i is equal to 10 just like it should be
```

```python
i = 5

# but let's say we want 'i' to now be 8 ...

while i < 8:     # ... so we change this 10 into and 8 ...
	i += 1

while i < 10:    # ... but we forget to change this one!
	i += 1

# by the end i is equal to 10, but we wanted it to be 8!
```

so we'd have to go back and look for each instance where we're adding something to 'i'

this example is very simple, but coding projects can get very complex and a lot of time could be wasted trying to undo many issues

you want changes you make to your code to have predictable consequences!
