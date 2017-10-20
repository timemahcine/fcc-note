### 任务要求
检查字符串结尾

判断一个字符串(str)是否以指定的字符串(target)结尾。

如果是，返回true;如果不是，返回false。
### 案例
- confirmEnding("Bastian", "n") 应该返回 true.
- confirmEnding("Connor", "n") 应该返回 false.
- confirmEnding("Walking on water and developing software from a specification are easy if both are frozen", "specification") 应该返回 false.
- confirmEnding("He has to give me a new name", "name") 应该返回 true.
- confirmEnding("He has to give me a new name", "me") 应该返回 true.
- confirmEnding("He has to give me a new name", "na") 应该返回 false.
- confirmEnding("If you want to save our world, you must hurry. We dont know how much longer we can withstand the nothing", "mountain") 应该返回 false.

### 代码

#### 我的
```
function confirmEnding(str, target) {
  // 请把你的代码写在这里
 return (str.substr(-target.length) === target);
}

confirmEnding("Bastian", "n");

```
##### 思路
- 原本想的是通过将字符串用`split`分解成数组，但看到案例中不仅有句子也有单词时，就不能这样来做。
- 想到了`substr` 通过获取字符串下标来截取字符串，`substr`支持负值，-1就是倒数第一个，-`target.length`正好对应结尾，如果相等就返回`true`
- 大神的解法和我一致就不贴了