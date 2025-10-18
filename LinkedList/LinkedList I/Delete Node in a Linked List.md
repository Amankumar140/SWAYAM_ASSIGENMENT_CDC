# Delete Node in a Linked List

**Programming Lang :** C++

**Time Complexity :** O(1)  
**Space Complexitiy :** O(1)

```cpp
void deleteNode(ListNode* node) {
        node->val=node->next->val;
        node->next=node->next->next;
    }
```
