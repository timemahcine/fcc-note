### 任务要求
摧毁数组

金克斯的迫击炮！

实现一个摧毁(destroyer)函数，第一个参数是待摧毁的数组，其余的参数是待摧毁的值。
### 案例
- destroyer([1, 2, 3, 1, 2, 3], 2, 3) 应该返回 [1, 1].
- destroyer([1, 2, 3, 5, 1, 2, 3], 2, 3) 应该返回 [1, 5, 1].
- destroyer([3, 5, 1, 2, 2], 2, 3, 5) 应该返回 [1].
- destroyer([2, 3, 2, 3], 2, 3) 应该返回 [].
- destroyer(["tree", "hamburger", 53], "tree", 53) 应该返回 ["hamburger"].

### 代码

#### 我的
```
function destroyer(arr) {

 var tempArguments = arguments;
 return arr.filter(function(entry) {
  for(var i = 1; i< tempArguments.length; i++) {
   if (entry == tempArguments[i]) {
    return false;
   }
  }
  return true;
 });
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);

```

##### 思路
- arguments对象即对应于传递给函数的参数的类数组对象。
- 直接将arguments赋值给tempArguments 转化为数组
- 通过for循环遍arguments对象不断比较第二个参数是否等于第一个参数的某个元素，等于时返回`false`，因为`fliter`的`callback`为`false`就会舍弃这个元素，以此删去所有和第二个参数相同的数组元素，直到遍历到最后一个参数，循环结束。

#### Rafase282
```
function destroyer(arr) {
  var args = Array.prototype.slice.call(arguments);
  args.splice(0,1);
  return arr.filter(function(element) {
    return args.indexOf(element) === -1;
  });
}
```

##### 思路
- 通过`Array.prototype.slice.call`将arguments对象转换为真实数组，我的方法比较不规范。
- 用`splic(0,1)`去掉第一个参数这时`args`只剩下剩余参数
- 用`filter`进行筛选，`args.indexOf(element)` 在对args进行查找，按照arr的元素一个个找，找不到时返回-1，-1===-1=true，就被`fliter`留下，不符合的删去。
- 这种方法的好处是转换为真实数组比较规范``filter`的callback函数也比较简洁。
- 要记住`fliter`的`callback`返回的值为`false`就会舍弃这个元素，`splice`会改变原数组，`splice(start,count)`返回的值是被删去的数组元素。