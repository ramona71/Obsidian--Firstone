- `__name__=="__main__"`
- when module is imported , if any function is called in that imported module, the file will run in the main module too
- worst case- when the module deletes ur files just by importing it
- “<mark style="background: #FFF3A3A6;">Only run this code if this file is being run directly, NOT when it’s imported</mark>.”
- readability
- leaves no global variables
- avoid unintended execution
```python
# main.py
import module_add_in       # just importing prints square fxn

#imported_module
def square(x):
    return x**2  
print(square(5))
```
- to prevent the fxn to run in main , we keep it in `__name__=="__main__"`, so that the fxn calls will only run in the file and not when imported 
```python
# main.py
import module_add_in       

#imported_module
def square(x):
    return x**2  
if __name__=="__main__":
    print(square(5))        # now it won't print by just importing
```
- `__name__` is the name of the file
- `__name__=="__main__"` this mean , execute the below only when the file is main 
```python
# imported_module 
def food(name):
    print(f"Your favourite food is {name}")
  
def main():           # will get executed only in this file
    print("Hi!!!")
    food("pizza")
  
if __name__=="__main__":
    main()
    
# main.py
import module_add_in
print(module_add_in.food("Burger"))
print("bye")
```
- <mark style="background: #FFF3A3A6;"> It is recommended to import this in every .py file</mark>