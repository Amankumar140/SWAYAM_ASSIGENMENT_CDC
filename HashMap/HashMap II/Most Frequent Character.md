# Most Frequent Character

**Programming Lang:** C++  

**Time Complexity :**  O(n)  
**Space Complexity :** O(256)

```cpp
class Solution {
public:
    char getMaxOccuringChar(string& s) {
        vector<int> freq(256, 0); // to handle all ASCII characters
        for (char c : s) {
            freq[c]++;
        }

        int maxFreq = 0;
        char result = 'a'; // default
        for (int i = 0; i < 256; i++) {
            if (freq[i] > maxFreq) {
                maxFreq = freq[i];
                result = char(i);
            } 
            // In case of tie, choose lexicographically smaller
            else if (freq[i] == maxFreq && char(i) < result) {
                result = char(i);
            }
        }
        return result;
    }
};

```
