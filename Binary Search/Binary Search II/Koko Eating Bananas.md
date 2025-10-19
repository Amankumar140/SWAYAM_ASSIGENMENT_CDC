# Koko Eating Bananas

**Programming Lang :** C++

**Time Complexity :** O(log n)  
**Space Complexitiy :** O(1)

```cpp
 class Solution {
public:
    long long possible(int mid, vector<int>& piles) {
        long long hr = 0;
        for (int i = 0; i < piles.size(); i++) {
            hr += (piles[i] + mid - 1LL) / mid;
        }
        return hr;
    }
    int minEatingSpeed(vector<int>& piles, int h) {
        int low = 1;
        int high = *max_element(piles.begin(), piles.end());
        while (low <= high) {
            int mid = low + ( high - low) / 2;
            long long x = possible(mid, piles);
            if (x <= h) {
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }
        return low;
    }
};

```
