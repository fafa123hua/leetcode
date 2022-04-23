### 代码

```js
var checkRecord = function(s) {
    let a = 0
    let l = 0
    for(let i of s){
        if(i == 'A'){
            a++
            l = 0
        }else if(i == 'L'){
            l++
        }else{
            l = 0
        }
        if(l == 3 || a == 2){
            return false
        }
    }
    return true
};
```

