# LeetCode Problem 80: Remove Duplicates from Sorted Array II

## Problem Description
Given an integer array `nums` sorted in non-decreasing order, remove some duplicates in-place such that each unique element appears at most twice. The relative order of the elements should be kept the same.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array `nums`. More formally, if there are k elements after removing the duplicates, then the first k elements of `nums` should hold the final result. It does not matter what you leave beyond the first k elements.

Return `k` after placing the final result in the first `k` slots of `nums`.

## Approach
The provided solution utilizes a two-pointer approach to remove duplicates in-place from the sorted array `nums`. It iterates through the array using a `for` loop, starting from index 1, and compares each element with the previous one. If the current element is unique or if the element `p1 - 2` positions back is not equal to the current element, it's added to the modified array at position `p1`. Otherwise, duplicates are skipped. Finally, it returns the value of `p1`, which represents the number of unique elements in the modified array.

## Code Breakdown
```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        p1 = 1
        for i in range(1, len(nums)):
            if nums[i] != nums[i - 1]:
                nums[p1] = nums[i]
                p1 += 1
                continue
            if p1 - 2 >= 0 and nums[i] != nums[p1 - 2]:
                nums[p1] = nums[i]
                p1 += 1
                continue
            if i == 1:
                nums[p1] = nums[i]
                p1 += 1
        
        return p1
```

- `removeDuplicates()` function takes in an array `nums` sorted in non-decreasing order.
- It initializes a pointer `p1` at index 1.
- It iterates through the array using a `for` loop, starting from index 1.
- If the current element is unique or if the element `p1 - 2` positions back is not equal to the current element, it's added to the modified array at position `p1`.
- Otherwise, duplicates are skipped.
- Finally, it returns the value of `p1`, which represents the number of unique elements in the modified array.

## Time Complexity
The time complexity of this solution is O(n), where n is the number of elements in the array `nums`, as it requires a single pass through the array to remove duplicates.

## Space Complexity
The space complexity of this solution is O(1) because it operates in-place without using any additional space.
