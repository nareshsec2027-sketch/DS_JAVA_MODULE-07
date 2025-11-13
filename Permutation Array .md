## Ex9: Finding the Longest Length of Nested Set in a Permutation Array

## AIM:
To write a program that finds the length of the longest set s[k] = { nums[k], nums[nums[k]], nums[nums[nums[k]]], … }, where the iteration stops before a duplicate element occurs.

## Algorithm:

Create a boolean array visited to mark visited elements.

For each unvisited index, trace its sequence until a repeat is found.

Track the length of each chain.

Return the maximum length found.

## Program:
```
Program to find the Longest Length of Nested Set in a Permutation Array
Developed by: Naresh P.S.
RegisterNumber: 212223040127
Date: 11-11-2025


public class NestedSetLength {
    public static int arrayNesting(int[] nums) {
        boolean[] visited = new boolean[nums.length];
        int maxLen = 0;

        for (int i = 0; i < nums.length; i++) {
            if (!visited[i]) {
                int start = nums[i], count = 0;
                while (!visited[start]) {
                    visited[start] = true;
                    start = nums[start];
                    count++;
                }
                maxLen = Math.max(maxLen, count);
            }
        }
        return maxLen;
    }

    public static void main(String[] args) {
        int[] nums = {5, 4, 0, 3, 1, 6, 2};
        System.out.println("Longest nested set length: " + arrayNesting(nums));
    }
}
```

Output:
Longest nested set length: 4

Result:

The program successfully computes the longest length of the nested set for the given permutation array.
