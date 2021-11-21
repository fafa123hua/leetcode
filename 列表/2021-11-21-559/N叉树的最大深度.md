### dfs代码

```js
var maxDepth = function(root) {
    let ans = 0
    let x = 0
    var dfs = function(root){
        if(!root){
            return
        }
        x++
        for(let children of root.children){
            dfs(children)
        }
        ans = Math.max(ans,x)
        x--
    }
    dfs(root)
    return ans
};
```