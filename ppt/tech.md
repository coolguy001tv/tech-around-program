title: 开发周边的技术
speaker: 丁丁
url: https://github.com/coolguy001tv/tech-around-program
transition: zoomin
files: /css/common.css
theme: dark
date: 2016/03/16
[slide]
# 开发周边的技术
----

* MarkDown {:&.rollIn}
* 正则实例
* windows命令行

[slide]

# MarkDown
## 目标： ** 易读易写 **
-----
Markdown 是一种轻量级标记语言，创始人为约翰·格鲁伯（John Gruber）。它允许人们“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档”。这种语言吸收了很多在电子邮件中已有的纯文本标记的特性。

<small style="font-size:small">摘自 https://zh.wikipedia.org/wiki/Markdown</small>
[note]
一份使用 Markdown 格式撰写的文件应该可以直接以纯文本发布

兼容 HTML

Markdown 语法受到一些既有 text-to-HTML 格式的影响，

包括 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，

而最大灵感来源其实是纯文本电子邮件的格式。

[/note]
[slide]
# 基本语法
----

* 段落、标题
    * Setext: 底线的形式利用=（1阶）和 -（2阶）
    * Atx: 行首插入 1 到 6 个 \# ，对应到标题 1 到 6 阶
    
eg: 

<pre class="pre">
    A First Level Header
    ====================
    A Second Level Header
    ---------------------
    # A 1st Level Header
    ## A 2nd Level Header
</pre>
[slide]  
# **段落、标题**展示效果
----

A First Level Header
====================
A Second Level Header
---------------------
# A 1st Level Header
## A 2nd Level Header

[slide]
# 基本语法(续)
----
* 强调
    * 星号（1个或者2个）
    * 底线（1个或者2个）
<pre class="pre">
Some of these words _are emphasized_
Use two asterisks for __strong emphasis__
</pre>

Some of these words _are emphasized_

Use two asterisks for __strong emphasis__

[slide]
# 基本语法(续)
----
* 列表
    * 星号
    * 加号
    * 减号
    * 数字接着一个英文句点
 
<pre class="pre">
+ Candy
+ Gum
+ Booze
</pre>
[note]
请不要混合使用符号，以免出现不一样的解析结果

数字接着一个英文句点 方式其实并不关心数字的顺序

[/note]

[slide]
# 基本语法(续)
----
* 链接
    * 行内链接
        * 接在后面用括号直接接上链接
    * 参考链接
        * 链接定一个名称，之后你可以在文件的其他地方定义该链接的内容
        
<pre class="pre">
    This is an [example link](http://example.com/ "With a Title").
    
    
    I get 10 times more traffic from [Google][1] than from
    [Yahoo][2] or [MSN][3].
    
    [1]: http://google.com/ "Google"
    [2]: http://search.yahoo.com/ "Yahoo Search"
    [3]: http://search.msn.com/ "MSN Search"
</pre>
[slide]
# **链接**展示效果
----
This is an [example link](http://example.com/ "With a Title").
    
I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].

[1]: http://google.com/ "Google"
[2]: http://search.yahoo.com/ "Yahoo Search"
[3]: http://search.msn.com/ "MSN Search"

[note]
下一页先讲换行
[/note]
[slide]
#  基本语法(续)
----
* 换行
    * 行尾插入至少两个空格，或直接一行空行
* 图片
    * 行内形式 
<pre class="pre">![alt text](/path/to/img.jpg "Title")</pre>
    * 参考形式

    
[slide]
#  基本语法(续)
----
* 代码
    * 反引号(`)
    * 制表符或至少四个空格缩进的行
* 引用
    * 段落开头加上右尖括号('>')
        * 一个引用里插入一个引用，可以用两个('>')开头
    
[note]
`区段内的 &、< 和 > 都会被自动的转换成 HTML 实体，这项特性让你可以很容易的在代码区段内插入 HTML 码`
[/note]
[slide]
# 总结
----

---
类型 | 表述方式 | HTML
:---|:---|:---
段落、标题|Setext/Atx|h1~h6
强调|\*/\_|em/strong
列表|\*/\+/\-/数字与句点|ul(ol)/li
链接|\[\]\(\)|`<a>`
换行|2个空格或者一个空行|`<br>`
图片|\!\[\]\(\)|`<img>`
代码|\`/制表符|`<code>`
引用|\>|`<blockquote><p>`



[slide]
# 参考链接
----

[Markdown快速入门](http://wowubuntu.com/markdown/basic.html)

[Markdown维基百科](https://zh.wikipedia.org/wiki/Markdown)

[GitHub官方帮助文档](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

[GitHub上README写法暨markdown语法解读](http://www.tuicool.com/articles/zIJrEjn)

[麻花在线markdown编辑器](http://mahua.jser.me/)
[note]
* \`\`\`的使用
* 表格的使用

[/note]


[slide]
# 正则实例
----

* 版本号替换
* 文本替换
* 字符串拼接
* 其他

[slide]
# 版本号替换(1)
## 将所有引入css的地方加入一个版本号：?v=2
----
```
<link rel="stylesheet" href="demo/css/demo.css">
<link rel="stylesheet" href="demo/css/demo.css?v=1">
<link rel="stylesheet" href="demo/css/demo.css?w=1">
<link rel="stylesheet" href="demo/css/demo.css?x=1" >
<link rel="stylesheet" href="demo/css/demo.css?yx=10" />
```
[note]
不考虑`<link rel="stylesheet" href='demo/css/demo.css'>`
[/note]
[slide]
#解决思路
----
* 其中的一个思路：
    * `\.css[^"]*"  -> .css?v=2"`
    * `\.css.*"`

等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[slide]
#什么问题
----

```
<script>
    var height = $(window).css("height");
    $(window).css("height","320px");
</script>
```
变成了
```
<script>
    var height = $(window).css?v=2");
    $(window).css?v=2"height","320px");
</script>
```
[slide]
#解决思路（续）
----
* `\.css(\?\w+=\d+)?  -> .css?v=2`

[note]
方案不是完美的，需要自行考虑:如果是
* a.css?=1
* a.css?1
* a.css?v=1 (后面跟空格)
[/note]

[slide]
# 版本号替换(2)
## 加入所有引入的js文件的版本号
-----
```
<script src="demo/js/demo.js"></script>
<script src="demo/js/demo.js?v=1"></script>
<script src='demo/js/demo.js'></script>
```
[slide]
#解决思路
----
* 其中的一个思路：
    * `\.js.*"  -> .js?v=2"`

等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[note]
我们仍然不考虑单引号的问题
[/note]
[slide]
#什么问题
----
```
<script>
    $(".js_confirm").click();
</script>
```
变成了
```
<script>
    $(".js?v=2").click();
</script>
```

[slide]
# 文本替换
----
将代码
```
#purview("200012")
#author("2007")
<li id="menu-distribution-order"><a class="menu-link" href="//xxxx"><span
        class=" menu-item clearfix"><i class="left icon-menu-right"></i><span
        class="left">分销订单</span></span></a></li>
#end
#end
```
转化成
```
<a id="menu-deal-orderStatics" href="//xxxx">订单统计</a>
```

[slide]
# 解决思路
----
* `<li id="(.*)"` ....

等等 {:&.fadeIn}

出问题了 {:&.fadeIn}

[slide]
# ** 贪婪模式 ** 和 ** 非贪婪模式 **
-----

*   贪婪模式： 尽可能多
* 非贪婪模式：尽可能少
    * 问号(?)符紧跟在任何一个其他限制符（*,+,?，{n}，{n,}，{n,m}）后面时，匹配模式是非贪婪的
    * 例如，对于字符串“oooo”，“o+?”将匹配单个“o”，而“o+”将匹配所有“o”
[slide]
# $n 与括号
## 第n个匹配项
----

* $n表示第n个括号匹配的项
* 实际测试中$0是表示整个字符串
* (?:pattern)是一个非获取匹配
    * 对于字符串`<li id="menu-distribution-order">`  
    * 正则表达式`<li id="(.*?)"`中$1是`menu-distribution-order`
    * 正则表达式`<li id="(?:.*?)"`中$1是空串

然后继续我们的思路

[slide]
# 解决思路（续）
----
* `<li id="(.*?)".*?href="(.*?)".*\n.*\n.*?>(.*?)</.*` ->
* `<a id="$1" href="$2">$3</a>`


等等 {:&.fadeIn}

出问题了 {:&.fadeIn}


[slide]
#什么问题
----
```
<!--<li id="menu-distribution-order"><a class="menu-link" href="//xxxx"><span
        class=" menu-item clearfix"><i class="left icon-menu-right"></i><span
        class="left">分销订单</span></span></a></li>-->
```
会被替换成：
```
<!--<a id="menu-distribution-order" href="//xxxx">分销订单</a>
```
导致不应该被注释掉的代码被注释掉（没有结束注释符号）  
解决方案请自行考虑


[slide]
# 字符串拼接
## html转化成JS中拼接的字符串
----
```
<form id="home-search-form" action="/zh-CN/search" method="get">
    <div class="home-search-form search-form">
        <input class="search-input" type="search" id="home-q">
        <button type="submit" class="offscreen">搜索</button>
    </div>
</form>
```
转化成JS中的字符串拼接，类似于
```
'<form id="home-search-form" action="/zh-CN/search" method="get">' + 
'<div class="home-search-form search-form">' +
....
````
[slide]



