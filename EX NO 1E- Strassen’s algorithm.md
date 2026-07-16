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
