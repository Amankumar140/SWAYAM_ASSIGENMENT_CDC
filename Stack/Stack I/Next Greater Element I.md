# Next Greater Element I

**Programming Lang :** C++

**Time Complexity :** O(n+m)  
**Space Complexitiy :** O(n+m)

```cpp
   class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        unordered_map<int, int> m;
        stack<int> st;

        for (int i = nums2.size() - 1; i >= 0; i--) {
            while (!st.empty() && st.top() <= nums2[i])
                st.pop();
            if (st.empty())
                m[nums2[i]] = -1;
            else
                m[nums2[i]] = st.top();
            st.push(nums2[i]);
        }

        vector<int> nge(nums1.size());
        for (int i = 0; i < nums1.size(); i++) {
            nge[i] = m[nums1[i]];
        }
        return nge;
    }
};

```
