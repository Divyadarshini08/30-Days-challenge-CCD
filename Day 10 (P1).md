Day 10 of 30 Days challenge CCD

**PROBLEM:** Majority Element II

**DESCRIPTION:**
You are given an array of integer arr[] where each number represents a vote to a candidate. 
Return the candidates that have votes greater than one-third of the total votes, If there's not a majority vote, return an empty array. 

**INPUT & OUTPUT:**
Input: arr[] = [2, 1, 5, 5, 5, 5, 6, 6, 6, 6, 6]
Output: [5, 6]
Explanation: 5 and 6 occur more n/3 times.

**APPROACH:**
1. Initialize an empty frequency map and an empty result vector.
2. Iterate over the array and increment each element’s count in the map.
3. Compute the threshold as ⌊arr.size() / 3⌋.
4. Loop over the map entries to check each element’s frequency against the threshold.
5. If an element’s frequency exceeds the threshold, add it to the result vector.
6. Return the result vector containing all majority elements.

**CODE:**
```cpp
class Solution {
  public:
    // Function to find the majority elements in the array
    vector<int> findMajority(vector<int>& arr) {
        // Your code goes here.
        vector<int> result;
        map<int,int> mp;
        for(int i=0;i<arr.size();i++)
        mp[arr[i]]++;
        
        int n=arr.size()/3;
        for(auto it=mp.begin();it!=mp.end();it++)
        {
            if(it->second>n)
            result.push_back(it->first);
        }
        
        return result;
    }
};
