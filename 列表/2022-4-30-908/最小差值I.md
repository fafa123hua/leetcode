### 代码

```js
var smallestRangeI = function(nums, k) {
    let max = nums[0],min = nums[0]
    for(let i of nums){
        max = Math.max(i, max)
        min = Math.min(i, min)
    }
    return Math.max(0, max - min - 2 * k)
};
```

