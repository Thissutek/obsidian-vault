2025-08-20 16:03

Status:
Tag: #easy 
Difficulty: [[Arrays & Hashing]] [[Arrays & Hashing Problems]] [[leetcode]]
# Contains Duplicate
## Problem

Given an integer array `nums`, return `true` if any value appears **more than once** in the array, otherwise return `false`.

**Example 1:**

```java
Input: nums = [1, 2, 3, 3]

Output: true
```

  

**Example 2:**

```java
Input: nums = [1, 2, 3, 4]

Output: false
```
## Constraints


## My Thoughts
Well the first thing was that brute forcing this would just be by using two for loops to check constantly check each number but that would mean use going through the array twice which would O(n²) time complexity but we can go through the loop once just by having a hash map that counts the frequency for each number and then when that frequency for that mapped number is over 1 we can return true otherwise we just return false

## Plan Pseudocode
```
function containsDuplicate(nums):
    create empty set called seenNumbers

    for each num in nums:
        if num is in seenNumbers:
            return true   // duplicate found
        else:
            add num to seenNumbers

    return false  // no duplicates found

```

## Solution
```
class Solution {
    /**
     * @param {number[]} nums
     * @return {boolean}
     */
    containsDuplicate(nums) {
        const seenNumbers = new Set();

        for (let num of nums) {
            if (seenNumbers.has(num)) {
                return true; // duplicate found
            }
            seenNumbers.add(num);
        }

        return false; // no duplicates
    }
}
```

## Notes
Just going over the more easier problems I've done to brush up on some leetcode the logic and reasoning is easy so I'm not too worried about this