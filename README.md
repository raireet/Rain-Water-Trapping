# Rain-Water-Trapping
![image](https://user-images.githubusercontent.com/121010130/209323875-6b0f09c1-523f-4062-850b-ee9c23ba4bd6.png)
Input Format

Line 1 represents total number of bars denoted 
n
. Line 2 represents 
h
i
 of total 
n
 bars.

Output Format

Print the total units of water stored due to these 
n
 bars

Example 1:

Input

12

0 1 0 2 1 0 1 3 2 1 2 1

Output

6

Explanation

The above figure represents the diagram for Example 1. Here, 6 units of water is trapped between bars of width 1.

Example 2:

Input

6

4 2 0 3 2 5

Output

9



/* package codechef; // don't place package name! */
import java.util.*;
import java.lang.*;
import java.io.*;

/* Name of the class has to be "Main" only if the class is public. */
public class Main
{
    public static void main (String[] args) throws java.lang.Exception
    {
		Scanner sc = new Scanner(System.in);

int n = sc.nextInt();

int [] arr = new int[n];

for(int i =0;i<n;i++)

{

arr[i] = sc.nextInt();

}

int sum =0;

for(int i =1;i<n-1;i++)

{
int[] prefmax = new int[n];
int pMax = Integer.MIN_VALUE;

int sMax = Integer.MIN_VALUE;

int min = 0;

for(int j =0;j<i;j++)

{

if(pMax<arr[j])

pMax = arr[j];
prefmax[j]= pMax;
}

for(int j =i+1;j<n;j++)

{

if(sMax<arr[j])

sMax = arr[j];

}

if(pMax<sMax)

min = pMax;

else

min = sMax;

if(min>arr[i])

sum =sum+(min-arr[i]);

}

System.out.println(sum);

    }

}



