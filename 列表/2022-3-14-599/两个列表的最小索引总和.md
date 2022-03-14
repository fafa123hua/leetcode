### 代码

```js
var findRestaurant = function(list1, list2) {
    let ans = [], min = Number.MAX_VALUE
    let hash = new Map()
    for(let i = 0; i < list1.length; i++){
        hash.set(list1[i], i)
    }
    for(let i = 0; i < list2.length; i++){
        if(hash.has(list2[i]) && i + hash.get(list2[i]) == min){
            ans.push(list2[i])
        }else if(i + hash.get(list2[i]) < min){
            ans = []
            min = i + hash.get(list2[i])
            ans.push(list2[i])
        }else{
            continue
        }
    }
    return ans
};
```

