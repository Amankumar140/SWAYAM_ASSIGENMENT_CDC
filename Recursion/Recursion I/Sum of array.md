```cpp
// User function template for C++
class Solution {
  public:
     int Sum(vector<int>& arr, int i){
         if(i== arr.size()) return 0;
         int sum=arr[i];
         return sum+ Sum(arr, i+1);
         
     }
    int arraySum(vector<int>& arr) {
        // code here
        return Sum(arr,0);
        
    }
};
```
