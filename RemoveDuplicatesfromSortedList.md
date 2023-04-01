# Remove Duplicates from Sorted List LeetCode - 83

Given the head of a sorted linked list, delete all duplicates such that each element appears only once. Return the linked list sorted as well.

Example 1:
```
Input: head = [1,1,2]
Output: [1,2]

```

### Code :
```JavaScript
var deleteDuplicates = function(head) {
    if(!head||head.next==null) return head
     const current = head;
    
    while (head !== null) {
        if (head.next !== null && head.val === head.next.val) {
            head.next = head.next.next;
        } else {
            head = head.next;
        }
    }
    
    return current;
};
```
![83](https://user-images.githubusercontent.com/96117746/229322851-c474d26e-ae6c-4bae-8666-fdaf9fe16eb6.png)

