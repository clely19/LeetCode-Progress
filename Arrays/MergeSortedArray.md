# Leetcode 88
# https://leetcode.com/problems/merge-sorted-array/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(m+n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {

        int end_index = m+n-1;
        while(m>0 && n>0){
            if(nums1[m-1]>nums2[n-1]){
                nums1[end_index]=nums1[m-1];
                m--;
            }
            else{
                nums1[end_index]=nums2[n-1];
                n--;
            }
            end_index--;
        }
        while(n>0){
            nums1[end_index]=nums2[n-1];
            n--;
            end_index--;
        }


    }
}
