# Trapping Rain Water  

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int trap(vector<int>& height) {
        int n=height.size();
        int total=0;
            int lMax=0;
            int rMax=0;
            int l=0;
            int r=n-1;

        while(l<r){
            if(height[l]<=height[r]){
                if(lMax>height[l]) total+=lMax-height[l];
                else lMax= height[l];
                l++;
            }
            else{
                if(rMax>height[r]) total+=rMax-height[r];
                else rMax=height[r];
                r--;
            }
        }

        return total;

    }
};
```
