# Power of Two

**Programming Lang :** C++

**Time Complexity :** O(1)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    bool isPowerOfTwo(int n) {
       if(n<0) return false;
        return ((n!=0) && (n&(n-1))==0); 
    }
};

```
