# Top K Frequent Elements

**Programming Lang :** C++

**Time Complexity :** O(n log k)  
**Space Complexitiy :** O(n)
 
```cpp
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        unordered_map<int, int> m;
        for (int num : nums)
            m[num]++;

        priority_queue<pair<int, int>, vector<pair<int, int>>,
                       greater<pair<int, int>>>
            pq;

        for (auto [num, freq] : m) {
            pq.push({freq, num});
            if (pq.size() > k)
                pq.pop();
        }

        vector<int> ans;
        while (!pq.empty()) {
            ans.push_back(pq.top().second);
            pq.pop();
        }
        return ans;
    }
};
```
