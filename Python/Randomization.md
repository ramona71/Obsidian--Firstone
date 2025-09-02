- https://www.askpython.com/python-modules/python-random-module-generate-random-numbers-sequences
- import random -> module
- random only prints between 0 and 0.9999999999, ie [0,1) , 
```python
import random

#random integer
random_interger =random.randint (1,10)
print(random_interger)

#random float
random_float = random.random()
print(random_float)

random_float = random.random()*5             # to print btw 0 and 5
print(random_float)

```
- random can be inclusive if we keep it in bracket, meaning prints those values too
```python
a=random.randint(0,1)                   # prints o or 1 , doesnt exclude
print(a)
```
- shuffle function
```python
import random
x=[1,2,3]
random.shuffle(x)
print(x)
```