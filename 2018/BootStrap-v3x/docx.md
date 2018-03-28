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
4.表格

①基本实例：为任意 `<table>` 标签添加 `.table` 类，可以为其赋予基本的样式——少量的内补（padding）和水平方向的分隔线。
````
<table class="table">
  ...
</table>
````
②条纹表格：添加类 `.table-striped`;
````
<table class="table table-striped">
  ...
</table>
````

③带边框的表格：添加类 `.table-bordered`;
````
<table class="table table-bordered">
  ...
</table>
````
④鼠标悬停：添加类 `.table-hover`;
````
<table class="table table-hover">
  ...
</table>
````
⑤紧缩表格：添加类 `.table-condensed`,可以让表格更加紧凑，单元格中的内补（padding）均会减半;
````
<table class="table table-condensed">
  ...
</table>
````
⑥状态类：通过状态类可以为行或单元格设置颜色

⑦响应式表格：将任何 `.table` 元素包裹在 `.table-responsive` 元素内，可以创建响应式表格，其会在小屏幕设备上（小于768px）水平滚动；当屏幕大于768px宽度时，水平滚动条消失。
````
<div class="table-responsive">
  <table class="table">
    ...
  </table>
</div>
````
5.表单

①基本实例：所有设置了 **`.form-control`** 类的 `<input>` 、`<textarea>` 、`<select>` 元素都被默认设置宽度属性为 **`width:100%;`** 。
将 `label` 元素和前面提到的控件包裹在 `.form-group` 中可以获得更好的排列。
````
<form>
  <div class="form-group">
    <label for="exampleInputEmail1">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
  </div>
  <div class="form-group">
    <label for="exampleInputFile">File input</label>
    <input type="file" id="exampleInputFile">
    <p class="help-block">Example block-level help text here.</p>
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> Check me out
    </label>
  </div>
  <button type="submit" class="btn btn-default">Submit</button>
</form>
````
②内联表单：添加类 `.form-inline` 。只适用于视口（viewport）至少在768px宽度时（视口过小的话会使表单折叠）。

③水平排列的表单：为表单添加类 `.form-horizontal` 类，并联合使用Bootstrap的预置的栅格类，
可以将 `label` 标签和 _控件组_ 水平并排布局。这样做将改变 `.form-group` 的行为，使其表现为
栅格系统中的行（.row),因此就不需要额外添加类 `.row` 了。
````
<form class="form-horizontal">
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-2 control-label">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control" id="inputEmail3" placeholder="Email">
    </div>
  </div>
  <div class="form-group">
    <label for="inputPassword3" class="col-sm-2 control-label">Password</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword3" placeholder="Password">
    </div>
  </div>
  <div class="form-group">
    <div class="col-sm-offset-2 col-sm-10">
      <div class="checkbox">
        <label>
          <input type="checkbox"> Remember me
        </label>
      </div>
    </div>
  </div>
  <div class="form-group">
    <div class="col-sm-offset-2 col-sm-10">
      <button type="submit" class="btn btn-default">Sign in</button>
    </div>
  </div>
</form>
````
④被支持的控件：

输入框（包括大部分表单控件、文本输入域控件，还支持所有 HTML5 类型的输入控件： text、password、datetime、datetime-local、date、month、time、week、number、email、url、search、tel 和 color）；

输入框组（在文本输入域 `<input>` 前面或后面添加文本内容或按钮控件）；

文本域（支持多行文本表单控件）；
````
<textarea class="form-control" rows="3"></textarea>
````
多选、单选框（默认外观为堆叠在一起；可以设置内联的单选、多选框）；

下拉列表。

⑤静态控件：如果需要在表单中将一行 `纯文本` 和 `label` 元素放置于同一行，为 `<p>` 元素添加 `.form-control-static` 类即可。
````
<form class="form-horizontal">
  <div class="form-group">
    <label class="col-sm-2 control-label">Email</label>
    <div class="col-sm-10">
      <p class="form-control-static">email@example.com</p>
    </div>
  </div>
  <div class="form-group">
    <label for="inputPassword" class="col-sm-2 control-label">Password</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword" placeholder="Password">
    </div>
  </div>
</form>
````
⑥校验状态：

Bootstrap对表单控件的校验状态，如error、warning和success状态，都定义了样式。
使用时，在这些控件的父元素上面添加类 `.has-warning` 、`.has-error` 或 `.has-success` 即可。
任何包含在此元素内的 `.control-label` 、`.form-control` 和 `.help-block` 元素都将接受这些校验状态的样式。
````
<div class="form-group has-success">
  <label class="control-label" for="inputSuccess1">Input with success</label>
  <input type="text" class="form-control" id="inputSuccess1" aria-describedby="helpBlock2">
  <span id="helpBlock2" class="help-block">A block of help text that breaks onto a new line and may extend beyond one line.</span>
</div>
<div class="form-group has-warning">
  <label class="control-label" for="inputWarning1">Input with warning</label>
  <input type="text" class="form-control" id="inputWarning1">
</div>
<div class="form-group has-error">
  <label class="control-label" for="inputError1">Input with error</label>
  <input type="text" class="form-control" id="inputError1">
</div>
<div class="has-success">
  <div class="checkbox">
    <label>
      <input type="checkbox" id="checkboxSuccess" value="option1">
      Checkbox with success
    </label>
  </div>
</div>
<div class="has-warning">
  <div class="checkbox">
    <label>
      <input type="checkbox" id="checkboxWarning" value="option1">
      Checkbox with warning
    </label>
  </div>
</div>
<div class="has-error">
  <div class="checkbox">
    <label>
      <input type="checkbox" id="checkboxError" value="option1">
      Checkbox with error
    </label>
  </div>
</div>
````
⑦添加图标

6.按钮

