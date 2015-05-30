移动优先！

## meta标签

移动设备屏幕大小和分辨率会造成网页显示错误（严格来说是体验不好），可以设置viewport来解决这一问题！
#### viewport
如果直接设置
````
<meta name="viewpoer" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,minimum-scale=1.0" />
````
对于视力不好的人不可以缩放，体验不好；解决办法是通过JS判断设置viewport！

在HTML中设置基本viewport
````
<meta name="viewport" content="width=device-width,initial-scale=1.0" />
````
JS:
````
var metas =document.getElementsByTagName("meta");
var i;
if(navigator.userAgent.match(/iPhone/i)){
         for(i=0;i<metas.length;i++){
                   if(metas[i].name == "viewport"){
                            metas[i].contents = "width=device-width,minimum-scale=1.0,maximum-scale=1.0";
                   }
         }
         // 放大操作
         document.addEventListener("gesturestart",gestureStart);
}
function gestureStart(){
        for(i=0;i<metas.length;i++){
                   if(metas[i].name == "viewport"){
                           metas[i].content ="width=device-width,minimum-scale=0.25,maximum-scale=1.6";
                   }
        }
}
````
上面的代码有bug：[改进代码](https://gist.github.com/903131)/[第二种](https://gist.github.com/901295)

在移动设备上访问网站，必须先打开浏览器才可以，可不可以直接在操作界面上打开网站？可以！
####  设置桌面图标
````
<!-- touch-icon 在 iOS 中用于桌面图标-->
<link href="http://img01.taobaocdn.com/tps/i1/T1zo51XxXfXXXeOHro-144-144.png" rel="apple-touch-icon-precomposed"/>
<!-- IPhone4  Retina屏幕 -->
<link rel="apple-touch-icon-precomposed" sizes="114×114" href="apple-touch-icon-114×114-precomposed.png" />
<!-- iPad -->
<link rel="apple-touch-icon-precomposed" sizes="72×72" href="apple-touch-icon-72×72-precomposed.png" />
<!-- Android2.1以上  和 不是Retina屏幕的iPhone 57×57的低分辨率图标 -->
<link rel="apple-touch-icon-precomposed" href="apple-touch-icon-precomposed.png" />
<!-- Symbian 60 -->
<link rel="shortcut icon" href="img/1/apple-touch-icon.png" />
````
上面的语句是否可以合并：No;并且注意前两项，推荐图标尺寸144*144,小于144会被拉伸。

设置完图标之后，让网站可以全屏打开
#### 全屏打开
````
<!-- 从桌面 icon 启动 iOS Safari 是否进入全屏状态（App模式） yes | no-->
<meta content="yes" name="apple-mobile-web-app-capable"/>
<!-- iOS Safari 全屏状态下的状态栏样式  default | balck | black-translucent-->
<meta content="black-translucent" name="apple-mobile-web-app-status-bar-style"/>
````



## 媒体查询
根据设备视图宽度来进行排版。
````
<link rel="stylesheet" media="all and (orientation:portrait)" href="portrait.css">    // 竖放加载
<link rel="stylesheet" media="all and (orientation:landscape)"href="landscape.css">   // 横放加载

//竖屏时使用的样式
<style media="all and (orientation:portrait)" type="text/css">
    #landscape { display: none; }
</style>

//横屏时使用的样式
<style media="all and (orientation:landscape)" type="text/css">
    #portrait { display: none; }
</style>
````
[媒体类型Media Types 及响应式网页设计](http://www.w3cfuns.com/blog-5425789-5397618.html)<br/>
[移动设备媒体查询参数](http://nmsdvid.com/snippets/)



## 更多
[viewport控制](http://segmentfault.com/a/1190000002685485)<br/>
[WP 上IE实现“device-width”效果](http://blogs.msdn.com/b/iemobile/archive/2010/11/22/the-ie-mobile-viewport-on-windows-phone-7.aspx)<br/>
[Safari  viewport问题](http://developer.apple.com/library/safari/#documentation/appleapplications/reference/saffarihtmlref/articles/metatags.html)<br/>
[黑莓](http://docs.blackberry.com/en/developers/deliverables/4305blackberry_browser-4.6.0-us.pdf)<br/>
[关于触摸图标](http://mathiasbynens.be/notes/touch-icons)<br/>
[苹果公司文档](http://developer.apple.com/library/safari/#documentation/appleapplications/reference/safariwebcontent/configuringwebapplications/configuringwebapplications.html)<br/>
[whatwg官网](http://www.whatwg.org/specs/web-apps/current-work/multipage/links.html#rel-icon)<br/>
[创建苹果图标指引](http://developer.apple.com/library/ios/#documentation/userexperience/conceptual/mobilehig/iconsimages/iconsimages.html#//apple_ref/doc/uid/tp40006556-ch14-sw11)<br/>
[Safari图标指引](http://developer.apple.com/library/safari/#documentation/userexperience/conceptual/mobilehig/iconsimages/iconsimages.html#//apple_ref/doc/uid/tp40006556-ch14)
