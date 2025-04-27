# Day 1 - Two Sum Problem

## 📜 Problem Statement
Write a function that takes in a non-empty array of distinct integers and an integer representing a target sum. If any two numbers in the input array sum up to the target sum, the function should return them in an array, in any order.
If no two numbers sum up to the target sum, the function should return an empty array.

**Note:**
You cannot add a single integer to itself to obtain the target sum; you must use two different integers.
You can assume that there will be at most one pair of numbers summing up to the target sum.


### Sample Input
array=[3,5,-4,8,11,1,-1,6]
targetSum=10
### Sample Output
[-1, 11] //the number could be in reverse order


## 🧠 Approach
- Brute force with two loops - Time complexity -- (O(n²))| Space Complexity -O(1) 
- HashMap for optimized search (O(n)) - Time complexity -- (O(n))| Space Complexity - 
- Two Pinter Approach (O(nlogn)) - Time complexity -- (O(nlogn))| Space Complexity - 

## 🔥 Solution 1 (Python)--Brute Force
```def twoNumberSum(array, targetSum):
    # Write your code here.
    n= len(array)
    for i in range(n-1):
        for j in range(i+1,n):
            if array[i]+array[j]==targetSum:
                return[array[i], array[j]]

    return[]
        
    pass
```
#time complexity - O(n^2)- 2 for loop 
#Space complexity- O(1) - no space exra required.
    
## 🔥 Solution 2 (Python) - using hash Map
```def twoNumberSum(array, targetSum):
    # Write your code here.
   nums={} ## Empty hash Map creation 
    for i in array:
       potentialMatch = targetSum - i
        if potentialMatch in nums:   ## Searching in hash map if value exist or not 
            return [potentialMatch, i]
        else:
           nums[i]=True# if not add the I value in hash map (value:True)
    return [] ## return empty if no match found
    
    pass
```
    Time Complexity-- O(n) time --to search sum pair with target sum.
    Space Complexity -- O(n) to create Hash map of size of arrray.
    

 ## 🔥 Solution 3 (Python) -- Using Two Pointer Approach
    ```def twoNumberSum(array, targetSum):
            array.sort()
    left=0
    right=len(array)-1
    while left<right:
        currentsum=array[left]+array[right]
        if currentsum == targetSum:
            return[array[left],array[right]]
        elif currentsum < targetSum:
            left +=1
        elif currentsum > targetSum:
            right -=1
    return []
    ```
      
    #Time Complexity-- O(nlog(n)) time for sorting
    #Space Complexity -- O(1) 

