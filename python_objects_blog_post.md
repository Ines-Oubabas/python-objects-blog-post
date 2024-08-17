# Understanding Python Objects: Mutable vs Immutable, and Function Argument Passing

![Python Logo](https://tse3.mm.bing.net/th?id=OIP.o7UGGxD7QmFLlVkwqT_OowHaEK&pid=Api&P=0&h=180)


## Introduction:
Python is a powerful and versatile programming language with a unique approach to handling data. One of the key concepts in Python is the distinction between mutable and immutable objects, which can greatly impact how your code behaves. In this blog post, we'll explore what mutable and immutable objects are, why they matter, and how Python treats them differently. We will also delve into how arguments are passed to functions in Python and what implications this has for mutable and immutable objects.


## - id and type:

Every object in Python has a unique identifier and a type. The 'id()' function returns the identity of an object, which is typically the memory address where the object is stored. The 'type()' function, on the other hand, returns the type of the object, such as 'int', 'list', or 'tuple'. Understanding the identity and type of objects is crucial when working with different data structures in Python.

## Example:

```
a = [1, 2, 3]
print(id(a)) # Outputs: Memory adress of the list
print(type(a)) # Outputs: <class 'list'>
```

## - Mutable Objects:

Mutable objects are objects whose state or content can be changed after they are created. Examples of mutable objects in Python include lists, dictionaries, and sets. When you modify a mutable object, the object's identity does not change, but its contents do. This characteristic of mutable objects is particularly important when passing them to functions.

## Example:

```
l = [1, 2, 3]
print(id(l)) # Outputs: Memory adress of the list
l.append(4)
print(id(l)) # The memory adress is the same, but the list is now [1, 2, 3, 4]
```

## - Immutable Objects:

Immutable objects, as the name suggests, cannot be altered once they are created. Common examples include integers, strings, and tuples. When you try to change the value of an immutable object, Python creates a new object with the new value, leaving the original object unchanged. This difference has important implications when dealing with variables and function arguments.

## Example:

```
s = "hello"
print(id(s)) # Outputs: Memory adress of the string
s = s + "world"
print(id(s)) # Outputs: A different memory address, because a new string object is created
```


## - Why Does It Matter and How Differently Does Python Treat Mutable and Immutable Objects?

Understanding the difference between mutable and immutable objects is crucial for writing efficient and bug-free Python code. Python handles mutable and immutable objects differently, especially when they are passed as arguments to functions. Mutable objects can be changed within a function, affecting the original object outside the function, while immutable objects cannot be changed in this way.

## Example with a mutable object:

```
def add_item(lst):
    lst.append(4)

l = [1, 2, 3]
add_item(l)
print(l) # Outputs: [1, 2, 3, 4]
```

## Example with an immutable object:

```
def increment(n):
    n += 1

a = 1
increment(a)
print(a)  # Outputs: 1 (unchanged)
```

## - How Arguments Are Passed to Functions and What Does That Imply for Mutable and Immutable Objects?

In Python, arguments are passed to functions by assignment. This means that when you pass an object to a function, the function gets a reference to the original object, not a copy. However, the way this reference behaves depends on whether the object is mutable or immutable. If you pass a mutable object, the function can modify the object in place, affecting the original object. If you pass an immutable object, the function cannot alter the original object; it can only create a new one.

## Example with mutable object:

```
def modify_list(l):
    l.append(100)

my_list = [1, 2, 3]
modify_list(my_list)
print(my_list)  # Outputs: [1, 2, 3, 100]
```

## Example with immutable object:

```
def modify_string(s):
    s += " world"

my_string = "hello"
modify_string(my_string)
print(my_string)  # Outputs: "hello" (unchanged)
```


## Conclusion:

Understanding the differences between mutable and immutable objects in Python is essential for writing effective code. It affects how data is manipulated, especially when passing objects to functions. By knowing these distinctions, you can avoid common pitfalls and make informed decisions about how to structure your code.

# - Author:

- [Ines Oubabas](https://github.com/Ines-Oubabas)
