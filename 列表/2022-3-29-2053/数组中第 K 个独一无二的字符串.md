### 代码

```js
var kthDistinct = function(arr, k) {
    let hash = new Map()
    for(let i of arr){
        hash.set(i, hash.get(i) + 1 || 1)
    }
    for(let i of arr){
        if(hash.get(i) == 1){
            if(k == 1){
                return i
            }
            k--
        }
    }
    return ''
};
```

