### 代码

```js
var repeatedNTimes = function(nums) {
    let hash = new Map()
    for(let i of nums){
        hash.set(i, hash.get(i) + 1 || 1)
        if(hash.get(i) >= 2){
            return i
        }
    }
};
```

