#Babel-Polyfill在webpack中的配置使用
①安装(polyfill需要在源代码之前运行，需要让它成为一个dependency，而不是devDependency)
````
npm install --save babel-polyfill
````

````
"dependencies": {
    "babel-polyfill": "^6.26.0",
  }
  ````
②在webpack中使用，添加到 `entry` 数组中
````
module.exports = {
  entry: ["babel-polyfill", "./app/js"]
};
````
③在浏览器中使用

可以在 `babel-polyfill npm` 发布版中的 `dist/polyfill.js` 文件中找到它。 它需要在你编译过的 Babel 代码之前被包括进去。你可以将它追加到你编译过的代码中，或者在这些代码之前通过 `<script>` 引入它。
#参考链接
[https://babeljs.cn/docs/usage/polyfill/]