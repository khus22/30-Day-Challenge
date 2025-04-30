# Day 3 - Single Number(136)

## 📜 Problem Statement
Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.
You must implement a solution with a linear runtime complexity and use only constant extra space.

### Sample Input
Input: nums = [2,2,1]
### Sample Output
Output: 1

## 🧠 Approach
- Brute force Using a HashMap (Dictionary)

## 🔥 Solution 1 (Python)--Brute Force
```
class Solution:
    def singleNumber(self, nums: list[int]) -> int:
        count = {}
        for num in nums:
            count[num] = count.get(num, 0) + 1
        for key in count:
            if count[key] == 1:
                return key
```

### Breakdown:
- count is a dictionary (dict) that stores numbers as keys and their counts as values.
- count.get(num, 0):
- Tries to get the value for key num.
- If num is not in the dictionary, it returns 0 by default.
- So, this ensures we don't get a KeyError for new elements.
- + 1: We increment the current count by 1.

**🔁 Example:**
Let’s say nums = [2, 2, 1]

First loop iteration: num = 2
→ count.get(2, 0) → not found → returns 0
→ count[2] = 0 + 1 = 1
→ count = {2: 1}

Second loop: num = 2
→ count.get(2, 0) → returns 1
→ count[2] = 1 + 1 = 2
→ count = {2: 2}

Third loop: num = 1
→ count.get(1, 0) → not found → returns 0
→ count[1] = 0 + 1 = 1
→ count = {2: 2, 1: 1}

- ✅time complexity: O(n)--One pass to build the dictionary
- ✅ Space Complexity: O(n) ---Extra space for the dictionary to store counts of up to n elements

## 🔥 Solution 2 (Python)--XOR operator
```
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        result=0
        for num in nums:
            result=result^num #xor operator x^x=0, x^0=x
        return result
```
        
- ✅ Time Complexity: O(n)--One pass through the list, performing constant-time operations
- ✅ Space Complexity: O(1)--Only one integer result is used, regardless of input size
