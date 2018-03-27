# Babel在webpack中的配置使用
①安装：使用npm安装
````
npm install --save-dev babel-loader babel-core
````
②在webpack.config.js中的使用
````
module: {
  rules: [
    { test: /\.js$/, exclude: /node_modules/, loader: "babel-loader" }
  ]
}
````
③在package.json中配置使用,需要先安装 `babel-preset-env` (转换ES2015+的 env preset)

安装：
````
npm install babel-preset-env --save-dev
````
在package.json中使用
````
"babel": {
    "presets": [
      "env"
    ]
  }
  ````
# 参考链接
[https://babeljs.cn/docs/setup/#installation]