# Leetcode 42
# https://leetcode.com/problems/trapping-rain-water/description/?envType=study-plan-v2&envId=top-interview-150
# reference: https://youtu.be/ZI2z5pq0TqA?si=Pe7RboRpKYlRdSWh

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int trap(int[] height) {
        //Solution 2
        //initialize l, r pointers, and variables leftMax, rightMax, and res
        int n = height.length-1;
        int l = 0, r = n;
        int leftMax = height[l];
        int rightMax = height[r];
        int res = 0;

        //run loop until l and r do not cross each other
        while (l < r) {
            //check if leftMax < rightMax
            if (leftMax < rightMax) {
                l++;
                //calculate the next max in left side
                leftMax = Math.max(leftMax, height[l]);
                //Calculate the Water trapped
                res += leftMax - height[l];
            }
            else {
                r--;
                //calculate the next max in right side
                rightMax = Math.max(rightMax, height[r]);
                //Calculate the Water trapped
                res += rightMax - height[r];
            }
        }
        return res;
    }
}
