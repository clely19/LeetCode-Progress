# Leetcode 134
# https://leetcode.com/problems/gas-station/submissions/1758690419/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int canCompleteCircuit(int[] gas, int[] cost) {
        if(IntStream.of(gas).sum()<IntStream.of(cost).sum()){
            return -1;
        }
        int total=0;
        int startIndex=0;
        for(int i=0;i<gas.length;i++){
            total += gas[i]-cost[i];
            if(total<0){
                total =0;
                startIndex=i+1;
            }
        }
        return startIndex;
    }
}
