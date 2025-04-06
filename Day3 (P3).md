Day 3 of 30 days challenge CCD

**PROBLEM**
Rotate a given String in the specified direction by specified magnitude.
After each rotation make a note of the first character of the rotated String, After all rotation are performed the accumulated first character as noted previously will form another string, say FIRSTCHARSTRING.
Check If FIRSTCHARSTRING is an Anagram of any substring of the Original string.
If yes print YES otherwise NO.

**INPUT**
The first line contains the original string s.
The second line contains a single integer q.
The ith line of the next q lines contains character d[i] denoting direction and integer r[i] denoting the magnitude.

**RULES**
1 <= Length of original string <= 30.
1<= q <= 10.

**EXAMPLE INPUT**
carrace
3
L 2
R 2
L 3

**OUTPUT**
NO

**APPROACH**
1. Count original characters — Make a frequency map of the original string.
2. Do n rotations:
    Rotate left or right as told.
    After rotation, note the first character.
    Collect first characters from each rotation into a string.
3. Compare:
    For every character in this collected string, reduce the count from the original map.
    If, after this, the map is empty, print YES (all characters matched).
    Else, print NO.

**CODE**
```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
    string input,firstcharstring="";
    cin>>input;
    map<char,int> mp;
    int n;
    cin>>n;
    int size=input.size();
    for(int i=0;i<size;i++)
    mp[input[i]]++;
    for(int i=0;i<n;i++)
    {
        char magnitude;
        int No;
        cin>>magnitude>>No;
        if(magnitude=='L')
        {
            while(No!=0)
            {
                char store=input[0]; 
                for(int i=1;i<size;i++)
                {
                    input[i-1]=input[i];
                }
                input[size-1]=store;
                No--;
            }
            firstcharstring=firstcharstring+input[0];
        }
        else if(magnitude=='R')
        {
            while(No!=0)
            {
                char store=input[size-1];  
                for(int i=size-1;i>=0;i--) 
                {
                    input[i+1]=input[i];
                }
                input[0]=store;
                No--; 
            }
            firstcharstring=firstcharstring+input[0];
        }
    }
    int newsize=firstcharstring.size();
    for(int i=0;i<newsize;i++)
    {
        mp[firstcharstring[i]]--;
        if(mp[firstcharstring[i]]==0)
        mp.erase(firstcharstring[i]);
    }
    if(mp.size()==0)
    cout<<"YES";
    else
    cout<<"NO";
}
