```
  void reverseArray(vector<int> &arr , int m) {
    int e=arr.size()-1;
    m++;
     while(m<=e){
         swap(arr[m++], arr[e--]);
     }       	
}
```
