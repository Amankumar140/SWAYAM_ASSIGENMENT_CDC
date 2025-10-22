# Check K-th Bit

**Programming Lang :** C++

**Time Complexity :** O(1)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
  public:
    bool checkKthBit(int n, int k) {
        //  code here
        return ((n>>k) & 1)==1;
    }
};

```
