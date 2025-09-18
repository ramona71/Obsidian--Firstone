# Variable Scope
- where a variable is visible and accessible
# Scope Resolution
- LEGB
	- ![[Pasted image 20250903142248.png]]
- when using a variable first Local version is considered, if not found , enclosed is preferred (fxn inside fxn), then global and then built in
```python
#local
def fun2():
	x=2
	print(x)
	
#enclosed 
def fun1():
    x=1
    def fun2():
        x=2
        print(x)
    fun2()
fun1()                       # 2 is printed

#global
def fun2():
    print(x)
x=3
fun2()

# built in
from math import e
print(e)
```
- find what e will be printed below
```python
from math import e
def fun(e):
    print(e)
e=4
fun(e)
```
- 