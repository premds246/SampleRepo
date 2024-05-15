# String Data Structure  
- String is a built in data structure in python which handles is text data. Python provdes multiples operators, built-in methods, functions, modules to handle string data in python. 

## Creation of String data
- We can create a string literal by just by using single quotes, double or tripple quotes
```python
a = 'premkumar' 
b = "premkumar"
c = ''' I have a bag.
        which has a lot of books''' # triples quotes are for multi line text
```
## Operators with Strings
### Concatenation (+)
- We use + operator to join two or more strings
```python 
a = 'PremKumar'
b = ' sanamala'
c = a+b # 'PremKumar sanamala'
```
### Repetition (*)
- To repeate chareters in a string or a string itself we use * operator
```python
a = 'prem'
b = a*3 # 'prempremprem'
```

### Length of a string 
- len() function retuns the number of charecters in a given string. 
```python
a = len('prem kumar')
a # 10
```

### Accessing a string 
- We can access charecter or charecters in a string by using [] operators
```python
a = 'premkumar'
# passing index of the charecter in a string
a[4]  # k
# passing the strat index and stop index 
a[4:8] #kumar
# passing the start stop indices and step 
a[4:8:-1] #ramuk 

```



