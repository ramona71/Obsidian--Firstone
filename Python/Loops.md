- use for loop for iteration
- use while loop for iteration if there's a condition we need to meet and break out of it (Remember the chances of infinite loop is more here)
### for loop syntax:

```python
 for i in range(10):
    block   
   ```
   - some examples:
   ```python
   for i in range(1,100+1,3):                    #can add step in range fxn
     print (str(i)+ "The number is a multiple of 3")


	for sec in range(10,0,-1):
	  print(sec)
	  time.sleep(1)
	print("Happy new year")  
	# another way to reverse
	for sec in reversed(range(10)):

	for i in range(10):
	  print(i, end=" ")
  # iterate a string
	for x in "The long brown fox":
	  print(x)
```
### while loop :

```python
   while 1==1(cond is true):                        #just 1 will also work
		block                                   #this gives infinit loop
		
while not food=="q":
	 block
```
- negation
```python
while not at_goal():
	 block
```
## nested loop

```python
for i in range(10):
 for j in range(5):
   print(i,j, sep="," , end=" ")
```

## loop control statements
- break - used to terminate the loop entirely
- continue- skips to next iteration of loop
- pass- does ntg, acts as place holder
- You don't have to always use i in range(0, len(student_score)) just use
```python
for score in student_score:
 block

```
## Range fxn
```python
range(1,11)     #to print 1 to 10, [1,11)
reversed(range(10))   # prints in reverse
range(1,11,3)   #prints what?
```
- code to add numbers till 1000?
```python
for n in range(1,101):
total+= n
```
- code for add only even numbers till user input number?
```python
target = int(input()) # Number between 0 and 1000
# Your code here 👇
even_sum = 0
for number in range(2, target + 1, 2):
  even_sum += number
print(even_sum)

# or

# alternative_sum = 0
# for number in range(1, target + 1):
#   if number % 2 == 0:
#     alternative_sum += number
# print(alternative_sum)
```