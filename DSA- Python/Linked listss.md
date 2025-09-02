# [876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)
- optimal - tortoise hare
```python
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        slow= head
        fast =head
        while fast is not None and fast.next is not None:
            slow=slow.next
            fast=fast.next.next
        return slow
```
# [206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)
- brute  (almost got it but small mistakes)
```python
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        curr= head
        prev=None
        while curr is not None:
            front= curr.next
            curr.next=prev
  
            prev=curr
            curr=front
        return prev
```
# [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
- my own (wrong- finds duplicates instead of cycle)
- brute
```python
class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        cycle= set()
        temp=head
        while temp is not None:
            if temp in cycle :
                return True
            cycle.add(temp)
            temp=temp.next
        return False
```
- floyd cycle detection (similar to totoise hare)
```python
class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        slow, fast= head, head
        while fast is not None and fast.next is not None:
            slow= slow.next
            fast=fast.next.next
            if slow==fast:
                return True
        return False
```
- the optimal ended up being less optimal? nah the memory got better
	![[Pasted image 20250823182455.png]]
	![[Pasted image 20250823182516.png]]
	![[Pasted image 20250823182529.png]]
# [142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)
- own - brute
```python
class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        temp= head
        cycle= set()
        while temp is not None:
            if temp in cycle:
                return temp
            cycle.add(temp)
            temp=temp.next
        return None
```
- optimal
```python
class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        slow, fast= head, head
        while fast is not None and fast.next is not None:
            slow= slow.next
            fast=fast.next.next
            if slow==fast:
                slow=head
                while slow!= fast:
                    slow=slow.next
                    fast=fast.next
                return slow
        return None
```
# [328. Odd Even Linked List](https://leetcode.com/problems/odd-even-linked-list/)
- brute - copy them in list and copy them back
- optimal 
```python
class Solution:
    def oddEvenList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head or not head.next:
            return head
        odd= head
        even= head.next
        even_head= even
        while even and even.next:
            odd.next= odd.next.next
            odd=odd.next
            even.next=even.next.next
            even=even.next
        odd.next=even_head
        return head
```
# [19. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
- brute
```python
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        temp= head
        length=0
        while temp:
            length+=1
            temp=temp.next
        k= length-n
        temp=head
        if length==n:
            return head.next
        while k-1:
            temp=temp.next
            k-=1
        temp.next=temp.next.next
        return head
```
- optimal  - guess how many times i fucked up ? TT
```python
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        i, j= head, head
        for _ in range(n):
            j= j.next
        if j==None:
            return head.next
        while j.next is not None :
            i=i.next
            j=j.next
  
        i.next=i.next.next
        return head
```