
# Palindrome Number

## Problem Description

A palindrome is a number that reads the same backward as forward.
**Example:**

**Input:**
```python
x = 121
```

**Output:**
```python
True
```

**Explanation:**
121 is a palindrome because reversing it gives the same number.
-121 is not a palindrome because reversing it results in 121-, which is not the same as the original.
10 is not a palindrome because reversing it results in 01, which is not the same as the original.
The goal is to determine whether a given integer 
𝑥
x is a palindrome..

---

## Solution

### Approach

To determine if a number is a palindrome, you can reverse the number and compare it to the original number. If they are the same, the number is a palindrome.

**Note:** We avoid reversing the number by converting it to a string to prevent potential overflow issues with very large numbers.

### Code

```python
def is_palindrome(x):
    # Negative numbers and numbers ending in 0 (except 0 itself) are not palindromes
    if x < 0 or (x % 10 == 0 and x != 0):
        return False
    
    reversed_num = 0
    original = x

    while x > 0:
        digit = x % 10
        reversed_num = reversed_num * 10 + digit
        x //= 10
    
    return reversed_num == original
```

### Complexity Analysis

- **Time Complexity:** O(log n): The number of digits in 
𝑥
x determines the number of iterations, which is proportional to 
log
⁡
10
𝑥
log 
10
​
 x.
- **Space Complexity:** O(1): The algorithm uses a constant amount of space for variables like reversed_num and original.

---

## Edge Cases

- **Negative Numbers:** Any negative number cannot be a palindrome by definition.
- **Numbers Ending in 0:** Numbers ending in 0 are not palindromes unless the number is exactly 0.

---

## Additional Notes

- This approach is efficient and avoids converting the integer to a string, making it more suitable for large inputs.
- Handles all edge cases for palindromic and non-palindromic integers. 

---

## References

**LeetCode Problem Link:** [Palindrome Number](https://leetcode.com/problems/palindrome-number/)

---
