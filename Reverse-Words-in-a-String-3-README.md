# leet-day78

# Reverse Words in a Sentence 3

## Problem Description

Given a string `s`, this program reverses the order of characters in each word within a sentence while still preserving whitespace and the initial word order.

## Example

**Input:**
```
s = "Let's take LeetCode contest"
```

**Output:**
```
"s'teL ekat edoCteeL tsetnoc"
```

## Constraints

- `1 <= s.length <= 5 * 10^4`
- `s` contains printable ASCII characters.
- `s` does not contain any leading or trailing spaces.
- There is at least one word in `s`.
- All the words in `s` are separated by a single space.

## Solution Approach

The solution uses a `std::istringstream` to split the input string `s` into words by spaces. For each word, it reverses the characters and appends them to the result string with a space. Finally, it removes the trailing space before returning the reversed sentence.

## How to Use

1. Include the necessary header files:

```cpp
#include <iostream>
#include <string>
#include <sstream>
```

2. Create an instance of the `Solution` class.

```cpp
Solution solution;
```

3. Call the `reverseWords` function with your input string.

```cpp
std::string s = "Let's take LeetCode contest";
std::string reversed = solution.reverseWords(s);
```

4. Print the result.

```cpp
std::cout << reversed << std::endl;
```

## Example Usage

```cpp
#include <iostream>
#include <string>
#include <sstream>

class Solution {
public:
    std::string reverseWords(std::string s) {
        std::istringstream iss(s);  // Use stringstream to split the string by spaces
        std::string word, result;
        
        while (iss >> word) {  // Read each word
            reverse(word.begin(), word.end());  // Reverse the word
            result += word + " ";  // Append the reversed word with a space
        }
        
        // Remove the trailing space before returning the result
        result.pop_back();
        
        return result;
    }
};
