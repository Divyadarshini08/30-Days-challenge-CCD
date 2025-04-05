**Day 2 of 30-Days Challenge**

**Problem Summary: Cricket World Cup Qualifier**

**LINK:** https://www.codechef.com/practice/course/basic-programming-concepts/DIFF500/problems/CWC23QUALIF

**DESCIPTION**
In the Chefland Cricket World Cup, a team qualifies for the next stage if it scores 12 or more points in the group stage matches.
You are given the total points scored by a particular team. Determine if the team has qualified for the next stage.

**INPUT FORMAT**
Single integer X — the total points scored by the team.

**OUTPUT FORMAT**
Output "Yes" if the team has qualified.
Output "No" otherwise.

**APPROACH**
1. Start
2. Input integer X (team's points)
3. If X ≥ 12, then:
    → Print "Yes"
   Else:
    → Print "No"
4. End

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
		int input=sc.nextInt();
		if(input>=12)
		System.out.println("Yes");
		else
		System.out.println("No");
	}
}
