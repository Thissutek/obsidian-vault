2025-08-07 16:58

Status:
Tag: [[Binary Search]] [[leetcode]]
Difficulty: #medium
# Koko Eating Bananas
## Problem
You are given an integer array `piles` where `piles[i]` is the number of bananas in the `ith` pile. You are also given an integer `h`, which represents the number of hours you have to eat all the bananas.

You may decide your bananas-per-hour eating rate of `k`. Each hour, you may choose a pile of bananas and eats `k` bananas from that pile. If the pile has less than `k` bananas, you may finish eating the pile but you can not eat from another pile in the same hour.

Return the minimum integer `k` such that you can eat all the bananas within `h` hours.

**Example 1:**

```java
Input: piles = [1,4,3,2], h = 9

Output: 2
```

Explanation: With an eating rate of 2, you can eat the bananas in 6 hours. With an eating rate of 1, you would need 10 hours to eat all the bananas (which exceeds h=9), thus the minimum eating rate is 2.

**Example 2:**

```java
Input: piles = [25,10,23,4], h = 4

Output: 25
```

## Constraints
- `1 <= piles.length <= 1,000`
- `piles.length <= h <= 1,000,000`
- `1 <= piles[i] <= 1,000,000,000`

## My Thoughts
My initial thought was since this is. a binary search and we are basically trying to find the lowest speed koko needs to eat at to finish it in h hours. Initially well with binary search we basically take the lowest and highest speeds and go from the middle if koko is eating to fast we go left of the middle if the koko is eating to slow we go right to raise the speed. We also need to account for the fact that if there is left over bananas it will take an extra hour to finish it so we can use the ceil()

## Plan Pseudocode
```
function minEatingSpeed(piles, h):
    # search space = [1, max(piles)]
    left = 1
    right = max(piles)
    result = right   # store best answer

    while left <= right:
        mid = (left + right) // 2   # candidate speed (bananas/hour)

        # check if Koko can eat all bananas at speed = mid
        hours = 0
        for pile in piles:
            hours += ceil(pile / mid)

        if hours <= h:
            # valid speed, but maybe there's a slower one that still works
            result = mid
            right = mid - 1
        else:
            # too slow, must increase speed
            left = mid + 1

    return result

```

## Solution
```
var minEatingSpeed = function(piles, h) {
    // Helper: check if Koko can eat all bananas at speed k within h hours
    function canEatAll(piles, h, k) {
        let hours = 0;
        for (let pile of piles) {
            // ceil division without using Math.ceil explicitly:
            hours += Math.ceil(pile / k);
        }
        return hours <= h;
    }

    let left = 1; // slowest possible speed (1 banana/hour)
    let right = Math.max(...piles); // fastest possible speed (eat the biggest pile in 1 hour)
    let result = right; // store min feasible speed

    while (left <= right) {
        let mid = Math.floor((left + right) / 2);

        if (canEatAll(piles, h, mid)) {
            // speed works, try to minimize it
            result = mid;
            right = mid - 1;
        } else {
            // speed too slow, need to go faster
            left = mid + 1;
        }
    }

    return result;
};

```

## Notes
This was a hard question like I understand the mechanics and why but thinking of writing like a helper function to figure out if the koko could eat all the bananas I didn't think of that.