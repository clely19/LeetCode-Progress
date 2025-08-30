# Leetcode 45
# https://leetcode.com/problems/jump-game-ii/submissions/1752962737/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int jump(int[] nums) {
        int furthest =0;
        int currEnd=0;
        int jumps=0;
        for(int i=0;i<nums.length-1;i++){
            furthest = Math.max(furthest, i+nums[i]);
            if(i==currEnd){
                jumps++;
                currEnd=furthest;
            }
        }
        return jumps;
        
    }
}
