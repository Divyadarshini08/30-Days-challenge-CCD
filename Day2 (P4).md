**Day 2 of 30-Days Challenge**

**Problem: Double Rent**

**LINK:** https://www.codechef.com/practice/course/basic-programming-concepts/DIFF500/problems/DOUBLERENT

**DESCIPTION**
Chef was paying X rupees as rent.
Since Chefina is moving in, the owner doubles the rent.
You need to calculate and print the final rent.

**INPUT FORMAT**
Single integer X — the initial rent.

**OUTPUT FORMAT**
Print the final rent (which is double of X).

**APPROACH**
1. Start
2. Input the initial rent amount X
3. Multiply X by 2 to get the final rent
4. Print the final rent
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
        int X=sc.nextInt();
        System.out.println(2*X);
	}
}
