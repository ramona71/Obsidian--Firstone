- obj- bundle of related attributes(variables) and methods (fxns)
	- need a class to make a obj
- class - (blueprint) used to design a obj
### Constructor method
- dunder method - double underscore method
```python
 def __init__(self):
```
- Basic class ex:
```python
class Car:
    def __init__(self, model, year, color, for_sale):
        self.model= model
        self.year=year
        self.color=color
        self.for_sale= for_sale
car1= Car("BMW", 1986, "pink", False)
print(car1)     # prints memeory address
print(car1.color)
```
- or make another file for class and import it to the main 
```python
# class 'Car' file
class Car:
    def __init__(self, model, year, color, for_sale):
        self.model= model
        self.year=year
        self.color=color
        self.for_sale= for_sale
  
    def drive(self):
        print(f"Your driving a {self.color} {self.model}")
        
    def stop(self):
        print(f"You stopped driving {self.model}")
        
    def describe(self):
        print(f"ur car is a {self.yar} {self.color} {self.model} and it's status for sale is {self.for_sale}")

#main file
from car import Car
  
car1= Car("BMW", 1986, "pink", False)
print(car1)     # prints memeory address
print(car1.color)
car1.drive()
car1.stop()
car1.describe()
```
### Class variables
- defined outside constructors
- same for all instances of class
![[Pasted image 20250830135246.png]]    ![[Pasted image 20250830135303.png]]
```python
class Student:
    class_year=10                 # class variable  
    num_of_students=0
    def __init__(self,name, age):
        self.name=name
        self.age=age
        Student.num_of_students+=1     # way to use class variable
                                   #increments whenever a new obj is created
  
student1= Student("Gun", 56)
student2=Student("Bun", 6)
  
print(student1.name)
print(student2.age)
  
print(student1.class_year) # same for both
print(student2.class_year)   
print(Student.class_year) #direct way to access class variable (recommended)

print(f"Year of the class: {Student.class_year} no of students : {Student.numof_students}")    
```