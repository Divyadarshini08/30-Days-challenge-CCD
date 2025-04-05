**Day 2 of 30-Days Challenge**

**Problem: Lucky Seven**

**LINK:** https://www.codechef.com/practice/course/basic-programming-concepts/DIFF500/problems/LUCKYSEVEN

**DESCIPTION**
Chef considers the number 7 lucky.
Given a string S of length 10, representing the first 10 letters Chef saw today, you need to find out Chef's lucky letter — which is the 7th letter of this string.

**INPUT FORMAT**
A single line containing the string S, of length 10.

**OUTPUT FORMAT**
Output a single character: the 7th letter of string S.

**APPROACH**
1. Start
2. Read input string S
3. Access the character at index 6 (which is the 7th character)
4. Print the character
5. End
   
**CODE**
```java
import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
	    Scanner sc=new Scanner(System.in);
	    String string=sc.next();
	    System.out.println(string.charAt(6));
	}
}
