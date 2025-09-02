1. describe the problem, 
	1. write it down step by step and see which of ur assumptions are wrong
2. reproduce bug
	1. when the code works sometimes and doesn't the other times and produce error (ex: list index out of range)
3. evaluate each line (play computer)
	1. u are the computer now :(
4. fix errors
	1. show by editor/ terminal
	2. by exception handling
```python
try:
    age=int(input("How old are you?: "))
except ValueError:
    print("You entered invalid no. Try again and input an integer no.")
    age=int(input("How old are you?: "))
if age>18:
    print("yea you can drive ")
```
![[Pasted image 20250610132832.png]]
5. print!! PRINT!!!! 
6. Debugger
	1. 