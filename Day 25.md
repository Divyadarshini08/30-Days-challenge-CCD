**PROBLEM:** Find H-Index.

**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/find-h-index--165609.

**DESCRIPTION:** 
Given an integer array citations[], where citations[i] is the number of citations a researcher received for the ith paper. 
The task is to find the H-index.
H-Index is the largest value such that the researcher has at least H papers that have been cited at least H times.

**SAMPLE INPUT & OUTPTUT:**
Input: citations[] = [3, 0, 5, 3, 0]
Output: 3
Explanation: There are at least 3 papers (3, 5, 3) with at least 3 citations.

**CODE:**
```cpp

class Solution {
  public:
    // Function to find hIndex
    int hIndex(vector<int>& citations) {
        // code here
        int count=0;
        sort(citations.rbegin(),citations.rend());
        for(int i=0;i<citations.size();i++)
        {
            if(citations[i]>=i+1)
            count++;
        }
        return count;
    }
};

