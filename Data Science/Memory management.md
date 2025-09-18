- automatic garbage collection
- needs `gc` for cyclic references -> manual garbage collection needed
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
print(sys.getrefcount(b))   # since b is deleted it gives an error
```
####  Memory Management Best Practices

1. Use Local Variables: Local variables have a shorter lifespan and are freed sooner than global variables.
2. Avoid Circular References: Circular references can lead to memory leaks if not properly managed
3. Use Generators: Generators produce items one at a time and only keep one item in memory at a time, making them memory efficient.
4. Explicitly Delete Objects: Use the del statement to delete variables and objects explicitly.
5. Profile Memory Usage: Use memory profiling tools like tracemalloc and memory_profiler to identify memory leaks and optimize memory usage.
# Garbage collection
- Python includes a cyclic garbage collector to handle reference cycles. Reference cycles occur when objects reference each other, preventing their reference counts from reaching zero.
- destructor - deallocate obj memory  
	- `def __del__(self):`
	- `del obj1`
```python
import gc

gc.collect()              # manually trigger collection
gc.isenabled()            # check if GC is on
gc.disable()              # turn off GC
gc.enable()               # turn it back on
gc.get_stats()            # see stats of collection
print(gc.garbage)               ### get unreachable objects
```
- circular reference
```python
import gc
class MyObject:
    def __init__(self, name):
        self.name = name
        print(f"Object {self.name} created")
    def __del__(self):
        print(f"Object {self.name} deleted")
        
# Create circular reference
obj1 = MyObject("obj1")
obj2 = MyObject("obj2")
obj1.ref = obj2
obj2.ref = obj1

del obj1
del obj2        # this won't be enough
## Manually trigger the garbage collection
gc.collect()
```
# # Generators for memory efficiency
```python
def generate_numbers(n):
    for i in range(n):
        yield i
  
## using the generator
for num in generate_numbers(100000):
    print(num)
    if num>10:
        break
```
# Tracemalloc 
- Python’s built-in **memory tracking module**.
- It helps you **trace memory allocations** line by line in your code.
- Useful for debugging **memory leaks** or finding **high memory usage** spots.
```python
import tracemalloc

def create_list():
    return [i for i in range(10000)]   # creates a list of 10,000 integers

def main():
    tracemalloc.start()   # ✅ Start tracing memory allocations
    
    create_list()         # ✅ This line allocates memory for the list
    
    snapshot = tracemalloc.take_snapshot()  # ✅ Take a "memory snapshot"
    top_stats = snapshot.statistics('lineno')  
    #   → Groups memory usage statistics by line number in your code
    
    print("[ Top 10 ]")
    for stat in top_stats[::]:
        print(stat)       # ✅ Print each memory usage stat

```