原文：[15 CSS Questions to Test Your Knowledge](http://sixrevisions.com/css/css-questions/)<br/>
作者：[Alexander Dawson](http://www.hitechy.com/#main)

本文测试用例，将涉及以下知识点：
* [基础CSS](#基础css)
* [中级CSS](#中级css)
* [先进CSS](#先进css)

这是前面[15个HTML测试问题]()的后续。

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