2025-08-19 23:13

Status:
Tag: #easy 
Difficulty: [[Two Pointer]] [[leetcode]] [[Two Pointer Method]]
# Valid Palindrome
## Problem
Given a string `s`, return `true` if it is a **palindrome**, otherwise return `false`.

A **palindrome** is a string that reads the same forward and backward. It is also case-insensitive and ignores all non-alphanumeric characters.

**Note:** Alphanumeric characters consist of letters `(A-Z, a-z)` and numbers `(0-9)`.

**Example 1:**

```java
Input: s = "Was it a car or a cat I saw?"

Output: true
```

Explanation: After considering only alphanumerical characters we have "wasitacaroracatisaw", which is a palindrome.

**Example 2:**

```java
Input: s = "tab a cat"

Output: false
```

Explanation: "tabacat" is not a palindrome.
## Constraints
**Constraints:**

- `1 <= s.length <= 1000`
- `s` is made up of only printable ASCII characters.
## My Thoughts
its basically checking if the reverse order of the string is still the same as the regular order we can use a two pointer for this basically we have one at the beginning and one at the end of the string and we basically just check each pointer as it moves closer to the middle.

think about the constraints what happens if we have a string character that is capital oppose to lowercase letters like "A" vs "a" they should still count. We also have to think about skipping over the commas and periods and anything not alphanumerical

## Plan Pseudocode

```
function validPalindrome(word):
    set left = 0
    set right = word.length - 1

    while left < right:
        if word[left] is NOT alphanumeric:
            move left pointer forward (left++)
            continue to next loop iteration

        if word[right] is NOT alphanumeric:
            move right pointer backward (right--)
            continue to next loop iteration

        if lowercase(word[left]) != lowercase(word[right]):
            return false

        move both pointers:
            left++
            right--

    return true


```
## Solution
```
class Solution {
    /**
     * @param {string} s
     * @return {boolean}
     */
    isPalindrome(s) {
        const isValidChar = (char) => {
            char = char.toLowerCase();
            return /^[a-z0-9]$/.test(char);
        };

        let left = 0;
        let right = s.length - 1;

        while (left < right) {
            // Skip non-alphanumeric characters
            while (left < right && !isValidChar(s[left])) {
                left++;
            }
            while (left < right && !isValidChar(s[right])) {
                right--;
            }

            // Compare characters
            if (s[left].toLowerCase() !== s[right].toLowerCase()) {
                return false;
            }

            left++;
            right--;
        }

        return true;
    }
}
```

## Notes
The explanation makes sense to me like I understand the way this code works, minus some things I didn't think about like edge cases or specific things like upper and lowercase and commas periods. I think thats one thing though I notice that i dont like about the javascript is that how is there not like a method to check for alphanumeric. that fact that we have to use regex to build out a helper function that mkes this work is interesting.