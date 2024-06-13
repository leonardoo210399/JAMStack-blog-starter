---
title: LeetCode Problem 242 - Valid Anagram
description: Exploring Solutions for the Valid Anagram Problem in Python and Js
author: Aditya
date: '2024-06-13T14:59:56+05:30'
tags:
  - post
  - featured
image: /assets/blog/screenshot-2024-06-13-2.16.01-pm.png
imageAlt: idk
---
**Title:** Exploring Solutions for the Valid Anagram Problem

**Question Number and Name:** LeetCode Problem 242 - Valid Anagram

Please solve the following algorithmic problem step-by-step, and present your solution with a detailed explanation, code implementation, and complexity analysis. Use the structure outlined below:

---

*Problem Statement:*

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

*Example:*

*Input:*
s = "anagram", t = "nagaram"
*Output:*
true

Explanation: 
Both strings contain the same letters but in a different order.

*Approach:*

### 1. Sorting Approach

This approach involves sorting both strings and checking if they are equal.

#### Algorithm:

1. Sort both strings.
2. Compare the sorted strings.

#### Code:

python
```python
def isAnagram(s: str, t: str) -> bool:
    return sorted(s) == sorted(t)
```

#### Complexity Analysis:

- *Time Complexity:* O(nlogn) - Sorting both strings.
- *Space Complexity:* O(n) - Space required for sorted strings.

Javascript
```javascript
var isAnagram = function(s, t) {
    return s.split('').sort().join('') === t.split('').sort().join('');
};
```

#### Complexity Analysis:

- *Time Complexity:* O(nlogn) - Sorting both strings.
- *Space Complexity:* O(n) - Space required for sorted strings.

### 2. Hashmap Approach

In this approach, we use a hashmap to count the occurrences of characters in both strings and then compare the counts.

#### Algorithm:

1. Create two hashmaps to count character occurrences for both strings.
2. Compare the hashmaps.

#### Code:

python
```python
def isAnagram(s: str, t: str) -> bool:
    if len(s) != len(t):
        return False
    count_s = collections.Counter(s)
    count_t = collections.Counter(t)
    return count_s == count_t
```

#### Complexity Analysis:

- *Time Complexity:* O(n) - Counting occurrences in both strings.
- *Space Complexity:* O(n) - Space required for hashmaps.

Javascript
```javascript
var isAnagram = function(s, t) {
    if (s.length !== t.length) return false;
    const count = {};
    for (let char of s) {
        count[char] = (count[char] || 0) + 1;
    }
    for (let char of t) {
        if (!count[char]) return false;
        count[char]--;
    }
    return true;
};
```

#### Complexity Analysis:

- *Time Complexity:* O(n) - Counting occurrences in both strings.
- *Space Complexity:* O(n) - Space required for hashmap.

*Conclusion:*

Both approaches provide solutions to determine if two strings are anagrams. The sorting approach is simpler but less efficient compared to the hashmap approach, which has a better time complexity. Depending on the constraints of the problem and the size of the input strings, one might be preferred over the other.
