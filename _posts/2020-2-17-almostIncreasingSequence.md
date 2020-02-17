# almostIncreasingSequence
### Requirements:
Given a sequence of integers as an array, determine whether it is possible to obtain a strictly increasing sequence by removing no more than one element from the array.

Note: sequence a0, a1, ..., an is considered to be a strictly increasing if a0 < a1 < ... < an. Sequence containing only one element is also considered to be strictly increasing.

#### Example

1) For sequence = [1, 3, 2, 1], the output should be
almostIncreasingSequence(sequence) = false.

There is no one element in this array that can be removed in order to get a strictly increasing sequence.

2) For sequence = [1, 3, 2], the output should be
almostIncreasingSequence(sequence) = true.

You can remove 3 from the array to get the strictly increasing sequence [1, 2]. Alternately, you can remove 2 to get the strictly increasing sequence [1, 3].

### [input] array.integer sequence

##### Guaranteed constraints:
2 ≤ sequence.length ≤ 105, -105 ≤ sequence[i] ≤ 105.

### [output] boolean

Return true if it is possible to remove one element from the array in order to get a strictly increasing sequence, otherwise return false.

### Python Code
```python
sequence = [1, 2, 5, 3, 5]

def almostIncreasingSequence(sequence):
    n = len(sequence)
    dp = [1] * n
    for i in range(1, n):
        for j in range(0, i):
            if(sequence[j] < sequence[i]):
                dp[i] = max(dp[i], dp[j] + 1)
    return n - max(dp) <= 1
print(almostIncreasingSequence(sequence)) # True
```
__We could firstly get the longest increasing sequence by using dynamic programming. If the difference of the length of sequence and the length of the longest increasing sequence equal or less than 1, then we should return True because we can remove one of the element in the sequence so that the whole sequence can be monoton increased.__

#### Time complexity: O(n2)
