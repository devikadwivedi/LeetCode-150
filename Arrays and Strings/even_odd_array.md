# Even Odd Array Problem
## Problem Statement
Given an array of integers, the task is to rearrange the array such that all even numbers appear at the beginning, maintaining their relative order, followed by odd numbers. The sorting should be done in-place, using only a constant amount of extra space.

## Example
For example, given the array:

```
[3, 1, 2, 4, 6, 5, 7, 8]
```

The sorted array should be:

```
[2, 4, 6, 8, 3, 1, 5, 7]
```

## Solution Approach
For this problem, partition the array into three subarrays: Even, Unclassified, and Odd, appearing in that order. Initially, Even and Odd are empty, and Unclassified is the entire array. We iterate through Unclassified, moving elements to the boundares of Even and Odd subarrays via swaps. This is a sort of two pointer approach

## Algorithm
```python
def even_odd_array(A: List[int]) -> None:
    # set two pointers, one to the beginning the other to the end of the List
    next_even, next_odd = 0, len(A) - 1
    # while the pointers have not crossed,
    while next_even < next_odd:
        # if the number is even, move the even pointer forward
        if A[next_even] % 2 == 0:
            next_even += 1
        else:
            # if its odd, swap the number with the next odd, and update the odd pointer
            A[next_even], A[next_odd] = A[next_odd], A[next_even]
            next_odd -= 1
```

## Time Complexity
O(n) due to traversing array and doing constant time operations at each iteration.
