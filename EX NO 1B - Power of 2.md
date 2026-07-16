
# EX 1B Power of 2
## DATE: 18/07/2026
## AIM:
To write a Java program to for given constraints.Given an integer n, return true if it is a power of two. Otherwise, return false.

An integer n is a power of two, if there exists an integer x such that n == 2x.

## Algorithm
1.Start the program.

2.Read an integer input n from the user.

3.Check if n is less than or equal to 0.

4.If yes, return false (since powers of two are positive).

5.Perform a bitwise AND operation between n and n - 1.

6.If the result is 0, then n is a power of two (only one bit is set in its binary form).

7.Otherwise, it is not a power of two.

8.Display the result (true or false) to the user. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vamsi Krishna G
Register Number:212223220120

import java.util.Scanner;

public class Solution {

    public boolean isPowerOfTwo(int n) {
        if (n <= 0) {
            return false;
        }
        return (n & (n - 1)) == 0; // Checks if only one bit is set
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution sol = new Solution();
        int n = scanner.nextInt();

        boolean result = sol.isPowerOfTwo(n);
        System.out.println(result);

        scanner.close();
    }
}

*/
```

## Output:
<img width="510" height="230" alt="image" src="https://github.com/user-attachments/assets/d4f55e9f-2f7c-423e-bcff-73dc3303fa4c" />



## Result:
The program successfully implemented and the expected output is verified.
