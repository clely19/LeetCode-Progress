# Leetcode 26
# https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int removeDuplicates(int[] nums) {

        int u_ele =0;
        int ele = 1;
        while(ele<nums.length){
            if(nums[u_ele]!=nums[ele]){
                u_ele++;
                int temp = nums[u_ele];
                nums[u_ele] = nums[ele];
                nums[ele] =temp;
            }
            ele++;
        }
        return u_ele+1;
    }
}
