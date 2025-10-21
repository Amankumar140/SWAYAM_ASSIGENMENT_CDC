# Find All Anagrams in a String

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

 

```cpp
 
class Solution {
public:
    vector<int> findAnagrams(string s, string p) {
        if (p.size() > s.size()) return {};

        vector<int> res;
        vector<int> pCount(26, 0), sCount(26, 0);

        // Count frequency of first window (size of p)
        for (int i = 0; i < p.size(); i++) {
            pCount[p[i] - 'a']++;
            sCount[s[i] - 'a']++;
        }

        if (pCount == sCount)
            res.push_back(0);

        // Sliding window
        for (int i = p.size(); i < s.size(); i++) {
            sCount[s[i] - 'a']++;                 // add right char
            sCount[s[i - p.size()] - 'a']--;      // remove left char

            if (pCount == sCount)
                res.push_back(i - p.size() + 1);
        }

        return res;
    }
};


```
