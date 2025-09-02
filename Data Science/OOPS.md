# Classes and obj
- CAPITAL LETTER FOR CLASS NAME
- obj, instantiated from class
```python
class Car:
    pass

audi= Car()
audi.windows= 4          # windows attribute wasn't even present in class car , but it can be instatiated like this (not recommended)
print(audi.windows)
```
	- 'dir' will show windows as attribute for obj 'audi'
- creating variables, methods for class -> can't change later, fixed parameters
- `__init__` -> constructor
- `self` -> keyword, accessing instance variable inside class itself 
	- should always be first parameter
	-  can use any word but `self` is universal
	- Without `self`, a method wouldn't know which specific instance's data it should operate on.
```python
class Dog:
    def __init__(self,name,age):
        self.name=name
        self.age=age
dog1=Dog("cat", 36)
print(dog1, dog1.name, dog1.age)

#ex2
class Car:
    def __init__(self, windows, doors, enginetype):
        self.windows1=windows                        # allowed
        self.door1=doors
        self.enginetype1=enginetype
    def drive(self):
        print(f'the person drives {self.enginetype1} car')
car1=Car(4,5,'petrol')
car1.drive()
```
- `self.name=name` u can keep another name `self.name1=name` but before is preferred


# Inheritance
- inherit FROM parent class 
```python
class TeslaCar(Car):
    def __init__(self, windows, doors, enginetype, is_selfdriving):
        super().__init__(windows, doors, enginetype)  # no self when super
        self.is_selfdriving= is_selfdriving
    def selfdriving(self):
        print(f'Tesla supports self driving: {self.is_selfdriving}')
tesla1= TeslaCar(4,5,'electric', True)
tesla1.selfdriving()
tesla1.drive()                      # all methods will be inherited
```
### Multiple Inheritance
- a class inherits from more than one base class