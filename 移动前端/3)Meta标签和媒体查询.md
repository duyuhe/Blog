移动优先！


## <meta>


#### viewport
如果直接设置
````
<meta name="viewpoer" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,minimum-scale=1.0" />
````
对于视力不好的人不可以缩放，体验不好；解决办法是通过JS判断设置viewport

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
上面的代码有bug,[改进代码](https://gist.github.com/903131)/[第二种](https://gist.github.com/901295)

