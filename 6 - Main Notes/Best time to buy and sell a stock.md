2025-08-19 22:54

Status:
Tag: [[leetcode]] [[Sliding Window Method]] [[Sliding Window]]
Difficulty: #easy 
# Best time to buy and sell a stock
## Problem
You are given an integer array `prices` where `prices[i]` is the price of NeetCoin on the `ith` day.

You may choose a **single day** to buy one NeetCoin and choose a **different day in the future** to sell it.

Return the maximum profit you can achieve. You may choose to **not make any transactions**, in which case the profit would be `0`.

**Example 1:**

```java
Input: prices = [10,1,5,6,7,1]

Output: 6
```

Explanation: Buy `prices[1]` and sell `prices[4]`, `profit = 7 - 1 = 6`.

**Example 2:**

```java
Input: prices = [10,8,7,5,2]

Output: 0
```

Explanation: No profitable transactions can be made, thus the max profit is 0.
## Constraints
**Constraints:**

- `1 <= prices.length <= 100`
- `0 <= prices[i] <= 100`

## My Thoughts
We are basically using a two pointer/sliding window method. We want to know what the lowest we can buy and the highest we can sell. 

## Plan Pseudocode
```
function maxProfit(prices) {
	let left = 0;  // buy day
    let right = 1; // sell day
    let maxProfit = 0;

    while (right < prices.length) {
        if (prices[right] > prices[left]) {
            // profitable scenario
            let profit = prices[right] - prices[left];
            maxProfit = Math.max(maxProfit, profit);
        } else {
            // found a cheaper buy option
            left = right;
        }
        right++;
    }
    return maxProfit;
}
```

## Solution
```
function maxProfit(prices) {
    let left = 0;  // buy day
    let right = 1; // sell day
    let maxProfit = 0;

    while (right < prices.length) {
        if (prices[right] > prices[left]) {
            // profitable scenario
            let profit = prices[right] - prices[left];
            maxProfit = Math.max(maxProfit, profit);
        } else {
            // found a cheaper buy option
            left = right;
        }
        right++;
    }

    return maxProfit;
}

```

## Notes
The solution makes sense to me I can walk through the idea of it. Its always translating the idea into code that makes this a lot harder I think I just forget syntax and the ability to code stuff like this but the problem and solution makes a lot of sense to me 