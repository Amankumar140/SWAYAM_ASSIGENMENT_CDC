# Min Stack

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
class MinStack {
public:
    vector<int>arr;
    int Top=-1;
    MinStack() {
        
    }
    
    void push(int val) {
        if(Top==INT_MAX) return;
        arr.push_back(val);
        Top++;
    }
    
    void pop() {
        if(Top==-1) return;
        arr.pop_back();
        Top--;
    }
    
    int top() {
        return arr[Top];
    }
    
    int getMin() {
         return *min_element(arr.begin(), arr.end()); 
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(val);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->getMin();
 */
```
