# 质数
> 质数（Prime number），又称素数，指在大于1的自然数中，除了1和该数自身外，无法被其他自然数整除的数（也可定义为只有1与该数本身两个因数的数）。[来自维基百科](https://zh.wikipedia.org/wiki/%E7%B4%A0%E6%95%B0)

类似于 2、3、5、7、11、17都是质数，那么根据定义我们将其用JavaScript来实现：求莫个范围内的所有质数。

```javascript
 function getPrimeNumber(n){
    var result = [];

    if(n <= 1) return result;

    for(var i = 2; i <= n; i++){
        var arr = [];

        for(var j = 1; j <= i; j++){
            var num = i / j;

            if(i % j === 0){
                arr.push( num );
            }
        }

        if(arr.length === 2){
            result.push( i );
        }
    }

    return result;
 }
```
运行函数`getPrimeNumber`求得`100`以内的所有质数：

```javascript
> getPrimeNumber(100)

> [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97]
```