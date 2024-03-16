# LeetCode Problem 27: Remove Element

## Problem Description
Given an integer array `nums` and an integer `val`, remove all occurrences of `val` in `nums` in-place. The order of the elements may be changed. Then return the number of elements in `nums` which are not equal to `val`.

## Approach and Explanation
The solution uses a straightforward approach to remove all occurrences of `val` from the array `nums`. It utilizes a while loop to continuously remove the value `val` from the array using the `remove()` method until a `ValueError` occurs, indicating that there are no more occurrences of `val` in the array. Finally, it returns the length of the modified array, which represents the count of elements not equal to `val`.

## Code Breakdown
```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        while True:
            try:
                nums.remove(val)
            except ValueError:
                break
        return len(nums)
```

- `removeElement()` function takes in an array `nums` and an integer `val`.
- It continuously attempts to remove `val` from the array `nums` using the `remove()` method.
- The try-except block is used to catch the ValueError that occurs when val is not found in the array.
- When all occurrences of `val` are removed, it breaks out of the loop.
- Finally, it returns the length of the modified `nums` array, which represents the count of elements not equal to `val`.

## Time Complexity
The time complexity of this solution is O(n^2) due to the worst-case scenario where every element in the array `nums` is equal to `val`, and removal operation takes linear time.

## Space Complexity
The space complexity of this solution is O(1) because it operates in-place without using any additional space.
