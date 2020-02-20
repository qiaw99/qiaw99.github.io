# LeetCode 26 Remove Duplicates from Sorted Array
## Requirements:
Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

__Do not allocate _*extra space*_ for another array, you must do this by modifying the input array _in-place_ with O(1) extra memory.__

### Example 1:
Given nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.

It doesn't matter what you leave beyond the returned length.

### Example 2:

Given nums = [0,0,1,1,1,2,2,3,3,4],

Your function should return length = 5, with the first five elements of nums being modified to 0, 1, 2, 3, and 4 respectively.

It doesn't matter what values are set beyond the returned length.

### Clarification:
Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by reference, which means modification to the input array will be known to the caller as well.

    // nums is passed in by reference. (i.e., without making a copy)
    int len = removeDuplicates(nums);

    // any modification to nums in your function would be known by the caller.
    // using the length returned by your function, it prints the first len elements.
    for (int i = 0; i < len; i++) {
        print(nums[i]);
    }

## Python Solution
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        i = 0
        while i <= len(nums) - 2:
            if(nums[i] == nums[i + 1]):
                del nums[i]
            else:
                i += 1
        return len(nums)
```

Another idea to solve this problem by python might be using of set. However, I don't know the reason, the solution with set can't be accepted. But it works.
```python
    class Solution:
        def removeDuplicates(self, nums: List[int]) -> int:
            return len(list(set(nums)))
```
__Time complexity = O(n)__ 
