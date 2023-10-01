# leet-day78

# Reverse String II

**Problem Description:**

Given a string `s` and an integer `k`, reverse the first `k` characters for every `2k` characters counting from the start of the string. If there are fewer than `k` characters left, reverse all of them. If there are less than `2k` but greater than or equal to `k` characters, then reverse the first `k` characters and leave the others as original.

**Example:**

Input: `s = "abcdefg", k = 2`

Output: `"bacdfeg"`

**Constraints:**

- 1 <= `s.length` <= 10^4
- `s` consists of only lowercase English letters.
- 1 <= `k` <= 10^4

---

## Approach

We can solve this problem by iterating through the string in segments of `2k` characters and reversing the first `k` characters in each segment.

1. Initialize a variable `n` to store the length of the input string `s`.

2. Iterate through the string from left to right in steps of `2k`, where `k` is the given integer.

3. For each segment, determine the start and end indices. If the segment has fewer than `k` characters, we reverse all of them. If it has between `k` and `2k` characters, we reverse the first `k` characters.

4. Use a two-pointer approach to reverse the characters within the segment.

5. Repeat this process for all segments, and build the final result.

6. Return the modified string as the output.

## Code

Here's the C++ code implementing the above approach:

```cpp
#include <iostream>
#include <string>

class Solution {
public:
    std::string reverseStr(std::string s, int k) {
        int n = s.length();
        for (int i = 0; i < n; i += 2 * k) {
            int start = i;
            int end = std::min(i + k - 1, n - 1);  // Determine the end of the current segment
            
            // Reverse the characters in the current segment
            while (start < end) {
                std::swap(s[start], s[end]);
                start++;
                end--;
            }
        }
        return s;
    }
};

