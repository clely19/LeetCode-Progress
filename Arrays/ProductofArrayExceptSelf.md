# Leetcode 238
# https://leetcode.com/problems/product-of-array-except-self/submissions/1757753754/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(n)


### Code:

```java
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int[] prefix = new int[n];
        Arrays.fill(prefix, 1);
        for(int p=1;p<prefix.length;p++){
            prefix[p] = prefix[p-1]*nums[p-1];
        }

        int suffix =1;
        for(int i=n-1;i>=0;i--){
            prefix[i] = prefix[i]*suffix;
            suffix *=nums[i];
        }
        return prefix;
    }
}
