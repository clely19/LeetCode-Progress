# Leetcode 58
# https://leetcode.com/problems/length-of-last-word/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int lengthOfLastWord(String s) {
        int count =0;
        String trimmerS = s.trim();
        int i=trimmerS.length()-1;

        while(i>=0&& trimmerS.charAt(i)!=' '){
            count++;
            i--;
        }
        return count;
    }
}
