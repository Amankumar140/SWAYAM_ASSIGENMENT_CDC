#  Count Digits

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
class Solution {
  public:
     
    int countDivisibleDigits(int n, int original) {
     
    if (n == 0) return 0;

    int tmp = n % 10;            
    int count = 0;

     
    if (tmp != 0 && original % tmp == 0)
        count = 1;

    return count + countDivisibleDigits(n / 10, original);
    } 
    
    int evenlyDivides(int n) {
         return countDivisibleDigits(n, n);
        
    }
};
```
