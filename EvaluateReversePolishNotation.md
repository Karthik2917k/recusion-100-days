# Evaluate Reverse Polish Notation

You are given an array of strings tokens that represents an arithmetic expression in a Reverse Polish Notation.

Evaluate the expression. Return an integer that represents the value of the expression.

Note that:

The valid operators are '+', '-', '*', and '/'.
Each operand may be an integer or another expression.
The division between two integers always truncates toward zero.
There will not be any division by zero.
The input represents a valid arithmetic expression in a reverse polish notation.
The answer and all the intermediate calculations can be represented in a 32-bit integer.
 

Example 1:
```
Input: tokens = ["2","1","+","3","*"]
Output: 9
Explanation: ((2 + 1) * 3) = 9
```

### Code :

```Javascript
var evalRPN = function(tokens) {
    const stack = [];
    const operations = {
        "+":(n1,n2)=>n1+n2,
        "-":(n1,n2)=>n1-n2,
        "*":(n1,n2)=>n1*n2,
        "/":(n1,n2)=>Math.trunc(n1/n2)
    }

    for(token of tokens){
        if(operations[token]){
            let n2 = stack.pop();
            let n1 = stack.pop();
            stack.push(operations[token](n1,n2));
        }else{
            stack.push(parseInt(token));
        }
    }
    return stack.pop();
};
```

![150](https://user-images.githubusercontent.com/96117746/224695263-f55d70ef-6719-4ee9-8bc4-ba5f9611107e.png)
