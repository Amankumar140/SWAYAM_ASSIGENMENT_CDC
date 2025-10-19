# Aggressive Cows   

**Programming Lang :** C++

**Time Complexity :** O(n log n)  
**Space Complexitiy :** O(1)

```cpp
  class Solution {
  public:
    bool canWePlace(vector<int> &stalls, int dist, int k){
        int cntCows=1, lastIdx=stalls[0];
        for(int i=0; i<stalls.size(); i++){
            if(stalls[i]-lastIdx>=dist){
               cntCows++; 
               lastIdx=stalls[i];
            }
        }
        if(k<=cntCows) return true;
        return false;
    }
    int aggressiveCows(vector<int> &stalls, int k) {
        // code here
        sort(stalls.begin(), stalls.end());
        int low=1; int high=stalls[stalls.size()-1]-stalls[0];
        while(low<=high){
            int mid=low +(high-low)/2;
            if(canWePlace(stalls, mid, k)){
                //ans=mid;
                 low=mid+1;
            }else{
                high=mid-1;
            }
        }
        return high;
    }
};

```
