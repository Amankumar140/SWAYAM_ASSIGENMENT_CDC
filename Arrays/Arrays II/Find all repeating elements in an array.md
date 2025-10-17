# Find all repeating elements in an array

**Programming Lang :** C++

**Time Complexity :** O(nlogn)  
**Space Complexitiy :** O(1)

```cpp
void findRepeatingElements(vector<int>& arr) {
    sort(arr.begin(),arr.end());
    
    cout<<"The repeating elements are: ";
    for(int i=0;i<arr.size()-1;i++) 
        if(arr[i] == arr[i+1]) cout<<arr[i]<<" ";
}
```
