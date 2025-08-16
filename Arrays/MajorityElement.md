# Leetcode 169
# https://leetcode.com/problems/majority-element/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int majorityElement(int[] nums) {
        int maj_ele =nums[0], count =0;
        for(int ele=0;ele<nums.length;ele++){
            if(nums[ele]==maj_ele){
                count++;
            }
            else{
                count--;
                if(count<0){
                    maj_ele = nums[ele];
                    count=1;
                }
            }
        }
        return maj_ele;
    }
}
