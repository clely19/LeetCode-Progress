# Leetcode 14 
# https://leetcode.com/problems/longest-common-prefix/description/?envType=study-plan-v2&envId=top-interview-150
# Reference: https://youtu.be/0sWShKIJoo4?si=3-WRBQUyGCfgmGhW

### Time Complexity: O(mxn), Space Complexity: O(1)


### Code:

```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String res = "";
        for(int i=0;i<strs[0].length();i++){
            for(String str: strs){
                if(i==str.length() || str.charAt(i)!=strs[0].charAt(i)){
                    return res;
                }
            }
            res+=strs[0].charAt(i);
        }
        return res;
    }
}
