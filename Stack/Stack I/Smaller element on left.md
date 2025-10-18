```cpp
vector<int> Smallestonleft(int arr[], int n) {
    // code here
    vector<int>ans(n,-1);
    set<int>s;
    for(int i=0; i<n; i++){
        s.insert(arr[i]);
        auto it= s.find(arr[i]);
        if(it!=s.begin()){
            it--;
            ans[i]=*it;
        }
    }
    return ans;
}
```
