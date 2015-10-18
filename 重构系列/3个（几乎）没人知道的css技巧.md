原文：[3 Things (Almost) No One Knows About CSS](http://www.sitepoint.com/3-things-almost-one-knows-css/)<br/>
作者：[Kevin Yank](http://www.sitepoint.com/author/kevin-yank/)

你真的了解CSS吗？我要讲的三点技巧就是在观察参与者[测试](https://sitthetest.com/tests)之后，发现的有趣的问题。

### 如何设置双倍行高`line-height`
* 200%
* 2em
* 2
* double

首先，先排除了`double`，虽然有部分人会选择这个答案。

`2em`有39%的人会选择它，另有21%的人会选择`200%`;看来，你们还不会使用更时尚的百分比。

然而，正确答案是`2`.

指定一个无单位的数字，这样`font-size`后代的值将继承这一数字，而不是固定行高。

比如说，你想将网页中的行距设置成双倍，普通元素字体12px、h1元素字体24px，你如果将`line-height`设置成`2em`或`200%`，页面所有的文本行高都是24px；但是是设置成无单位的`2`的话，页面所有的文本行高都会相应的变大x倍，普通元素24px，h1元素48px行高。

### 如何使元素重叠
* z-index
* margin
* overflow
* background

首先，还是先排除最不可能的值`background`。

有46%的人会选择`z-index`，看来你们还是没有理解`z-index`，它不做任何动作，只有在需要重叠的地方设置才有效（position），MDN上有一篇“[理解 CSS z-index](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Understanding_z_index)”需要好好阅读。

`overflow`控制文档溢出处理，并不对控制重叠起作用；但有相当部分人不这么认为。

正确答案是`margin`，将其设置成负值会引起元素相叠的效果，效果如下图：
![margin](http://dab1nmslvvntp.cloudfront.net/wp-content/uploads/2015/04/1429090154fig-negative-margin-float.png)

Web爱好者，根据`margin`重叠特性研究的多列布局的效果[One True Layout](http://positioniseverything.net/articles/onetruelayout/)（和后来的[In Search of the Holy Grail](http://alistapart.com/article/holygrail)）。

### 伪元素 VS 伪类
利用`伪元素`和`伪类`可以作出非常炫的页面效果。

`伪类`是一个特定的状态，比如:hover（鼠标放上去才会触发）。

`伪元素`是一个虚拟的HTML元素（:after），是文档的一部分，让你的页面风格更加优秀。

实例讲解：略！

### 结语
或许你可以试着去做一下[测试](https://sitthetest.com/tests)。

### ps：
[中文：理解CSS z-index](http://www.ituring.com.cn/article/68352)<br/>
[全文翻译-前端外刊](http://zhuanlan.zhihu.com/FrontendMagazine/20020090)<br/>
[12 Little-Known CSS Facts (The Sequel)](http://www.sitepoint.com/12-little-known-css-facts-the-sequel/) [译](http://tgideas.qq.com/webplat/info/news_version3/804/7104/7106/m5723/201509/376300.shtml)<br/>
[12个很少被人知道的CSS事实 ](http://www.w3cplus.com/css/12-little-known-css-facts.html)
