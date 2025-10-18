# Power Of Numbers.md

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
class Solution {
  public:
    int reverse(int n){
        int rev=0;
        while(n>0) {
            int r= n%10;
            rev= rev*10+r;
            n/=10;
        }
        return rev;
        
    }
    int power(int n, int p){
        if(p==1){
            return n;
        }
        return n* power(n, p-1);
    }
    int reverseExponentiation(int n) {
        int rev=reverse(n);
        return power(n,rev);
        
    }
};
```
