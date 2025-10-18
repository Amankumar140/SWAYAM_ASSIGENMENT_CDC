# Print 1 to n without using loops
 
**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)
 
```cpp
class Solution {
  public:
  
    void printTillN(int n) {
        if(n==0){
            return;
        }
        printTillN(n-1);
        cout<<n<<" ";
    }
};
```
