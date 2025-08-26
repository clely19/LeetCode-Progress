# Leetcode 189
# https://leetcode.com/problems/rotate-array/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public void rotate(int[] nums, int k) {

        if(k>nums.length){
            k = k%nums.length;
        }
        
        reverse(nums,0,nums.length-1);
        reverse(nums,0,k-1);
        reverse(nums, k, nums.length-1);

        
    }
    public void reverse(int[] nums, int start, int end){
            while(start<end){
                int temp = nums[start];
                nums[start] = nums[end];
                nums[end] = temp;
                start++;
                end --;
            }
            
        }
}
