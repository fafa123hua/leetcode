### 代码

```js
var arrayPairSum = function(nums) {
    nums.sort((a,b) => a - b)
    let ans = 0
    for(let i = 0 ; i < nums.length; i += 2){
        ans += Math.min(nums[i],nums[i + 1])
    }
    return ans
};
```

