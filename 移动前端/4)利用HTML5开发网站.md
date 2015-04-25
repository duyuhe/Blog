移动网站相对PC端来说，性能方面是有劣势的；但是我们可以利用HTML5/CSS3来构建更加健壮的Web应用— —可以利用设备的硬件。

## HTML5

#### 语义化标签
header/footer等等<br/>
部分标签使用的时候需要将其设置成块`display:block;`

#### canvas
原先的动画的效果，会有严重的性能（卡顿）问题，但是canvas可以调用设备的硬件来加速。

#### 应用缓存
让网站部分存储在[本地](http://www.w3cfuns.com/blog-5425789-5397631.html)，下次启动的时候可以加快访问。

#### 数据
新提供了[Web storage](http://www.w3cschool.cc/html/html5-webstorage.html)保存数据：SessionStorage(浏览器关闭清除)与localStorage（一直存在，除非手动清除）。

#### 地理位置
[Geolocation API](http://www.w3cschool.cc/html/html5-geolocation.html)来判断用户的位置

#### 屏幕方向
浏览器或设备一般提供禁止屏幕切换功能，开发者可以自己设置网页显示方向。<br/>
W3C:[The Screen Orientation API](http://www.w3.org/TR/screen-orientation/)<br/>
````
function hengshuping(){
   if(window.orientation==180||window.orientation==0){
       alert(“竖屏状态！”)
   }
   if(window.orientation==90||window.orientation==-90){
       alert(“横屏状态！”)
   }
}

window.addEventListener(“onorientationchange” in window ? “orientationchange” : “resize”, hengshuping, false);
````
[jQuery Mobile orientationchange 事件](http://www.w3cschool.cc/jquerymobile/event-orientationchange.html)



## CSS3

#### 阴影
`box-shadow`

#### 圆角
`border-radius`


处理以上这些内容，还有许多新特性，如果想知道更多，请仔细研究文档。<br/>


## 更多
[http://html5test.com/](检测当前浏览器的对HTML5特性的支持度)
[modernizr.js ](兼容检测库)