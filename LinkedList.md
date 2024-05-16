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

#### Traversal of a list
- We store data in a data structure with an aim be able to retrve the data when ever we want. 
- For this we must be able to traverse each item of a data structure. Let's look how can we travese the linked list. 
- To traverse a linked list we should run a while loop and using the pointer of a node we should move to every other node and access data. 

```python
current = n1

while current:
    print(current.data)
    current = current.next


```

- We start with the first node for which we store it in a variable called current. 
- Then we run a while loop this loop runs till it hits none data which means the end of the list. 
- We can access the data stored in a node using node.data notation and then we shange the current node to the next node by current.next notation. 
- There is a problem with this approach the programmer gets to know the inner workings of nodes and objects. 

```python 
# This method iterates through the list and yields values as a generator object
def iter(self):
    current = self.head
    while current:
        val = current.data
        current = current.next 
        yield val 

```
- Now we can simply loop through the elements like a python list using a for loop. 

```python 
for word in word.iter():
    print(word)

```
- Now node internal objects are exposed to programmer. 
- Every time we need to add a node we need to do two things creating a node object and linking it to the last node. 
- Doing this for every node when data is huge to be stored is an tedeous task. So lets comeup with a method to append the new items in to the Linked list. 


### Appending Items 
- The first method we need to create is to append elements in to the list. 
- This method enables the programmer not to interact with the node classes or objects directly. 
- Here in this topic we discuss how to append the elements at the begining, middle and end of the list. 

#### Appending items to the end of the list
- To append an element at the end of the list we need to travese through the entire list and reach the last node and then link the new node to the last node of the list. 

```python 
class SinglyLinkedList:
    def __init__(self):
        self.head = None 

    def insert(self,data):
        newNode = Node(data)
        if self.head is None:
            self.head = newNode
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = node

```
- The methods checks the head pointer is none or not if it none the list is empty then we point head to the newNode. 
- Here we have created a new method which takes a value, creates a node using the node class and loops through the nodes using while loop. 
- The while loop runs till there is a next node for the current node, where for the last node ther wont be next node then the loop breaks and then we add the new node to last node using current.next = node notation.  
- This implementation is not efficient where we need to traverse till the end of the list to add every element every time. 
- Let's try another way, in this way we every time we add an element we try to store the last element using a different pointer. The moment we need to add and element rather to traverse till the last node we simply add this new node to the next of the last node and update the last node to the added node. 

```python

class SinglyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None 
    
    def insert(self,data):
        
        newNode = Node(data)
        
        if self.tail:
            self.tail.next = newNode
            self.tail = newNode
        else:
            self.head = newNode
            self.tail = newNode 
    

```
- Here we have created a new pointer variable in the init method called tail. 
- This tails keeps the reference of the last node. 
- When the self.head and self.tail is none we add the newNode to the head and tail. 
- Now eveytime we add a new element by just keeping the head pointer to the first node itself. we move the tail pointer pointing the last node. 
- This done by assigning the newNode to the next of the tail node and 

#### Appending at intermediate positions 
- Just as we add new elements in a list by appending them at the end of the list, sometime we also requires to add the elements at the middle at a specific position of the list. 
- As we added the last element without using to traverse the list we cannot do this here as we never know before where we need to add the element. 
- So we must have to travese the list till the index position and then hold the two elements prev node and next node in variables and then insert and link the required node. 

```python 

class LinkedList:
    
    def __init__(self):
        self.head = None
        self.tail = None
    
    def insertAt(self,data,index):
        newNode = Node(data)
        current = self.head
        prev    = self.head 
        count = 1

        while current:
            if count == 1:
                newNode.next = current
                self.head = newNode 
                return
            elif count == index:
                newNode.next = current
                prev.next = newNode 
                return
            else:
                prev = current
                current = current.next
                count+=1
        if count < index:
            print('No such index position exist')
        
        def insertAtEqualValue(self,data):
            newNode = Node(data)
            current = self.head
            prev = self.head
            while current:
                if current.data == data:
                    newNode.next = current
                    prev.next = newNode
                    return
                prev = current
                current = current.next
                

```
- Sometimes we also wants to insert elements at a node where the value is same or the value lies between the prev and current values. 
- Then the logic of the above method changes. 

### Querying a List 
- Whenever we create a list, we sometimes may require to get informtaion about the list. like below. 

#### Searching for an Item

```python

def search(self,item):
    current = self.head
    while current:
        if current.data == item:
            return True
        current = current.next 
    return False

```
#### Getting the size of the List 
- To get the size of a linked list we cana traverse through and couunt the number of elements. 

```python 
class LinkedList:
    def __init__(self):
        self.head = None
        self.tail = None
        self.size = 0

    def insert(self,data):
        newNode = Node(data)
        if tail:
            self.tail.next = newNode
            self.tail = newNode

        else:
            self.head = newNode
            self.tail = newNode 
        self.size +=1

    def size(self):
        count = 0
        current = self.head
        while current:
            count +=1
            current = current.next
        return count 

```

### Deleting Items
#### Deleting node at the begining 
- To delete the first node all we need to do is to move the head pointer to the next of the head 

```python 

def delete_first_node(self):
    
    if self.head is None:
        print('There are no elements to delete')
    else:
        current = self.head
        self.head == current.next 

```
#### Deleting node at the end 
- To delete the last node of the list we need to 

```python 

def delete_node_at_end(self):
    
    current = self.head 
    prev    = self.head 
    
    while current.next: 
        prev = current
        current = current.next
        
    prev.next = None
    self.size -= 1

```
#### Deleting node at intermediate 

```python

def delete_node_at_index(self,data,index):
    current = self.head
    prev    = self.head 
    count = 1

    while current:
        if count == index:
            prev.next = current.next
        prev = current
        curent = curren.next
        count +=1



```

#### Clearing a list
- To clear the list all we need to do is to set the pointers to none. 

```python

def clear(self):
    self.head = None
    self.tail = None

```


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