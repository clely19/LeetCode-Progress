# Leetcode 274
# https://leetcode.com/problems/h-index/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n²), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int hIndex(int[] citations) {
        int hIndex=0;
        for(int h=1;h<=citations.length;h++){
            int num0fPapers=0;
            for(int i=0;i<citations.length;i++){
                if(citations[i]>=h){
                    num0fPapers++;
                }
            }
            if(num0fPapers>=h){
                hIndex=h;
            }
        }
        return hIndex;
    }
}
