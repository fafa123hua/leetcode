### 两次循环思路

```js
var getHint = function(secret, guess) {
    let bulls = 0, cows = 0;
    const n = secret.length, cntsS = new Map(), cntsG = new Map();
    for(let i=0;i<n;i++){
        const s = secret.charAt(i), g = guess.charAt(i);
        if(s == g)
            bulls++;
        else{
            if(cntsS.has(s))
                cntsS.set(s, cntsS.get(s) + 1);
            else
                cntsS.set(s, 1);
            if(cntsG.has(g))
                cntsG.set(g, cntsG.get(g) + 1);
            else
                cntsG.set(g, 1);
        }
    }
    for(const k of cntsS.keys()){
        if(cntsG.has(k))
            cows += Math.min(cntsS.get(k), cntsG.get(k));
    }
    return `${bulls}A${cows}B`
};

```



### 一次循环解决

类似于计数排序的思路。把0作为分界线进行操作。

例如现在`guess[i]`的值为5，`hash[guess[i]]++`，此时5出现次数为1；

当再次进入判断若`secret[i]`此时为于5，`hash[secret[i]]` 先判断再自减，大于0，n++，次数自减归零

```js
var getHint = function(secret, guess) {
    let hash = Array(10).fill(0)
    let m = n = 0
    for(let i in secret){
        if(secret[i] == guess[i]){
            m++
        }else{
            if(hash[guess[i]]++ < 0) n++  
            if(hash[secret[i]]-- > 0) n++
        }
    }
    return `${m}A${n}B`
};
```

