```cpp
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
        if (nums.empty())
            return 0;

        unordered_set<int> s(nums.begin(), nums.end());
        int longest = 0;

        for (int num : s) {
            // check if it's the start of a sequence
            if (s.find(num - 1) == s.end()) {
                int curr = num;
                int length = 1;

                // expand the sequence
                while (s.find(curr + 1) != s.end()) {
                    curr++;
                    length++;
                }

                longest = max(longest, length);
            }
        }

        return longest;
    }
};
```
