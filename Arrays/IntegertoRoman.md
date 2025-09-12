# Leetcode 12
# https://leetcode.com/problems/integer-to-roman/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(1), Space Complexity: O(1)


### Code:

```java
class Solution {
    public String intToRoman(int num) {
        LinkedHashMap<String, Integer> map = new LinkedHashMap<>();
        map.put("M", 1000);
        map.put("CM", 900);
        map.put("D", 500);
        map.put("CD", 400);
        map.put("C", 100);
        map.put("XC", 90);
        map.put("L", 50);
        map.put("XL", 40);
        map.put("X", 10);
        map.put("IX", 9);
        map.put("V", 5);
        map.put("IV", 4);
        map.put("I", 1);
        

        String res = "";
        for(Map.Entry<String, Integer> entry:map.entrySet()){
            if(num/entry.getValue()>=1){
                int count = num/entry.getValue();
                res += entry.getKey().repeat(count);
                num = num%entry.getValue();
            }
            
        }
        return res;
    }
}
