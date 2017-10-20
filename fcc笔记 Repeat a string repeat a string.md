### 任务要求
重复输出字符串

（重要的事情说3遍）

重复一个指定的字符串 num次，如果num是一个负数则返回一个空字符串。

### 案例
- repeat("*", 3) 应该返回 "***".
- repeat("abc", 3) 应该返回 "abcabcabc".
- repeat("abc", 4) 应该返回 "abcabcabcabc".
- repeat("abc", 1) 应该返回 "abc".
- repeat("*", 8) 应该返回 "********".
- repeat("abc", -2) 应该返回 "".

### 代码

#### 我的
```
function repeat(str, num) {
  // 请把你的代码写在这里
 
  var ystr="";
  for(var i=0;i<num;i++)
    { 
    ystr+=str;
    }
    return ystr;
    
}

repeat("abc", 3);
```
##### 思路
- 用for循环，循环每重复一次，计数器i+1，当num>i时循环结束输出
- 

#### Rafase282
```
function repeat(str, num) {
    var accumulatedStr = "";
    while (num > 0) {
        accumulatedStr += str;
        num--;
    }
    return accumulatedStr;
}
```
##### 思路
- rafase直接用while循环，循环一次num-1，num=0循环结束，更加简洁