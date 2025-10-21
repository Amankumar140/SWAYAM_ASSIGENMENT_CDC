```cpp
 

class Solution {
  public:
    int CountNodes(Node* root){
        if(!root) return 0;
        return 1+CountNodes(root->left)+ CountNodes(root->right);
    }
    
    bool isComplete(Node* root, int index, int totalNodes){
        if(!root) return true;
        if(index>= totalNodes) return false;
        return isComplete(root->left, 2*index+1, totalNodes) && 
        isComplete(root->right, 2*index+2, totalNodes);
        
    }
    
    bool isHeapProperty(Node* root){
        // leaf node
        if(!root->left && !root->right) return true;
        
        // left 
        if(root->left && !root->right){
            return (root->data>= root->left->data) && isHeapProperty(root->left);
        }
        
         if (root->left && root->right)
            return (root->data >= root->left->data &&
                    root->data >= root->right->data &&
                    isHeapProperty(root->left) &&
                    isHeapProperty(root->right));
        return true;
    }
    
    bool isHeap(Node*  root) {
        // code here
        int totalNodes = CountNodes(root);
        return isComplete(root, 0, totalNodes) && isHeapProperty(root);
    }
};
```
