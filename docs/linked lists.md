[codecademy ->](https://www.codecademy.com/paths/computer-science/tracks/cspath-cs-102/modules/linked-lists/articles/linked-lists-conceptual)

#current_notetaking

---

example:

![[linked list.png]]

common operations:

- adding nodes
	- linking new node to current head node (first node) thereby making new node the head node
- removing nodes
	- depending on the language, orphaned (no links to the node) nodes are removed automatically
	- so, you have to maintain the links *before* you delete any nodes
	- so if you want to delete node_b, you should link node_a to node_c
		- node_c is preserved and node_b is orphaned and thus deleted
- finding nodes
- traversing the list

```python
class Node:
  def __init__(self, value):
    self.value = value
    self.next_node = None
    
  def get_value(self):
    return self.value
  
  def get_next_node(self):
    return self.next_node
  
  def set_next_node(self, next_node):
    self.next_node = next_node

# ======================================================

class LinkedList:
  def __init__(self):
    self.head_node = None
  
  def get_head_node(self):
    return self.head_node
  
  def insert_beginning(self, new_value):
    new_node = Node(new_value)
    new_node.set_next_node(self.head_node)
    self.head_node = new_node
    
  def stringify_list(self):
    current_node = self.get_head_node()
    while current_node:
      print(str(current_node.get_value()) + " -> ", end = "")
      current_node = current_node.get_next_node()
    print("NULL")
  
  def remove_node(self, value_to_remove):
    current_node = self.get_head_node()
    if current_node.get_value() == value_to_remove:
      self.head_node = current_node.get_next_node()
    else:
      while current_node:
        next_node = current_node.get_next_node()
        if next_node.get_value() == value_to_remove:
          current_node.set_next_node(next_node.get_next_node())
          current_node = None
        else:
          current_node = next_node

  def print_middle(self):
    fast_pointer = self.head_node
    slow_pointer = self.head_node
    while fast_pointer and fast_pointer.next_node:
      fast_pointer = fast_pointer.next_node.next_node
      slow_pointer = slow_pointer.next_node
    print("The middle element is", slow_pointer.value)

# ======================================================

def generate_test_linked_list(length):
  linked_list = LinkedList()
  for i in range(length, 0, -1):
    linked_list.insert_beginning(i)
  return linked_list

test_list = generate_test_linked_list(9)
test_list.stringify_list()
test_list.print_middle()
```
