### String.prototype.trim()
1.概念

`trim()`方法会从一个字符串的两端删除空白字符。在这个上下文的空白字符包括所有的空白字符（**space、tab、no-break space** 等）以及所有的行终止符字符（如**LF、CR**）。

2.使用

````
var orig = '   foo  ';
console.log(orig.trim()); // 'foo'
````
3.兼容旧环境
````
if (!String.prototype.trim) {
  String.prototype.trim = function () {
    return this.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, '');
  };
}
````
##### 参考链接
[MDN-trim()方法](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/Trim)