 Letter Case Permutation leetCode - 784
 
 Given a string s, you can transform every letter individually to be lowercase or uppercase to create another string.

Return a list of all possible strings we could create. Return the output in any order.

Example

```
Input: s = "a1b2"
Output: ["a1b2","a1B2","A1b2","A1B2"]
```

## Code
```Javascript
var letterCasePermutation = function(s) {

    const allPermutaions = [];
    const letters = s.split("");

    function recur(i){

        if(i == s.length){
            allPermutaions.push(letters.join(""));
            return;
        }

        let AASCICode = s.charCodeAt(i);
        if(AASCICode>=48 && AASCICode <= 57){
            recur(i+1);
        } else{
            letters[i] = letters[i].toLowerCase();
            recur(i+1);
            letters[i] = letters[i].toUpperCase();
            recur(i+1);
        }
    }
    recur(0);
    return allPermutaions;
};
```

![image](https://user-images.githubusercontent.com/96117746/223733549-18d767fd-4e39-4836-a2dd-afdbfa03c4c4.png)
