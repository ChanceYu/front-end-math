# 整数
> 整数（Integer），分为：正整数、零与负整数，它是一个无限集合。

既然知道了概念，那判断一个数是不是整数也就有点头绪了。

#### 方法一：
根据函数`parseInt(string, radix)`

```javascript
function isInteger(n){
    return parseInt(n, 10) === n;
}
```
运行函数`isInteger`测试：

```javascript
> isInteger(8)
> true

> isInteger(8.1)
> false

> isInteger(-8.1)
> false
```
一切看起来多美完美，那么再来测试：

```javascript
> isInteger(8888888888888888888888)
> 
```
给你短暂的几秒思考下结果...... 你就会发现上面的结果竟然是`false`，这是怎么回事呢？
原因是函数`parseInt`会将第一个参数自动转为科学计数法的数字，数字 8888888888888888888888 用科学计数法表示为 8.888888888888889e+21，最后的结果也就导致不相等了。关于科学计数法可以参考我的一篇文章[科学计数法](03_exponential.md)。上面的方法也是有缺陷的。

#### 方法二：
判断数据类型，然后求余数看看能不能被1整除，是的话就是整数。

```javascript
function isInteger(n){
    return typeof n === 'number' && n % 1 === 0;
}
```
运行函数`isInteger`测试：

```javascript
> isInteger(8)
> true

> isInteger(8.1)
> false

> isInteger(-8.1)
> false

> isInteger(8888888888888888888888)
> true
```

#### 方法三：
根据`Math.ceil`、`Math.floor`、`Math.round`方法来判断

```javascript
function isInteger(n){
    return typeof n === 'number' && Math.ceil(n) === n;
}
```
测试结果也是妥妥的~