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
2.ES6方法

- 2.1 set数据结构与Array.from()

```
var arr = [1, 2, 2, 3, 4, 5, 6, 6, "10", "10"];
function getArray(arr){
  var sets = new Set(arr);
  return Array.from(sets);
}
getArray(arr); // 输出[1, 2, 3, 4, 5, 6, "10"]

```

- 2.2 set数据结构与扩展运算符(...)
```
var arr = [1, 2, 2, 3, 4, 5, 6, 6, "10", "10"];
function getArray(arr){
  var sets = new Set(arr);
  return [...sets];
}
getArray(arr); // 输出[1, 2, 3, 4, 5, 6, "10"]

```
3.原型定义方法
```
		var a = [5,8,5,9,12,15,1,1,3,4,5,"4","4"];

		Array.prototype.unique = function() {

			var temp = []; //临时数组

			//查找元素下标函数
			function search(item) {
				var index = -1;

				for (var i = 0;i < temp.length;i ++) {
					if (item === temp[i]) {
						index = i;
						break;
					}
				}

				return index;
			}

			//遍历当前数组，把不重复的值加到临时数组中
			for (var i = 0;i < this.length;i ++){
				if (search(this[i]) == -1) {
					temp.push(this[i]);
				}
			}

			return temp;
		}

		a = a.unique();
		alert(a);
```
