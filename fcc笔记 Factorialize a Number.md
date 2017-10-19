## 任务要求
计算一个整数的阶乘

如果用字母n来代表一个整数，阶乘代表着所有小于或等于n的整数的乘积。

阶乘通常简写成 n!

例如: 5! = 1 * 2 * 3 * 4 * 5 = 120

### 代码
```
function factorialize(num) {
  // 请把你的代码写在这里
  var sum=1;
  for(var i=2;i<=num;i++){
    sum*=i;
  }
  return sum;
}


factorialize(5);
```
### 思路
- 因为该任务要进行阶乘运算，乘的次数＝数值，因此运用for循环
- sum初始值＝１，每次乘的数从２开始递增，运用*=改变sum的值，当i=sum时完成阶乘，返回sum