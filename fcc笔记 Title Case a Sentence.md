### 任务要求

句中单词首字母大写

确保字符串的每个单词首字母都大写，其余部分小写。

像'the'和'of'这样的连接符同理。

### 案例
- titleCase("I'm a little tea pot") 应该返回一个字符串
- titleCase("I'm a little tea pot") 应该返回 "I'm A Little Tea Pot".
- titleCase("sHoRt AnD sToUt") 应该返回 "Short And Stout".
- titleCase("HERE IS MY HANDLE HERE IS MY SPOUT") 应该返回 "Here Is My Handle Here Is My Spout".

### 代码

#### 我的
```
function titleCase(str) {  
    //将字符串分解为数组并将其小写化  
    var convertToArray = str.toLowerCase().split(" ");  
  
    for (var i = 0; i < convertToArray.length; i++) {  
        var char = convertToArray[i].charAt(0);  
        //使用 replace()方法将数组中的每个首字母大写化  
        convertToArray[i] = convertToArray[i].replace(char,  
            char.toUpperCase());  
    }  
    return convertToArray.join(" ");  
}  

titleCase("HERE IS MY HANDLE HERE IS MY SPOUT");

```
##### 思路
-通过`split`与`toLowerCase`将字符串分解为数组小写
- `chartAt(0)`取到每个数组元素的第一个字母,运用`replace`替换首字母
- 通过`join`重新组成字符串


#### Rafase282
```
String.prototype.replaceAt = function(index, character) {
    return this.substr(0, index) + character + this.substr(index+character.length);
};


function titleCase(str) {
    var newTitle = str.split(' ');
    var updatedTitle = [];
    for (var st in newTitle) {
        updatedTitle[st] = newTitle[st].toLowerCase().replaceAt(0, newTitle[st].charAt(0).toUpperCase());
    }
    return updatedTitle.join(' ');
}
```
##### 思路

- 直接写一个`replaceAt`方法给String类，通过`substr`抽取首字母　替换
- z最后将数组重新转换为字符串
- 这个方法个人感觉有些麻烦


#### for循环
```
var a = 'Hi, my name\'s Han Meimei, a SOFTWARE engineer';  
  
//for循环  
function titleCase(s) {  
    var i, ss = s.toLowerCase().split(/\s+/);  
    for (i = 0; i < ss.length; i++) {  
        ss[i] = ss[i].slice(0, 1).toUpperCase() + ss[i].slice(1);  
    }  
    return ss.join(' ');  
}  
console.log(titleCase(a)); 
```
##### 思路
- 通过for循环遍历数组，用`slice`找到首字母改为大写加上后面的字母
- 最后再转换为字符串

#### 正则＋replace
```
//正则+replace  
function titleCase2(s) {  
    return s.toLowerCase().replace(/\b([\w|']+)\b/g, function(word) {  
        //return word.slice(0, 1).toUpperCase() + word.slice(1);  
        return word.replace(word.charAt(0), word.charAt(0).toUpperCase());  
    });  
}  
console.log(titleCase2(a));  
```

##### 思路
- 运用正则找出首字母而不是将字符串转为数组

#### for in遍历循环
```
function titleCase(str) {
	str = str.toLowerCase().split(' ');
  	for (var i in str) { 
  	str[i] = str[i].replace(str[i].charAt(0), str[i].charAt(0).toUpperCase());
  	 }; 
  	 return str.join(' '); 
}


  titleCase("hello world");
```
##### 思路
- 主要就是通过for in遍历而不是for循环