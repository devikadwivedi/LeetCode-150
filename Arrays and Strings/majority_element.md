# LeetCode Problem 169: Majority Element

## Problem Description
Given an array `nums` of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

## Explanation
The provided solution sorts the array `nums` in ascending order and returns the element at index ⌊n / 2⌋, which corresponds to the majority element. Since the majority element appears more than ⌊n / 2⌋ times, it will occupy the middle position in the sorted array.

## Code Breakdown
```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        nums.sort()
        return nums[int(len(nums) / 2)]
```

- `majorityElement()` function takes in an array `nums` of integers.
- It sorts the array in ascending order using the `sort()` method.
- It returns the element at index ⌊n / 2⌋, where n is the length of the array, which corresponds to the majority element.

## Time Complexity
The time complexity of this solution is O(n log n) due to the sorting operation, where n is the number of elements in the array `nums`.

## Space Complexity
The space complexity of this solution is O(1) because it operates in-place without using any additional space.
