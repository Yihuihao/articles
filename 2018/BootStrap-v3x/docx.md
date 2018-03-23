# Bootstrap3.x
1.基本模板：
````
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://cdn.bootcss.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
`````
2.使用响应式布局：引入 `.col-*-*` 来设置布局
````
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
    <script src="https://cdn.bootcss.com/html5shiv/3.7.3/html5shiv.min.js"></script>
    <script src="https://cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
</head>
<body>
<div class="container layout_test1">
    <style>
        .layout_test1 div[class*='col']:nth-child(2n) {
            background: red;
        }
        .layout_test1 div[class*='col']:nth-child(2n+1){
            background: green;
        }
    </style>
    <div class="row">
        <div class="col-md-1">1</div>
        <div class="col-md-1">2</div>
        <div class="col-md-1">3</div>
        <div class="col-md-1">4</div>
        <div class="col-md-1">5</div>
        <div class="col-md-1">6</div>
        <div class="col-md-1">7</div>
        <div class="col-md-1">8</div>
        <div class="col-md-1">9</div>
        <div class="col-md-1">10</div>
        <div class="col-md-1">11</div>
        <div class="col-md-1">12</div>
    </div>

<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
<script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
<!-- Include all compiled plugins (below), or include individual files as needed -->
<script src="js/bootstrap.min.js"></script>
</body>
</html>
````
3.禁止响应式布局：

①移除文档中设置浏览器视口（ `viewport` ）的标签： ` <meta> ` ;

②通过为 `.container` 类设置一个 `width` 值从而覆盖框架默认的 `width` 设置，例如：`width:970px !important;`。
并确保这些设置全部放在默认Bootstrap的CSS文件后面。如果把它放在媒体查询中，可以省略`!important`。

③如果使用了导航条，需要移除所有导航条的折叠展开属性。

④对于栅格布局，额外添加 `.col-xs-*` 类或者替换掉 `.col-md-*` 和 `.col-lg-*`。
对于超小屏幕设备的栅格系统能够在所有分辨率的环境下展开。

````
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <!--<meta name="viewport" content="width=device-width, initial-scale=1">-->
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
    <script src="https://cdn.bootcss.com/html5shiv/3.7.3/html5shiv.min.js"></script>
    <script src="https://cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
</head>
<body>
<div class="container layout_test1">
    <style>
        .layout_test1 {
            width: 500px !important;
        }
        .layout_test1 div[class*='col']:nth-child(2n) {
            background: red;
        }
        .layout_test1 div[class*='col']:nth-child(2n+1){
            background: green;
        }
    </style>

    <div class="row">
        <div class="col-xs-1 ">1</div>
        <div class="col-xs-1 ">2</div>
        <div class="col-xs-1 ">3</div>
        <div class="col-xs-1 ">4</div>
        <div class="col-xs-1 ">5</div>
        <div class="col-xs-1 ">6</div>
        <div class="col-xs-1 ">7</div>
        <div class="col-xs-1 ">8</div>
        <div class="col-xs-1 ">9</div>
        <div class="col-xs-1 ">10</div>
        <div class="col-xs-1 ">11</div>
        <div class="col-xs-1 ">12</div>
    </div>
</div>

<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
<script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
<!-- Include all compiled plugins (below), or include individual files as needed -->
<script src="js/bootstrap.min.js"></script>
</body>
</html>
````

