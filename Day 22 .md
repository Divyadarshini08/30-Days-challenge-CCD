**MIN CHAR TO ADD FOR PALINDROME**

class Solution {
  public:
    int minChar(string& s) {
        // Write your code here
        string rev=s;
        reverse(rev.begin(),rev.end());
        
        string temp=s+"$"+rev;
        int n=temp.length();
        
        vector<int> lps(n,0);
        int len=0,i=1;
        while(i<n){
            if(temp[i]==temp[len])
            {
              len++;
              lps[i]=len;
              i++;
            }
            else{
                if(len!=0)
                len=lps[len-1];
                
                else
                {
                    lps[i]=0;
                    i++;
                }
            }
            
        }
        return s.length()-lps[n-1];
    }
};
