# Fibbonacci Number

**Programming Lang :** C++

**Time Complexity :** O(2^n)  
**Space Complexitiy :** O(n)
 
```cpp
// User function Template for C++
class Solution {
  public:
  
    int nthFibonacci(int n) {
        if(n==0 || n==1) return n;
        
        return nthFibonacci(n-1)+nthFibonacci(n-2);
    }
};
```
