Sum of Digits of String After Convert LeetCode - 1945

You are given a string s consisting of lowercase English letters, and an integer k.

First, convert s into an integer by replacing each letter with its position in the alphabet (i.e., replace 'a' with 1, 'b' with 2, ..., 'z' with 26). Then, transform the integer by replacing it with the sum of its digits. Repeat the transform operation k times in total.

For example, if s = "zbax" and k = 2, then the resulting integer would be 8 by the following operations:

Convert: "zbax" ➝ "(26)(2)(1)(24)" ➝ "262124" ➝ 262124
Transform #1: 262124 ➝ 2 + 6 + 2 + 1 + 2 + 4 ➝ 17
Transform #2: 17 ➝ 1 + 7 ➝ 8
Return the resulting integer after performing the operations described above.

 

Example 1:
```
Input: s = "iiii", k = 1
Output: 36
Explanation: The operations are as follows:
- Convert: "iiii" ➝ "(9)(9)(9)(9)" ➝ "9999" ➝ 9999
- Transform #1: 9999 ➝ 9 + 9 + 9 + 9 ➝ 36
Thus the resulting integer is 36.
```

## Code 

```Javascript
  var getLucky = function(s, k) {
    const obj = {
        'a':1,'b':2,'c':3,'d':4,'e':5,'f':6,'g':7,'h':8,'i':9,'j':10,
        'k':11,'l':12,'m':13,'n':14,'o':15,'p':16,'q':17,'r':18,'s':19,
        't':20,'u':21,'v':22,'w':23,'x':24,'y':25,'z':26
    }
    let convert = '';
    let arr = s.split('');
    console.log(arr)
    for(let i=0;i<arr.length;i++){
        convert += obj[arr[i]];
    }
    console.log(convert);
    let narr = convert.split('');
    let count = 0;
    while(count<k){
        let total = 0;
        for(let i = 0;i<narr.length;i++){
            total+=parseInt(narr[i]);
        }
        total = total.toString();
        narr = total.split('');
        count++;
    }
    return narr.join('')
};
```

![SumofDigitsofStringafterConvert](https://user-images.githubusercontent.com/96117746/221867537-16a3bd3f-704f-4a42-ada0-dd2e5fdf99ff.png)
