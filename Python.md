# Functions
----

 ```python
 type(32)
 <class 'int'>
```

the name of the fn is `type` Expression inside parentheses is called the *argument*. 
Common to say that a fn "takes" an argument and "returns" a result.  The result is called the return value. 


# Creating your own Fn
----
```python
def print_lyrics():
  print("I'm a lumberjack, and I'm okay.")
  print("I sleep all night and I work all day.")
```
 `def` is a keyword that indicates that this is a function definition
 
# Return
----
```python
def addtwo(a, b):
    added = a + b
    return added

x = addtwo(3, 5)
print(x)

# // 8
```
