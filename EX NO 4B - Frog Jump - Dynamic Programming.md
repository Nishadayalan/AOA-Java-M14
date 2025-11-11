
# EX 4B Frog Jump - Dynamic Programming.
## DATE: 06-10-2025
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

## Algorithm
1. If n == 1, return 1; if n == 2, return 2.
2. Create an array dp of size n + 1 to store ways for each step.
3. Initialize base cases: dp[1] = 1, dp[2] = 2.
4. For each step i from 3 to n, compute dp[i] = dp[i - 1] + dp[i - 2].
5. Return dp[n] as the total number of ways the frog can reach the top. 

## Program:
```

Developed by: NISHA D
Register Number: 212223230143

import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
       
        int n = scanner.nextInt();
        scanner.close();

        System.out.println(countWays(n));
    }

   
    public static int countWays(int n) {
       //Type your code here
       if (n == 1) return 1;
        if (n == 2) return 2;
    
        int[] dp = new int[n + 1];
        dp[1] = 1;
        dp[2] = 2;
    
        for (int i = 3; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
    
        return dp[n];
       
    }
}

```

## Output:

<img width="342" height="201" alt="image" src="https://github.com/user-attachments/assets/8c82cf05-a1f5-4308-9110-4af688d29cf8" />


## Result:
The program successfully implemented and the expected output is verified.
