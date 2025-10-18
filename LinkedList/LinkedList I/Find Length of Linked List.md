# Find Length of Linked List

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
/*
class Node {
  public:
    int data;
    Node *next;

    Node(int x) {
        data = x;
        next = NULL;
    }
};
*/

class Solution {
  public:
    int getCount(Node* head) {
         int count=0;
         while(head){
             count++;
             head=head->next;
             
         }
         return count;
        
    }
};
```
