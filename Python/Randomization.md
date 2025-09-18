- https://www.askpython.com/python-modules/python-random-module-generate-random-numbers-sequences
- https://www.geeksforgeeks.org/python/python-random-module/
- import random -> module
- random only prints between 0 and 0.9999999999, ie [0,1) , 
```python
import random

#random integer
random_interger =random.randint (1,10)   # prints 10 too
print(random_interger)

#random float between 0.0 to 1.0  [0.0, 1.0) 
random_float = random.random()
print(random_float)

random_float = random.random()*5             # to print btw 0 and 5
print(random_float)

a= [1,5,3,9,8,4,6]
print(random.choice(a))

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
# Seeding
- Python uses pseudorandom number generator (PRNG) to generate random no so it's not really random
- If u use the same seed , the random no's will be same on every run
	- (For seed 42, it’ll always print `2, 1, 5` on the first three calls.)
```python
import random
random.seed(42)  # set the seed
print(random.randint(1, 10))
```