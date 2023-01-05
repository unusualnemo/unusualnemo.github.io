---
title: lists
tags: comp_sci
date created: 22.12.28, 11:02:55
date modified: 23.01.03, 09:46:22
---

## list types

```python
list = [1, 2, 3, 4, 5]                                            #declare a list of numbers
list_of_people = ["bulbasaur", "charmander", "squirtle"]          #a list of strings
my_favorite_stuff = ["charizard", 5]                              #a list of numbers and strings
pokedex = [["bulbasaur", 1], ["ivysaur", 2], ["venusaur", 3]]     #a list of lists

print(list)                                                       #print lists
print(list_of_people)
print(my_favorite_stuff)
print(pokedex)

# output:

#[1, 2, 3, 4, 5]
#['bulbasaur', 'charmander', 'squirtle']
#['charizard', 5]
#[['bulbasaur', 1], ['ivysaur', 2], ['venusaur', 3]]
```

---

## adding lists together

```python
list_1 = [1, 2, 3]          #declare a list
list_2 = [4, 5]             #declare another list
total = list_1 + list_2     #add those lists together
print(total)                #and print the total out

# output:

#[1, 2, 3, 4, 5]
```

---

## modifying lists

```python
list = [4, 2, 1, 3]            #declare a list
print(list)

list.append(5)                 #add 5 to the list
print(list)

list.remove(2)                 #remove the first element that is a 2
print(list)

list.insert(3, 2)              #insert 2 at index 3
print(list)

sorted_list = sorted(list)     #'sorted' creates a new, sorted list
sorted_list.append(6)          #modify this list without altering original list
print(sorted_list)

list.sort()                    # .sort() sorts the original list without returning another list
print(list)

# output:

#[4, 2, 1, 3]           #original
#[4, 2, 1, 3, 5]        #append
#[4, 1, 3, 5]           #remove
#[4, 1, 3, 2, 5]        #insert
#[1, 2, 3, 4, 5, 6]     #sorted()
#[1, 2, 3, 4, 5]        #.sort()
```

---

## selecting from a list

```python
list = [1, 2, 3]      #declare a list
print(list[0])        #print the number at the 0th index
print(list[2])        #print the number at the 2nd index
print(list[-2])       #print the 2nd to last number

pokedex = [["bulbasaur", 1], ["ivysaur", 2], ["venusaur", 3]]     #a list of lists
print(pokedex[2][0])                                              #print an element from a sublist using two indices

letters = ["a", "b", "c", "d", "e", "f"]     #a list of letters
letters_sliced = letters[1:4]                #slice list from index 1 to (but not including) index 4
print(letters_sliced)
print(letters)

popped_letter = letters.pop()                #pop the last letter automatically
print(popped_letter)
print(letters)

third_letter_popped = letters.pop(2)         #but you can also choose which letter to pop
print(third_letter_popped)
print(letters)

# output:

#1                                          #indexing
#3                                          #indexing
#2                                          #indexing
#venusaur                                   #indexing lists within lists

#['b', 'c', 'd']                            #slicing lists
#['a', 'b', 'c', 'd', 'e', 'f']             #original list, unmodified by slicing

#f                                          #popped from end of list
#['a', 'b', 'c', 'd', 'e']                  #original list with the last element popped

#c                                          #popping from 2nd index
#['a', 'b', 'd', 'e']                       #original list with the 3rd element popped
```

---

## counting

```python
list = ["a", "b", "c", "a", "c", "c", "b"]      #declare a list

num_of_c = list.count("c")        #how many c's are in the list
size_of_list = len(list)          #what is the size of the list

print(num_of_c)                   #print numbers
print(size_of_list)

# output

#3
#7
```
