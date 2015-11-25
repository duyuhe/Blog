#深入了解JavaScript（译）

原文： [A Dive Into Plain JavaScript](http://blog.adtile.me/2014/01/16/a-dive-into-plain-javascript/)
作者： [Viljami S](http://blog.adtile.me/authors/viljami/)


为了平台兼容性，开发人员会使用第三方库来进行工作，但这些纯JS不能很便捷的完成吗？本文由浅入深、一步步
解析JS，看是否需要使用jQuery等库。

##渐进增强

使用特性检测，让支持新特性的浏览器处理效果完美（当然低版本浏览器也要保留最基本效果）。
```
       if (window.addEventListener && document.querySelectorAll) {
                 //  代码
       }
```

##开始JS之旅

###实现jQuery载入效果
你需要了解`onload`与`ready`的差异，但是使用js中的`DOMContentLoaded`，可以完全实现`ready`效果。
```
      document.addEventListener("DOMContentLoaded", function() {
               // Code
      }, false);
```

###模拟jQuery的选择器
使用js的 `querySelectorAll` 和 `querySelector` ，完全可以使用CSS语法获取元素
```
      // 获取父元素
      var navigation = document.querySelector("nav");
      // 获取子元素
      var links = navigation.querySelectorAll("a");
```
还可以实现链式操作、直接在元素上绑定事件：
```
      // 定义选择器和事件绑定
      var $ = document.querySelectorAll.bind(document);
      Element.prototype.on = Element.prototype.addEventListener;
      // 使用
      $(".element")[0].on("touchstart", handleTouch, false);
```

###遍历文档
jQuery提供了遍历同级元素、子元素等的方法，js也可以做到这些
```
      // 获取父元素
      var parent = document.querySelector("div").parentNode;
      // 获取同级下一个元素
      var next = document.querySelector("div").nextSibling;
      // 获取同级上一个元素
      var next = document.querySelector("div").previousSibling;
      // 获取子元素
      var child = document.querySelector("div").children[0];
      // 获取最后一个子元素
      var last = document.querySelector("div").lastElementChild;
```

###操作class
原先类的添加、查找、删除等操作非常繁琐（可以参考jQuery源码），但是 HTML5提供了一个便捷
的API--`classList` ，让上述行为不再麻烦。
```
      if ("classList" in document.documentElement) {
                 // 先进行特性检测
                 
                 element.classList.add("bar");              //  添加
                 element.classList.remove("foo");         //  移除
                 element.classList.contains("foo");       //  查找
                 element.classList.toggle("active");       //  切换
      }
```

###操作文档
重绘或重排以及新建一个标签都会带来严重的性能问题：推荐克隆节点，对克隆的节点进行操作，再刷新
```
      var element = document.querySelector(".class");
      var clone = element.cloneNode(true);
      clone.style.background = "#000";
      element.parentNode.replaceChild(clone, element);
      // 如果只是想添加节点，可以直接插入文档
      document.body.appendChild(clone);
```

###获取image的初始大小
```
      function getMaxWidth(img) {
             var maxWidth;

             // 特性检测，兼容处理
             if (img.naturalWidth !== undefined) {
                      maxWidth = img.naturalWidth;
             } else {
                      var image = new Image();
                      image.src = img.src;
                      maxWidth = image.width;
            }

            return maxWidth;
      }
```
需要注意的是，图片一定要是完整的
```
      function hasDimensions(img) {
            return !!((img.complete && typeof img.naturalWidth !== "undefined") || img.width);
      }
```

###判断元素是否在可视区域内
`getBoundingClientRect()`返回一个矩形对象，它的四个属性表示在浏览器边界位置
```
      // 是否在可视区域内
      function isInViewport(element) {
             var rect = element.getBoundingClientRect();
             var html = document.documentElement;
             return (
                   rect.top >= 0 &&
                   rect.left >= 0 &&
                   rect.bottom <= (window.innerHeight || html.clientHeight) &&
                   rect.right <= (window.innerWidth || html.clientWidth)
             );
       }
```

##结论
根据自己的工作需求决定是否使用jQuery等库。
------------------------------------------------
福利：   [The Right Way](http://jstherightway.org/)  js代码规范、各种工具库还有推荐大牛 <br/>
文章：   [DOM的技巧和技术:父元素,子元素,兄弟元素](http://www.sitepoint.com/dom-tips-techniques-parent-child-siblings/?utm_campaign=Front%2BEnd%2BDev%2BWeekly&utm_medium=web&utm_source=Front_End_Dev_Weekly_79)