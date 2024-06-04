### Greatest Common Divisor of Strings

For two strings s and t, we say "t divides s" if and only if s = t + t + t + ... + t + t (i.e., t is concatenated with itself one or more times).

Given two strings str1 and str2, return the largest string x such that x divides both str1 and str2.

Example 1:

Input: str1 = "ABCABC", str2 = "ABC"
Output: "ABC"
Example 2:

Input: str1 = "ABABAB", str2 = "ABAB"
Output: "AB"
Example 3:

Input: str1 = "LEET", str2 = "CODE"
Output: ""

### Solution

```
/**
 * @param {string} str1
 * @param {string} str2
 * @return {string}
 */
var gcdOfStrings = function(str1, str2) {
     if(str1 + str2 !== str2+ str1) return ''

     let size1 = str1.length;
     let size2 = str2.length;

     while(size2)
     {
        let temp = size2;
        size2 = size1%size2;
        size1 = temp;
     }
     return str1.substring(0,size1)
};
```
