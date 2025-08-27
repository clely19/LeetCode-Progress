# Leetcode 121
# https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(1)


### Code:

```java
class Solution {
    public int maxProfit(int[] prices) {
        int b=0;
        int sum_profit =0;
        if(prices.length<2){
            return sum_profit;
        }
        for(int s=1;s<prices.length;s++){
            int profit  = prices[s]-prices[b];
            if(profit>0){
                sum_profit+=profit;
            }
            b++;
        }
        return sum_profit;
    }
}
