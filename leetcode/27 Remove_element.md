Link: https://leetcode.com/problems/remove-element/  
Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The relative order of the elements may be changed.
Tags: In-place\_array\_modification, 
```python3
def swap(nums, val):
    front, back = 0, len(nums)
    while front < back:
        if nums[front] == val:
            back -= 1
            nums[front], nums[back] = nums[back], nums[front]
        else:
            front += 1
    return back

print(swap([0,1,2,3,0,4,3], 3))
```
Output: `5`
