- class inherits attributes and methods of another class
- reusability and extensibility
- `class Child (Parent)`
![[Pasted image 20250830140415.png]]
```python
class Animal:
    def __init__(self, name):
        self.name=name
        self.is_alive=True     #another type of variable
    def eat(self):
        print(f"{self.name} is eating")
  
    def sleep(self):
        print(f"{self.name} is sleeping")
# even if they don't have their own attributes and methods , they can still use the parents'
class Dog(Animal):
    def bark(self):
        print(f"{self.name} is barking")        
  
class Cat(Animal):
    pass
  
dog1=Dog("Kory")
dog1.bark()
dog1.sleep()
```
# Multiple Inheritance
- child inherits from more than one class `Child( A , B )`
# Multi Level Inheritance
- inherit from a parent which inherits from another parent
	- C(B) <- B(A)<- A
# Super
- 