#  find element in an array

**Programming Lang:** C++

**Time Complexity :** O(n)  
**Space Complexity :** O(1)
```cpp

int findElement(int arr[], int n, int key)
{
    int i;
    for (i = 0; i < n; i++)
        if (arr[i] == key)
            return i;

    // If the key is not found
    return -1;
}
```
