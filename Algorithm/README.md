## 异或算法筛选：
- 根据异或运算的特点，相同的数字经过异或运算后结果为0，除单独出现一次的数字外，其他数字都是出现两次的，那么这些数字经过异或运算后结果一定是0
```
4^1^2^1^2 = 4 
 4^1 = 5
1^2^1^2=0
```
## 贪心算法(JS):
```
var res = 0;
    for(var i=0;i<prices.length-1;i++){
        if(prices[i+1] > prices[i]){
            res += prices[i+1] - prices[i]
        }
    }
return res

```
