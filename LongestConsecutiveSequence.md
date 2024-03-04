# 最长连续序列

## 双指针法
```java
class Solution {
    public int longestConsecutive(int[] nums) {
        int length = nums.length;
        if(length == 0)
            return 0;
        //排序法
        Arrays.sort(nums);
        int i = 0, j = i + 1;
        //计数
        int count = 1, result = count;
        while (j < length) {
            if (nums[i] == nums[j] - 1) {
                count++;
                //双指针移动
                i++;
                j++;
            } else if (nums[i] == nums[j]) {
                i++;
                j = i + 1;
            } else {
                //更新当前最大长度
                result = Math.max(result, count);
                count = 1;
                i++;
                j = i + 1;
            }
        }
        return Math.max(result, count);
    }
}
```