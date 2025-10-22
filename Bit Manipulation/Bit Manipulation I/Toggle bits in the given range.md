# Toggle bits in the given range

**Programming Lang :** C++

**Time Complexity :** O(l)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
  public:
    int toggleBits(int n, int l, int r) {
        // code here
        int mask = 1; 
        mask <<= r; 
        mask = mask - 1; 
        l--; 
        while(l--) mask = mask & (mask - 1) ;
        return n ^ mask; 
    }
};

```
