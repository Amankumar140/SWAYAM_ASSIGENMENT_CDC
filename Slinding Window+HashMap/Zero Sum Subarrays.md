# Zero Sum Subarrays

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

 

```cpp
 class Solution {
  public:
    int findSubarray(vector<int> &arr) {
        // code here.
        int count=0;
        unordered_map<int, int> map;
        
        int prefixSum=0;
        map[0]=1;
        
        for(int i: arr){
            prefixSum+=i;
            if(map.find(prefixSum)!=map.end()){
                count+=map[prefixSum];
            }  
                map[prefixSum]++;
            
        }
        return count;
    }
};
```
