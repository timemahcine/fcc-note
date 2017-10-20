## 任务要求
翻转字符串

先把字符串转化成数组，再借助数组的reverse方法翻转数组顺序，最后把数组转化成字符串。

你的结果必须得是一个字符串

- reverseString("hello") 应该返回一个字符串
- reverseString("hello") 应该返回 "olleh".
- reverseString("Howdy") 应该返回 "ydwoH".
- reverseString("Greetings from Earth") 应该返回 "htraE morf sgniteerG".

### 代码部分
```
function reverseString(str) {
  // 请把你的代码写在这里
  var arr=str.split('').reverse();
  str=arr.join('');
  return str;
}

reverseString("Greetings from Earth");

```
### 思路
- 先将字符串通过split切割成一个个形成一个数组（字符串中的空格也可以被放入数组）
- 通过reverse反转数组元素
- 通过join将数组重新组成字符串
