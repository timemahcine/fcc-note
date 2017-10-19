## 任务要求
检查回文字符串

如果给定的字符串是回文，返回true，反之，返回false。

如果一个字符串忽略标点符号、大小写和空格，正着读和反着读一模一样，那么这个字符串就是palindrome(回文)。

注意你需要去掉字符串多余的标点符号和空格，然后把字符串转化成小写来验证此字符串是否为回文。

函数参数的值可以为"racecar"，"RaceCar"和"race CAR"。
### 案例

- palindrome("eye") 应该返回一个布尔值
- palindrome("eye") 应该返回 true.
- palindrome("race car") 应该返回 true.
- palindrome("not a palindrome") 应该返回 false.
- palindrome("A man, a plan, a canal. Panama") 应该返回 true.
- palindrome("never odd or even") 应该返回 true.
- palindrome("nope") 应该返回 false.
- palindrome("almostomla") 应该返回 false.
- palindrome("My age is 0, 0 si ega ym.") 应该返回 true.
- palindrome("1 eye for of 1 eye.") 应该返回 false.
- palindrome("0_0 (: /-\ :) 0-0") 应该返回 true.

### 代码
```
function palindrome(str) {
  // 请把你的代码写在这里
  var re=/[\W_]/g;
  var restr=str.replace(re,"").toLowerCase();
  var newstr=restr.split("").reverse().join("");
 return newstr===restr;
}



palindrome("eye");
```

## 思路
- 因为需要忽略大小写和反转，所以要用到`String.toLowerCace`和`Array.reverse`**注意**reverse是针对数组的，所以要将字符串转换成数组再转换为字符串。这需要用到`split`和`join`
- 因为要去掉空格和其他符号用正则表达式`/[\W_]/g`,`\W`表示所有非[0-9a-zA-Z_]
- 因为最后一个案例返回的true也就是连下划线`_`也要替换
- 最后通过比较忽略大小写去掉符号空格后的与进行反转的进行对比，符合回文的返回true