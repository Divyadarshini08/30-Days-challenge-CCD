**Day 2 of 30-Days Challenge**

**Problem : Greater Average**

**LINK:** https://www.codechef.com/practice/course/logical-problems/DIFF800/problems/AVGPROBLEM

**DESCIPTION**
In the Chefland Cricket World Cup, a team qualifies for the next stage if it scores 12 or more points in the group stage matches.
You are given the total points scored by a particular team. Determine if the team has qualified for the next stage.

**INPUT FORMAT**
The first line contains a single integer T, the number of test cases.
Each test case consists of three integers: A, B, C.

**OUTPUT FORMAT**
For each test case, output:
  YES if average of A and B is strictly greater than C.
  NO otherwise.

**APPROACH**
1. Start
2. Input: Read integer T (number of test cases).
3. Repeat the following steps T times:
4. Read integers A, B, C.
5. Calculate average: (A + B) / 2.0.
6. If average > C, print "YES".
   Else, print "NO".
7. End

**CODE**
```java
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		Scanner sc=new Scanner(System.in);
		int TestCases=sc.nextInt();
		while(TestCases>0)
		{
		    int A=sc.nextInt();
    		int B=sc.nextInt();
    		int C=sc.nextInt();
    		
    		float avg=(A+B)/2.0f;
    		if(avg>C)
    		System.out.println("YES");
    		else
    		System.out.println("NO");
    		TestCases--;
		}
	}
}
