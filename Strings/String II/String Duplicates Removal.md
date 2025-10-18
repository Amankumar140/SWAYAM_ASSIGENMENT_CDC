# String Duplicates Removal

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(k)

```cpp
 
class Solution {
  public:
    string removeDuplicates(string &s) {
         
         vector<int> freq(256,0);
         string ans="";
         for(int i=0; i<s.length(); i++){
             char c=s[i];
             if(freq[c]==0){
                 ans.push_back(c);
             }
             freq[c]++;
         }
         return ans;
        
    }
};
```
