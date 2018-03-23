# Webpack
# webpack 配置

1.整个配置中使用Node的内置path模块，并且在它前面加上__dirname这个全局变量。可以防止不同操作系统之间的路径问题，并且可以是相对路径按照预期工作。

2.使用webpack-dev-server时，在编译运行的时候，可能会出现waring信息：
````
"C:\Program Files (x86)\JetBrains\WebStorm 2016.1.1\bin\runnerw.exe" "C:\Program Files\nodejs\node.exe" "C:\Program Files\nodejs\node_modules\npm\bin\npm-cli.js" run-script dev

    > angular-webpack@1.0.0 dev C:\Users\yinpeiepei\Desktop\功能测试\angular-webpack
    > cross-env NODE_ENV=development webpack-dev-server --config webpack.config.js

    i ｢wds｣: Project is running at http://0.0.0.0:3100/
    i ｢wds｣: webpack output is served from /
    i ｢wdm｣: Compiled with warnings.
    ‼ ｢wdm｣: Hash: f80a24a049a38994cc66
    Version: webpack 4.2.0
    Time: 712ms
    Built at: 2018-3-22 11:36:50
                   Asset       Size  Chunks                    Chunk Names
    my-webpack.bundle.js    828 KiB       0  [emitted]  [big]  main
              index.html  214 bytes          [emitted]
    Entrypoint main [big] = my-webpack.bundle.js
       [2] ./src/main.js 108 bytes {0} [built]
       [4] (webpack)/hot/emitter.js 77 bytes {0} [built]
       [6] (webpack)/hot sync nonrecursive ^\.\/log$ 170 bytes {0} [built]
       [9] ./node_modules/html-entities/index.js 231 bytes {0} [built]
      [10] ./node_modules/ansi-html/index.js 4.16 KiB {0} [built]
      [11] (webpack)-dev-server/client/overlay.js 3.58 KiB {0} [built]
      [12] ./node_modules/sockjs-client/dist/sockjs.js 176 KiB {0} [built]
      [13] (webpack)-dev-server/client/socket.js 1.05 KiB {0} [built]
      [14] ./node_modules/loglevel/lib/loglevel.js 7.68 KiB {0} [built]
      [15] ./node_modules/ansi-regex/index.js 135 bytes {0} [built]
      [16] ./node_modules/strip-ansi/index.js 161 bytes {0} [built]
      [19] ./node_modules/querystring-es3/index.js 127 bytes {0} [built]
      [23] ./node_modules/url/url.js 22.8 KiB {0} [built]
      [24] (webpack)-dev-server/client?http://0.0.0.0:3100 7.75 KiB {0} [built]
      [25] multi (webpack)-dev-server/client?http://0.0.0.0:3100 ./src/main.js 40 bytes {0} [built]
        + 11 hidden modules

    WARNING in configuration
    The 'mode' option has not been set. Set 'mode' option to 'development' or 'production' to enable defaults for this environment.

    WARNING in asset size limit: The following asset(s) exceed the recommended size limit (244 KiB).
    This can impact web performance.
    Assets:
      my-webpack.bundle.js (828 KiB)

    WARNING in entrypoint size limit: The following entrypoint(s) combined asset size exceeds the recommended limit (244 KiB). This can impact web performance.
    Entrypoints:
      main (828 KiB)
          my-webpack.bundle.js


    WARNING in webpack performance recommendations:
    You can limit the size of your bundles by using import() or require.ensure to lazy load some parts of your application.
    For more info visit https://webpack.js.org/guides/code-splitting/
    Child html-webpack-plugin for "index.html":
         1 asset
        Entrypoint html-webpack-plugin for "index.html" = index.html
           [0] (webpack)/buildin/module.js 519 bytes {0} [built]
           [1] (webpack)/buildin/global.js 509 bytes {0} [built]
           [2] ./node_modules/lodash/lodash.js 527 KiB {0} [built]
           [3] ./node_modules/html-webpack-plugin/lib/loader.js!./src/index.html 521 bytes {0} [built]
````
此时在package.json中的配置为：
````
"scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "build": "cross-env NODE_ENV=production webpack --config webpack.config.js --progress --display-modules",
        "dev": "cross-env NODE_ENV=development webpack-dev-server --config webpack.config.js"
      }
````
为了解决此类问题，在dev的配置中添加mode配置：
````"dev": "cross-env NODE_ENV=development webpack-dev-server --config webpack.config.js --mode development"
````
这是就可以编译成功：
````
"C:\Program Files (x86)\JetBrains\WebStorm 2016.1.1\bin\runnerw.exe" "C:\Program Files\nodejs\node.exe" "C:\Program Files\nodejs\node_modules\npm\bin\npm-cli.js" run-script dev

> angular-webpack@1.0.0 dev C:\Users\yinpeiepei\Desktop\功能测试\angular-webpack
> cross-env NODE_ENV=development webpack-dev-server --config webpack.config.js --mode development

i ｢wds｣: Project is running at http://0.0.0.0:3100/
i ｢wds｣: webpack output is served from /
i ｢wdm｣: Hash: 593be3f91ccce7396357
Version: webpack 4.2.0
Time: 695ms
Built at: 2018-3-22 11:49:56
               Asset       Size  Chunks             Chunk Names
my-webpack.bundle.js    858 KiB    main  [emitted]  main
          index.html  214 bytes          [emitted]
Entrypoint main = my-webpack.bundle.js
[./node_modules/ansi-html/index.js] 4.16 KiB {main} [built]
[./node_modules/ansi-regex/index.js] 135 bytes {main} [built]
[./node_modules/loglevel/lib/loglevel.js] 7.68 KiB {main} [built]
[./node_modules/punycode/punycode.js] 14.3 KiB {main} [built]
[./node_modules/url/url.js] 22.8 KiB {main} [built]
   [0] multi (webpack)-dev-server/client?http://0.0.0.0:3100 ./src/main.js 40 bytes {main} [built]
[./node_modules/sockjs-client/dist/sockjs.js] 176 KiB {main} [built]
[./node_modules/strip-ansi/index.js] 161 bytes {main} [built]
[./node_modules/url/util.js] 314 bytes {main} [built]
[./node_modules/webpack-dev-server/client/index.js?http://0.0.0.0:3100] (webpack)-dev-server/client?http://0.0.0.0:3100 7.75 KiB {main} [built]
[./node_modules/webpack-dev-server/client/overlay.js] (webpack)-dev-server/client/overlay.js 3.58 KiB {main} [built]
[./node_modules/webpack-dev-server/client/socket.js] (webpack)-dev-server/client/socket.js 1.05 KiB {main} [built]
[./node_modules/webpack/hot sync ^\.\/log$] (webpack)/hot sync nonrecursive ^\.\/log$ 170 bytes {main} [built]
[./node_modules/webpack/hot/emitter.js] (webpack)/hot/emitter.js 77 bytes {main} [built]
[./src/main.js] 108 bytes {main} [built]
    + 11 hidden modules
Child html-webpack-plugin for "index.html":
     1 asset
    Entrypoint html-webpack-plugin for "index.html" = index.html
    [./node_modules/html-webpack-plugin/lib/loader.js!./src/index.html] 521 bytes {html-webpack-plugin for "index.html"} [built]
    [./node_modules/lodash/lodash.js] 527 KiB {html-webpack-plugin for "index.html"} [built]
    [./node_modules/webpack/buildin/global.js] (webpack)/buildin/global.js 509 bytes {html-webpack-plugin for "index.html"} [built]
    [./node_modules/webpack/buildin/module.js] (webpack)/buildin/module.js 519 bytes {html-webpack-plugin for "index.html"} [built]
i ｢wdm｣: Compiled successfully.
````

3.在编译.less文件时，需要注意两处，之后就不需要做其他操作了
在webpack.config.js中：
````
                {
                    test: /\.less$/,
                    use: [
                        'style-loader',
                        'css-loader',
                        'less-loader'
                    ]
                }
````
在使用less-loader时，必须安装less，单独一个less-loader是没办法起作用的：
````
    npm install --save-dev less-loader less
````

4.在同一个文件中，引用操作可以使用：import和require；但是必须保证统一使用给一个，不然编译后的文件加载顺序可能不是我们想要的，
下面是入口文件的内容：
````
// require('./styles/base.css');
// require('./styles/less/index.less');
import './styles/base.css';
import './styles/less/index.less';

const h1 = document.createElement('h1');
h1.innerHTML = '这是main.js入口文件中的内容';
document.body.appendChild(h1);

function test() {
    console.log("test","tesst");
}
test();
`````
