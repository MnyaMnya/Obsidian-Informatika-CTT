```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashSet<Integer> Hash = new HashSet<>();
        for (int i=0;i<nums.length;i++){
            if(Hash.contains(nums[i])){
                return true;
            }
            else{
                Hash.add(nums[i]);
            }
        }
        return false;
    }
}
```
