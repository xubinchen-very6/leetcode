### 买卖股票的最佳时机 II
> 没太搞明白这题的意思

> 假设有一个数组，它的第 i 个元素是一个给定的股票在第 i 天的价格。
设计一个算法来找到最大的利润。你可以完成尽可能多的交易（多次买卖股票）
然而，你不能同时参与多个交易（你必须在再次购买前出售股票）

```
input  = [2,1,2,0,1]
1<2不操作，2>1卖-->赚1，0<2不操作，1>0卖-->赚1
output= 1

```

__以为比较复杂需要动态规划求解 然而并不用__
#### 数组操作
```
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        days = len(prices)
        money = 0
        for i in range(days-1):
            if prices[i]<prices[i+1]:
                money = money+(prices[i+1]-prices[i])
        return money
```