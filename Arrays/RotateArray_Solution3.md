# Leetcode 189
# https://leetcode.com/problems/rotate-array/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(n)


### Code:

```java
class Solution {
    public void rotate(int[] nums, int k) {

    int helper[] = new int[nums.length];
    if(k>nums.length){
        k = k%nums.length;
    }
    System.arraycopy(nums, 0,helper, 0,nums.length);

    for(int i=0;i<helper.length;i++){
        int index = (i+k) %nums.length;
        nums[index] = helper[i];
    }
        }
}
