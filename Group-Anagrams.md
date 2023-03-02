Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 

Example 1:
```
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```

## Code :
```Javascript
var groupAnagrams = function(strs) {
    const sorted = strs.map(word=>word.split("").sort().join(""));
    const hash = {};

    for(let i=0;i<strs.length;i++){
        if(!hash[sorted[i]]){
            hash[sorted[i]]=[strs[i]];
        }
        else{
            hash[sorted[i]].push(strs[i])
        }
    }
    return Object.values(hash)
};
```

![Group Anagrams](https://user-images.githubusercontent.com/96117746/222437767-3e48f5c2-4a05-4028-b282-f46548cb7755.png)
