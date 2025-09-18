- everything is a function, 
- there r a lot of inbuilt fxns like len(), append(), int() etc 
- basic fxn
```python
def my_fxn(*parameter*):   
  block
my_fxn(*argument*)  
```
> [!NOTE] Parameters ->variables defined in fxn    Arguments ->passed through user
- built in py fxns ->   https://docs.python.org/3/library/functions.html
```python
def fxn (a,b,c)

fxn(1,2,3)
# to make this more clear
fxn(a=1, b=2, c=3)
# u can fuck up the order and the values won't change now
fxn(c=3, b=2, a=1)
```
# fxns with outputs
- returns output
```python
def fxn (a):
 return a

output = fxn(2)
```
- you can return 'f strings'
```python
def format_name(f_name, l_name):
    f_name=f_name.title()
    l_name=l_name.title()
    return f"{f_name} {l_name}"
print(format_name("agHAGKOgno", "klahHkshg"))
```
- nest fxns
```python
output= fxn2(fxn1("hello"))
```
- 'return' would be the last line to execute, after 'return' code comes out of that fxn , n anything after that will not execute
- can have empty return
```python
fxn1(name)():
    if name== "":
	    return
print(fxn(""))

# it prints "None"
```
![[Pasted image 20250531120757.png]]
# to give another name to a fxn
- just assign to a variable without '( )'
- `alternate_name = og_name`
```python
def add(n1,n2):
    return n1+n2
addition_of_numbers= add                #like this
print(addition_of_numbers(5,10))        #15
```
- day 10 for more info
# Default Arguments
- default values for certain parameters
- if nothing is passed as argument, default value will be considered
```python
def fxn (company= "IBM"):
    print("The company is "+ company)
fxn("Google")         # prints Google
fxn()                 # prints IBM
```
# Keyword Arguments
- argument preceded by identifier (order of arguments doesn't matter)
- readability 
```python
def name(first, last):
    print(first + " "+ last)
name(last="Lisa", first="Mona")
```
# Arbitrary 
- varying amount of arguments
- * args - multiple non-key arguments
	- <mark style="background: #FFF3A3A6;">pack all the arguments into TUPLE</mark> if args
- ** kwargs - multiple keyword arguments
	- <mark style="background: #BBFABBA6;">pack all arguments into DICITIONARY</mark> if kwargs
```python
def fxn(*args):
    print(type(args))
    total=0
    for arg in args:
        total+=arg
    return total

re=fxn(1,2,3,5,6)
print(re)
```
- can use something other than `*args`  (naming convention is not as important)
```python
def fxn(*nums):                  # works same as *args
```
## kwargs
- guess what's wrong with the below code
```python
def fxn(**kwargs):
    print(type(kwargs))
fxn("hi", 15, "lola bunny", 896.2)
```
	u cna't use positional arguments for kwargs,use dict key:value arguments
```python
def fxn(**kwargs):
    print(type(kwargs))
    for key,value in kwargs.items():
        print(f"{key } = {value}")
    if "name" in kwargs:
        print(kwargs.get("name"))     # can access like this too
fxn(greet="hi", no=15,name= "lola bunny",flo= 896.2)
```
> [!NOTE] The order of priority for Arguments
> 1. Positional   (normally)
> 2. default
> 3. keyword
> 4. Arbitrary   (args and then kwargs)
# Iterables
- obj/ collection that's iterated
- list, sets, dict, tuple, STRING

# DocStrings
- create documentation for fxns u write (like the documentation u get while u hover over in built fxns like len( ), title( ) etc)
- use 3 "  -> `"""`
```python
def format_name(f_name, l_name):
    """ Takes a first and last name
        returns a title case version of it """
    f_name=f_name.title()
    l_name=l_name.title()
    return f"man the strings are {f_name} {l_name}"
```
- u can also use `"""` as multi line comment, but no recommended
