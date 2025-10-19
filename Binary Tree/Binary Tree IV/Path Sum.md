
# Path Sum

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(h)

```cpp
 
 class Solution {
public:
    bool solve(TreeNode* root, int targetSum, int sum) {
        if (!root)
            return false;
        sum += root->val;
        if (!root->left && !root->right) {
            return sum == targetSum;
        }
        return solve(root->left, targetSum, sum) ||
               solve(root->right, targetSum, sum);
    }
    bool hasPathSum(TreeNode* root, int targetSum) {
        return solve(root, targetSum, 0);
    }
};

```
