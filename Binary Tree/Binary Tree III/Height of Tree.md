# Height of Tree

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(h)

```cpp
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if (root == NULL)
            return 0;
        int leftH = maxDepth(root->left) + 1;
        int rightH = maxDepth(root->right) + 1;
        return max(leftH, rightH);
    }
};
```
