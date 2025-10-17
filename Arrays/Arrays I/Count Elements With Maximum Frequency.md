# Count Elements With Maximum Frequency

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(k) (storing frequencies)

```cpp

class Solution {
public:
    int maxFrequencyElements(vector<int>& nums) {
        unordered_map<int,int> freq;

        // Count frequency of each element
        for (int num : nums) {
            freq[num]++;
        }

        // Find the maximum frequency
        int maxFreq = 0;
        for (auto &p : freq) {
            maxFreq = max(maxFreq, p.second);
        }

        // Count total elements that have maximum frequency
        int count = 0;
        for (int num : nums) {
            if (freq[num] == maxFreq) {
                count++;
            }
        }

        return count;
    }
};
```
