# Python-Google-Foo.bar

![375CCFBB-71E5-4040-AE2E-A79D9FD04E6E](https://raw.githubusercontent.com/callmarkforIT/Python-Google-Foo.bar/main/foobar.jpg)

## Challenge Level 1:

The cake is round, and decorated with M&Ms in a circle around the edge. But while the rest of the cake is uniform, the M&Ms are not: there are multiple colors, and every minion must get exactly the same sequence of M&Ms. Commander Lambda hates waste and will not tolerate any leftovers, so you also want to make sure you can serve the entire cake.

To help you best cut the cake, you have turned the sequence of colors of the M&Ms on the cake into a string: each possible letter (between a and z) corresponds to a unique color, and the sequence of M&Ms is given clockwise (the decorations form a circle around the outer edge of the cake).

Write a function called solution(s) that, given a non-empty string less than 200 characters in length describing the sequence of M&Ms, returns the maximum number of equal parts that can be cut from the cake without leaving any leftovers.

-- Python cases --
Input:
solution.solution("abcabcabcabc")
Output:
    4

Input:
solution.solution("abccbaabccba")
Output:
    2

## Answer:
Based on the provided information, the function "solution(s)" is solving a problem related to cutting a cake decorated with M&Ms. The cake is round, and the M&Ms are arranged in a circle around the edge. The colors of the M&Ms are represented by letters in the range of 'a' to 'z' in a clockwise sequence. The function takes a string input "s" that represents the sequence of M&Ms on the cake. The goal of the function is to find the maximum number of equal parts that can be cut from the cake without any leftovers. The function should return an integer representing the maximum number of equal parts that can be cut from the cake.

```r{}
def solution(s):
    # Find the length of the string
    n = len(s)
    
    # Iterate through all possible substrings of the input string
    for i in range(1, n+1):
        # Check if the length of the substring divides the length of the input string
        if n % i == 0:
            # Check if all the substrings of the same length are equal
            substring = s[:i]
            if substring * (n // i) == s:
                return (n // i)
    return 1

```

This code first finds the length of the input string "s" and assigns it to the variable "n". Then, it iterates through all possible substrings of the input string, starting with a substring of length 1 and ending with a substring of length "n". For each substring, it checks if the length of the substring divides the length of the input string. If it does, it then checks if all the substrings of the same length are equal by creating a new variable "substring" that is equal to the first substring, and then checks if that substring multiplied by the number of times the substring fits in the input string is equal to the input string. If this is true, the function returns the number of times the substring fits in the input string, which represents the maximum number of equal parts that can be cut from the cake. If the loop completes and no valid substrings are found, the function returns 1.
