## Frequency Counter

Frequency Counter - validAnagram
Given two strings, write a function to determine if the second string is an anagram of the first. An anagram is a word, phrase, or name formed by rearranging the letters of another, such as cinema, formed from iceman.

Examples:

validAnagram('', '') // true
validAnagram('aaz', 'zza') // false
validAnagram('anagram', 'nagaram') // true
validAnagram("rat","car") // false) // false
validAnagram('awesome', 'awesom') // false
validAnagram('amanaplanacanalpanama', 'acanalmanplanpamana') // false
validAnagram('qwerty', 'qeywrt') // true
validAnagram('texttwisttime', 'timetwisttext') // true

## Solution

```
function validAnagram(str1, str2){

    if(str1.length!==str2.length) return false;

    let strKeys = {};
    for(let key in str1){
        let letter = str1[key];
        strKeys[letter] ? strKeys[letter]+=1: strKeys[letter]1;
        <!-- strKeys[letter] = (strKeys[letter] ?? 0)+1 -->
    }
    for( let key in str2){
      let letter = str2[key];
      if(strKeys[letter] === undefined || strKeys[letter] <=0)
      return false
      strKeys[letter]--;
    }
    return true
}
```
