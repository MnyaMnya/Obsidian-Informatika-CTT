```java
class Solution {

    public int[] twoSum(int[] nums, int target) {

        HashMap<Integer, Integer> Hash = new  HashMap<>();

  

        for(int i=0;i<nums.length;i++){

        if(Hash.containsKey(target-nums[i])){

            return new int[]{i,Hash.get(target-nums[i])};

        }

        Hash.put(nums[i],i);

        }

        return new int[]{};

    }

}
```
