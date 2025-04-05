**Day 2 of 30-Days Challenge**

**Problem: Saving Taxes**

**LINK:** https://www.codechef.com/practice/course/basic-programming-concepts/DIFF500/problems/TAXSAVING

**DESCIPTION**
In Chefland, if you earn more than Y rupees per year, you have to pay tax.
But Chef allows you to invest money to reduce taxable income.
You earn X rupees this year (X > Y).
Find the minimum amount to invest so that you don’t have to pay any taxes.

**INPUT FORMAT**
The first line contains an integer T — number of test cases.
Each test case consists of two space-separated integers:
  X — your earnings
  Y — the tax-free limit

**OUTPUT FORMAT**
For each test case, print a single integer: the minimum amount you need to invest.

**APPROACH**
1. Start
2. Input integer T (number of test cases)
3. For each test case, repeat:
4. Input integers X (earnings) and Y (tax limit)
5. Calculate investment = X - Y
6. Print the investment
7. End

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
	        int x = sc.nextInt();
	        int y = sc.nextInt();
	        System.out.println(x-y);
	    }
	}
}
