### 代码

```js
var sumZero = function(n) {
    let ans = []
    if(n == 1){
        return [0]
    }
    let z = 1
    let f = -1
    while(n > 1){
        n -= 2
        ans.push(z,f)
        z++
        f--
    }
    if(n == 1){
        ans.push(0)
    }
    return ans
};
```

