# Lambda fxns
#### <mark style="background: #FFF3A3A6;">fxn_name=lambda arguments: expression</mark>
- small anonymous fxn
```python
addition= lambda a,b: a+b
type(addition)
addition(1,5)

even_or_odd=lambda x: x%2==0
even_or_odd(53)

addi=lambda x,y,z: x+y+z
result=addi(5,8,9)

```
# map()
#### <mark style="background: #FFF3A3A6;">map(fxn_name, iterable)</mark> -> fxn name is called without `()`
- applies a given fxn to all items in an input list (or other iterables) and returns a map object (an iterator)
```python 
square= lambda x: x**2
numbers=[1,5,6,3,2,8,7,5,9,3,1]
map(square, numbers)    # returns map memory address
list(map(square, numbers))    # returns the list
# or just do
list(map(lambda x: x**2, numbers))
```
- add elements of two lists
```python
nums1=[1,2,3]
nums2=[4,5,6]
nums1+nums2                             # appends nums2 at end
list(map(lambda x,y:x+y, nums1,nums2))  # adds the elements of list

```
- convert a list of strings to int (typecasting)
```python
str_nums=['1','2','3']
integers= list(map(int,str_nums))
integers
```
- can also do stuff like string.upper( ) etc 
```python
words=['apple', 'bana','shit']
upper_words=list(map(str.upper, words))
upper_words
```
- list of dicts
```python
def get_name(person):
    return person['name']
  
people=[
    {'name':'Krish','age':32},
    {'name':'Jack','age':33}
]
list(map(get_name,people))
```
# filter()
#### <mark style="background: #FFF3A3A6;">filter(function, iterable)</mark>
- filter out items from a list(or other iterable) based on a condition
- constructs an iterator from elements of iterable for which a fxn returns true
- commonly used for data cleaning, filtering objects, and removing unwanted elements from lists and collections.
```python
def even(num):
    if num%2==0:
        return True
        
lst=[1,2,3,4,5,6,7,8,9,10,11,12]
list(filter(even,lst))

numbers=[1,2,3,4,5,6,7,8,9]
greater_than_5=list(filter(lambda x: x>5, numbers))
greater_than_5

even_and_greater_than_five=list(filter(lambda x:x>5 and x%2==0,numbers))
print(even_and_greater_than_five)

people=[
    {'name':'Krish','age':32},
    {'name':'Jack','age':33},
    {'name':'John','age':25}
]
  
def age_greater_than_25(person):
    return person['age']>25
  
list(filter(age_greater_than_25,people))
```
