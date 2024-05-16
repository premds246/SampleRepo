# Linked List

## Singly Linked List 

### Creating and Traversing 
#### Creating a Linked list
- To create a singly linked list we need to create two things. 
- The first one is the fundamental building block of a Linked list, a node. 
- A node has two values in it. one is the value or data it requires to store and the other is a pointer where it needs to stores address of the next node. 
- The sceond we require is a pointer to the first node of the linked list. 
- The third is to link the nodes with each other. 
- To create a Node we create a node class and add two attributes as instance variables self.data to store the data and self.next whose value by default is None to store the address of next node, which are created everytime we create a node by passing the data

```python

class Node:
    def __init__(self,data=None):
        self.data = data
        self.next = None

```
- The next thing we need to create is the head pointer of the Linked list. 
- To do this we can create a new class called Linkedlist and add an attribute head to it as a instance variable which store the address of the first node of a linked list. 

```python 

class LinkedList:
    def __init__(self):
        self.head = None 

```
- This is how we can code the Node and head pointer of a singly linked list 
- Now lets create some nodes and link them together

```python 

n1 = Node(1)
n2 = Node(2)
n3 = Node(3)

l = LinkedList()
l.head = n1
n1.next = n2
n2.next = n3 

```
- We can create a node by creating a Node instance by passing the data. 
- We can create the linked list by creating an instance of Linked list. 
- To link nodes with other all we need to do is assign the node to be linked to the next attribute of a node. 
- Now to store the head pointer assign the firt node to the head attribute of the Linkedlist instance.



#### Improved Version 

### Appending Items
#### Appending items to the end of the list
#### Appending at the begining of the list
#### Appending at intermediate positions

### Querying a List 
#### Searching for an Item
#### Getting the size of the List

### Deleting Items
#### Deleting node at the begining 
#### Deleting node at the end 
#### Deleting node at intermediate 
#### Clearing a list


## Doubly Linked List 
### Creating and Traversing
### Appending Items 
### Querying a List 
### Deleting Items


## Circular Linked List 
### Creating and Traversing
### Appending Items 
### Querying a List 
### Deleting Items