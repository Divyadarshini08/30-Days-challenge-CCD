**TODAY MARKS THE END OF 30 DAYS CHALLENGE.....I REALLY FEEL LITTLE PROUD OF MYSELF FOR BEING CONSISTENT, COMMITTED, AND SHOWING UP EVERY SINGLE DAYS. HUGE THANKS TO CCD FOR GIVING ME THIS OPPURTUNITY🚀🚀🚀**

**DAY 30** OF 30 DAYS CHALLENGE 🚀🚀🚀

**PROBLEM:** Merge Without Extra Space

**CODE:**
```cpp
class Solution {
  public:
    void mergeArrays(vector<int>& a, vector<int>& b) {
        // code here
        int n=a.size();
        for(int i=0;i<b.size();i++)
        a.push_back(b[i]);
        
        sort(a.begin(),a.end());
        int k=0;
        
        for(int i=n;i<a.size();i++)
        b[k++]=a[i];
        
        a.erase(a.end()-b.size(),a.end());
    }
};
