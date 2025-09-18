# Dictionary
### Example of error:

```python
s = "hello" hash_map = {}  # empty dictionary  
for char in s:   
  hash_map[char] += 1  # KeyError:'h' because 'h' is not yet in the dictionary
```
- Correct ways to fix it:
1. Use `dict.get()` with default:
```python
for char in s:
    hash_map[char] = hash_map.get(char, 0) + 1
    
# Initialize keys if not present:

for char in s:
    if char not in hash_map:
        hash_map[char] = 0
    hash_map[char] += 1

```
# Counters
```python
nums = [1, 2, 2, 3, 3, 3]
counter = Counter(nums)
print(counter)  # Counter({3: 3, 2: 2, 1: 1})

s = "leetcode"
counter = Counter(s)
print(counter)  # Counter({'e': 3, 'l': 1, 't': 1, 'c': 1, 'o': 1, 'd': 1})

d = {'a': 3, 'b': 1}
counter = Counter(d)
print(counter)  # Counter({'a': 3, 'b': 1})

from collections import Counter

sentence = "this is a test this is only a test"
words = sentence.split()
word_count = Counter(words)
print(word_count)

from collections import Counter

s = "abracadabra"
hash_map = Counter(s)
print(hash_map.most_common(3))  # top 3 frequent letters

```