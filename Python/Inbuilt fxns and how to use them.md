- https://docs.python.org/3/library/functions.html
# len()
```python
n=len(score)        # let score be a list or tuple, then len will be printed
n=len("score")           # 5
f_name-=f_name.title()   #first letter capital, rest lower case
```
- some important stuff
```python
-> .lower()
word=input("Enter a word: ").lower()
```
# Sort() and Sorted()
- sort / reverse sort a list
```python
import random
lst= [random.randint(1,100) for x in range(10)]
print(lst)
# sort the same list
lst.sort()
print(lst)
lst.sort(reverse=True)
print(lst)
  
# sort and save into another variable
ascending= sorted(lst)
desending= sorted(lst,reverse=True)
print(ascending)
print(desending)

s=['man', 'woman']
res = "".join(sorted(s, reverse=True))
print(res)
```
