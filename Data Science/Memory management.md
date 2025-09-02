- automatic garbage collection
- Reference counting - manage memory
	- each obj in python maintains a count of references pointing to it
	- if reference count drops to 0, memory occupied by obj is deallocated
```python
import sys
a=[]
print(sys.getrefcount(a))
# 2 , cuz one reference from a , and one from getrefcount()
b=a
print(sys.getrefcount(a))
#3 , from a , b and getrefcount()
del b
print(sys.getrefcount(a))   # when this drops to 0, memory is deallocated
```
# Garbage collection
- destructor - deallocate obj memory