# Leetcode 27
# https://leetcode.com/problems/remove-element/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int removeElement(int[] nums, int val) {

        int curr=0;
        int last = nums.length-1;
        while(curr<=last){O
            if(nums[curr]==val){
                int temp = nums[curr];
                nums[curr]=nums[last];
                nums[last]=temp;
                last--;
            }
            else{
                curr++;
            }
        }
        return curr;

    }
}
