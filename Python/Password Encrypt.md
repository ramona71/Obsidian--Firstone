```python
import string
import random
  
chars= string.punctuation+ string.ascii_letters+ string.digits+ " "
chars= list(chars)
  
go_on=True
while go_on:
    key=chars.copy()
    random.shuffle(key)
    password= input("Enter the password that u want to encrypt: ")
    encrypt=""
    for i in range(len(password)):
        encrypt+=key[i]
    print(encrypt)
  
    keep_playing= input("Want to encrypt another password? (y/n)"). lower()
    if not keep_playing=='y':
        go_on=False
```