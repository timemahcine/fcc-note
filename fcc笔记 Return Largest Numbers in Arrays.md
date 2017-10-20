### 任务要求
找出多个数组中的最大数

右边大数组中包含了4个小数组，分别找到每个小数组中的最大值，然后把它们串联起来，形成一个新数组。

提示：你可以用for循环来迭代数组，并通过arr[i]的方式来访问数组的每个元素。
### 案例
- largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]) 应该返回一个数组
- largestOfFour([[13, 27, 18, 26], [4, 5, 1, 3], [32, 35, 37, 39], [1000, 1001, 857, 1]]) 应该返回 [27,5,39,1001].
- largestOfFour([[4, 9, 1, 3], [13, 35, 18, 26], [32, 35, 97, 39], [1000000, 1001, 857, 1]]) 应该返回 [9, 35, 97, 1000000].

### 代码

#### 我的
```
function largestOfFour(arr) {
  // 请把你的代码写在这里
  var newarr=[];
  for(var i=0;i<arr.length;i++){
    for(var j=0;j<arr[i].length;j++){
      arr[i].sort(function(a,b){
        return  b-a;
      });
    }
    newarr.push(arr[i][0]);
  }
  return newarr;
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);

```

##### 思路
- 通过两次for循环遍历数组，运用sort对每个小数组进行从大到小排序。每次排序完后，将第一个数组元素也就是这个数组内最大的用push压入新数组。

#### Rafase282
```
function largestOfFour(arr) {
  var results = [];
  for (var n in arr) {
      var largestNumber = 0;
      for (var sb in arr[n]) {
          if (arr[n][sb] > largestNumber) {
              largestNumber = arr[n][sb];
          }
      }
    results[n] = largestNumber;
}
  return results;
}
```
##### 思路
- 通过for in遍历数组，通过比较小数组内的数组元素与largestnumber比较如果大于就赋值给大，每次遍历完小数组就刚好得到小数组最大的元素
- 将每次遍历的最大值放入数组，不需要push

#### tips
- 数组遍历中 forin写起来最简单但是实际上效率不然普通for循环，也比优化版for循环差
for(var i=0,len=arr.length;i<len;i++)这种遍历是最优化的，使用临时变量，将长度缓存起来，避免重复获取数组长度，当数组较大时优化效果才会比较明显。