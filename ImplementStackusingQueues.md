# Implement Stack using Queues LeetCode 225
Implement a last-in-first-out (LIFO) stack using only two queues. The implemented stack should support all the functions of a normal stack (push, top, pop, and empty).

Implement the MyStack class:

void push(int x) Pushes element x to the top of the stack.
int pop() Removes the element on the top of the stack and returns it.
int top() Returns the element on the top of the stack.
boolean empty() Returns true if the stack is empty, false otherwise.

Example 1:
```
Input
["MyStack", "push", "push", "top", "pop", "empty"]
[[], [1], [2], [], [], []]
Output
[null, null, null, 2, 2, false]

Explanation
MyStack myStack = new MyStack();
myStack.push(1);
myStack.push(2);
myStack.top(); // return 2
myStack.pop(); // return 2
myStack.empty(); // return False
```
### Code 
```Javascript
let a 
var MyStack = function() {
    a = []
};
MyStack.prototype.push = function(x) {
    a.push(x)
};
MyStack.prototype.pop = function() {
    return a.pop()
};
MyStack.prototype.top = function() {
    return a[a.length -1]
};
MyStack.prototype.empty = function() {
    return a.length === 0
};
```

![image](https://user-images.githubusercontent.com/96117746/224561282-807f5cd6-d098-4b0b-8519-313ba1838cc8.png)
