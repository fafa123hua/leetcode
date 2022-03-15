### 代码

```js
var reverseWords = function(s) {
    let str = s.split(' ')
    let ans = []
    for(let i = 0; i < str.length; i++){
        let der = [], j = str[i].length
        while(j--){
            der.push(str[i][j])
        }
        ans.push(der.join(''))
    }
    return ans.join(' ')
};
```

