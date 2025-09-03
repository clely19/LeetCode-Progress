# Leetcode 27
# https://leetcode.com/problems/remove-element/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int removeElement(int[] nums, int val) {

        int k = nums.length-1;
        int curr = 0;
        while(curr<=k){
            if(nums[curr]==val){
                int temp = nums[curr];
                nums[curr] = nums[k];
                nums[k] = temp;
                k--;
            }
            else{
                curr++;
            }
        }
        return k+1;

    }
}
