Day 1 of 30 days challenge CCD

**PROBLEM**
Chef has recently moved into an apartment. It takes 30 minutes for Chef to reach the office.
Given that Chef left X minutes before he was supposed to reach, determine whether he will be able to reach on time.

**INPUT FORMAT**
The first line contains a single integer T — the number of test cases.
The next T lines each contain a single integer X — the number of minutes before the reporting time that Chef left.

**OUTPUT FORMAT**
For each test case, print "YES" if Chef reaches on time (i.e., X ≥ 30), otherwise print "NO".
Output is case-insensitive, but preferred output format is uppercase YES or NO.

**APPROACH**
1. Read the number of test cases T.
2. Repeat T times:
 a. Read x (minutes before arrival time Chef left).
 b. If x ≥ 30, print YES.
 c. Else, print NO.

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
		int TestCases=sc.nextInt();
		for(int i=0;i<TestCases;i++)
		{
		    int x=sc.nextInt();
		    if(x>=30)
		    System.out.println("YES");
		    else
		     System.out.println("NO");
		}
	}
}
