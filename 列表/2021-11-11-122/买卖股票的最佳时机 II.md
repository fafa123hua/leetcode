### 贪心

只要前方小于当前值就累加他们的差，例如：

输入: prices = [1,2,3,4,5]，在第 1 天（股票价格 = 1）的时候买入，在第 5 天 （股票价格 = 5）的时候卖出, 这笔交易所能获得利润 = 5-1 = 4 。

但是按照我们的思路就是当prices[i]比前一位大，就累加差，效果就是2-1=1，3-2=1，4-3=1，5-4=1。ans最终值也为4，这样通过贪心的思想从局部最优达到全局最优。


```js
var maxProfit = function(prices) {
    let ans = 0
    for(let i = 1; i < prices.length; i++){
        if(prices[i - 1] < prices[i])
        ans += prices[i] - prices[i - 1]
    }
    return ans
};
```

