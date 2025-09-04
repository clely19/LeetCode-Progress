# Leetcode 135
# https://leetcode.com/problems/candy/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(n), Space Complexity: O(n)


### Code:

```java
class Solution {
    public int candy(int[] ratings) {

        int n = ratings.length;
        int min[] = new int[n];

        Arrays.fill(min, 1);

        for(int i=1;i<ratings.length;i++){
            if(ratings[i]>ratings[i-1]){
                min[i]=min[i-1]+1;
            }
        }
         for(int i=ratings.length-2;i>=0;i--){
            if(ratings[i]>ratings[i+1]){
                min[i]=Math.max(min[i],min[i+1]+1);
            }
        }
        int total =0;
        for(int i=0;i<min.length;i++){
            total+= min[i];
        }
        return total;
    }
}
