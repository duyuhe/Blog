原文：[15 HTML Questions for Testing Your Knowledge](http://sixrevisions.com/html/html-questions/)<br/>
作者：[Alexander Dawson](http://www.hitechy.com/#main)


你真的知道HTML吗？

![HTML](http://cdn.sixrevisions.com/0511-01-html-questions.jpg)


## 初级问题

### 1.叫什么名字的主要国际标准机构发布HTML规范?

#### 答案：
World Wide Web Consortium (W3C).


### 2.HTML标题有多少级？

#### 答案：
````
6

h1 ~ h6
````


### 3.下面的标记有什么问题？
````
<p style"font-size:10px;">Copyright <span>2015</span></p>
````

#### 答案：
没有`=`。


### 4.IE从什么版本开始支持HTML5？

#### 答案：
IE9


### 5.使用什么标签设置initial-scale=2可以使页面放大成2倍？

#### 答案：
````
<meta name="viewport" content="width=device-width, initial-scale=2">
````
相关：[META](http://www.w3.org/TR/html5/document-metadata.html#standard-metadata-names) 和 [viewport](http://www.quirksmode.org/mobile/metaviewport/)


### 6.什么是微格式？请把下面“ ？”处填完整。
````
<span class="???">
     <span class="latitude">纬度：52.48</span>,
     <span class="longitude">经度：-1.89</span>
</span>
````

#### 答案：
`geo` <br/>
相关：[出处](http://microformats.org/wiki/geo)


### 7.RSS、Atom和OpenSearch用什么语言生成的？

#### 答案：
`Extensible Markup Language (XML).` <br/>
相关：[CML规范](http://www.w3.org/TR/REC-xml/)


### 8.哪个HTML5元素开头是“K”？

#### 答案：
keygen

## 中级问题

### 9.对于一个版权的超链接，怎么指定其类型？

#### 答案：
````
license

<main>
    <img src="freephoto.gif" />
    <a rel="license" href="copyright.html">Copyright info.</a>
</main>
````
相关：[rel](http://sixrevisions.com/html/link-types-hyperlinks/)


### 10.微数据相关（略，详见原文）

#### 答案：
`itemscope` <br/>
相关：[HTML5扩展之微数据与丰富网页摘要](http://www.zhangxinxu.com/wordpress/2011/12/html5%E6%89%A9%E5%B1%95-%E5%BE%AE%E6%95%B0%E6%8D%AE-%E4%B8%B0%E5%AF%8C%E7%BD%91%E9%A1%B5%E6%91%98%E8%A6%81/)


### 11.HTML5中表示换行的元素？

#### 答案：
wbr


### 12.input什么属性可以指定正则？

#### 答案：
````
pattern

<input pattern="[0-9][A-Z]{3}" name="part" data-x="A part number is a digit followed by three uppercase letters."/>
````
相关：[pattern](http://www.w3.org/TR/html5/forms.html#the-pattern-attribute)

## 深入讨论

### 13.HTML5 W3C规定多少种input类型？

#### 答案：
18种 。<br/>
相关：[type](http://www.w3.org/TR/html5/forms.html#states-of-the-type-attribute)


### 14.可不可以注释拼音？

#### 答案：
````
ruby

<ruby>日<rt>に</rt></ruby><ruby>本<rt>ほん</rt></ruby>
````
相关：[ruby](http://www.w3.org/TR/html5/text-level-semantics.html#the-ruby-element)


### 15.ARIA对HTML5区域元素（footer/article ...）的作用？

#### 答案：
contentInfo <br/>
相关：[文档](http://www.w3.org/TR/html5/dom.html#sec-strong-native-semantics)

## 更多 
* [20 Questions to Know for Avoiding Website Project Disasters](http://sixrevisions.com/project-management/20-questions-to-know-for-avoiding-website-project-disasters/)
* [Semantic HTML for Web Content](http://sixrevisions.com/html/semantic-html-web-content/)
* [10 Useful Infographics about HTML5](http://sixrevisions.com/html/html5-infographics/)
* [60 Questions to Consider When Designing a Website](http://sixrevisions.com/web_design/60-questions-to-consider-when-designing-a-website/)