Day1 of 30 Days challenge CCD

**LINK** https://www.codechef.com/practice/course/logical-problems/DIFF800/problems/WGHTS

**PROBLEM**
Chef has an object weighing W units. He also has three different weights of X, Y, and Z units.
You need to determine whether Chef can measure exactly W units using one or more of the given weights.

**INPUT FORMAT**
The first line contains a single integer T — the number of test cases.
Each of the next T lines contains four positive integers: W, X, Y, Z.

**OUTPUT FORMAT**
For each test case, output YES if Chef can measure exactly W units using one or more of the weights (X, Y, Z). Otherwise, output NO.
Output is case-insensitive (e.g., YES, yes, YeS are all valid).

**APPROACH**
1. Read the number of test cases T.
2. Repeat T times:
   a. Read four integers: w, x, y, z.
   b. If any of the following is true:
    - x == w
    - y == w
    - z == w
    - x + y == w
    - x + z == w
    - y + z == w
    - x + y + z == w
    then print "YES"
   c. Else, print "NO"
 
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
            int w=sc.nextInt();
            int x=sc.nextInt();
            int y=sc.nextInt();
            int z=sc.nextInt();
            
            if((x==w) || (y==w) || (z==w) || (x+y==w) || (z+y==w) || (x+z==w) || (x+y+z==w))
            System.out.println("YES");
            else
            System.out.println("NO");
        }
	}
}
```
```java
