# 两数之和
> 此题目共有两种解法，一种是暴力枚举，一种是哈希表
## 暴力枚举
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int length = nums.length;
        for(int i = 0; i< nums.length-1; ++i)
        {
            for(int j = i + 1; j < nums.length; ++j)
            {
                if(nums[i] + nums[j] == target) {
                    return new int[]{i,j};
                }
            }
        }
        return new int[0];
    }
}
```
## 哈希表
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> hashTable = new HashMap<>();
        for(int i = 0; i < nums.length; ++i) {
            //如果哈希表中存在另一个数
            if (hashTable.containsKey(target - nums[i])) {
                return new int[]{i,hashTable.get(target - nums[i])};
            } else {
                //放入哈希表中
                hashTable.put(nums[i],i);
            }
        }
        return new int[0];
    }
}
```