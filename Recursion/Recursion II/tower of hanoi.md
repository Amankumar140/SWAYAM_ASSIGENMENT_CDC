#  Tower of Hanoi

**Programming Lang :** C++

**Time Complexity :** O()  
**Space Complexitiy :** O()


```cpp
class Solution {
  public:
    // You need to complete this function
    int count=0;
    void helper(int n, int from, int to, int aux ){
        if(n==0) return;
        if(n==1){
            count++;
            return;
        }
        helper(n-1, from, aux, to);
        count++;
        helper(n-1, aux,to,from);
    }
    int towerOfHanoi(int n, int from, int to, int aux) {
         // using formulareturn pow(2,n)-1;
         
         // using recursion
         helper(n,from,to,aux);
         return count;
        
    }
};
```
