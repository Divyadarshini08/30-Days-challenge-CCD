Day 21 of 30 Days Challenge

**PROBLEM:** Non Repeating Character

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/non-repeating-character-1587115620

**DESCRIPTION:** 
Given a string s consisting of lowercase English Letters. Return the first non-repeating character in s.
If there is no non-repeating character, return '$'.
Note: When you return '$' driver code will output -1.

**INPUT & OUTPUT:**
Input: s = "geeksforgeeks"
Output: 'f'
Explanation: In the given string, 'f' is the first character in the string which does not repeat.

**APPROACH:**
1. Create a hashmap to count the frequency of each character in the string.  
2. Traverse the string and update character counts in the hashmap.  
3. Traverse the string again.  
4. Return the first character with a count of 1 from the hashmap.  
5. If no such character is found, return '$'.

**CODE:**
```cpp
class Solution {
  public:
    char nonRepeatingChar(string &s) {
        // Your code here
        unordered_map<char,int> mp;
        for(int i=0;i<s.size();i++)
        mp[s[i]]++;
        
        for(int i=0;i<s.size();i++)
        {
            if(mp[s[i]]==1)
            return s[i];
        }
        return '$';
    }
};
