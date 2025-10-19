
# Binary Tree Right Side view

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(h)

```cpp
 
class Solution {
public:
    void helper(TreeNode* root, int level, int& maxlevel, vector<int>& ans) {
        if (!root)
            return;
        if (level > maxlevel) {
            ans.push_back(root->val);
            maxlevel = level;   
        }
        helper(root->right, level + 1, maxlevel, ans);
        helper(root->left, level + 1, maxlevel, ans);
        
    }
    vector<int> rightSideView(TreeNode* root) {
        vector<int> ans;
        int maxlevel = 0;
        helper(root, 1, maxlevel, ans);
        return ans;
    }
};

```
