# LeetCode 136 Single Number
Given a non-empty array of integers, every element appears twice except for one. Find that single one.

### Note:

Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

### Example 1:
> Input: [2,2,1]

> Output: 1

### Example 2:
> Input: [4,1,2,1,2]

> Output: 4

## Java Solution
`````java
import java.util.Hashtable;

class Solution {
    public int singleNumber(int[] nums) {
        Hashtable<Integer, Integer> hashTable = new Hashtable<Integer, Integer>();
        for(int i : nums){
            if(!hashTable.containsKey(i)){
                hashTable.put(i, 1);
            }else{
                hashTable.remove(i);
            }
        }
        return hashTable.keys().nextElement();
    }
}
`````

## Python solution:
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        return 2 * sum(list(set(nums))) - sum(nums)
```
