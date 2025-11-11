
# EX 4D Longest Common SubSequence - Dynamic Programming.
## DATE: 13-10-2025
## AIM:
To write a Java program to for given constraints.
Given two strings text1 and text2, return the length of their longest common subsequence. If there is no common subsequence, return 0.
A subsequence of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.

For example, "ace" is a subsequence of "abcde".
A common subsequence of two strings is a subsequence that is common to both strings.

Input: text1 = "abcde", text2 = "ace" 
Output: 3  
Explanation: The longest common subsequence is "ace" and its length is 3.
Constraints:

1 <= text1.length, text2.length <= 1000
text1 and text2 consist of only lowercase English characters.

## Algorithm
1️. Let m and n be lengths of text1 and text2, and create a dp[m+1][n+1] table.

2️. For each character i in text1 and j in text2:
  If text1[i−1] == text2[j−1], then dp[i][j] = dp[i−1][j−1] + 1.
  
3️. Otherwise, dp[i][j] = max(dp[i−1][j], dp[i][j−1]).

4️. Continue filling the table until both strings are fully processed.

5️. Return dp[m][n] — the length of the longest common subsequence.

## Program:
```
Developed by: NISHA D
Register Number: 212223230143

import java.util.Scanner;

public class Solution {
  public int longestCommonSubsequence(String text1, String text2) {    
    
    //ADD YOUR CODE HERE
    int m = text1.length();
    int n = text2.length();
    int[][] dp = new int[m + 1][n + 1];

    for (int i = 1; i <= m; i++) {
        for (int j = 1; j <= n; j++) {
            if (text1.charAt(i - 1) == text2.charAt(j - 1)) {
                dp[i][j] = dp[i - 1][j - 1] + 1;
            } else {
                dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
            }
        }
    }

    return dp[m][n];
  }

    // Main method for input and output
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        String text1 = sc.nextLine().replaceAll("\"", "");
        String text2 = sc.nextLine().replaceAll("\"", "");

        int lcsLength = sol.longestCommonSubsequence(text1, text2);
        System.out.println("Length of Longest Common Subsequence: " + lcsLength);

        sc.close();
    }
}


```

## Output:

<img width="1001" height="251" alt="image" src="https://github.com/user-attachments/assets/c73dfe36-3506-4788-8253-8a2358296f23" />




## Result:
The program successfully implemented and the expected output is verified.
