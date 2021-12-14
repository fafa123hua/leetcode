### 代码

之后补一个优先队列的

```js
var scheduleCourse = function(courses) {
    courses.sort((a,b) => a[1]-b[1])
    const ans = []
    let learning= 0 
    for(let i = 0; i < courses.length; i++){
        if(learning + courses[i][0] <= courses[i][1]){
            learning += courses[i][0]
            ans.push(courses[i][0])
            ans.sort((a, b) => a - b)
            continue
        }
        if(courses[i][0] <= ans[ans.length - 1]){
            let out = ans.pop()
            learning -= out
            learning += courses[i][0]
            ans.push(courses[i][0])
            ans.sort((a, b) => a - b)
            continue
        }
    }
    return ans.length
};
```

