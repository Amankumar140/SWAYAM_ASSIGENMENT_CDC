# Remove Duplicates from Sorted List

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
 class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode* ptr = head;
        if (!ptr) {
            return head;
        }
        while (ptr->next ) {
            if (ptr->val == ptr->next->val) {
                ptr->next = ptr->next->next;
            } else {
                ptr = ptr->next;
            }
        }
        return head;
    }
};
```
