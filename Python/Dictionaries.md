 - key: value pair
- unordered
- mutable
- no duplicates for key (unique and immutable)
```python
dictionary ={ key: value, key2:value2 }
dictionary[key]   # to get value
dictionary[key3]=value3  #to add 

# to loop
for key in dictionary:
	print (key + dictionary[key])
```
- in depth
```python
capitals= {"USA": "Washington" , "India": "New Delhi" , "China": "Beijing"}
# # print(dir(capitals))
# # print(help(capitals))

print(capitals["USA"])
print(capitals.get("USA"))  # if it doesn' find the key, id return "None"
print(capitals)
  
if capitals.get("Japan"):
    print("That capital exists")
else:
    print("That capital doesn't exist")
  
capitals.update({"Germany": "Berlin"})  # insert new / update existing
capitals.update({"Germany": "Eren"})
capitals.pop("China")
capitals.popitem()  # removes the latest key value
capitals.clear()
  
keys= capitals.keys()   # returns all keys, only keys
for key in capitals.keys():
    print(key)
for value in capitals.values():
    print(value)
    
# Ds course
student= {'man': 'dih', 'women': 'puh'}
print(student)
print(student['man'])
print(student.get('rock'))    # if not present , returns None
print(student.get('rock', 'Not available'))   # returns 'Not available'
student['rock']= 'ts not human'   # updating
print(student)
del student['rock']               # deleting

keys= student.keys()
values= student.values()
items= student.items()
print(keys,values)
print(items)
```
- `items` return dict object that resembles a 2d list of tuples
	 ![[Pasted image 20250902114239.png]]
```python
item = capitals.items()
print(item)
  
for key,value in capitals.items():
    print(key, value)
```
![[Pasted image 20250902114503.png]]
- can keep anything as value inside dict
![[Pasted image 20250512104211.png]]
![[Pasted image 20250512104501.png]]
- to clear the page, just fill it up with `print("/n"* 100)`
# Shallow copy
- shallow copy doesn't point to og,
- it has different memory location and changes to og r not reflected in shallow copy
```python
# copy
student_copy= student
print(student_copy)   # copy
student['name']= 'mona lisa'
print(student_copy)   # added in this too, since it points to the og

# shallow copy
student_copy=student.copy()    
student['name']= 'lisa lisa'
print(student_copy)
print(student)
```
# Iterating
```python
for keys in student.keys():
    print(keys)
  
for values in student.values():
    print(values)
  
for keys,values in student.items():
    print(keys,values)
```
# Dictionary Comprehension
```python
square= {x: x**2 for x in range(10) if x%2==0}

dict1={'a':1, 'b': 2}
dict2={'c':3, 'd': 4}
merge_dict={**dict1, **dict2}   # keyword aurguments
merge_dict
```
### 1. Normal keyword arguments (`**kwargs`)
In a function, `**kwargs` collects arguments passed as key=value into a dictionary.
```python
def fxn(**kwargs):     
	print(kwargs)  

fxn(a=1, b=2) # Output: {'a': 1, 'b': 2}`
Here, `**kwargs` is "unpacking" key–value pairs into a dictionary.