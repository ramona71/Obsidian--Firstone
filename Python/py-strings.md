- some methods

> [!NOTE] `print(help(str))` to get info about strings

| Method         | Example                                                 |
| -------------- | ------------------------------------------------------- |
| capitalize()   | `"hello".capitalize() → "Hello"`                        |
| casefold()     | `"HELLO".casefold() → "hello"`                          |
| center()       | `"hi".center(5) → "  hi "`                              |
| count()        | `"banana".count("a") → 3`                               |
| encode()       | `"hello".encode() → b'hello'`                           |
| endswith()     | `"test.py".endswith(".py") → True`                      |
| expandtabs()   | `"a\tb".expandtabs(4) → "a   b"`                        |
| find()         | `"hello".find("e") → 1`     (first occurance)           |
| format()       | `"{}+{}={}".format(2,3,5) → "2+3=5"`                    |
| format_map()   | `"{x}{y}".format_map({'x':1,'y':2}) → "12"`             |
| index()        | `"hello".index("e") → 1`                                |
| isalnum()      | `"abc123".isalnum() → True`                             |
| isalpha()      | `"abc".isalpha() → True`                                |
| isascii()      | `"abc".isascii() → True`                                |
| isdecimal()    | `"123".isdecimal() → True`                              |
| isdigit()      | `"123".isdigit() → True`                                |
| isidentifier() | `"var1".isidentifier() → True`                          |
| islower()      | `"hello".islower() → True`                              |
| isnumeric()    | `"Ⅳ".isnumeric() → True`                                |
| isprintable()  | `"hi".isprintable() → True`                             |
| isspace()      | `"   ".isspace() → True`                                |
| istitle()      | `"Hello World".istitle() → True`                        |
| isupper()      | `"HELLO".isupper() → True`                              |
| join()         | `"-".join(["a","b"]) → "a-b"`                           |
| ljust()        | `"hi".ljust(5) → "hi   "`                               |
| lower()        | `"HELLO".lower() → "hello"`                             |
| lstrip()       | `"  hi".lstrip() → "hi"`                                |
| maketrans()    | `str.maketrans("a","1")`                                |
| partition()    | `"hello world".partition(" ") → ("hello"," ","world")`  |
| replace()      | `"hello".replace("l","x") → "hexxo"`                    |
| rfind()        | `"banana".rfind("a") → 5`   (last occurance)            |
| rindex()       | `"banana".rindex("a") → 5`                              |
| rjust()        | `"hi".rjust(5) → "   hi"`                               |
| rpartition()   | `"hello world".rpartition(" ") → ("hello"," ","world")` |
| rsplit()       | `"a,b,c".rsplit(",") → ["a","b","c"]`                   |
| rstrip()       | `"hi  ".rstrip() → "hi"`                                |
| split()        | `"a,b,c".split(",") → ["a","b","c"]`                    |
| splitlines()   | `"a\nb".splitlines() → ["a","b"]`                       |
| startswith()   | `"hello".startswith("he") → True`                       |
| strip()        | `"  hi  ".strip() → "hi"`                               |
| swapcase()     | `"Hello".swapcase() → "hELLO"`                          |
| title()        | `"hello world".title() → "Hello World"`                 |
| translate()    | `"abc".translate(str.maketrans("a","1")) → "1bc"`       |
| upper()        | `"hello".upper() → "HELLO"`                             |
| zfill()        | `"42".zfill(5) → "00042"`                               |
```python
name="Mona Lisa "

res= len(name)
re=name.find(" ")    # dirst occurance
re=name.rfind("q ")  # last occurance  - if not found returns -1
re=name.capitalize()
name=name.upper()
name=name.lower()
re= name.isdigit()   # True/ False - only digits
re= name.isalpha()   # True/False  - only alphabets  
re=name.count("8")   # counts how many 8's r there in a string
re=name.replace("a", "b")  # replace a with b
```
# Slicing
- `[start: end: step]`
	- start -> 0 , end -> len of string (not included)
```python
credit_no= "123456789"
print(credit_no[0 :5])
print(credit_no[5:])
print(credit_no[-1:])    # only 9 is printed
print(credit_no[::])     # prints all
print(credit_no[::-1])   # reverse the string
print(credit_no[::3])
print(credit_no[-4::])  # last 4 digits
```

# Format specifiers
- `{value: flag}` format a value based on what flags are inserted
	![[Pasted image 20250901135918.png]]
```python
price1= 38456.1456
price2=-5691.5
price3= 12.97
print(f"Price 1 is {price1:.2f}")   # rounds to 2 decimal palces
print(f"Price 2 is {price2:10}")
print(f"Price 3 is {price3:021}")   # zero pad
print(f"Price 3 is {price3:<}")
print(f"Price 3 is {price3:>}")
print(f"Price 3 is {price3:^}")
print(f"Price 3 is {price2:,}")
print(f"Price 1 is {price1:+,.2f}")
```