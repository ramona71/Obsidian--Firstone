# Iterator
- efficient looping and memory management
- uses lazy loading technique - won't show elements unless we iterate
```python
lst=[1,5,6,8,7,9,3]
iterator=iter(lst)
print(iterator)     # doesn't show elements like list
  
# to iterate
print(next(iterator))     # 1st value is shown
print(next(iterator))     # 2nd value is shown
```
- if it runs out of elements it shows error  -> catch an exception
```python
try:
    print(next(iterator))
except StopIteration:
    print("Out of elements")
```
 - more ex
 ```python
 name= "Mona "
iterator=iter(name)
  
try:
    print(next(iterator))
except StopIteration:
    print("Out of char")
 ```
# Generator
- sub class of Iterator
- simpler way to create iterators
- yield keyword to produce series of values lazily (generate values on fly and not store them in memory)
```python
def fun(max):
    cnt = 1
    while cnt <= max:
        yield cnt
        cnt += 1

ctr = fun(5)
for n in ctr:
    print(n)
```
- A generator **creates items one at a time, only when you ask for them**:
    
    ```python
    nums = (x for x in range(5))
    ```
    
    → It doesn’t make the whole list.  
    → It just _remembers how to make the next number_.
 how do we make a generator?

### 1. Using `yield` inside a function

```python
def number_gen():
    for i in range(5):
        yield i   # pause here, give value, continue next time

gen = number_gen()
```

Now you can get values one by one:

```python
print(next(gen))  # 0
print(next(gen))  # 1
print(next(gen))  # 2
```

---

### 2. Generator expressions

Like list comprehensions but with `()` instead of `[]`:

```python
gen = (x*x for x in range(5))
```

---

## 🧠 Why use generators?

1. **Save memory** → no need to store big lists.
    
    ```python
    nums = (x for x in range(1000000000))  # works fine!
    ```
    
2. **Efficient for large/streaming data**
    
    - Reading big files line by line
        
    - Handling endless data (like sensor readings or live logs)
        
3. **Stop anytime** → You don’t need the full list, just ask for the next value.
    
## 🌟 Example: File reading

Instead of:

```python
lines = open("bigfile.txt").readlines()  # loads everything 😱
```

Use a generator:

```python
def read_file():
    with open("bigfile.txt") as f:
        for line in f:
            yield line  # gives one line at a time
```

👉 In short:

- **List** = stores everything now.
    
- **Generator** = makes things one by one, only when needed.