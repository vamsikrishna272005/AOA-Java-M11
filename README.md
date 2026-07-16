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


# EX 1C Valid Pairs using Brute Force Approach
## DATE: 20/07/2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.

## Algorithm
1.Start the program and read the integer input n (array size), the array elements nums[], and the integer k.

2.Initialize a variable count to 0 to store the number of valid pairs.

3.Use two nested loops to check all possible pairs (i, j) where i < j.

4.For each pair, calculate |nums[i] - nums[j]|;

5.If the result equals k, increment the count by 1.

6.After checking all pairs, print the value of count and stop the program   

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vamsi Krishna G
Register Number: 212223220120

import java.util.Scanner;
public class CountPairsWithDifference {
    public static int countKDifference(int[] nums, int k) {
        int count=0;
        for (int i=0;i<nums.length;i++){
            for (int j=i+1;j<nums.length;j++){
                if(Math.abs(nums[i]-nums[j])==k){
                    count++;
                }
            }
        }
        //Type your code here
        return count;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        int k = sc.nextInt();
        int result = countKDifference(nums, k);
        System.out.println(result);
        sc.close();
    }
}
  
*/
```

## Output:
<img width="627" height="324" alt="image" src="https://github.com/user-attachments/assets/7308b6af-8317-4321-ba72-dba342c99ff4" />



## Result:
The program successfully implemented and the expected output is verified.


# EX 1D Sorted Array using Divide and Conquer Approach.
## DATE: 22/07/2026
## AIM:
To write a Java program to for given constraints.
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

## Algorithm
1. Start the program.
2. Create a Scanner object to take input from the user.
3. Read the size of the first array m and its elements.
4. Read the size of the second array n and its elements.
5. Initialize two pointers p1 and p2 to 0.
6. Use a helper function getMin() that returns the smaller of the two current elements from nums1 and nums2, advancing the corresponding pointer.
7. Continue merging until the middle index (or middle two indices) of the combined array is reached.
7. If the total number of elements is odd, the median is the middle element.
8. If it’s even, the median is the average of the two middle elements.
9. Display the median.
10. End the program.

## Program:
```
/*
Program to find the median of two sorted arrays
Developed by: Vamsi Krishna G
Register Number: 212223220120
*/
import java.util.Scanner;

public class Solution {
    private int p1 = 0, p2 = 0;

    // Get the smaller value between nums1[p1] and nums2[p2], and move the pointer forward
    private int getMin(int[] nums1, int[] nums2) {
        if (p1 < nums1.length && p2 < nums2.length) {
            return nums1[p1] < nums2[p2] ? nums1[p1++] : nums2[p2++];
        } else if (p1 < nums1.length) {
            return nums1[p1++];
        } else if (p2 < nums2.length) {
            return nums2[p2++];
        }
        return -1; // Should not reach here if input is valid
    }

    // Main logic to find median of two sorted arrays
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int totalLength = nums1.length + nums2.length;
        int mid1 = (totalLength - 1) / 2; // left middle index
        int mid2 = totalLength / 2;       // right middle index

        int current = -1, prev = -1;
        for (int i = 0; i <= mid2; i++) {
            prev = current;
            current = getMin(nums1, nums2);
        }

        if (totalLength % 2 == 0) {
            return (prev + current) / 2.0; // even length → average of 2 mids
        } else {
            return current; // odd length → middle element
        }
    }

    // Main method with user input
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        // Input for nums1
        int m = sc.nextInt();
        int[] nums1 = new int[m];
        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }

        // Input for nums2
        int n = sc.nextInt();
        int[] nums2 = new int[n];
        for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        // Find and display the median
        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);
        
        sc.close();
    }
}

```

## Output:

<img width="1021" height="371" alt="image" src="https://github.com/user-attachments/assets/147b8e42-f1ea-4e48-8643-1701f0572e74" />


## Result:
The program successfully implemented and the expected output is verified.

# EX 1E Integer Multiplication using Divide and Conquer Approach(Strassen’s algorithm).
## DATE: 24/07/2026
## AIM:
To write a Java program to for given constraints.
You are given two square matrices A and B of size n × n (where n is a power of 2). Your task is to compute their matrix product using Strassen’s Matrix Multiplication algorithm and return the resulting matrix.

Unlike traditional matrix multiplication which takes O(n3)O(n^3)O(n3) time, Strassen’s algorithm improves this by reducing the number of recursive multiplications from 8 to 7, achieving approximately O(n2.81)O(n^{2.81})O(n2.81) complexity.
## Algorithm
1. Start the program.
2. Create a Scanner object to take input from the user.
3. Read the order n of the square matrices.
4. Input elements for matrix A and B.
5. Divide each matrix into four submatrices (quadrants).
6. Compute the following seven products recursively using Strassen’s formula:

M1 = (A11 + A22) × (B11 + B22)

M2 = (A21 + A22) × B11

M3 = A11 × (B12 − B22)

M4 = A22 × (B21 − B11)

M5 = (A11 + A12) × B22

M6 = (A21 − A11) × (B11 + B12)

M7 = (A12 − A22) × (B21 + B22)

7. Calculate the resulting submatrices using:

C11 = M1 + M4 − M5 + M7

C12 = M3 + M5

C21 = M2 + M4

C22 = M1 − M2 + M3 + M6

8. Combine the four submatrices (C11, C12, C21, C22) into the final matrix.

9. Display the resulting product matrix.

10. End the program.

## Program:
```
/*
Program to perform Strassen Matrix Multiplication
Developed by: Vamsi Krishna G
Register Number: 212223220120
*/
import java.util.Scanner;

public class StrassenMatrix {

    // Add two matrices
    static int[][] add(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] + B[i][j];
        return C;
    }

    // Subtract matrix B from A
    static int[][] subtract(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] - B[i][j];
        return C;
    }

    // Strassen recursive multiplication
    static int[][] strassen(int[][] A, int[][] B) {
        int n = A.length;

        // Base case: 1x1 matrix
        if (n == 1) {
            int[][] C = { { A[0][0] * B[0][0] } };
            return C;
        }

        int newSize = n / 2;

        // Split matrices into quadrants
        int[][] A11 = new int[newSize][newSize];
        int[][] A12 = new int[newSize][newSize];
        int[][] A21 = new int[newSize][newSize];
        int[][] A22 = new int[newSize][newSize];

        int[][] B11 = new int[newSize][newSize];
        int[][] B12 = new int[newSize][newSize];
        int[][] B21 = new int[newSize][newSize];
        int[][] B22 = new int[newSize][newSize];

        for (int i = 0; i < newSize; i++) {
            for (int j = 0; j < newSize; j++) {
                A11[i][j] = A[i][j];
                A12[i][j] = A[i][j + newSize];
                A21[i][j] = A[i + newSize][j];
                A22[i][j] = A[i + newSize][j + newSize];

                B11[i][j] = B[i][j];
                B12[i][j] = B[i][j + newSize];
                B21[i][j] = B[i + newSize][j];
                B22[i][j] = B[i + newSize][j + newSize];
            }
        }

        // Compute the 7 products
        int[][] M1 = strassen(add(A11, A22), add(B11, B22));
        int[][] M2 = strassen(add(A21, A22), B11);
        int[][] M3 = strassen(A11, subtract(B12, B22));
        int[][] M4 = strassen(A22, subtract(B21, B11));
        int[][] M5 = strassen(add(A11, A12), B22);
        int[][] M6 = strassen(subtract(A21, A11), add(B11, B12));
        int[][] M7 = strassen(subtract(A12, A22), add(B21, B22));

        // Compute result quadrants
        int[][] C11 = add(subtract(add(M1, M4), M5), M7);
        int[][] C12 = add(M3, M5);
        int[][] C21 = add(M2, M4);
        int[][] C22 = add(subtract(add(M1, M3), M2), M6);

        // Combine into one matrix
        int[][] C = new int[n][n];
        for (int i = 0; i < newSize; i++) {
            for (int j = 0; j < newSize; j++) {
                C[i][j] = C11[i][j];
                C[i][j + newSize] = C12[i][j];
                C[i + newSize][j] = C21[i][j];
                C[i + newSize][j + newSize] = C22[i][j];
            }
        }
        return C;
    }

    // Function to print matrix
    static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            for (int val : row)
                System.out.print(val + " ");
            System.out.println();
        }
    }

    // Main method to get input and run Strassen multiplication
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Read size of matrix
        int n = sc.nextInt();

        int[][] A = new int[n][n];
        int[][] B = new int[n][n];

        // Input Matrix A
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                A[i][j] = sc.nextInt();

        // Input Matrix B
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                B[i][j] = sc.nextInt();

        // Multiply using Strassen
        int[][] result = strassen(A, B);
        System.out.println("Result of Strassen Matrix Multiplication:");
        // Output the result matrix
        printMatrix(result);
    }
}

```

## Output:

<img width="898" height="791" alt="image" src="https://github.com/user-attachments/assets/77a1b380-15ae-4416-b670-7c71d06dc7cd" />


## Result:
The program successfully implemented and the expected output is verified.
