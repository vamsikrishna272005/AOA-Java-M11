
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
