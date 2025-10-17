# Problem :-  Reverse The Array
[Link] (https://www.naukri.com/code360/problems/reverse-the-array_1262298?leftPanelTabValue=PROBLEM)
TC= o(n-m)  SC=O(1)

Program  lang :- c++
```
  void reverseArray(vector<int> &arr , int m) {
    int e=arr.size()-1;
    m++;
     while(m<=e){
         swap(arr[m++], arr[e--]);
     }       	
}
```
