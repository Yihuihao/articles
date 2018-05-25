# 判断设备及浏览器
    
    (function(){
    
                判断是否是移动设备
                if(/AppleWebKit.*Mobile/i.test(navigator.userAgent) || (/MIDP|SymbianOS|NOKIA|SAMSUNG|LG|NEC|TCL|Alcatel|BIRD|DBTEL|Dopod|PHILIPS|HAIER|LENOVO|MOT-|Nokia|SonyEricsson|SIE-|Amoi|ZTE|Huawei|huawei|honor/.test(navigator.userAgent))){
                    if(window.location.href.indexOf("?mobile")<0){
                        try{
                            if(/Android|webOS|iPhone|iPod|BlackBerry/i.test(navigator.userAgent) || /iPad/i.test(navigator.userAgent)){
                                var meta = document.createElement("meta");
                                meta.name="aplus-terminal";
                                meta.content="1";
                                document.documentElement.firstElementChild.appendChild(meta)
                            }
                        }catch(e){}
                    }
                }
    
            })();
            
            
            判断浏览器
            (function(){
            
                        $(document).ready(function() {
                            if(IEVersion() == 8){
                                window.location.href = "/html/1.shtml";
                            }else{
                                $('#pagepiling').pagepiling({
                                    // sectionsColor: ['red', '#2ebe21', '#2C3E50', '#51bec4'],
                                    navigation: {
                                        'textColor': 'red',
                                        'bulletsColor': '#000',
                                        'position': 'left',
                                        'tooltips': ['支教活动', '基地', '项目介绍', '峰会', '招募令', '学习教练']
                                    }
                                });
                                layui.use(['element','carousel'], function(){
                                    var element = layui.element;
                                    var carousel = layui.carousel;
            
                                    //建造实例
                                    element.render('');
            
                                    carousel.render({
                                        elem: '#test1'
                                        ,width: '100%' //设置容器宽度
                                        ,arrow: 'none' //始终显示箭头
                                        //,anim: 'updown' //切换动画方式
                                    });
                                    carousel.render({
                                        elem: '#test2'
                                        ,width: '100%' //设置容器宽度
                                        ,arrow: 'none' //始终显示箭头
                                        //,anim: 'updown' //切换动画方式
                                    });
                                    //…
                                });
                                initEvent();
                            }
                        });
            
                        function initEvent(){
                            $("#teacher").click(function(){
                                layer.open({
                                    type: 2,
                                    title: false,
                                    area: ['450px', '414px'], //宽高
                                    content: ['/mem/teacherRecruit.jsp' , 'no']
                                });
                            });
                            $("#public").click(function(){
                                layer.open({
                                    type: 2,
                                    title: false,
                                    area: ['450px', '414px'], //宽高
                                    content: ['/mem/schoolJoin.jsp' , 'no']
                                });
                            });
                            $("#private").click(function(){
                                layer.open({
                                    type: 2,
                                    title: false,
                                    area: ['450px', '414px'], //宽高
                                    content: ['/mem/schoolJoin.jsp' , 'no']
                                });
                            });
                        }
                        function IEVersion() {
                            var userAgent = navigator.userAgent; //取得浏览器的userAgent字符串
                            var isIE = userAgent.indexOf("compatible") > -1 && userAgent.indexOf("MSIE") > -1; //判断是否IE<11浏览器
                            var isEdge = userAgent.indexOf("Edge") > -1 && !isIE; //判断是否IE的Edge浏览器
                            var isIE11 = userAgent.indexOf('Trident') > -1 && userAgent.indexOf("rv:11.0") > -1;
                            if(isIE) {
                                var reIE = new RegExp("MSIE (\\d+\\.\\d+);");
                                reIE.test(userAgent);
                                var fIEVersion = parseFloat(RegExp["$1"]);
                                if(fIEVersion == 7) {
                                    return 7;
                                } else if(fIEVersion == 8) {
                                    return 8;
                                } else if(fIEVersion == 9) {
                                    return 9;
                                } else if(fIEVersion == 10) {
                                    return 10;
                                } else {
                                    return 6;//IE版本<=7
                                }
                            } else if(isEdge) {
                                return 'edge';//edge
                            } else if(isIE11) {
                                return 11; //IE11
                            }else{
                                return -1;//不是ie浏览器
                            }
                        }
            
                    })();




# 参考链接
·[javascript判断移动端访问设备](http://www.jb51.net/article/60786.htm)
·[移动web开发--页面头部META总结](https://www.bbsmax.com/A/E35p77AJvX/)