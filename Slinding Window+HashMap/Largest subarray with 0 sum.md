# Largest subarray with 0 sum

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

 

```cpp
 class Solution {
  public:
    int maxLength(vector<int>& arr) {
        // code here
         unordered_map<int,int> map;
         map[0]=-1;
         int prefix=0;
         int ans=0;
         
         for(int i=0; i<arr.size(); i++){
             prefix+=arr[i];
             if(map.count(prefix)){
                 ans=max(ans, i- map[prefix]);
             } else {
                 map[prefix]=i;
             }
         }
        return ans;
    }
};
```
