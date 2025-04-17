# Leetcode 42
# https://leetcode.com/problems/trapping-rain-water/description/?envType=study-plan-v2&envId=top-interview-150
# reference: https://youtu.be/ZI2z5pq0TqA?si=Pe7RboRpKYlRdSWh

### Time Complexity: O(n), Space Complexity: O(n)


### Code:

```java
class Solution {
    public int trap(int[] height) {
        int n = height.length;
        int totalWater = 0;

        // Create maxLeft and maxRight arrays
        int[] maxLeft = new int[n];
        int[] maxRight = new int[n];

        // Fill maxLeft array
        maxLeft[0] = height[0];
        for (int i = 1; i < n; i++) {
            maxLeft[i] = Math.max(maxLeft[i - 1], height[i]);
        }

        // Fill maxRight array
        maxRight[n - 1] = height[n - 1];
        for (int i = n - 2; i >= 0; i--) {
            maxRight[i] = Math.max(maxRight[i + 1], height[i]);
        }

        // Calculate the total water trapped
        for (int i = 0; i < n; i++) {
            totalWater += Math.max(0, Math.min(maxLeft[i], maxRight[i]) - height[i]);
        }

        return totalWater;
    }
}
