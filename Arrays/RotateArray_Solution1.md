# Leetcode 189
https://leetcode.com/problems/rotate-array/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(n)


### Code:

```java
class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        if(k>n){
            k=k%n;
        }
        int[] arr1 = new int[n-k];
        int a1=0, a2=0;
        int[] arr2 = new int[k];
        for(int i=0;i<n;i++){
            if(i<n-k){
                arr1[a1] = nums[i];
                a1++;
            }
            else{
                arr2[a2] = nums[i];
                a2++;
            }
        }
        System.arraycopy(arr2, 0, nums,0,arr2.length);
        System.arraycopy(arr1, 0, nums, arr2.length, arr1.length);
    }
}
