# First Bad Version

**Programming Lang :** C++

**Time Complexity :** O(log n)  
**Space Complexitiy :** O(1)

```cpp
// The API isBadVersion is defined for you.
// bool isBadVersion(int version);

class Solution {
public:
    int firstBadVersion(int n) {
        int st = 1;
        int end = n;
        int ans=0;
        while (st <= end) {
            int mid = st + (end - st) / 2;
            if (isBadVersion(mid)) {
                 
                end = mid-1;
            } else {
                st = mid + 1;
            }
        }
        return st;
    }
};

```
