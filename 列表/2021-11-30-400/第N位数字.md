### 代码

找规律模拟

```js
let cur = 1, base = 9;
    while(n > cur * base){
        n -= cur * base;
        cur++;
        base*=10;
        if(Number.MAX_SAFE_INTEGER / base < cur){
            break;
        }
    }
    n--;
    const num = Math.pow(10,cur - 1) + Math.floor(n / cur), idx = n % cur;
    return Math.floor(num / Math.pow(10,cur - 1 - idx)) % 10;

```

