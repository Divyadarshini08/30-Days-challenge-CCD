**Day 2 of 30-Days Challenge**

**Problem: Clear Day**

**LINK:** https://www.codechef.com/practice/course/basic-programming-concepts/DIFF500/problems/CLEARDAY

**DESCIPTION**
Chef classifies days as either:
  Rainy
  Cloudy
  Clear

In a week (7 days total):
  X days are rainy
  Y days are cloudy
  You need to find the number of clear days in the week.

**INPUT FORMAT**
A single line containing two space-separated integers: X (rainy days) and Y (cloudy days).

**OUTPUT FORMAT**
Output a single integer: the number of clear days in the week.

**APPROACH**
1. Start
2. Take input integer x → number of rainy days
3. Take input integer y → number of cloudy days
4. Calculate clear days as 7 - (x + y)
5. Print the result
6. End

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
		int x=sc.nextInt();
        int y=sc.nextInt();
        System.out.println(7-(x+y));
	}
}
