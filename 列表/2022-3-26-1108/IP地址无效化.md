### 代码

```js
var defangIPaddr = function(address) {
    let str = []
    for(let i of address){
        if(i != '.'){
            str.push(i)
        }else{
            str.push('[')
            str.push('.')
            str.push(']')
        }
    }
    return str.join('')
};
```

