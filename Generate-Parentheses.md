# Day-7 Generate Parentheses LeetCode -(22)

Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

Example 1:

Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]

### Code:

```Javascript
var generateParenthesis = function(n) {
    const ans = [];

    const recursive = (i,n,arr,open,close)=>{
        if(open >n) return;
        if(close>open) return; 

        if(i===n*2){
            ans.push(arr.join(""));
            return
        }

        arr.push("(");
        recursive(i+1,n,arr,open+1,close);
        arr.pop();

        arr.push(")");
        recursive(i+1,n,arr,open,close+1);
        arr.pop();
    }

    recursive(0,n,[],0,0);
    return ans;
};
```

![Generate Parentheses](https://user-images.githubusercontent.com/96117746/221183487-9401627c-8127-47eb-b11f-330582e74e46.png)
