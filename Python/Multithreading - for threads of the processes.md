- program- sequence of instructions 
- process- instance of program that is being executed
	- each process has separate memory space
		- so one process can't corrupt another process
		- increased execution time to switch b/w processes
	- each process has it's own
		- ![[Pasted image 20250904101419.png]]
- Thread - unit of execution within the process
	- Types:
		- Single threaded process - shared everything with process
		- Multi threaded process - each thread has it's own stack and register , and shares everything else with process
		- ![[Pasted image 20250904101645.png]]
- When to use multithreading? 
	- I/O bound operations (file operations, network requests)
	- concurrent execution- improve throughput
```python
import threading
import time

def numbers():
    for i in range(5):
        print(f"Numbers {i} ")
        time.sleep(2)
def letter():
    for letter in "manis":
        print(f"letter {letter} ")
        time.sleep(2)
  
thread1=threading.Thread(target=numbers)
thread2=threading.Thread(target=letter)
start_time=time.time()
thread1.start()
thread2.start()
  
#wait for threads to complete
thread1.join()
thread2.join()
finished_time= time.time()
print(finished_time- start_time)
```
	-The "weird" mixed output is completely normal when using threads in Python. cuz both threads run concurrently and print() is not atomic (writes to stdout in small chunks)
# Multiprocessing - for processes
- creates processes that runs in parallel
- when to use? 
	- CPU bound tasks (math/ data computations)
	- Parallel execution (Multiple cores of CPU)
### Reason you need `if __name__ == "__main__":` with `multiprocessing`

When you create a new `Process`, Python **spawns a new interpreter** and re-imports your script as a module.

- That means it will **execute the top-level code again**.
- If your process creation code (`p1=...`, `p2=...`) is at the top level, the child process will try to run it again → leading to **infinite child process spawning**.
### Why it’s not needed with `threading`
- Threads run **inside the same process**.
- No new Python interpreter is spawned.
- So your file isn’t re-imported → no risk of infinite recursion.
With `multiprocessing`, though, **every new process runs the file from scratch**. That’s why the `__main__` guard is **mandatory** (especially on Windows).
```python
import multiprocessing
import time
  
def square ():
    for i in range(5):
        time.sleep(1.5)
        print(f"Square {i}")
  
def numbers():
    for i in range(5):
        time.sleep(1.5)
        print(f"Number {i}")
if __name__=='__main__':  
    t=time.time()
    p1= multiprocessing.Process(target= numbers)
    p2= multiprocessing.Process(target=square)
  
    p1.start()
    p2.start()
  
    p1.join()
    p2.join()
    t2=time.time()
    print(t2-t)
```
# Multithreading with thread pool executor
- Lets you run multiple tasks **in parallel** without manually creating/joining threads.
- Runs tasks in parallel, at most 3 at a time.  
- No need to `start()` or `join()` manually.
```python
from concurrent.futures import ProcessPoolExecutor
import time
  
def numbers(task):
    for i in range(5):
        time.sleep(1)
        print(f"no {task}")
    return f"done {task}"
  
if __name__ == '__main__':   # important for Windows!
    tasks = ['a', 'b', 'c', 'd']
  
    with ProcessPoolExecutor(max_workers=3) as executor:
        results = executor.map(numbers, tasks)
  
        for result in results:
            print(result)
```
	i deadass dk what he's doing
# Web Scraping
- idk what he's saying tbh
```python
import threading
import requests
from bs4 import BeautifulSoup   # for web scraping
  
urls=[
'https://python.langchain.com/v0.2/docs/introduction/',
'https://python.langchain.com/v0.2/docs/concepts/'
'https://python.langchain.com/v0.2/docs/tutorials/' 
]
  
def fetch_content(url):
    response=requests.get(url)
    soup=BeautifulSoup(response.content,'html.parser')
    print(f'Fetched {len(soup.text)} characters from {url}')
  
threads=[]
  
for url in urls:
    thread=threading.Thread(target=fetch_content,args=(url,))
    threads.append(thread)
    thread.start()
  
for thread in threads:
    thread.join()
  
print("All web pages fetched")
```
# Real World Multiprocessing CPU bound task
- distribute work load across multiple CPU cores for performance
```python
import multiprocessing
import math
import sys
import time
  
# Increase the maximum number of digits for integer conversion
sys.set_int_max_str_digits(100000)
  
## function to compute factorials of a given number
  
def computer_factorial(number):
    print(f"Computing factorial of {number}")
    result=math.factorial(number)
    print(f"Factorial of {number} is {result}")
    return result
  
if __name__=="__main__":
    numbers=[5000,6000,700,8000]
  
    start_time=time.time()
  
    ##create a pool of worker processes
    with multiprocessing.Pool() as pool:
        results=pool.map(computer_factorial,numbers)
  
    end_time=time.time()
  
    print(f"Results: {results}")
    print(f"Time taken: {end_time - start_time} seconds")
```