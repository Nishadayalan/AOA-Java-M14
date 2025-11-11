
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 16-10-2025
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1️. Initialize a dp array of size n, filled with 1 (each element is an LIS of length 1).

2️. For each index i from 1 to n-1:
  Compare with all previous indices j < i.
  
3️. If nums[i] > nums[j], update dp[i] = max(dp[i], dp[j] + 1).

4️. Track maxLen = max(maxLen, dp[i]) after each iteration.

5️. Return maxLen — the length of the longest increasing subsequence.  

## Program:
```
Developed by: NISHA D
Register Number: 212223230143

import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        int n = nums.length;
        int[] dp = new int[n];
        Arrays.fill(dp, 1);
        int maxLen = 1;

        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (nums[i] > nums[j]) {
                    dp[i] = Math.max(dp[i], dp[j] + 1);
                }
            }
            maxLen = Math.max(maxLen, dp[i]);
        }

        return maxLen;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}
```

## Output:


<img width="1082" height="222" alt="image" src="https://github.com/user-attachments/assets/37673199-fd0a-41d6-8a60-c343ce8ed894" />


## Result:
The program successfully implemented and the expected output is verified.
