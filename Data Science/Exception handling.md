- handle errors and take action without stopping the execution
- exception - errors that happen during execution, that CAN be handled

| error                                                 | exception                                              |
| ----------------------------------------------------- | ------------------------------------------------------ |
| serious issue in program                              | issue that can be handled                              |
| Mostly due to logic/syntax issues or system failures. | Due to runtime issues in code (e.g., invalid input).\| |
- all these errors r derived from main exception class
	- `Exception as ex `  -> just use this for any exception if u don't know the name
	- can write any no of exceptions but make sure main exception class is at last
```python
try:
	block
except:
	resolve


# have exception names
try:
    a=b
except NameError as ex:
    print("they don't exist :(")
    print(ex)
#ex 2
try:
    res=1/0
except ZeroDivisionError as zero:
    print(zero)
    print("Enter denominator other than 0")

#can handle multiple exceptions
try:
    res=1/0
    a=b
except ZeroDivisionError as zero:               
    print(zero)
    print("Enter denominator other than 0")
except Exception as ex:                    -> main exception class(at last)
    print("they don't exist :(")
    print(ex)

# Exception always at last
try:
    num=int(input("Enter a no"))
    res=(10/num)
except ValueError:
    print(f"Not a valid ans-{ValueError}")
except ZeroDivisionError:
    print(f"Not a valid denom-{ZeroDivisionError}")
except Exception as ex:
    print(es)
```