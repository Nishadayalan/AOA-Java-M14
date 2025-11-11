
# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE: 02-10-2025
## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.
A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

The company wants to find a contiguous sequence of buildings (possibly wrapping around from the end to the beginning) that maximizes the total net energy.

Write a program to compute the maximum net energy that can be collected from any contiguous block of buildings on the circular grid.

Input Format:
First line: Integer n (number of buildings)

Second line: n space-separated integers: net energy for each building

Output Format:
A single integer: Maximum net energy collectable from a contiguous block (wrapping allowed)

Constraints:
1 <= n <= 10^6
## Algorithm
1. Initialize variables: totalSum, maxKadane, minKadane, currentMax, currentMin.
2. Traverse the array once, updating: currentMax = max(val, currentMax + val), maxKadane = max(maxKadane, currentMax), currentMin =      min(val,currentMin + val), minKadane = min(minKadane, currentMin)
3. Add each element to totalSum.
4. If all values are negative → return maxKadane.
5. Else → return max(maxKadane, totalSum - minKadane).


## Program:
```
Developed by: NISHA D
Register Number: 212223230143

import java.util.*;

public class SolarEnergyMaximizer {
    public static int maxCircularEnergy(int[] energy) {
        // Type Your Code
        int totalSum = 0;
        int maxKadane = Integer.MIN_VALUE;
        int currentMax = 0;
        int minKadane = Integer.MAX_VALUE;
        int currentMin = 0;

        for (int val : energy) {
            totalSum += val;
            currentMax = Math.max(val, currentMax + val);
            maxKadane = Math.max(maxKadane, currentMax);
            currentMin = Math.min(val, currentMin + val);
            minKadane = Math.min(minKadane, currentMin);
        }

        if (maxKadane < 0) return maxKadane;
        return Math.max(maxKadane, totalSum - minKadane);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] energy = new int[n];
        for (int i = 0; i < n; i++) {
            energy[i] = sc.nextInt();
        }
        System.out.println(maxCircularEnergy(energy));
    }
}

```

## Output:

<img width="445" height="260" alt="image" src="https://github.com/user-attachments/assets/11ee10bf-d0d6-4db7-8f73-079466fb022f" />


## Result:
The program successfully Implemented and the output is verified. 
