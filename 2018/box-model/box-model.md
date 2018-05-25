# 盒模型（Box Model）
标准盒模型（content-box）+IE盒模型（border-box）

# BFC（Block Formatting Context）

BFC：块级格式化上下文。是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。属于普通流定位。

# box-sizing(用户界面属性)

box-sizing允许以特定的方式定义匹配某个区域的特定元素。

    box-sizing: content-box|border-box|inherit
    content-box: 由 CSS2.1 规定的宽度高度行为
                 宽度和高度分别应用到元素的内容框
                 在宽度高度之外绘制元素的内边距和边框
                 
    border-box: 为元素设定的宽度和高度决定了元素的边框盒
                即为元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制
                通过从已设定的宽度和高度分别减去边框盒内边距才能得到内容的宽度和高度
                
    inherit: 规定从父元素继承 box-sizing 属性的值


# 参考链接
·[盒模型：https://zhuanlan.zhihu.com/p/25321647](https://zhuanlan.zhihu.com/p/25321647)

·[box-sizing](http://www.w3school.com.cn/cssref/pr_box-sizing.asp)