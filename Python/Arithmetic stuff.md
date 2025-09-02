
> [!NOTE] Type cast ur input number as FLOAT and not INT

```python
age=25
age+=1
age-=1
age*=5
age/=10
print(age)
age//=2
print(age)
print(type(age))    # still gonna be float cuz age is float before
age**=2
print(age)
age%=5
print(age)         # still gonna be flaot cuz age is float before
  
x=3.14
y=-4
z=5
x=round(x)     # 3
x=round(x,2)   # round to 2 decimal places
y=abs(y)       # value from 0, absolute value -> 4
result= pow(x,y)    #x to power y
res= max(x,y,z)
res=min(x,y,z)
```
# import math
- for scientific math, import this module
```python
import math
  
print(math.pi)
print(math.e)
  
x,y = 28,5.6
res=math.sqrt(x)
res=math.ceil(y)  # rounds to above float point -> increase
res=math.floor(y) # rounds to below int -> decrease
```