# EX 1A Print All Numbers 
## DATE: 16/07/2026
## AIM:
To Write a Java program that takes an integer input N from the user and prints all the numbers from 1 to N, separated by spaces, on a single line..

### Algorithm
1.Start the program.

2.Read an integer input N from the user.

3.Check if N is less than or equal to 0.

4.If yes, display the message: "Invalid input. N must be greater than 0."

5.If N is greater than 0, use a for loop to iterate from 1 to N.

6.Print each number separated by a space on the same line. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vamsi Krishna G
Register Number: 212223220120

import java.util.*;
public class demo
{
    public static void main(String arg[])
    {
        int N,i;
        Scanner sc=new Scanner(System.in);
        N=sc.nextInt();
        if (N<=0)
        {
            System.out.println("Invalid input. N must be greater than 0.");
        }
        else
        {
            for(i=1;i<=N;i++)
            {
                System.out.print(i+" ");
            }
        }
        
    }
}
*/
```

## Output:

<img width="572" height="188" alt="image" src="https://github.com/user-attachments/assets/63eadf65-2022-42a4-8186-7a0e8d2f4cfa" />


## Result:
The program successfully print all the numbers from 1 to N. 
