# 字母异位词分组
## 排序 + 哈希表
```java
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        Map<String, List<String>> hashTable = new HashMap<>();
        for(String str : strs) {
            char[] array = str.toCharArray();
            //对字符数组进行排序
            Arrays.sort(array);
            String key = new String(array);
            List<String> list = hashTable.getOrDefault(key, new ArrayList<String>());
            list.add(str);
            hashTable.put(key,list);
        }
        return new ArrayList<List<String>>(hashTable.values());
    }
}
```