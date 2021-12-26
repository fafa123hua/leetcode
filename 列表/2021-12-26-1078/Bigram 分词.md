### 代码

简单暴力

```js
var findOcurrences = function(text, first, second) {
    let ans = []
    let arr = text.split(/[ ]+/)
    for(let i = 0; i < arr.length; i++){
        if(arr[i] == first){
            if(i + 1 < arr.length && arr[i+1] == second){
                if(i + 2 < arr.length){
                    ans.push(arr[i + 2])
                }
            }
        }
        
    }
    return ans
};
```

