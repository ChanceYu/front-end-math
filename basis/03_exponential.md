# 科学计数法
> 这是一种记数的方法。把一个数字记为 a×10^n 的形式（1≤&#124;a&#124;<10，n为整数），这种记数法叫做科学记数法。例如 19971400000000=1.99714×10^13。计算器或电脑表达 10 的幂是一般是用 E 或 e，也就是 1.99714E13=19971400000000。[百度百科](http://baike.baidu.com/link?url=ceNgXqWhsqOKhO4v-WnTWC5byHTmOEjHRqVau_eCMgldqda1JroARITHCXGkV1y_Q4z4BEQ9mPJF8oMArPZdf18474YT065TO76QJYXlH-tSwbW0ponAnz-icZrGQM7XNGsTcHg3xZzi0U8sqM6ZSXu6jPqcyvV9Zvg4Iso7FizUQrNOgvYpnCshajS-u9MMjPzholwJ9R8WXh_H7USPYSKrKXiGekzr4m0pC_kG7JK)

而在JavaScript中有一个方法能将数字转化为科学计数法，那就是[toExponential](http://www.w3school.com.cn/jsref/jsref_toexponential.asp)。

该方法可把对象的值转换成指数计数法。`NumberObject.toExponential(num)`中的参数`num`规定指数计数法中的小数位数，是 0 ~ 20 之间的值，包括 0 和 20，有些实现可以支持更大的数值范围。如果省略了该参数，将使用尽可能多的数字。

例如：
```javascript
var num = 123456;

num.toExponential() //"1.23456e+5"
num.toExponential(1) //"1.23e+5"
```

反过来，将一个科学计数法的数字转化为普通数字：

```javascript
var eNum = "1.23456e+5";

Number(eNum) //123456
```