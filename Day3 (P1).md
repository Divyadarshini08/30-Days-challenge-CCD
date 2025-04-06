Day 3 of 30 days challenge CCD

**PROBLEM**
In this special Swayamvar:
There are N brides and N grooms.
Each person either drinks rum (r) or mojito (m).
Brides and grooms stand in queues, where:
Brides are queued by eligibility (most eligible first).
Grooms are queued by eligibility (most eligible first).

**RULES**
The first bride in line will only marry a groom who drinks the same drink.
If the current groom at the front is not a match, he moves to the back of the queue.
If the bride doesn’t find a suitable groom after checking the entire queue, the Swayamvar ends.

**OBJECTIVE**
 Find out how many brides (or grooms) are left unmatched at the end.

**APPROACH**
1. Input:
    Read integer N → total number of brides/grooms.
    Read string bride → drink choices of brides.
    Read string groom → drink choices of grooms.
2. Initialize:
    Create a map mp to store count of drink types among grooms.
    Iterate over groom string and count 'r' and 'm' in mp.
3. Set pointers:
    i = 0 → pointer for brides.
    j = 0 → pointer for grooms.
    cnt = 0 → flag to check if process was forcefully terminated.
4. Process brides one by one:
    While i < bride.length():
      If bride[i] == groom[j]:
          Match found!
          Decrease count in map mp[bride[i]].
          Move to next bride i++ and next groom j++.
     Else (bride and groom mismatch):
          If mp[bride[i]] == 0:
              No grooms left with this drink choice.
              Print bride.length() - i → remaining unmatched brides.
              Set cnt = 1 to mark termination.
              Exit loop.
          Else:
              Move groom to end of queue:
                  Store groom[j] in a temporary char c.
                  Shift groom queue left by 1 (from j to end).
                  Put c at the end of the queue.
5. After loop ends:
    If cnt == 0 (all brides matched):
    Print cnt → means 0 unmatched brides.

**CODE**
```c++
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int input;
    cin>>input;
    string bride,groom;
    cin>>bride;
    cin>>groom;
    map<char,int> mp;
    int sizeg=groom.size(),sizeb=bride.size();
    for(int i=0;i<sizeg;i++)
    mp[groom[i]]++;
    int i=0,j=0,cnt=0;
    while(i<sizeb)
    {
        if(bride[i]==groom[j])
        {
            mp[bride[i]]--;
            i++;
            j++;
        }
        else{
            if(mp[bride[i]]==0)
            {
                cout<<sizeb-i;
                i=bride.size();
                cnt=1;
            }
            else
            {
                char c=groom[j];
                for(int m=j;m<sizeg-1;m++)
                {
                    groom[m]=groom[m+1];
                }
                groom[groom.size()-1]=c;
            }
        }
    }
    if(cnt==0)
    cout<<cnt; 
}
