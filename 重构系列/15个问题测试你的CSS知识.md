原文：[15 CSS Questions to Test Your Knowledge](http://sixrevisions.com/css/css-questions/)<br/>
作者：[Alexander Dawson](http://www.hitechy.com/#main)

本文测试用例，将涉及以下知识点：
* [基础CSS](#基础css)
* [中级CSS](#中级css)
* [先进CSS](#先进css)

这是前面[15个HTML测试问题](https://github.com/duyuhe/Blog/blob/master/%E9%87%8D%E6%9E%84%E7%B3%BB%E5%88%97/15%E4%B8%AA%E9%97%AE%E9%A2%98%E6%B5%8B%E8%AF%95%E4%BD%A0%E7%9A%84HTML%E7%9F%A5%E8%AF%86.md)的后续。

![tests](http://cdn.sixrevisions.com/0519-02-css-questions.jpg)

## 基础CSS

### 1.下列哪个不是一个有效的边框样式属性值?
* dotted
* inset
* glazed
* groove
* solid

#### 答案：
`glazed` <br/>
![border](http://cdn.sixrevisions.com/0519-01-border-style-property-values.png)<br/>
[w3.org:border-style规范](http://www.w3.org/TR/css3-border/#the-border-style)


### 2.下列哪个不是一个有效的CSS长度单位?
* cm
* dm
* em
* mm

#### 答案：
`dm` <br/>
`cm``mm`是[绝对长度单位](http://www.w3.org/TR/css3-values/#absolute-lengths)，`em`是[字体相对单位](http://www.w3.org/TR/css3-values/#font-relative-lengths)。


### 3.什么选择器可以作用在页面上所有元素？

#### 答案：
`*`，例子： <br/>
````
*{margin:0;padding:0;}
````
相关：[是否应该重置CSS](http://sixrevisions.com/css/should-you-reset-your-css/)


### 4.哪个属性允许元素隐藏并占据页面空间？

#### 答案：
````
visibility:hidden   or   opacity:0
````


### 5.CSS个有16个基本颜色关键词，下面那个不是关键词？
* olive
* fuchsia
* cyan
* aqua
* maroon

#### 答案：
`cyan` <br/>
cyan是颜色，但不是[基本颜色关键词](http://www.w3.org/TR/css3-color/#html4)，而是[扩展颜色一部分](http://www.w3.org/TR/css3-color/#svg-color)。<br/>
相关：[CSS颜色](http://sixrevisions.com/css/css-colors/)


### 6.font-style属性有4个有效值，除inherit、normal和italic外还有什么值？

#### 答案：
`oblique` <br/>
相关：[MDN:font-style文档](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style) 和 [CSS字体知识](http://sixrevisions.com/css/css-typography-01/)


### 7.下面那个选择器权重更高
* #object h2::first-letter
* body .item div h2::first-letter:hover

#### 答案：
`#object h2::first-letter` <br/>
相关：[怎么计算选择器权重](http://sixrevisions.com/css/css-specificity/)

## 中级CSS

### 8.伪链接的设置顺序
* :active
* :hover
* :link
* :visited

#### 答案：
````
LVHA: :link > :visited > :hover > :active
````
相关：[伪链接](http://sixrevisions.com/css/link-pseudo-classes/)及其[怪异知识](http://sixrevisions.com/css/visited-pseudo-class-strange/)


### 9.下列哪个CSS属性不影响盒子模型?
* content
* padding
* margin
* outline
* border

#### 答案：
`outline`


### 10.当使用媒体查询（media）时，以下哪个不是有效媒体类型？
* tv
* all
* voice
* print
* braille
* tty
* embossed

#### 答案：
`voice` <br/>
相关：[Media文档](http://www.w3.org/TR/css3-mediaqueries/#background)


### 11.除了下面三个字体类型外，还有哪两个字体类型？
* serif 衬线
* sans-serif 无衬线
* monospace 等宽字体
* ?
* ?

#### 答案：
* cursive 手写
* fantasy 艺术 <br/>
相关：[文档](http://www.w3.org/TR/css3-fonts/#generic-font-families)和[@font-face](http://sixrevisions.com/css/font-face-guide/)


### 12.哪个属性可以让所选颜色继承文字颜色？

#### 答案：
````
currentColor

.box {
  color: green;
  background-color: currentColor;
  border: 1px dashed currentColor;
}
````
相关：[文档](http://www.w3.org/TR/css3-color/#currentcolor)和[CSS 变量](http://sixrevisions.com/css/variables/)

## 先进CSS

### 13.下面哪个不是有效的CSS单位？
* [ch](http://www.w3.org/TR/css3-values/#font-relative-lengths)
* [turn](http://www.w3.org/TR/css3-values/#angles)
* [px](http://www.w3.org/TR/css3-values/#absolute-lengths)
* ems
* [dpcm](http://www.w3.org/TR/css3-values/#resolution)
* [s](http://www.w3.org/TR/css3-values/#time)
* [hz](http://www.w3.org/TR/css3-values/#frequency)
* [rem](http://www.w3.org/TR/css3-values/#font-relative-lengths)

#### 答案：
`ems`


### 14.下面那个颜色关键词在W3规范中尚未提出？
* blanchedalmond
* dodgerblue
* peachpuff
* orchidblack
* navajowhite
* tomato

#### 答案：
`orchidblack` <br/>
相关：[颜色](http://dev.w3.org/csswg/css-color/#named-colors)


### 15.CSS允许定义字符编码吗？

#### 答案：
````
@charset

@charset "utf-8";
````
相关：[@charset](http://www.w3.org/International/questions/qa-css-charset)

## 相关
* [HTML和CSS网页设计师应该了解什么?](http://sixrevisions.com/web_design/should-web-designers-know-html-and-css/)
* [设计一个网站时要考虑的60个问题](http://sixrevisions.com/web_design/60-questions-to-consider-when-designing-a-website/)
* [成为一个自由职业者之前的问题](http://sixrevisions.com/project-management/questions-to-ask-yourself-before-becoming-a-freelancer/)