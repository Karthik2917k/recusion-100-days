# Ugly Number II

An ugly number is a positive integer whose prime factors are limited to 2, 3, and 5.

Given an integer n, return the nth ugly number.

 
Example 1:
```
Input: n = 10
Output: 12
Explanation: [1, 2, 3, 4, 5, 6, 8, 9, 10, 12] is the sequence of the first 10 ugly numbers.
```

### Code :
```JavaScript
 var nthUglyNumber = function(n) {
    let n1=0,n2=0,n3 = 0;
    let res = [1];
    for(let i=1;i<n;i++){
        let v1 = res[n1] *2;
        let v2 = res[n2] *3;
        let v3 = res[n3] *5;

        let min = Math.min(v1,v2,v3);

        v1 === min && n1++;
        v2 === min && n2++;
        v3 === min && n3++;
        res.push(min);
    }

    return res.pop();
};
```
![264](https://user-images.githubusercontent.com/96117746/229330039-6c43dced-b285-4753-8bac-a4ca9e41d34b.png)
