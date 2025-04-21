Day 18 of 30 Days Challenge CCD

**PROBLEM:** Implement Atoi
**LINK:** https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/implement-atoi

**DESCRIPTION:** 
Given a string s, the objective is to convert it into integer format without utilizing any built-in functions. Refer the below steps to know about atoi() function.

**Cases for atoi() conversion:**
Skip any leading whitespaces.
Check for a sign (‘+’ or ‘-‘), default to positive if no sign is present.
Read the integer by ignoring leading zeros until a non-digit character is encountered or end of the string is reached. If no digits are present, return 0.
If the integer is greater than 231 – 1, then return 231 – 1 and if the integer is smaller than -231, then return -231.

**INPUT & OUTPUT:**
Input: s = "-123"
Output: -123
Explanation: It is possible to convert -123 into an integer so we returned in the form of an integer

**APPROACH:**
1. Trim Whitespace: The algorithm first skips any leading spaces in the string.
2. Handle Sign: It then checks if the next character is a '-' or a '+', indicating the sign of the number.
3. Extract Digits: After the sign, it reads the characters one by one. If a character is a digit, it adds the digit to the result. If a non-digit is encountered, the process stops.
4. Overflow Check: Before adding a new digit to the result, it checks if doing so would overflow the integer bounds. If an overflow is detected, it returns INT_MAX or INT_MIN depending on the sign.
5. Return Result: Finally, it multiplies the result by the sign and returns the final number.

**CODE:**
```cpp
class Solution {
  public:
    int myAtoi(char *s) {
        // Your code here
        int i=0,sign=1,ans=0;
        while(i<strlen(s) && s[i]==' ')
        i++;
        
        if(s[i]=='-') {sign=-1;i++;}
        
        for(int j=i;j<strlen(s);j++)
        {
            if(!isdigit(s[j])) break;
            
            int digit=s[j]-'0';
            if(ans>(INT_MAX -digit)/10)
              return (sign==1)?INT_MAX:INT_MIN;
            
            
            ans=ans*10+digit;
        }
        return ans*sign;
    }
};
