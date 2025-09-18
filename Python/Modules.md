- file containing code 
	- use import to include a module ( inbuilt / ur own)
- useful to break up a large program (reusable separate files)
- 
```python
# to know more about these
print(dir("modules"))     # gives all attributes and method names
print(help("modules"))    # explains all attributes and methods

print(help/dir("specific_module"))
print(help/dir("math"))
```
- alias of module
	- `import module as nickname`
		- `import numpy as np
- import something specific
	- `from module import specific`
		- `from math import e`
- import all
	- `from module import *`
		- `from math import *`
```python
import math as m
print(m.pi)
  
from math import pi
print(pi)          # don't have to mention module while calling it (not recom)
```




### OWN modules
- import them from other files 
```python

my_module.py
pi= 3.14


main.py
import my_module
print(my_module.pi)                     #prints 3.14
```
- another ex
```python
# module file
name= "Mona"
  
def square(x):
    return x**2
  
def half(x):
    return x//2

# main
import module_add_in
  
res=module_add_in.name
print(res)
print(module_add_in.square(5))
print(module_add_in.half(10))
```