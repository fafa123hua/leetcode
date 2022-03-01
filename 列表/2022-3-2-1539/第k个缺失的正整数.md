### 代码

```js
var findKthPositive = function(arr, k) {
    for(let i of arr){
        if(i <= k){
            k++
        }
    }
    return k
};
```

