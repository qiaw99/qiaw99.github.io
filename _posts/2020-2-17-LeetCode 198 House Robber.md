# LeetCode 198 House Robber
### Requirements:
You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security system connected and it will automatically contact the police if two adjacent houses were broken into on the same night.

Given a list of non-negative integers representing the amount of money of each house, determine the maximum amount of money you can rob tonight without alerting the police.

### Example 1:
> Input: [1,2,3,1]

> Output: 4

> Explanation: Rob house 1 (money = 1) and then rob house 3 (money = 3).
             Total amount you can rob = 1 + 3 = 4.
### Example 2:
> Input: [2,7,9,3,1]

> Output: 12

> Explanation: Rob house 1 (money = 2), rob house 3 (money = 9) and rob house 5 (money = 1).
             Total amount you can rob = 2 + 9 + 1 = 12.

## Python Code
```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        # The special case
        if(nums == []): return 0
        dp = [0 for _ in range(len(nums) + 1)]
        dp[1] = nums[0]
        for i in range(1, len(nums)):
            # steal the last one or steal the last second and the current one
            dp[i + 1] = max(dp[i], dp[i - 1] + nums[i])
        return dp[-1]

```


