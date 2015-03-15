原文：[Replace CoffeeScript with ES6](https://robots.thoughtbot.com/replace-coffeescript-with-es6?utm_source=javascriptweekly&utm_medium=email)
作者：Blake Williams

我一直关注[ES6](http://es6.ruanyifeng.com/),因为他是JS的下一个版本，现在终于有机会使用他了。我用很短的时间就上手了，他比CoffeeScript的语法更加完美。

## 使用 ES6
我们可以通过 [6to5](https://babeljs.io/) 将ES6转换为ES5运行。6to5支持大量的构建工具：Grunt、Gulp和Sprockets。我使用的是[sprockets-es6](https://github.com/josh/sprockets-es6)和Sprocckets 4.x。

如果你使用Vim想要使用ES6的话，就需要设置你的`vimrc`。

     autocmd BufRead,BufNewFile *.es6 setfiletype javascript

你还可以在浏览器中使用 [6to5 REPL](https://babeljs.io/repl/)在线编辑器。

## 类
CoffeeScript和ES6都有`类`这一特性，让我们看看他们两个类的区别。

CoffeeScript允许我们设置实例变量的参数、插入字符串、没有调用函数和括号：

```
class Person
  constructor: (@firstName, @lastName) ->

  name: ->
    "#{@first_name} #{@last_name}"

  setName: (name) ->
    names = name.split " "

    @firstName = names[0]
    @lastName = names[1]

blake = new Person "Blake", "Williams"
blake.setName("Blake Anderson")
console.log blake.name()
```

ES6中我们可以使用 classes, getters, and setters：

```
class Person {
  constructor(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }

  get name() {
    return this.firstName + " " + this.lastName;
  }

  set name(name) {
    var names = name.split(" ");

    this.firstName = names[0];
    this.lastName = names[1];
  }
}

var blake = new Person("Blake", "Williams");
blake.name = "Blake Anderson"
console.log(blake.name);
```

如果你使用过其他库或框架，注意他们源代码中的类和ES6的不同：

*函数名之后没有分号
*没有“function”关键字
*类中的每一小项之间没有逗号

我们可以使用getters 和 setters 操作`name`。

## 插入
我们常常希望JS有更强大的字符串处理功能，现在E3S6引入了 [template strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/template_strings)。现在让我们看看 CoffeeScript 字符串、JS 字符串和 template strings的区别。

CoffeeScript：

```
"CoffeeScript allows multi-line strings
with
interpolation like 1 + 1 = #{1 + 1}
"
```
JS

```
"JavaScript strings can only span a single line " +
  "and interpolation isn't possible"
```

ES6 template strings:

```
`Template strings allow strings to span
multiple lines and allow interpolation like 1 + 1 = ${1 + 1}
```

我们可以在上一个例子中利用 template strings ：

```
get name() {
  return `${this.firstName} ${this.lastName}`;
}
```

这样看来简洁了许多，更接近CoffeeScript。

## 箭头函数
这也是ES6中另一个特性： =>。

在ES5中，定时器或事件中的this指向window，在使用前需要保存this

```
var self = this;

$("button").on("click", function() {
  // do something with self
});
```

CoffeeScript

```
$("button").on "click", =>
  # do something with this
```

ES6 =>

```
$("button").on("click", () => {
  // do something with this
});
```

## 其他特性

### 默认参数
CoffeeScript

···
hello = (name = "guest") ->
  alert(name)
···

ES6

```
var hello = function(name = "guest") {
  alert(name);
}
```

### 省略参数
`...others`传入的是一个数组

CoffeeScript

```
awards = (first, second, others...) ->
  gold = first
  silver = second
  honorable_mention = others
```

ES6

```
var awards = function(first, second, ...others) {
  var gold = first;
  var silver = second;
  var honorableMention = others;
}
```

### 解构
解构模式允许你数组设置为：键 和 值 一一对应。

CoffeeScript

```
[first, _, last] = [1, 2, 3]
```

ES6

```
var [first, , last] = [1, 2, 3]
```

在上面的例子set中使用解构;

```
set name(name) {
  [this.firstName, this.lastName] = name.split(" ");
}
```

## 结语
ES6的设计模式和CoffeeScript非常类似，本文只是介绍了其一小部分特性。

如果想更深了解ES6，就在项目中使用他吧。