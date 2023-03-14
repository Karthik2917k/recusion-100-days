# Simplyfy Path

Given a string path, which is an absolute path (starting with a slash '/') to a file or directory in a Unix-style file system, convert it to the simplified canonical path.

In a Unix-style file system, a period '.' refers to the current directory, a double period '..' refers to the directory up a level, and any multiple consecutive slashes (i.e. '//') are treated as a single slash '/'. For this problem, any other format of periods such as '...' are treated as file/directory names.

The canonical path should have the following format:

The path starts with a single slash '/'.
Any two directories are separated by a single slash '/'.
The path does not end with a trailing '/'.
The path only contains the directories on the path from the root directory to the target file or directory (i.e., no period '.' or double period '..')
Return the simplified canonical path.

Example 1

```
Input: path = "/home/"
Output: "/home"
Explanation: Note that there is no trailing slash after the last directory name.
```

## Code 
```Javascript
var simplifyPath = function(path) {
    const stack = [];
    let arr = path.split("/").filter(el=>el!==".").filter(el=>el!=="");
    console.log(arr)
    for(let path of arr){
        if(path===".."){
            stack.pop();
        }else{
            stack.push(path)
        }
        console.log(stack)
    }
    return "/"+stack.join("/");
};
```

![image](https://user-images.githubusercontent.com/96117746/224998743-5bff7fb2-f9d3-4ce0-9627-e5e1d9a13692.png)
