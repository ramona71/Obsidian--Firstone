- if you don't know how many elements to store during runtime, we can't use array 
- never created in stack, always in heap
- memory is created in heap during runtime 
- more flexible than array(size is adjustable)
- can easily remove or insert elements into it
## Node
- linked list- collection of nodes, with data and pointed to next node
- head- pointer pointing to first node or head node
- Address no need to be contiguous
- Continuity is maintained by links
- Node:
	- data - can be any type int, float, char etc
	- pointer- is of node type (pointer of it's own type)
```cpp
struct Node{             // self referential structures
int data;
struct Node *next;
};

class Node{
    public:
        int data;         // if int takes 2 bytes
        Node *next;       // pointer takes the same
}*first;                  // Total: 4 bytes
// first is global pointer
```
- create a node
```cpp
Node *p;
p=new Node;
p->data=10;
p->next=0
```
![[Pasted image 20241018170505.png]]
- p and q pointing on the same node
```cpp
Node *p,*q;
q=p;
```
![[Pasted image 20241018171916.png]]
 - q pointing next node of p
```cpp
q=p->next;
```
![[Pasted image 20241018172009.png]]
- p pointing on next of p
```cpp
p=p->next
```
![[Pasted image 20241018172040.png]]
- p pointing nowhere(NULL)
```cpp
Node *p=NULL;
// conditions for p pointing to null
if(p==NULL)
if(p==0)
if(!p)              // all these become true if p is NULL
```
![[Pasted image 20241018172245.png]]
- if p is pointing to some node
```cpp
if(p!=Null)
if(p!=0)
if(p)               // = true if p is pointing to some node
```
![[Pasted image 20241018172441.png]]
- if p is last node
```cpp
if(p->next==NULL)
//if it's not last node
if(p->next!=NULL)
```