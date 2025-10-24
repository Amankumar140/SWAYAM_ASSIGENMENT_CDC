# Minimum Platforms

**Programming Lang :** C++

**Time Complexity :** O(n long n )  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int findPlatform(vector<int>& arr, vector<int>& dep) {
        sort(arr.begin(), arr.end());
        sort(dep.begin(), dep.end());
        
        int n = arr.size();
        int i = 0, j = 0; 
        int platforms = 0, max_platforms = 0;
        
        while(i < n && j < n){
            if(arr[i] <= dep[j]){
                platforms++;
                max_platforms = max(max_platforms, platforms);
                i++;
            } else {
                platforms--;
                j++;
            }
        }
        return max_platforms;
    }
};
 
```
