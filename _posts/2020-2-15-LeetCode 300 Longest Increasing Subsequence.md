# LeetCode 300 Longest Increasing Subsequence

---
tags: dynammic programming
---
## Requirement
Given an unsorted array of integers, find the length of longest increasing subsequence.

### Example:

> Input: [10,9,2,5,3,7,101,18]

> Output: 4 

> Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4. 

### Note:

There may be more than one LIS combination, it is only necessary for you to return the length.
Your algorithm should run in O(n2) complexity.

## Python Code
```python
# longest increasing sequence
nums = [1,3,2,4,9,2,3,1,10] #[1,2,4,9,10]
dp = [1 for _ in range(len(nums))]
maxResult = 0
for i in range(1, len(nums)):
    for j in range(0, i):
        if(nums[j] < nums[i]):
            dp[i] = max(dp[i], dp[j] + 1)   
print(dp[-1])
```



