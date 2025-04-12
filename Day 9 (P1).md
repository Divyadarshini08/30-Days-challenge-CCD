Day 9 of 30 Days challenge CCD

**PROBLEM:** CLOCK ANGLE

**DESCRIPTION:** 
There are 360 Longitudes on the Earth, which are equidistant vertical imaginary lines drawn on the Earth, separated by 1 degree each from center of the Earth. 
Period of the rotation of the Earth on its axis is 24 hours. All countries have their own official times and hence time zones.
UTC is universal time coordinate which passes through 0 (Zero degree) longitude.
Time at a particular location on Earth can be calculated using period of the rotation of Earth and longitude of that particular location. 
For example, Indian time zone IST (Indian standard Time) is located at 82.5° E longitude. Hence, Indian time can be calculated as below:
IST = UTC + (24/360)*82.5 = UTC + 5:30Hrs
Now suppose we changed period of rotation of the earth using some imaginary power, this will change the time at every longitude on the earth.
Calculate the smallest angle between hour and minute hand of the clock, which shows the difference of time at a particular longitude and the time at UTC i.e. we have to take smaller of the two angle formed between hour and minute hand.

**Constraints:**
To show the time difference on clock, 12-hour clock shall be used, irrespective of period of the earth's rotation, for this question only.

**INPUT FORMAT:**
1. Period of the earth’s rotation in Hours (Integer only)
2. Value of Longitude up to 2 place of decimal

**Output:**
Smallest angle between hour and minute hand of the clock, which shows the difference between time at a particular longitude and time at UTC, up to 2 decimal places.

**Example Test Case #1**
24
82.50
**Output**
15.00

**APPROACH:**
1. Input n and a.
2. Compute res = (n / 360) * a * 60.
3. Extract:
    min = int(res) % 60
    hour = int(res) / 60
4. Calculate angle:
    angle = |(5.5 * min) - (30 * hour)|
5. If angle != 360.00, print angle (2 decimal places).
    Else, print 0.00.

**CODE:**
```c
#include<stdio.h>
#include<math.h>
int main()
{
    int n;
    float a;
    scanf("%d",&n);
    scanf("%f",&a);
    float res=(float(n)/360.0)*a;
    res=res*60.0;
    int min=int(res)%60;
    res=res-min;
    int hour=int(res)/60;
    
    float final=abs(5.5*float(min)-30*float(hour));
    if(final!=360.00)
    printf("%0.2f",final);
    else
    printf("0.00"); 
}
