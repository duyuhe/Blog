原文作者：[James Hibbard](http://www.sitepoint.com/author/jhibbard/)<br/>
原文链接：[jQuery setTimeout() Function Examples](http://www.sitepoint.com/jquery-settimeout-function-examples/)

`setTimeout`虽然是JS原生API，但是在jQuery中使用效果良好。

## 语法
`setTimeout`是`window`下的方法，不过大家很少这样写：
````
var timer=window.setTimeout(func,[delay，param]);
````
而是直接写成— —`var timer=setTimeout(func,[delay，param]);`。

* 赋值给`timer`，是为了可以方便取消定时`clearTimeout`
* `func`，可以直接写函数代码function(){/* code */}或者函数名字funcName
* `func`，也可以是字符串`“alert(code);”`— —不推荐
* `delay`，定义时间，默认为0
* `param`，参数下面有讲

带参函数，常规写法：
````
setTimeout(function(){ greet(randomGreeting);}, 1000);
````
或者是将参数放在最后（注意这种写法<IE9不支持）：
````
setTimeout(greet, 1000, randomGreeting);
````

### this
定时器中`this`指向`window`:
````
var person = {
  firstName: "Jim",
  introduce: function(){
    console.log("Hi, I'm " + this.firstName);
  }
};
 
person.introduce();
// Outputs: Hi, I'm Jim
 
setTimeout(person.introduce, 50);
// Outputs: Hi, I'm undefined
````
你可以使用[bind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)函数，来让`this`指向对象。
````
setTimeout(person.introduce.bind(person), 50);
// Outputs: Hi, I'm Jim
````
或者使用jQuery中的[$.proxy](http://api.jquery.com/jQuery.proxy/)方法来设置
````
setTimeout($.proxy(person.introduce, person), 50);
// Outputs: Hi, I'm Jim
````

## 总结
`setTimeout`可以让函数延迟执行，效果等同jQuery中的[delay()](https://api.jquery.com/delay/)
````
$( "button" ).click(function() {
  // 元素隐藏.8s之后再渐显
  $( "div.first" ).slideUp( 300 ).delay( 800 ).fadeIn( 400 );
});
````
如果需要一直运行定时器，推荐`setInterval`。

## 更多
[sitepoint论坛](http://community.sitepoint.com/)<br/>
[stackoverflow论坛](http://stackoverflow.com/)