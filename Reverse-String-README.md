# leet-day78

# Reverse a String In-Place

## Description

This C++ code demonstrates how to reverse a string in-place using a simple two-pointer approach. The input is given as a vector of characters, and the code modifies the input vector to reverse the string. It achieves this efficiently with O(1) extra memory usage.

## Features

- Reverses a string in-place.
- Minimal memory usage (O(1) extra memory).
- Works with any vector of characters representing a string.

## Usage

1. Include the necessary headers:

```cpp
#include <iostream>
#include <vector>
```

2. Define the `reverseString` function:

```cpp
class Solution {
public:
    void reverseString(std::vector<char>& s) {
        int n = s.size();
        for (int i = 0; i < n / 2; i++) {
            std::swap(s[i], s[n - i - 1]);
        }
    }
};
```

3. Create an instance of the `Solution` class and call the `reverseString` function with your input vector:

```cpp
int main() {
    Solution solution;
    std::vector<char> s = {'h', 'e', 'l', 'l', 'o'};
    solution.reverseString(s);

    std::cout << "Reversed string: ";
    for (char ch : s) {
        std::cout << ch;
    }

    return 0;
}
```

4. Compile and run the code. It will reverse the input string and display the result.

## Example

- Input: `s = ['h', 'e', 'l', 'l', 'o']`
- Output: `Reversed string: olleh`

## Constraints

- 1 <= s.length <= 105
- s[i] is a printable ASCII character.

