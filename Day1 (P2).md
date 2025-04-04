Day 1 of 30 days challenge CCD

**PROBLEM**

**Audible Range**
Chef's dog Binary hears frequencies starting from 67 Hertz to 45000 Hertz (both inclusive).
If Chef's commands have a frequency of X Hertz, determine whether Binary can hear them or not.

**Input Format**
The first line of input contains a single integer T — the number of test cases.
Each test case consists of a single integer X — the frequency of Chef's command in Hertz.

**Output Format**
For each test case, print "YES" if Binary can hear Chef's command. Otherwise, print "NO".
The output is case-insensitive, so "YES", "yes", "YeS", etc., are all valid. However, you should print "YES" or "NO" in uppercase for consistency.

**APPROACH**
1. Read the number of test cases T.
2. For each test case:
 a. Read frequency X.
 b. If 67 ≤ X ≤ 45000, print "YES".
 c. Else, print "NO".

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
		    int Frequency=sc.nextInt();
		    if(Frequency>=67 && Frequency<=45000)
		    System.out.println("YES");
		    else
		    System.out.println("NO");
		}
	}
}



