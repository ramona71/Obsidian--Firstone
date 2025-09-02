- if package is not installed, u have to install it
	- requirements.txt -> write all package names to be installed
	- ![[Pasted image 20250716151844.png]]
	- in terminal -> `pip install -r requirements.txt`
- other method to install just a single package
	- in terminal->`pip install package_name`
	- `pip install numpy`
- import specific module to reduce time
```python
# from package_name import module
from math import sqrt, pi
math.sqrt(16)

# import package as alias
import numpy as np
```
- different ways to import
```python
import math           
from math import *    -> imports all modules
```
difference is how u access content
```python
import math
print(math.sqrt(25))   # You use math.sqrt, math.pi, etc.

from math import *
print(sqrt(25))   # No need to prefix with math

```
# Create custom package
- make a folder
- files in it `__init__.py`   -> special file to define package n initialize their namespaces
	- can be empty but it's a must file
-  other file with the custom fxns
```python
# from package_folder_name.file_name import fxn_name
from package.meth import addition
           (or)
from package.meth import *
addition(2,3)
```
- automatic pycache folder will be formed
- can make sub packages inside packages -> but make sure to make `__init__.py `file inside it
```python
# from package_folder_name.subpackage_folder_name.file_name import fxn_name
from package.subpackage.mult import multiply
```
# Standard Library Overview
- Libraries covered
	- Array
	- math
	- random
	- os (file and directory access)
	- shutil
	- json     -> convert json api data to normal data
	- csv
	- date and time
	- time
	- regular expression
```python
import array
arr=array.array('i',[1,5,9,8,6])
print(arr)

import math
math.sqrt(16)
math.pi

import random
print(random.randint(1,56))        -> returns single no between 1 and 56
print(random.choice(["apple", "banana", 'cherry']))    

import os
print(os.getcwd())                -> get current working directory
os.mkdir('test_dir')
open("file.txt", "w").close()

import shutil                     -> high level operations on files/ dir
shutil.copyfile('source.txt', 'destination.txt')

import json                       -> data serialization
data={'name': "Ram", 'age': 56}
  
json_str= json.dumps(data)
print(json_str)
print(type(json_str))
  
parsed_data=json.loads(json_str)
print(parsed_data)
print(type(parsed_data))

import csv
with open('example.csv', mode='w', newline='') as file:
    writer=csv.writer(file)
    writer.writerow(['name','age'])
    writer.writerow(['Ram','31'])
  
with open('example.csv', mode='r') as file:
    reader=csv.reader(file)
    for row in reader:
        print(row)

from datetime import datetime, timedelta
now= datetime.now()
print(now)
yesterday=now-timedelta(days=1)
print(yesterday)

import time
print(time.time())
time.sleep(2)
print(time.time())

import re
pattern=r'\d+'
text='There are 123 apples'
match=re.search(pattern,text)
print(match.group())
```