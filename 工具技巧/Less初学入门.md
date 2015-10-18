[LESS](http://lesscss.net/)是动态样式语言，属于CSS预处理语言的一种。

推荐编译工具：[koala（考拉）](http://koala-app.com/index-zh.html)

### 开始认识LESS

#### 安装
`.less`文件要在`less.js`之前

####  注释
`/* a little text */` Less编译成css的时候，注释会保留
`//a lillte text`  Less编译成css的时候，注释会删除

#### 变量
`@name :value`  别忘了`@`符号
````
@color :red;
body{color:@color;} => body{color:red;}
````

###  混合
一个类可以直接引用另一个类，继承并使用其中的样式
````
.base{color:red}
.box{background:green; .base;} =>.box{background:green;color:red;}
````
进一步，可以带参数混合
````
.base(@color){color:@color;}
.box{background:green; .base(red);} =>.box{background:green;color:red;}
````
还可以指定默认样式
````
.base(@color:red){color:@color;}
.box{background:green; .base();} =>.box{background:green;color:red;} 
另一种自定义 ：.box{background:green; .base(gray);} =>.box{background:green;color:gray;}
````
####  嵌套
即是css中的`body header p {}`这类情况
````
body{
       header{
              p{color:red;}
       }
}
````
需要注意的是，注意性能问题，切勿深层嵌套。
实现:hover效果
````
a{
   color:red;
   &:hover{color:pink;}
}
````

#### 运算
可以运用加减乘除等数学运算设置颜色、宽高等... ...
````
@color :#f00;
.base{color:@color -20;} =>转换成rgb（0-255），再转换成十六进制
````

#### 匹配模式

#### 其它知识点
1.@arguments 接收参数数组
````
.base(5px,solid,red){
       border:@arguments;
}
````
2.`~`避免编辑
让Less无视，原文输出
````
.base{color:~'这里面的内容会原文输出';}
````
3.!important 尽量不使用


###  扩展
[大漠：CSS的代码组织和预处理器比较](http://www.w3cplus.com/css/css-sass-scss-compass-less-bem-smacss-oocss-acss-ccss-wtfss.html)<br/>
[大漠：LESS&SASS差异](http://www.w3cplus.com/css/an-introduction-to-less-and-comparison-to-sass.html)<br/>
[CSS新方法：自定义变量](http://www.w3cfuns.com/blog-5425789-5398338.html)