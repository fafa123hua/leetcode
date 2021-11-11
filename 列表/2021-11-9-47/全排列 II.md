### dfs回溯剪枝

核心代码，如果要对树层中前一位去重，就用`used[i - 1] == false`，如果要对树枝前一位去重用`used[i - 1] == true`。

```js
if(i > 0 && nums[i] == nums[i - 1] && !use[i - 1]){continue}
```

#### 代码

```js
var permuteUnique = function(nums) {
    nums.sort((a,b) => a - b)
    let path = []
    let ans = []
    function dfs (use){
        if(path.length == nums.length){
            ans.push(path.slice())
            return 
        }
        for(let i = 0; i < nums.length; i++){
            if(i > 0 && nums[i] == nums[i - 1] && !use[i - 1]){
                continue
            }
            if(!use[i]){
                use[i] = true
                path.push(nums[i])
                dfs(use)
                path.pop()
                use[i] =false
            }
        }
    }
    dfs([])
    return ans
};
```

