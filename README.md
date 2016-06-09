# CodeSnippets
>Collection of commonly used code snippets

1.数组去重(通过hash表)
```
var arr = [1, 2, 2, 3, 4, 5, 6, 6];

function getArray(a) {
 var hash = {},
     len = a.length,
     result = [];

 for (var i = 0; i < len; i++){
     if (!hash[a[i]]){
         hash[a[i]] = true;
         result.push(a[i]);
     } 
 }
 return result;
}

getArray(arr); // 输出[1， 2， 3， 4， 5， 6]
```