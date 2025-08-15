# Leetcode 80
# https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(m+n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int ctr =1;
        int k=1;
        for(int i=1;i<nums.length;i++){
            if(nums[i]==nums[i-1]){
                ctr++;
            }
            else{
                ctr =1;
            }
            if(ctr<=2){
                nums[k] = nums[i];
                k++;
            }
        }
        return k;

    }
}
