
> [!NOTE] Use while loop instead of for
> cuz we don't know how many elements are present
## Creation of LL from Array ( using constuctor)
```cpp
LinkedList::LinkedList(int A[],int n){
    Node *t, *last;
    first= new Node;
    first->data=A[0];
    first->next=NULL;
    last=first;
  
    for(int i=1;i<n;i++){
        t=new Node;
        t->data=A[i];
        t->next=NULL;
        last->next=t;
        last=t;
    }
}
```
## Traversal
- take another pointer p (other than 'first /head pointer), and traverse using the addresses
```cpp
Node *p= first;           // p pointing to first node
while(p!=NULL){
	p=p->next;
}
```
## Display()
```cpp
Display(Node *p){
	while(p!=NULL){
		cout<< p->data;
		p=p->next;
	}
}
Display(first);
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```
## 
- t
```cpp
```