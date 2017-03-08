# 九九乘法表
> 九九乘法表是我们从小就开始了解的，一一得一、一二得二......（是不是能够勾起你美好的回忆）

下面这张图就是九九乘法表的，那么咱们就来玩玩用JavaScript来写出这样一个九九乘法表吧。:smiley:

![图片](https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1488960559&di=716e34941099dd6aee667998cbb6e5e4&src=http://www.51wendang.com/pic/c6299afefe74d56f93e61d6f/1-461-jpg_6_0_______-866-0-0-866.jpg)

从图片中我们不难看出，嵌套两层循环就能打印出来了。

```javascript
function createMultiTable(){
    for(var i = 1; i <= 9; i++){
        for(var j = 1; j <= i; j++){
            var num = i * j;
            var str = i + '*' + j + '=' + num;

            console.log(str);
        }
    }
}
```

运行结果：
```javascript
> createMultiTable()

> 1*1=1
> 2*1=2
> 2*2=4
> .
> .
> .
> 9*9=81
```

虽然打印出来了，但是没有把展示样式成表格，那么我们来改进下：

```javascript
function createMultiTable(){
    for(var i = 1; i <= 9; i++){
        var str = '';

        for(var j = 1; j <= i; j++){
            var num = i * j;
            
            str += j + '*' + i + '=' + num + '  ';
            
            //结果小余10,多补空格来保证上下对齐
            if(num < 10){
                str += ' ';
            }
        }

        str += '\n';
        console.log(str)
    }
}
```

运行结果：
```javascript
> createMultiTable()

> 1*1=1   
> 1*2=2   2*2=4   
> 1*3=3   2*3=6   3*3=9   
> 1*4=4   2*4=8   3*4=12  4*4=16  
> 1*5=5   2*5=10  3*5=15  4*5=20  5*5=25  
> 1*6=6   2*6=12  3*6=18  4*6=24  5*6=30  6*6=36  
> 1*7=7   2*7=14  3*7=21  4*7=28  5*7=35  6*7=42  7*7=49  
> 1*8=8   2*8=16  3*8=24  4*8=32  5*8=40  6*8=48  7*8=56  8*8=64  
> 1*9=9   2*9=18  3*9=27  4*9=36  5*9=45  6*9=54  7*9=63  8*9=72  9*9=81  
```

以上纯属无聊之作，看客勿喷！:stuck_out_tongue_closed_eyes: