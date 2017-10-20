### 任务要求
截断字符串

（用瑞兹来截断对面的退路）

如果字符串的长度比指定的参数num长，则把多余的部分用...来表示。

切记，插入到字符串尾部的三个点号也会计入字符串的长度。

但是，如果指定的参数num小于或等于3，则添加的三个点号不会计入字符串的长度。
### 案例
- truncate("A-tisket a-tasket A green and yellow basket", 11) 应该返回 "A-tisket...".
- truncate("Peter Piper picked a peck of pickled peppers", 14) 应该返回 "Peter Piper...".
- truncate("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length) 应该返回 "A-tisket a-tasket A green and yellow basket".
- truncate("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length + 2) 应该返回 "A-tisket a-tasket A green and yellow basket".
- truncate("A-", 1) 应该返回 "A...".
- truncate("Absolutely Longer", 2) 应该返回 "Ab...".

### 代码

#### 我的
```
function truncate(str, num) {
  
  if(num <= 3){
    str = str.slice(0,num)+'...';
  }else if(str.length > num){
    str = str.slice(0,num-3)+'...';
  }
  return str;
}
truncate("A-tisket a-tasket A green and yellow basket", 11);
```
##### 思路
- 直接通过num是否大于等于3，如果是就通过slice选取从0到num下标，加上`...`

#### Rafase282
```
function truncate(str, num) {
    var truncd = '';
    if (str.length > num) {
        truncd = str.slice(0,num-3) + '...';
        return truncd;
    }
    return str;
}
```
##### 思路
- 