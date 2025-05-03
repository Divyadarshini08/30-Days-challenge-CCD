**PROBLEM: NON OVERLAPPING INTERVALS**

**CODE:**
```cpp
class Solution {
    static bool compare (vector<int> &a, vector<int> &b){
        return a[1]<b[1];
    }
  public:
    int minRemoval(vector<vector<int>> &intervals) {
        // code here
        if(intervals.size()==0)
        return 0;
        
        sort(intervals.begin(),intervals.end(),compare);
        
        int count=0;
        int prev_end=intervals[0][1];
        for(int i=1;i<intervals.size();i++)
        {
            if(intervals[i][0]<prev_end)
            count++;
            else
            prev_end=intervals[i][1];
        }
        return count;
    }
};
