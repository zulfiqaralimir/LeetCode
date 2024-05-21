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




__WITHOUT DRY RUN__

Sure! Let's break down the provided code without performing a detailed dry run. Instead, we'll focus on explaining the overall logic and purpose of each part of the code.

Here's the given code again:

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

### Explanation

The goal of the function `maxSubArray` is to find the maximum sum of a contiguous subarray within a given array of integers `nums`. This problem is efficiently solved using Kadane's Algorithm. Let's break down each component of the code:

1. **Initialization**:
   ```python
   maxSum = float('-inf')
   currentSum = 0
   ```
   - `maxSum` is initialized to negative infinity to ensure that any sum from the array will be larger.
   - `currentSum` is initialized to 0, representing the current sum of the subarray being considered.

2. **Iteration through the array**:
   ```python
   for num in nums:
       currentSum += num
   ```
   - The code iterates over each element `num` in the array `nums`.
   - In each iteration, `num` is added to `currentSum`, updating the sum of the current subarray.

3. **Update `maxSum`**:
   ```python
   if currentSum > maxSum:
       maxSum = currentSum
   ```
   - After updating `currentSum`, the code checks if `currentSum` is greater than `maxSum`.
   - If it is, `maxSum` is updated to the value of `currentSum`.
   - This ensures that `maxSum` always holds the largest sum encountered so far.

4. **Reset `currentSum` if necessary**:
   ```python
   if currentSum < 0:
       currentSum = 0
   ```
   - If `currentSum` becomes negative, it is reset to 0.
   - This reset is crucial because a negative sum would decrease the sum of any subsequent subarray. Starting fresh with a sum of 0 allows for potentially larger sums in future iterations.

5. **Return the result**:
   ```python
   return maxSum
   ```
   - After iterating through all elements of `nums`, the function returns `maxSum`, which contains the maximum sum of any contiguous subarray found.

### Summary

- **Kadane's Algorithm**: This algorithm is designed to solve the maximum subarray problem with a linear time complexity \(O(n)\).
- **Key Steps**:
  1. **Accumulate**: Add each element to `currentSum`.
  2. **Track Maximum**: Update `maxSum` whenever `currentSum` exceeds it.
  3. **Reset When Necessary**: Reset `currentSum` to 0 if it becomes negative.
- **Final Result**: The value of `maxSum` at the end of the iteration is the maximum sum of any contiguous subarray within the input array `nums`.

This code efficiently finds the maximum subarray sum using a single pass through the array, ensuring optimal performance.
