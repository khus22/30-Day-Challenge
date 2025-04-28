# Day 2 - Three Sum Problem

## 📜 Problem Statement
Write a function that takes in a non-empty array of distinct integers and an integer representing a target sum. The function should find all triplets in the array that sum up to the target sum and return a 
two-dimensional array of all these triplets. Each triplet should be ordered in ascending order, and the triplets themselves should be ordered in ascending order with respect to the numbers they hold.
If no three numbers sum up to the target sum, the function should return an empty array.

### Sample Input
- array=[12,3,1,2,-6,5,-8,6]
- targetSum=0
### Sample Output
[[-8,2,6],[-8,3,5],[-6,1,5]] //the number should be in Ascending order

## 🧠 Approach
- Brute force with two loops 

## 🔥 Solution 1 (Python)--Brute Force
```
def threeNumberSum(array, targetSum):
    n = len(array)
    result = []  # List to store all valid triplets
    
    # Iterate over each triplet combination
    for i in range(n-2):
        for j in range(i+1, n-1):
            for k in range(j+1, n):
                if array[i] + array[j] + array[k] == targetSum:
                    triplet = [array[i], array[j], array[k]]
                    triplet.sort()  # Sort each triplet before adding to the result
                    result.append(triplet)  # Append sorted triplet to result list
    
    # Sort the entire list of triplets
    result.sort()  # Sort the list of triplets in ascending order
    
    return result  # Return the sorted list of all triplets
```
