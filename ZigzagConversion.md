# Zigzag Conversion Leetcode 6

The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)
```
P   A   H   N
A P L S I I G
Y   I   R
```
And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

string convert(string s, int numRows);
 

Example 1:
 ```
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```

### Code :

```Javascript
var convert = function(s, numRows) {
    const res = [];

    if(numRows<2){
        return s;
    }

    for(let i=0;i<numRows;i++){
        let j=i;
        while(j<s.length){
            res.push(s[j]);

            if(i!==0 && i!==numRows-1){
                const k = (numRows-i)*2-1-1+j;
                if(k<s.length){
                    res.push(s[k]);
                }
            }

            j +=numRows * 2-1-1;
        }
    }
    return res.join('');
};
```
![6](https://user-images.githubusercontent.com/96117746/229323435-c2aedc91-6491-4f74-9a99-c3489a7a167a.png)
