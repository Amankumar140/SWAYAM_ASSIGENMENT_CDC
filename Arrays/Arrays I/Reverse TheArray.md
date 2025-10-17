# Problem: Reverse The Array

[Link](https://www.naukri.com/code360/problems/reverse-the-array_1262298?leftPanelTabValue=PROBLEM)

**Program Language:** C++

**Time Complexity:** O(n - m)  
**Space Complexity:** O(1)

```cpp
 

void reverseArray(vector<int> &arr, int m) {
    int start = m + 1;          // start index after m
    int end = arr.size() - 1;   // last index

    while (start <= end) {
        swap(arr[start], arr[end]);
        start++;
        end--;
    }
}
