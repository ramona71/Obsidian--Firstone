# Arrays
### [217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
- my solution  - beats 10 % 
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hash_map=dict()
        for num in nums:
            hash_map[num]=hash_map.get(num ,0)+1
        for num in nums:
            if hash_map[num] > 1:
                return True
        return False
```
- optimal - checks after every element, finds duplicates in the beginning if present
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashMap= dict()
        for num in nums:
            hashMap[num]=hashMap.get(num,0)+1
            if hashMap[num] > 1:
                return True
        return False
```
- another optimal - convert the og list to set and check len dumbass TT (it still takes O(n) and doesn't stop if the first two elements r duplicate)
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashMap= set(nums)
        if len(nums)!= len(hashMap):
            return True
        return False
```
### [242. Valid Anagram](https://leetcode.com/problems/valid-anagram/)
- my solution- beats 72
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        hash_map=dict()
        for char in s:
            hash_map[char]= hash_map.get(char,0) +1
        for char in t:
            hash_map[char]=hash_map.get(char,0) - 1
        for value in hash_map.values():
            if value !=0:
                return False
        return True
```
- optimal - beats 24 ?? - combine two loops into one , edge case in the beginning
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        hash_map=dict()
        for i in range(len(s)):
            hash_map[s[i]]= hash_map.get(s[i],0) +1
            hash_map[t[i]]= hash_map.get(t[i],0) -1
        for i in range(len(s)):
            if hash_map[s[i]]!=0:
                return False
        return True
```
- ts prolly not allowed
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return Counter(s)== Counter (t)
```
# Bit Manipulation
### [136. Single Number](https://leetcode.com/problems/single-number/)
- my ans= optimal
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        no=0
        for num in nums:
            no=no^num
        return no
```
### [191. Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)
- my ans = optimal
```python
class Solution:
    def hammingWeight(self, n: int) -> int:
        count=0
        for i in range(0,32):
            if n& (1<<i)!=0:
                count+=1
        return count
```
- another way - Brian Kernighan’s Trick - ( changes the input :( )
```python
class Solution: 
	def hammingWeight(self, n: int) -> int: 
		count = 0 
		while n: 
			n = n & (n - 1) # remove rightmost 1 
			count += 1 
		return count
```
### [338. Counting Bits](https://leetcode.com/problems/counting-bits/)
- my ans
```python
```
- optimal
```python
```
###
- my ans
```python
```
- optimal
```python
```
###
- my ans
```python
```
- optimal
```python
```
###
- my ans
```python
```
- optimal
```python
```
###
- my ans
```python
```
- optimal
```python
```
###
- my ans
```python
```
- optimal
```python
```
