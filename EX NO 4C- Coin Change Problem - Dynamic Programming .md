
# EX 4C Coin Change Problem - Dynamic Programming.
## DATE: 09-10-2025
## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm
1. Initialize a dp array of size amount + 1, filled with amount + 1 (to represent infinity).
2. Set dp[0] = 0 (base case — 0 coins to make amount 0).
3. For each i from 1 to amount, check all coins:
  If coin ≤ i, update dp[i] = min(dp[i], dp[i - coin] + 1).
4. After processing all coins, if dp[amount] > amount, return -1.
5. Otherwise, return dp[amount] as the minimum coins required.


## Program:
```
Developed by: NISHA D
Register Number: 212223230143
 
import java.util.*;

public class Solution {
    public int coinChange(int[] coins, int amount) {
        //ADD YOUR CODE HERE
        int[] dp = new int[amount + 1];
        Arrays.fill(dp, amount + 1);
        dp[0] = 0;
    
        for (int i = 1; i <= amount; i++) {
            for (int coin : coins) {
                if (coin <= i) {
                    dp[i] = Math.min(dp[i], dp[i - coin] + 1);
                }
            }
        }
    
        return dp[amount] > amount ? -1 : dp[amount];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution solution = new Solution();
        String coinsLine = scanner.nextLine(); 
        String amountLine = scanner.nextLine();
        coinsLine = coinsLine.replaceAll("[^0-9,]", ""); 
        String[] coinsStr = coinsLine.split(",");
        int[] coins = new int[coinsStr.length];
        for (int i = 0; i < coinsStr.length; i++) {
            coins[i] = Integer.parseInt(coinsStr[i]);
        }
        int amount = Integer.parseInt(amountLine.replaceAll("[^0-9]", ""));
        int result = solution.coinChange(coins, amount);
        System.out.println(result);

        scanner.close();
    }
}

```

## Output:

<img width="361" height="247" alt="image" src="https://github.com/user-attachments/assets/347ade8b-0dcc-4dae-976b-279b32d60db2" />


## Result:
The program successfully implemented and the expected output is verified.
