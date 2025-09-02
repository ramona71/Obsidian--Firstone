# [1. Two Sum](https://leetcode.com/problems/two-sum/)
- optimal
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n=len(nums)
        hash_map={}
        for i in range(n):
            remaining= target-nums[i]
            if remaining in hash_map:
                return [i, hash_map[remaining]]
            hash_map[nums[i]]= i
        return None
```
# [121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)
- my optimal  -> beats 56
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        n=len(prices)
        min= float('inf')
        profit=0
        for i in range(n):
            if prices[i]>=min:
                profit=max(profit, prices[i]-min)
            else:
                min=prices[i]
        return profit
```
- better optimal ->
```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        n=len(prices)
        mini= float('inf')
        profit=0
        for i in range(n):
            mini= min(mini, prices[i])
            profit= max(profit, prices[i]-mini)
        return profit
```