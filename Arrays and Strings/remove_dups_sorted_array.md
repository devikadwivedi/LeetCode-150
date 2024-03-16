# LeetCode Problem 26: Remove Duplicates from Sorted Array

## Problem Description
Given an integer array `nums` sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in `nums`.

## Approach and Explanation
The provided solution utilizes a two-pointer approach to remove duplicates in-place from the sorted array `nums`. It initializes a pointer `p1` at index 1 and iterates through the array using a `for` loop. If the current element is not equal to the previous one, it moves the current element to the position pointed by `p1` and increments `p1`. Finally, it returns the value of `p1`, which represents the number of unique elements in the modified array.

## Code Breakdown
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        p1 = 1

        for i in range(1, len(nums)):
            if nums[i] != nums[i - 1]:
                nums[p1] = nums[i]
                p1 += 1
        return p1
```

- `removeDuplicates()` function takes in an array `nums` sorted in non-decreasing order.
- It initializes a pointer `p1` at index 1.
- It iterates through the array using a `for` loop, starting from index 1.
- If the current element is not equal to the previous one, it moves the current element to the position pointed by `p1` and increments `p1`.
- Finally, it returns the value of `p1`, which represents the number of unique elements in the modified array.

## Time Complexity
The time complexity of this solution is O(n), where n is the number of elements in the array `nums`, as it requires a single pass through the array to remove duplicates.

## Space Complexity
The space complexity of this solution is O(1) because it operates in-place without using any additional space.
