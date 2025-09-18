## if statement
- syntax
```python
	if condition:
	 block
	elif condition:
	 block
	else:
	block
```
- u can have nested if condition too 
	```python
	if condn:
	   if condn:
	     block
	   elif condn:
	     block
	   else:
	     block
	else:
	 block
```
  - use multiple if statements in succession if you needed 

> [!NOTE] else is not mandatory at the end (can just end with elif)

```python
print("Welcome to the rollercoaster!")
height = int(input("What is your height in cm? "))
bill = 0

if height >= 120:
  print("You can ride the rollercoaster!")
  age = int(input("What is your age? "))
  if age < 12:
    bill = 5
    print("Child tickets are $5.")
  elif age <= 18:
    bill = 7
    print("Youth tickets are $7.")
  else:
    bill = 12
    print("Adult tickets are $12.")
  
  wants_photo = input("Do you want a photo taken? Y or N. ")
  if wants_photo == "Y":
    bill += 3
  
  print(f"Your final bill is ${bill}")

else:
  print("Sorry, you have to grow taller before you can ride.")
```
- single code can be done in two ways
  Q. Based on a user's order, work out their final bill. 
	   Small pizza (S): $15
	   Medium pizza (M): $20
	   Large pizza (L): $25
	   Add pepperoni for small pizza (Y or N): +$2
	   Add pepperoni for medium or large pizza (Y or N): +$3
	   Add extra cheese for any size pizza (Y or N): +$1
  - first way
```python
print("Thank you for choosing Python Pizza Deliveries!")
size = input()  # What size pizza do you want? "S", "M", or "L"
add_pepperoni = input()  # Do you want pepperoni? "Y" or "N"
extra_cheese = input()  # Do you want extra cheese? "Y" or "N"
bill = 0
if size == "S":
  bill += 15
elif size == "M":
  bill += 20
else:
  bill += 25

if add_pepperoni == "Y":
  if size == "S":
    bill += 2
  else:
    bill += 3
    
if extra_cheese == "Y":
  bill += 1
print(f"Your final bill is: ${bill}.")
```
 - second way
```python
	bill=0
if size=="S":
  bill=15
  if add_pepperoni=="Y":
    bill+=2
if size=="M":
  bill=20
  if add_pepperoni=="Y":
    bill+=3
if size=="L":
  bill=25
  if add_pepperoni=="Y":
    bill+=3
if extra_cheese=="Y":
  bill+=1
print(f"Your final bill is: ${bill}.")
```
- multiple condns in single line using and, or , not
```python
if a>90 and a<=200:
 print("yay")
```
- use elif instead of if too many times plz
# conditional expression (ternary operator)
```python
num=20
a=10
b=5
print("even" if num>0 and num%2==0 else "odd")
result= "Even" if num%2==0 else "odd"
min_no= a if a<b else b
```

# Match Case (Switch)
- cleaner compared to shit tons if else
- syntax is
```python
match variable:
	case value_of_var:   # can add multiple with |, & etc
		block
	case val2:
		block
	case _:        # default case
		block
# ex
def day_of_week(day):
    match day:           
        case 1:
            return "It's Sunday"
        case 2:
            return "it's Monday"
        case 3 | 4 :
            return "It's Tuesday / Wednesday"
        case _:                         # default case
            return "Not Valid"
  
print(day_of_week(2))
```
