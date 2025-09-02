
- collection - single "variable" that stores multiple values
- list- `[]` ordered and changeable . Duplicates r allowed
- set - `{}` unordered and immutable (adding/removing is allowed) . No duplicates
- Tuple - `()` ordered and unchangeable .Duplicates are allowed . FASTER
# Lists
- https://docs.python.org/3/tutorial/datastructures.html
- https://developers.google.com/edu/python/lists#range
- fruits = [item1, item 2]
- colors = ["red", "yellow", "blue"]
-  has order (has index to them, iteration is possible)
- negative indexing exists
	- print(fruits[-1])
- some methods
```python
man= ["Jon", "Ken" , "Barbie"]
print(man[0])              # access
print(man[:])              #slicing
print(man)                 # to print whole list

print(dir(man))             #all names of attributes & methods of list
print(help(man))            # description of all  those attributes& methods

print("John" in man)        # to find an elements (True/False)
 
man.append("Brown")         # adds a single item at end
    or 
man[len(man):] =["Brown"]  

man.insert(0, "Brown")

man.extend("Hello")            #adds after extending 

man.index("Jon", 5)     #returns index of jon after 5th position
                        # gives error if not present

man.remove("Ken")

man.pop(5)           #if index not mentioned , removes from end

man.clear()           #deletes all

man.count("Ken")     #counts no of times it occurs

man.sort()           # alphabetical order

man.reverse()
print(man[::-1])   # for reverse

man.copy()      #returns shallow copy == man[:]

man.sum()

man.len()

for item in list:   #iterate using for loop    
	print(item)
```
- insert, remove and sort have no return value (None)
- [None, 'hello', 10] can't be sorted cuz different datatypes
- Nested listing exist
```python

```
- u can just add to list using + like you add to string

> [!NOTE] `print(help(man)) `  use this if you want methods 
# Sets
- unordered
- immutable (can add/ remove) 
- No duplicates
```python
man= {"Jon", "Ken" , "Barbie", "Barbie"}  #the other Barbie will be removed automatically

print(man)                     # won't be in same order everytime we print
print(dir(man))
print(help(man))

print(len(man))
print("pinapple" in man)
  
print(man[0])   #error  # can't use indexing ,cuz unordered (not subscriptable)
man.add("pinapple")
man.pop()         #random removal
man.clear()

for item in my_set:    # iterate using for loop
	print(item)
```
# Tuple
- ordered 
- immutable (can't add/ remove)
- Duplicates are okay

> [!NOTE] Use Tuples over list (faster)
> Faster than list so use tuples when ur okay with immutability
- has only two methods (index and count)
```python
man= ("Jon", "Ken" , "Barbie")

print(man)
print(man[2])      # has indexing
print(man[:])      # slicing works cuz has indexing
print(len(man))
print("pinapple" in man)

print(dir(man))
print(help(man))
  
for names in man:
    print(names)
  
print(man.index("Barbie"))
print(man.count("Mona"))
```