https://www.facebook.com/iCodeguru/videos/1245140913522755/

https://leetcode.com/problems/maximum-subarray/description/

class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        maxSum = float('-inf')
        currentSum = 0
        
        for num in nums:
            currentSum += num
            
            if currentSum > maxSum:
                maxSum = currentSum
            
            if currentSum < 0:
                currentSum = 0
        
        return maxSum





__EXPLANATION__

The provided code is an implementation of Kadane's Algorithm, which is used to find the maximum sum of a contiguous subarray in an array of integers. Let's perform a dry run of this code with a specific example to understand how it works step by step.

Here is the complete code formatted correctly:

```python
from typing import List

class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        maxSum = float('-inf')
        currentSum = 0

        for num in nums:
            currentSum += num

            if currentSum > maxSum:
                maxSum = currentSum

            if currentSum < 0:
                currentSum = 0

        return maxSum
```

### Example Dry Run

Let's take the example array `nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]` and perform a dry run.

1. **Initial Setup**:
   - `nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]`
   - `maxSum = float('-inf')` (initially negative infinity)
   - `currentSum = 0`

2. **Step Through the Code**:

   - **Iteration 1**:
     - `num = -2`
     - `currentSum += num` => `currentSum = 0 + (-2) = -2`
     - `currentSum > maxSum` => `-2 > -inf` => `maxSum = -2`
     - `currentSum < 0` => `-2 < 0` => `currentSum = 0`
   
   - **Iteration 2**:
     - `num = 1`
     - `currentSum += num` => `currentSum = 0 + 1 = 1`
     - `currentSum > maxSum` => `1 > -2` => `maxSum = 1`
     - `currentSum < 0` => `1 < 0` => No change to `currentSum`
   
   - **Iteration 3**:
     - `num = -3`
     - `currentSum += num` => `currentSum = 1 + (-3) = -2`
     - `currentSum > maxSum` => `-2 > 1` => No change to `maxSum`
     - `currentSum < 0` => `-2 < 0` => `currentSum = 0`
   
   - **Iteration 4**:
     - `num = 4`
     - `currentSum += num` => `currentSum = 0 + 4 = 4`
     - `currentSum > maxSum` => `4 > 1` => `maxSum = 4`
     - `currentSum < 0` => `4 < 0` => No change to `currentSum`
   
   - **Iteration 5**:
     - `num = -1`
     - `currentSum += num` => `currentSum = 4 + (-1) = 3`
     - `currentSum > maxSum` => `3 > 4` => No change to `maxSum`
     - `currentSum < 0` => `3 < 0` => No change to `currentSum`
   
   - **Iteration 6**:
     - `num = 2`
     - `currentSum += num` => `currentSum = 3 + 2 = 5`
     - `currentSum > maxSum` => `5 > 4` => `maxSum = 5`
     - `currentSum < 0` => `5 < 0` => No change to `currentSum`
   
   - **Iteration 7**:
     - `num = 1`
     - `currentSum += num` => `currentSum = 5 + 1 = 6`
     - `currentSum > maxSum` => `6 > 5` => `maxSum = 6`
     - `currentSum < 0` => `6 < 0` => No change to `currentSum`
   
   - **Iteration 8**:
     - `num = -5`
     - `currentSum += num` => `currentSum = 6 + (-5) = 1`
     - `currentSum > maxSum` => `1 > 6` => No change to `maxSum`
     - `currentSum < 0` => `1 < 0` => No change to `currentSum`
   
   - **Iteration 9**:
     - `num = 4`
     - `currentSum += num` => `currentSum = 1 + 4 = 5`
     - `currentSum > maxSum` => `5 > 6` => No change to `maxSum`
     - `currentSum < 0` => `5 < 0` => No change to `currentSum`

3. **Final Output**:
   - After iterating through all the elements, the final value of `maxSum` is `6`.

### Explanation

- **maxSum**: Keeps track of the maximum sum encountered so far.
- **currentSum**: Tracks the sum of the current subarray. If it becomes negative, it is reset to 0, as a negative sum would decrease the potential sum of future subarrays.

### Conclusion

The function returns `6`, which is the maximum sum of any contiguous subarray in the given example. The dry run confirms that the code correctly implements Kadane's Algorithm, efficiently finding the maximum subarray sum by maintaining running totals and resetting when necessary.
