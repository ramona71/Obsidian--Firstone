
- collection - single "variable" that stores multiple values
- list- `[]` ordered and changeable . Duplicates r allowed
- set - `{}` unordered and immutable (adding/removing is allowed) . No duplicates
- Tuple - `()` ordered and unchangeable .Duplicates are allowed . FASTER

- to know more about these do 
```python
print(help("tuple"))
print(dir("list"))
```
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
- union, intersection, difference, symmetric difference
```python
man= {"Jon", "Ken" , "Barbie", "Barbie"}  #the other Barbie will be removed automatically
woman=set([1,5,6])           # another way to make a set (by type casting)
empty_set = set()
print(man)                     # won't be in same order everytime we print
print(dir(man))
print(help(man))

print(len(man))
print("pinapple" in man)
  
print(man[0])   #error  # can't use indexing ,cuz unordered (not subscriptable)
man.add("pinapple")
man.remove("pinapple")     # gives error if the element is not present
man.discard('pinapple')    # doens't give error if element is not present
a=man.pop()                  #random removal  (set so , no order)
man.clear()

# in -> set membership test
for item in my_set:     # iterate using for loop
	print(item)
```
### Union, Intersection etc
```python
set1={1,5,6,8,7,9,3}
set2={10,4,2,8}
union_set=set1.union(set2)
print(union_set)
intersection_set=set1.intersection(set2)
print(intersection_set)
set1.intersection_update(set2)   # set1 has only intersection elements
print(set1)
  
print(set1.difference(set2))   # does't change set1 unleass assigned
print(set1.symmetric_difference(set2))  #unique elements from both sets are combined
```
### Set methods
```python
print(set1.issubset(set2))    # True or FAlse
print(set1.issuperset(set2))
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
# 2D lists
- matrices vro they're just matrices
```python
# two ways to write them
fruits= ["apple", "orange", "cocounut"]
vegetables =["carrots", "potatos"]
groceries =[fruits, vegetables]
  
# or
groceries= [["apple", "orange", "cocounut"],["carrots", "potatos"]]
groceries[1]   # prints entire row
groceries[0][2]
  
for collection in groceries:
    for item in collection:
        print(item)
```
# List Comprehension
- compact way to create lists
- `[exprssion for value in iterable if condition]`
```python
 double= [i+3 for i in range(10) if i%2==0]
print(double)

fruits= ["apple", "orange", "cocounut"]
fruits= [fruit.upper() for fruit in fruits]
#or
fruits= [fruit.upper() for fruit in ["apple", "orange", "cocounut"]]
```