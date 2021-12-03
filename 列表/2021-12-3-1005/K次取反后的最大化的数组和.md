### 代码

注意最小值定义就可以了 `let min = Number.MAX_VALUE`

```js
var largestSumAfterKNegations = function(nums, k) {
    nums.sort((a, b) => a - b)
    let ans = 0
    let min = Number.MAX_VALUE
    for(let i of nums){
        min = Math.min(Math.abs(i),min)
        if(k && i < 0){
            k--
            ans -= i
        }else{
            ans += i
        }
    }
    return k % 2 === 0 ? ans : ans - 2 * min;
};
```

