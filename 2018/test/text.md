## 环境及储备知识
### 安装
1.Node 8.9.1 建议使用nvm来管理node版本(为了适应各种开发环境)

windows版本： [https://github.com/coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows)

mac版本： [https://github.com/creationix/nvm#install-script (建议使用item2)](https://github.com/creationix/nvm#install-script)

2.Git

[Git简易基础 http://www.bootcss.com/p/git-guide/](http://www.bootcss.com/p/git-guide/)

3.Chrome最新浏览器 v62+

### 使用nvm

`cmd` 命令行工具，查看node当前版本
````
nvm ls  查看当前版本
nvm install 版本号（8.9.1）安装某一个版本
nvm use 版本号 使用某一个node版本
````

### 构建环境
1.Webpack 3.10.0

[https://doc.webpack-china.org](https://doc.webpack-china.org)

2.npm scripts

[http://www.ruanyifeng.com/blog/2016/10/npm_scripts.html](http://www.ruanyifeng.com/blog/2016/10/npm_scripts.html)

3.babel

[https://babeljs.cn/docs/usage/polyfill](https://babeljs.cn/docs/usage/polyfill)

[https://www.imooc.com/article/21866](https://www.imooc.com/article/21866)

### 编辑器
1.Atom

[https://atom.io](https://atom.io)

2.ESLint

[http://eslint.cn/docs/user-guide/configuring](http://eslint.cn/docs/user-guide/configuring)

### 基础知识
1.ES6

[http://es6-features.org/#Constants](http://es6-features.org/#Constants)

2.Sass

[http://sass.bootcss.com](http://sass.bootcss.com)

3.Vue.js

[https://cn.vuejs.org](https://cn.vuejs.org)

### 业务开发流程
1.技术选型（需求会议）

1）技术选型分析

①构建工具

    1、构建工具有哪些？
    gulp：流式--输入输出
    grunt：任务管理，不能做打包  --不是流操作
    webpack：编译、打包
    fis：百度内部的集成方案
    prepack：fackbook推荐
    rollup：类似webpack

    2.为甚要构建工具？
    资源压缩：图片、css、js
    静态资源替换：字体文件、图片--避免http请求
    模块化处理：commonJS
    编译处理：es6
    sourcemap

    3.我们使用哪个构建工具？
    webpack：编译
    npm scripts：任务管理


②MVVM框架选择

    Vue.js
    React.js
    Angular.js
    1.根据团队成员情况
    2.看生态：建体系、文档、开源的热度（作者维护的热度）
    3.对原理的了解程度（项目的复杂度是否能够满足）


③模块化设计

    1.css模块化设计：如相同的class名，不同的样式；合并后怎么能够正确？

    2.js模块化设计：
    common.js：共用的东西（多个项目通用）
    layout.js：通用布局


④自适应方案设计

    设计师根据某一个模板设计一份设计稿
    工程师根据设计稿--适用于不同设备的方案（上线后自动自适应）

⑤代码维护及复用性设计的思考

    1.需求变更：横向扩展、代码解耦
    2.产品迭代：怎样复用代码（可能是新项目）
    3.Bug定位：怎样修改问题
    4.新功能开发：（可能增加局部功能）

2.业务开发（功能开发）

3.测试实验（交互、逻辑、bug）

4.发布上线（小流量--单机房--上线）

### 项目设计与原理分析
1.CSS模块化设计

    1.设计原则
        a.可复用能继承要完整
        b.周期性迭代
            优秀的代码是模仿出来的
            优秀的代码是设计出来的
            优秀的代码是重构出来的
    2.设计方法
        a.先整体后部分再颗粒化
            布局-页面-功能-业务
        b.先抽象再具体


2.JS组件设计
    
    1.设计原则
        a.高内聚低耦合
            高内聚：尽量让组件的功能受控于组件本身，而不是依赖于其他组件；
            低耦合：组件之间抽象功能，但组件之间没有关联，复用抽象的js功能。
        b.周期性迭代
        
    2.设计方法
        a.先整体后部分再颗粒化
        b.尽可能抽象

3.自适应
    
    1.基本概念
        a.CSS像素、设备像素、逻辑像素、设备像素比
            https://github.com/jawil/blog/issues/21
            css像素==逻辑像素--px
            设备像素==物理像素
            设备像素比==逻辑像素/设备像素
        b.viewport
            <meta name="viewport" content="width=device-width,initial-scale=1.0">
                
                viewport:layout-viewport、visual-viewport、ideal-viewport
        c.rem
            rem相对于html标签
            em相对于父元素
    2.工作原理
        a.利用viewport和设备像素比调整标准像素
            大部分设计稿尺寸：320*568---iPhone5
        b.利用px2rem自动转换css单位

4.SPA设计

5.构建设计

6.上线指导