Day 3 of 30 days challenge CCD

**PROBLEM**
A rotation on a string is defined as removing first element and concatenating it at the end.
Given N, and an array of N strings, print the minimum no. of cumulative rotations on the strings so as to make all the strings equal.
If this is not possible return -1

**INPUT**
The first line contains N, the number of strings
This is followed by N strings

**RULES**
2 <= N <= 104
3 <= string length <= 100
All characters are in uppercase

**EXAMPLE INPUT**
4
AABCD
CDAAB
DAABC
AABCD

**OUTPUT**
3

**APPROACH**
1. Read n strings.
2. For each string (except the first one):
      Concatenate it with itself to simulate rotation.
      Find the position where the first string appears.
      Add that position to the total count.
3. Print the total count.

**CODE**
```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n,count=0;
    cin>>n;
    vector<string> input;
    for(int i=0;i<n;i++)
    {
        string temp;
        cin>>temp;
        input.push_back(temp);
    }
    int size=input.size();
    for(int i=1;i<size;i++)
    {
        string new1=input[i]+input[i];
        size_t index = new1.find(input[0]);
        count=count+index;
    }
    cout<<count;
}
