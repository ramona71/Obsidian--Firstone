```python
import time
  
my_time= int(input("Enter the time in sec:"))
  
for x in range(my_time, 0, -1):
    seconds= x %60
    minutes= x//60
    hours= (x//3600)
    print(f"{hours}: {minutes:02}: {seconds:02}")
    time.sleep(1)
```