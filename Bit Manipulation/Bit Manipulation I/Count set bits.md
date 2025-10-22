# Count set bits

**Programming Lang :** C++

**Time Complexity :** O((logn)^2)  
**Space Complexitiy :** O(log n)

```cpp
class Solution {
  public:
    int countSetBits(int n) {
        // code here
        if(n==0) return 0;
         long long x= larPowOf2(n);
        long long y=x* (1<< (x-1));
        long long z= n- (1<<x);
        return y+z+1+countSetBits(z);
        
    }
    long long larPowOf2(long long n){
        long long x=0;
        while((1<<x)<=n) x++;
        return x-1;
    }
};

```
