### 代码

```js
var postorder = function(root) {
    const ans = []
    hap(root, ans)
    return ans
};
var hap = function(root, ans){
    if(root == null){
        return 
    }
    for(let i of root.children){
        hap(i, ans)
    }
    ans.push(root.val)
} 
```

