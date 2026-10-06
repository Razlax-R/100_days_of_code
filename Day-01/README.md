## Day 1 — Two Sum

**Problem:** Two Sum — LeetCode

Given an array of integers and a target value, find two numbers whose sum equals the target and return their indices.

### What I Tried

I first solved the problem using **nested loops**. I compared each number with the numbers after it and checked whether their sum matched the target.

```python
class Solution:
    def twoSum(self, nums, target):
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
```

### What I Learned

* How to use nested loops to check pairs.
* How to work with array indices.
* Why the second loop starts from `i + 1`.
* My first approach has **O(n²)** time complexity.
* I learned how to optimize the solution using a **dictionary**.

### Optimized Approach

Instead of checking every possible pair, I learned to use a dictionary to store each number along with its index.

For every number, I calculate:

```text
complement = target - current number
```

Then I check whether that complement has already been seen.

Example:

```text
nums = (3, 4, 6, 1)
target = 9

3 → need 6 → not found → store 3:0
4 → need 5 → not found → store 4:1
6 → need 3 → found → return [0,2]
```

### Key Learning

The main idea I learned is:

> **Instead of searching for the pair directly, find the complement needed to reach the target and use a dictionary to check whether it was already seen.**

**Time Complexity:** O(n)
**Space Complexity:** O(n)

**Status:** ✅ Day 1 Completed
