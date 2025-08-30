# Leetcode 380
# https://leetcode.com/problems/insert-delete-getrandom-o1/description/?envType=study-plan-v2&envId=top-interview-150

### Time Complexity: O(1), Space Complexity: O(n)


### Code:

```java
class RandomizedSet {
    HashMap<Integer, Integer> map;
    List<Integer> list;
    Random random ;

    public RandomizedSet() {
        map = new HashMap<Integer, Integer>();
        list = new ArrayList<Integer>();
        random = new Random();
    }
    
    public boolean insert(int val) {
        boolean res = !map.containsKey(val);
        if(res){
            map.put(val, list.size());
            list.add(val);
        }
        return res;
    }
    
    public boolean remove(int val) {
        boolean res = map.containsKey(val);
        if(res){
            int index = map.get(val);
            int lastVal = list.get(list.size()-1);
            list.set(index, lastVal);
            list.remove(list.size()-1);
            map.put(lastVal,index);
            map.remove(val);
        }
        return res;

    }
    
    public int getRandom() {
        int randomIndex = random.nextInt(list.size());
        int randomNum = list.get(randomIndex);
        return randomNum;

    }
}

/**
 * Your RandomizedSet object will be instantiated and called as such:
 * RandomizedSet obj = new RandomizedSet();
 * boolean param_1 = obj.insert(val);
 * boolean param_2 = obj.remove(val);
 * int param_3 = obj.getRandom();
 */
