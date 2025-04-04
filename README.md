**Day 1** of 30-days challenge - CCD

Here's the question in two lines:

**PL Ticket**
Out of N students who want to attend an IPL match, only M tickets are available. How many students won’t be able to book tickets?

**Approach**

1. Read the number of test cases
2. Loop through each test case
3. Read number of students and available tickets
4. Calculate the difference (students - tickets)
5. If the difference is positive, print it
6. Else, print 0 (all students get tickets)

**Solution (JAVA)**

import java.util.*;
import java.lang.*;
import java.io.*;

class Codechef
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
        Scanner sc=new Scanner(System.in);
        int TestCases=sc.nextInt();
        for(int i=0;i<TestCases;i++)
        {
            int No_of_students=sc.nextInt();
            int No_of_avail_tickets=sc.nextInt();
            int diff=No_of_students- No_of_avail_tickets;
            if(diff>0)
            System.out.println(diff);
            else
            System.out.println("0");
        }
	}
}








