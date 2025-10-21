# Longest Substring Without Repeating Characters

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(k)

 

```cpp
  class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        unordered_set<int> set;
        int i = 0;
        int j = 0;
        int n = s.length();
        int maxlen = 0;
        while (j < n) {
            char ch = s[j];
            if (set.find(ch) != set.end()) {
                set.erase(s[i]);
                i++;

            } else {
                maxlen = max(maxlen, j - i + 1);
                set.insert(ch);
                j++;
            }
            
        }
        return maxlen;
    }
};
```
