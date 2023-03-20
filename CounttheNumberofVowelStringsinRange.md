# Count the Number of Vowel Strings in Range LeetCode 2586

You are given a 0-indexed array of string words and two integers left and right.

A string is called a vowel string if it starts with a vowel character and ends with a vowel character where vowel characters are 'a', 'e', 'i', 'o', and 'u'.

Return the number of vowel strings words[i] where i belongs to the inclusive range [left, right].

 

Example 1:
```
Input: words = ["are","amy","u"], left = 0, right = 2
Output: 2
Explanation: 
- "are" is a vowel string because it starts with 'a' and ends with 'e'.
- "amy" is not a vowel string because it does not end with a vowel.
- "u" is a vowel string because it starts with 'u' and ends with 'u'.
The number of vowel strings in the mentioned range is 2.
```

## Code : 
```JavaScript
const VOWELS = ['a', 'e', 'i', 'o', 'u'];

var vowelStrings = function(words, left, right) {
    let count = 0;

    for(let i=left; i<=right; i++) {
        const word = words[i];

        const firstLetter = word[0];
        const lastLetter = word[word.length - 1];

        if(VOWELS.includes(firstLetter) && VOWELS.includes(lastLetter)) {
            count += 1
        }
    }

    return count;
};
```

![2586](https://user-images.githubusercontent.com/96117746/226330754-69389b55-565a-4d42-8f62-46a52b85067e.png)
