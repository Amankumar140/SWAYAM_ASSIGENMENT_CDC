#  Bulls and Cows

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(10)

 

```cpp
   class Solution {
public:
    string getHint(string secret, string guess) {
        vector<int> countS(10, 0), countG(10, 0);
        int A = 0;
        int B = 0;
        for (int i = 0; i < secret.size(); i++) {
            if (secret[i] == guess[i])
                A++;
            else {
                countS[secret[i] - '0']++;
                countG[guess[i] - '0']++;
            }
        }
        for (int d = 0; d < 10; d++) {
            B += min(countS[d], countG[d]);
        }
        string res = to_string(A) + "A" + to_string(B) + "B";
        return res;
    }
};
```
