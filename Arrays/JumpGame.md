# Leetcode 55
# https://leetcode.com/problems/jump-game/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public boolean canJump(int[] nums) {
        int goal = nums.length-1;
        for(int i=nums.length-1;i>=0;i--){
            if(i+nums[i]>=goal){
                goal = i;
            }
        }
        return goal==0?true:false;
    }
}
