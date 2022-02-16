### 代码

```js
var nextGreaterElement = function(nums1, nums2) {
    let ans = []
    for(let i of nums1){
        let nextmax = -1
        let pan = 0
        for(let j of nums2){
            if(i == j){
                pan = 1
            }
            if(pan && i < j){
                nextmax = j
                break
            }
        }
        ans.push(nextmax)
    }
    return ans
};
```

