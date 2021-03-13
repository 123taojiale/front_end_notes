# 前言

[B站视频链接 click me](https://www.bilibili.com/video/BV1ZE41177b6)

[腾讯课堂视频链接 click me](https://ke.qq.com/course/231570?taid=2955805083273362)

> 在写该笔记时 看的是 腾讯视频上的 成哥 HTML + CSS 教学视频
> 不同平台上内容应该都一样 不过 目录 可能会有所不同

```
点击页面左下角 可查看目录
点击code区域右上角的复制按钮 可一键复制code
```

# 1. 课程前导

**内容概述**

1. 前端工程师主要负责的工作介绍
2. 前端技术的应用领域介绍
3. 市场对前端工程师的需求分析
4. 前端工程师需要掌握的必要技能
`HTML` `CSS` `JavaScript` `jQuery` `网络` `CSS3` `H5` `es6` `webpack4.0` `git` `小程序` `设计模式` `VUE` `VUEX` `VUE源码` `React` `Node.js` `Mongo DB数据库` ...

# 2. 课前须知及[编辑器]使用方法

**内容概述**
1. Sublime Text 的安装及基本使用;
2. Visual Studio Code 的安装及基本使用; (没介绍)

# 3. html - css lesson1

## 3.1 html 初级篇 - 基础标签

1. 认识 HTML CSS 和 JavaScript 主要负责的功能

成哥借助之前编写过的一个移动端的项目 来介绍HTML和CSS是什么?

| 主要技术   | 描述         |
| ---------- | ------------ |
| HTML       | 负责结构     |
| CSS        | 负责外观样式 |
| JavaScript | 负责交互行为 |

2. HTML是什么

[HTML（超文本标记语言） mdn](https://developer.mozilla.org/zh-CN/docs/Web/HTML)

3. 标签的属性名和属性值的书写

- 属性名不需要加引号
- 属性值需要加引号

**eg**

```
<html lang="en"></html>
    lang 就是属性名
    en 就是lang属性的属性值(注意需要使用""引号来将属性值给包裹起来)
```

4. 字符编码集

编码字符集 utf-8 gb2312 gbk unicode

```
防止页面出现乱码, 使用utf-8就完事;
因为编码字符集选 utf-8 就能确保浏览器识别任何国家的语言;
```

---

H5 的元素周期表: [Periodic Table of the HTML5 Elements](https://www.xuanfengge.com/funny/html5/element/)

5. html标签上的 lang 属性

[HTML lang 属性](https://www.w3school.com.cn/tags/att_standard_lang.asp)

```
lang属性的作用
    告诉浏览器爬虫 我们的网站是关于什么内容的
        lang="en" 表示告诉浏览器我们的网站是关于英文的
        lang="zh" 表示告诉浏览器我们的网站是关于中文的
lang实际上也就是SEO(Search Engine Optimization)技术的一部分
    百度百科对 SEO 的定义:
       搜索引擎优化（SearchEngine Optimization，简称SEO）是一种方式：利用搜索引擎的规则提高网站在有关搜索引擎内的自然排名。目的是让其在行业内占据领先地位，获得品牌收益。很大程度上是网站经营者的一种商业行为，将自己或自己公司的排名前移。
    简单地说就是让我们的网站更容易被用户访问到
```

6. `<meta>`

[HTML meta 标签](https://www.w3school.com.cn/tags/tag_meta.asp)

7. `<p>`

[HTML p 标签](https://www.w3school.com.cn/tags/tag_p.asp)

8. 标题标签 `<h1> - <h6>`

[HTML 标题](https://www.w3school.com.cn/html/html_headings.asp)

9. `<strong>`

- 字体加粗显示

[strong mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong)

10. `<em>`

- 字体斜体显示

[em mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em)

11. 标签嵌套

**eg**

```html
<!-- 实现既要加粗又要斜体 -->
<strong><em>for example</em></strong>
```

![20210313114126](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313114126.png)

12. `<del>`

[del mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del)

13. `<address>`

[address mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address)

14. `<div>`

[div mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)

```
div 是很好块级的容器
```

15. `<span>`

[span mdn](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)

```
span 是很好的行级容器
```

## 3.2 html进阶篇-高级标签

1. 回车 和 空格

```
HTML中 回车 和 空格 的含义
   1. 充当文本分隔符
   2. 即便连续地写了多个 依旧识别为一个
```

2. html编码

```
html编码的书写格式:
   开始是 & 结尾是 ;
```

| html编码 | 描述             |
| -------- | ---------------- |
| `&nbsp;` | 表示一个空格文本 |
| `&lt;`   | 表示小于号 <     |
| `&gt;`   | 表示小于号 >     |

3. 如何在页面上显示 `<div>`

```
1. 若直接写 <div> 那么页面上是无法展示的
   由于 div 被 <> 包裹着 浏览器认为它是一个标签 而非文本
2. 正确写法是结合html编码来实现 即: &lt;div&gt;
```

4. `<br>` 或 `<br/>`

```
<br> 和 <br/> 是它的两种不同写法
   它们都是等效的
   作用都是换行
<br> 它是一个单标签
   常见的单标签还有: <meta> <hr>
```

5. 有序列表 `ol>li`

```
1. type 属性
    Indicates the numbering type:
       'a' indicates lowercase letters,
       'A' indicates uppercase letters,
       'i' indicates lowercase Roman numerals,
       'I' indicates uppercase Roman numerals,
       and '1' indicates numbers (default). (type 属性的默认值是 "1")
2. 若用字母来排序 那么排到Z后 下一个是 ZA 以此类推
3. reserved 属性
    This Boolean attribute specifies that the items of the list are specified in reversed order.
    布尔属性 (Boolean attribute) 的两种写法
        1. reserved = "reserved"
        2. reserved
    这两种写法是等效的 如果想给布尔属性加上属性值 那么属性值就只能是属性名
    但是 HTML5 规范规定：元素的布尔型属性如果有值，就是 true，如果没有值，就是 false。
    也就是说 布尔属性 只要写了 就有效 不管给不给它值 不管给它啥值
4. start 属性
    This integer attribute specifies the start value for numbering the individual list items. Although the ordering type of list elements might be Roman numerals, such as XXXI, or letters, the value of start is always represented as a number. To start numbering elements from the letter "C", use <ol start="3">.
    Note: This attribute was deprecated in HTML4, but reintroduced in HTML5.
5. 实际开发中基本不会使用 有序列表 ol>li
6. ol li 是 order list 的缩写
```

**type**

```html
<ol> <!-- type 的默认值是 1 -->
    <li>marvel</li>
    <li>速8</li>
    <li>返老还童</li>
    <li>了不起的盖茨比</li>
</ol>
```

![20210313115502](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313115502.png)

```html
<ol type="1">
    <li>marvel</li>
    <li>速8</li>
    <li>返老还童</li>
    <li>了不起的盖茨比</li>
</ol>
```

![20210313115502](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313115502.png)

```html
<ol type="a">
    <li>marvel</li>
    <li>速8</li>
    <li>返老还童</li>
    <li>了不起的盖茨比</li>
</ol>
```

![20210313115749](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313115749.png)

```html
<ol type="A">
    <li>marvel</li>
    <li>速8</li>
    <li>返老还童</li>
    <li>了不起的盖茨比</li>
</ol>
```

![20210313115859](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313115859.png)

```html
<ol type="i">
    <li>marvel</li>
    <li>速8</li>
    <li>返老还童</li>
    <li>了不起的盖茨比</li>
</ol>
```

![20210313115922](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313115922.png)

```html
<ol type="I">
    <li>marvel</li>
    <li>速8</li>
    <li>返老还童</li>
    <li>了不起的盖茨比</li>
</ol>
```

![20210313115948](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313115948.png)

**reversed**

```html
<ol type="1" reversed="reversed">
    <li>橘子</li>
    <li>苹果</li>
    <li>茄子</li>
</ol>
```

![20210313120041](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313120041.png)

**start**

```html
<ol type="1" start="2">
    <li>marvel</li>
    <li>速8</li>
    <li>返老还童</li>
    <li>了不起的盖茨比</li>
</ol>
```

![20210313120107](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313120107.png)

6. 无序列表 `ul>li`

```
1. 无序列表在实际开发中非常的常用 但是在实际开发中基本上不会使用有序列表
2. ul li 是 unorder list 的缩写
```

```
type 属性
    circle  空心圆
    disc    实心圆(默认)
    square  方形
```

**type**

```html
<ul type="disc">
    <li>草莓</li>
    <li>苹果</li>
    <li>香蕉</li>
</ul>
```

![20210313120229](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313120229.png)

```html
<ul type="circle">
    <li>草莓</li>
    <li>苹果</li>
    <li>香蕉</li>
</ul>
```

![20210313120250](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313120250.png)

```html
<ul type="square">
    <li>草莓</li>
    <li>苹果</li>
    <li>香蕉</li>
</ul>
```

![20210313120314](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313120314.png)

**ul-li 案例**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>模拟淘宝导航栏效果</title>
    <style>
        ul {
            list-style-type: none;
        }

        li {
            float: left;
            padding: 0 5px;
            border-radius: 5px;
            height: 25px;
            line-height: 25px;
            color: #f40;
            font-size: 14px;
            font-weight: bold;
            cursor: pointer;
        }

        li+li {
            margin-left: 10px;
        }

        li:hover{
            background: #f40;
            color: #fff;
        }
    </style>
</head>

<body>
    <ul>
        <li>天猫</li>
        <li>聚划算</li>
        <li>天猫超市</li>
    </ul>
</body>

</html>
```

![20210313120438](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313120438.png)

7. `<img>`

```
1. 页面中引入图片
   语法: <img src="图片路径" alt="" title="">
    1. src属性
       表示的是图片的路径, 引入图片的 3 种方式如下:
       1. 网上的url
       2. 本地的绝对路径
       3. 本地的相对路径
    2. alt属性
       若图片无法加载 那么会显示alt的属性值
       alt 是写给 浏览器看的
    3. title属性
       图片提示符 也就是鼠标hover在img上时显示的内容
       title 是写给 用户看的
2. 网页中元素的基本组成
    文字 + 图片
3. img 是 image 的缩写
```

8. `<a>`

```
1. 超链接
   语法: <a href="链接地址" target="打开方式"></a>
      1. href 属性
         属性值是给浏览器看的 表示跳转到的 url 告诉浏览器跳转到哪个位置
      2. target 属性
         用于规定页面的打开方式
         认识 target 属性的4个值
         _self      在原来窗口打开链接 (默认值)    表示当前页面会被覆盖
         _blank     在新窗口打开链接 (记它就够)    表示会新开一个窗口来显示跳转到的那个页面, 当前窗口不会被覆盖
         _parent    在父窗口打开链接
         _top       在顶层窗口打开链接
   注意点:
      1. 写在a标签里面的内容 是给用户看的
         即 <a href="">www.baidu.com</a> 这么写是无效的
         但是页面上的显示效果和下面这种写法是一样的
         <a href="http://www.baidu.com" target="_blank">www.baidu.com</a>
2. a 是 anchor 的缩写
3. a标签的常见用法
    1. 图片超链接
       a标签里面包裹img 点击图片实现跳转
    2. a标签用作锚点
        置顶:
           点击后回到顶部(置顶)
        目录:
           网上浏览小说 左侧是小说的目录 右侧是小说的内容 点击左侧的目录 会跳转到右侧对应的内容区
    3. a标签用来打电话
        写法:
           <a href="tel:13836014778">给成哥打电话</a>
        注意:
           前提要求你使用的设备 可以拨打电话 比如你现在使用的是mac电脑 或者 是手机端等等
           打电话这个功能的应用场景非常多, 比如 点餐 app 上的一键呼叫外卖小哥
    4. a标签用于发邮件
        写法:
           <a href="mailto:cheng.ji@alibaba-inc.com">给成哥发邮件</a>
           点击后会自动调用系统中的发邮件功能
           该功能的应用场景非常少 基本上不会使用
    5. 协议限定符
        写法:
           <a href="javascript:while(1){alert("让你手欠")}">你点我试试呀! come on! 来呀!</a>
        场景:
           书签功能
4. a标签的常见功能中 初学时只需要记住一个就可以 也就是超链接这个功能
```

**锚点**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>a标签用作锚点</title>
    <style>
        div {
            width: 100px;
            height: 100px;
        }

        #demo1 {
            background: #f40;
        }

        #demo2 {
            background: #008c8c;
        }

        .anchor{
            position: fixed;
            right: 100px;
            top: 100px;
            color: #f40;
            border: 1px dashed #ddd;
            background-color: #999;
        }

        a{
            display: block;
            color: inherit;
        }
    </style>
</head>

<body>
    lorem1000<!-- lorem1000 这得手动敲进去 然后按回车或tab键 即可一键生成 1000 个英文单词 -->
    <div id="demo1">this is demo1</div>
    lorem1000
    <div id="demo2">this is demo2</div>
    lorem1000
    <p class="anchor">
        <a href="#demo1">find demo1</a>
        <a href="#demo2">find demo2</a>
    </p>

</body>

</html>
```

```
点击 find demo1 页面就会跳转至 #demo1
点击 find demo2 页面就会跳转至 #demo2
这就是实现目录功能的基本原理
```

![20210313122748](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313122748.png)

9. `<from>`

[HTML 表单](https://www.w3school.com.cn/html/html_forms.asp)

```
1. form标签上的属性
    method 属性规定在提交表单时所使用的发送数据的方式 (POST 或 GET)
    action 属性就是一个地址 也就是 表单数据接收方的地址
2. <input> 元素是最重要的表单元素 根据不同的 type 属性 它有很多不同的形态
3. 语义化问题
   1. <input> 换行显示
      想实现多个input之间换行显示
      不建议使用 <br/> 标签来实现
      建议使用 <p> 标签来实现 (语义化好)
   2. 语义化好有啥用呢?
      首先 得明白一点 公司请工程师来 主要并不是负责开发的 而是负责维护的 语义化好 能提高代码的可读性 自然也就能提高代码的可维护性
      当我们进入一个互联网公司后 我们会了解到啥时候上班 啥时候下班(不过这些上下班啥的 在互联网公司压根不那么重要(成哥说的...)) 等一些信息 其中包括公司规定的开发规范
         开发规范: 也就是公司的一些规定 在开发那一部分的功能时 我们应该怎么来写
         比如 在写导航栏这一部分的时候 基本上所有的互联网公司都是要求利用 ul li 来写
         这么做的目的也蛮容易理解的 试想一下 倘若有那么一天 我们跳槽了呢 那么我们之前在公司里面写的代码 就需要交给其他的同事来维护 其他的同事就需要来阅读我们之前写的代码 如果都按照我们个人的风格来写的话 那么那个同事在阅读我们的代码时 就会很困难 进而导致这个产品不易维护 所以相对而言 这个开发规范 更加重要
4. 数据提交问题
    1. 数据提交成功的条件
        1. 有数据值 ==> 表示的就是用户输入的值
        2. 有数据名 ==> 表示的就是我们在input标签上给的name属性的属性值
        注意: 是否有数据接收方的地址 并非一个必要的条件
    2. 数据提交成功的标志
        问: 数据是否提交成功 看什么地方呢
        答: 看地址栏中的信息
           1. 提交前 file:///C:/Users/23264/Desktop/stuProject/test.html
           2. 提交成功时显示 file:///C:/Users/23264/Desktop/stuProject/test.html?username=dahuyou&password=123123#
              实际上 后端获取到的数据就是 username=dahuyou&password=123123
           3. 提交失败时显示 若没有填写相关的数据名 那么提交失败 显示的是 file:///C:/Users/23264/Desktop/stuProject/test.html? 表示提交不成功
    3. password 密码 相关知识
        在一些大型互联网公司 用户输入的密码 对于公司的员工而言 实际上也是不可见的 简单点说 就是用户输入的密码确实会被加密 比如你输入的是 123123 他们看到的可能就是 #$@&!* 这样的话 那就会相对安全一些
        但是在一些小型的互联网公司 实际上用户输入的密码 仅仅是对用户不可见 但是对于公司的员工而言 他们都是明文的(这个也许可以作为一个参考 来评判当前公司的leval...)
    4. 2G 3G 4G 网络之间的区别
        速度方面 4G > 3G > 2G
        安全性方面 在2G网络下 是不会对传输的数据进行加密的 抓包后 视觉上就能看出发送的是啥数据 也就是 手机在2G网络下 是及其不安全的
    5. 单选框 input type="radio" name="数据名" value="数据值"
       注意点
        1. name属性的属性值 是数据名 key
        2. value属性的属性值 是数据值 value
        3. 同一组的单选框 它们的 数据名必须相同 表示它们属于同一道题
```

**form表单提交数据**

```html
<form method="get" action="#">
    <p>
        username: <input type="text" name="username" id="">
    </p>
    <p>
        password: <input type="password" name="password" id="">
    </p>
    <p>
        你们所喜欢的男星
    </p>
    <p>
        1. 贝克汉姆<input type="radio" name="star" value="xiaobei">
    </p>
    <p>
        2. 莱昂纳多<input type="radio" name="star" value="xiaolai">
    </p>
    <p>
        3. 姬成<input type="radio" name="star" value="handsome">
    </p>
    <p>
        <input type="submit" name="" id="" value="提交">
    </p>
</form>
```

填写好数据后, 点击提交按钮, 对比地址栏信息的变化

```
file:///C:/Users/23264/Desktop/stuProject/test.html?username=dahuyou&password=123123&star=handsome#
后端接收到的数据 ==> username=dahuyou&password=123123&star=handsome
```

![20210313124129](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313124129.png)

**输入框提示效果**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>模拟一个输入框的提示效果</title>
</head>

<body>
    <p>
        username: <input type="text" name="username" value="请输入用户名" class="username">
    </p>
    <p>
        password: <input type="password" name="password">
    </p>
    <input type="submit">
    <script>
        var inp = document.querySelector(".username");
        inp.style.color = "#999";
        // 输入框获取焦点时 若值是 "请输入用户名" 那么内容清空
        inp.onfocus = function () {
            if (this.value === "请输入用户名") {
                this.value = "";
                this.style.color = "#424242";
            }
        }
        // 输入框失去焦点时 若值是 "" 那么将值设置为 "请输入用户名"
        inp.onblur = function () {
            if (!this.value) {
                this.value = "请输入用户名";
                this.style.color = "#999";
            }
        }
    </script>
</body>

</html>
```

![20210313124404](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313124404.png)

**bug**

```
用户输入的内容就是 "请输入用户名" 那么当鼠标再次聚焦时 那么用户之前输入的内容 依旧会被清空
实际上网上在处理这个需求的时候 采用的都是一样的处理方式 闲着无聊 可以自个儿找几个网站来试试
```

![20210313124505](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313124505.png)

点击提交后, 我们之前输入的内容就会被清空

![20210313124533](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313124533.png)

# 4. html - css lesson 2

## 4.1 css初级篇-css引入css基础选择器选择器权重

1. html 补充

上一节课程 `3. html - css lesson 1` 中遗留下来的部分html知识点

```
1. 多选框 <input type="checkbox" name="" value="">
   属于同一道题的多选框 它们的name属性值 也和单选框一样 必须相同才行
   单选框 可以理解为 单选题
   多选框 可以理解为 多选题
2. 优化用户体验
    1. 默认选中 ==> 减少用户操作
       若访问该页面的用户以男性居多 那么我们在设计的时候 可以令男性单选框有一个默认选中(checked||selected)的效果
    2. label ==> 方便用户操作
       给每一个 input 绑定 id 结合 lable 标签 可以方便用户操作 当用户点击 文本时 也可以实现聚焦
3. select 表单元素中属性值和属性名的书写位置问题
    属性名
       写在 select 元素上的 name 属性上
    属性值
       写在每一个 option 元素上的 value 属性上
       若咋们没有在每一个 option元素上定义value属性值
       那么提交的属性值默认是 option元素包裹的文本内容

到此为止 在开发中 HTML的主要使用标签已介绍完毕
实际上 html标签还有很多 并且每年还在不断地增加
但是我们实际上会用到的 差不多也就上面介绍的这些

其中一个原因是 其实HTML和CSS和JavaScript是三门语言
它们是三家不同的公司做的 HTML后续在添加标签的时候
总是想着新增的标签是否能够覆盖一些CSS、JavaScript的功能 不受它们的限制
但是呢 我们在实际开发时 我们一般是把三者相分离出来的
它们各自仅负责好自个儿的功能就好了 简单点说 就是 各司其职

咋们现在讲解的是 HTML4.01版本 这是最基础的版本
后面接触到的 HTML5.0 里面很多东西都是JavaScript相关了
也就是说 咋们在学习 HTML5.0之前 我们得学习完 JavaScript CSS CSS3 之后
才能更好的理解 H5中的知识点
```

**label和select**

```html
<form method="GET" action="">
    <h1>Choose your favourite fruit!</h1>
    <p>
        <label for="apple">
            1. apple <input type="checkbox" name="fruit" value="apple" id="apple">
        </label>
        <label for="orange">
            2. orange <input type="checkbox" name="fruit" value="orange" id="orange">
        </label>
        <label for="banana">
            3. banana <input type="checkbox" name="fruit" value="banana" id="banana">
        </label>
    </p>
    <h1>CHOOSE YOUR SEX!!!</h1>
    <p>
        <label for="meal">
            male: <input type="radio" name="sex" value="male" id="meal" checked>
        </label>
    </p>
    <p>
        <label for="female">
            female: <input type="radio" name="sex" value="female" id="female">
        </label>
    </p>
    <h1>Province</h1>
    <select name="province" id="">
        <option value="bj">北京</option>
        <option value="sh" selected>上海</option>
        <option value="gz">广州</option>
    </select>
    <p>
        <input type="submit">
    </p>
</form>
```

```
提交前: file:///C:/Users/23264/Desktop/stuProject/test.html
提交后: file:///C:/Users/23264/Desktop/stuProject/test.html?fruit=orange&fruit=banana&sex=male&province=sh#
发送到后端的数据: fruit=orange&fruit=banana&sex=male&province=sh
```

![20210313160313](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313160313.png)

2. 当前市面上的主流浏览器及其内核是?(常见面试题)

```
主流浏览器的两个必要条件:
    1. 一定的市场份额
    2. 有独立研发的内核(值钱)
浏览器的组成:
    1. shell(外壳 不值钱)
    2. 内核(值钱)
```

| 主流浏览器    | 内核         |
| ------------- | ------------ |
| IE            | trident      |
| Firefox       | Gecko        |
| Google chrome | Webkit/blink |
| Safari        | Webkit       |
| Opera         | presto       |

3. html注释

```
格式: <!-- -->
   <!-- 注释内容 -->
   快捷键: Ctrl + /
```

4. 工程师最重要的是啥?

```
嘴
1. 成哥介绍的公司中的配合流程
    1. 产品经理拿着产品来和你沟通(确认需求)
    2. 你再和UI沟通(获取psd文件)
    3. 你还得跟测试工程师沟通
    4. 你还得跟运营去沟通
2. 总而言之 全公司沟通的核心 就是你
3. 若编程时长是10 那么3在开发 7在调试
   若一个项目 我们在公司中把这个项目用代码给写成来的时间是t 那么整个项目的项目周期 应该是咋们写这个项目所需的时间*3
4. 大型互联网公司 大夏天 搞开发的标准穿搭 大背心 大裤衩 拖个拖鞋... 舒服
```

<div style="text-align: center; font-size: 24px; color: #008c8c; border: 1px dashed #666;"> 以下是CSS的内容</div>

5. CSS是啥?

[css mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS)

```
CSS 全称 cascading style sheet 层叠样式表
若第一次接触 那大致的看一下 mdn 上对 CSS 的简介
差不多有个大致的概念就好 写多了 自然会理解
```

6. 如何引入CSS?

[css 三种引入方式及格式 csdn](https://blog.csdn.net/jt18729260336/article/details/82468375)

```
行间样式
    直接在html元素的身上的style属性上 写CSS代码
页面级CSS
    在head里的style标签下写css

(讲到这儿 走远了 听成哥给你唠唠表达能力的重要性)

外部CSS文件
    link引入外部css文件
```

**notes**

```
这三种方式的优先级: 行间样式 > ( 页面级CSS = 外部CSS文件 )
```

7. 浏览器异步获取文件

```
用户在访问某个页面时 向服务器发起请求后 服务器返回相关的页面代码文件
试问 浏览器是如何下载这些代码文件的(同步/异步)?
```

```
答: 异步
    当用户从服务器那请求回一个 index.html 文件后
    浏览器会开始下载 index.html 中的代码
    并丢到浏览器中执行(下载一点执行一点)

    比如说 当下载到 咋们利用link标签引入css文件的那行代码时
    浏览器不会等到 css 文件下载完成后 再去下载后续的 html代码
    而是会开启一个新的线程 来下载css代码 原来的线程继续下载它的 html代码

    即 这是异步(同时)进行的
```

8. CSS选择器

[css选择器 mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Type_selectors)

```
1. id 选择器
2. class 选择器 (类选择器)
3. 标签选择器 (元素选择器)
4. 通配符选择器 (*)

上面介绍的这4个选择器 最基础
```

9. 选择器的优先级

```
!important > style(写在元素身上) > id > class = 属性 > 元素 > *
```

10. CSS选择器权重


| 选择器                  | 权重     |
| ----------------------- | -------- |
| !important              | infinity |
| 行间样式 (写在元素身上) | 1000     |
| id                      | 100      |
| class 属性 伪类         | 10       |
| 元素 伪元素             | 1        |
| 通配符                  | 0        |

**notes**

```
选择器权重问题 基本上很多CSS书籍上都有介绍到.

在vscode编辑器上 咋们将鼠标hover在咋们写的选择器上 可以直接看这个选择器的权重是多少

这权重值 并非是 10进制 是 256进制

计算机中的 infinity 和 数学上的 infinity
    它们之间是有所不同的
    在计算机中的 infinity 是有值的 它并非数学上的无穷
    在数学中 infinity + 1 和 infinity 之间 是没法比较大小的
    但是 在计算机中 infinity + 1 > infinity 是成立的
```

11. CSS 的两大特性

```
继承性
   概念
      CSS的继承性 是指子元素继承了父元素的某些样式属性
   注意
      并非所有CSS属性都具有继承性
      具有继承性的属性有以下3类
        1. 文本相关的属性
        2. 列表相关的属性
        3. 颜色相关的属性

层叠性
   概念
      CSS的层叠性 指的就是样式的覆盖
   注意
      层叠性遵循后来居上的原则 但必须具备以下3个条件
        1. 元素相同
        2. 属性相同
        3. 权重相同
```

**文本相关的属性**

`font-family` `font-size` `font-style` `font-weight` `font` `line-height` `text-align` `text-indent` `word-spacing`

**列表相关的属性**

`list-style-image` `list-style-position` `list-style-type` `list-style`

**颜色相关的属性**

`color`


12. CSS 优先级

```
由 CSS 特性中的层叠性 我们知道当样式发生冲突时 会进行样式的覆盖
```

| 样式发生冲突的5种情况  | 描述                                    |
| ---------------------- | --------------------------------------- |
| 引用方式冲突           | 行内样式 > (内部样式 = 外部样式)        |
| 继承方式冲突           | 选用最近的父元素                        |
| 指定样式冲突           | 由选择器的权重来决定 选中权重优先级高的 |
| 继承样式和指定样式冲突 | 指定样式 > 继承样式                     |
| !important             | 直接覆盖其他的样式声明                  |

## 4.2 学员必听

> 介绍渡一的联系方式...

## 4.3 `css复杂选择器` `权重计算问题` `css基础属性`

1. 后代选择器

`要求只选中div下面的span`

```css
.wrapper span {
    background-color: red;
}
```

```html
<div class="wrapper">
    <span>123</span>
</div>
<span>234</span>
```

```
叫法很多: 父子选择器/派生选择器/后代选择器
知道它怎么写 怎么用即可
```

2. 直接子元素选择器

`要求只选中 1`

```css
div>em {
    background-color: red;
}
```

```html
<div>
    <em>1</em>
    <stong><em>2</em></stong>
</div>
```

3. 浏览器解析父子选择器的方式

`要求 让1变色`

```css
section div ul li a em {
    background-color: red;
}
```

```html
<section>
    <div>
        <p>
            <a href="">
                <span></span>
                <ul>
                    <li>
                        <a href="">
                            <span>
                                <em>1</em>
                                <p></p>
                            </span>
                        </a>
                        <li></li>
                    </li>
                </ul>
            </a>
        </p>
        <a href="">
            <div></div>
            <p><em>2</em></p>
        </a>
    </div>
</section>
```

```
浏览器的底层原理:
    浏览器在遍历父子选择器的时候 是 自右向左进行遍历的

子认爹 而非 爹找子
    但是最终操作的还是 子
```

> 这一个知识点 在 《从0到1 CSS进阶之旅》10.6.1 选择器在浏览器中的解析原理 中 也有介绍到

4. 并列选择器

`要求 让2变色`

```css
div.demo {
    background-color: red;
}
```

```html
<div>1</div>
<div class="demo">2</div>
<p class="demo">3</p>
```

```
并列选择器
   可以理解为 用多个限制条件来限定想要选中的元素

注意
   1. 若元素选择器和其他类型的选择器一起出现
      那么 需要将标签选择器写在最前面
   比如
      div.demo 不能写成 .demodiv
   2. 其他类型的选择器相互并列 随意搭
   比如
      .demo#only[class="box"] 等价于 #only[class="box"].demo
```

5. 分组选择器

```css
.demo1,
.demo2 {
    width: 100px;
    height: 100px;
    line-height: 100px;
    text-align: center;
    font-size: 20px;
    font-weight: bold;
    border: 1px solid #666;
    border-radius: 5%;
}

.demo1 {
    color: #008c8c;
}

.demo2 {
    color: #f40;
}
```

```html
<div class="demo1">1</div>
<div class="demo2">2</div>
```

![20210313164046](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313164046.png)

```
分组选择器
    应用场景 常用于减少代码的冗余度
分组选择器的写法: 用逗号将每一组相互分开即可
    demo1, demo2 { css代码 }
```

> 选择器的相关知识就介绍这么多, 下面是 CSS 属性 的相关内容

6. CSS属性

- [font-size mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)

```
font-size 用于设置字体的大小
注意: 它设置的是字体的高 而不是字体的宽
```

- [font-weight mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)

```
只要记住一个属性值 bold(加粗) 即可

注意: bold 和 bolder
    font-weight 它有一个属性值 bolder 表示更粗
    很多时候 我们书写这个属性值 会发现页面上的字体并没有被加到更粗
    视觉上 bold 和 bolder 效果相同 这是因为对应的字体包里头 该字体就没有更粗的样式
```

- [font-style mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)

```
记住一个值 italic(斜体) 即可
```

- [font-family mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)

```
最通用的字体 arial (乔布斯发明的)
```

- [color mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/color)

```
颜色值写法
    1. 土鳖式 (纯英文单词)
       开发时 一般不会使用纯英文单词
       测试时 才会使用到 土鳖式的纯英文单词
    2. 颜色代码
    3. 颜色函数

写法上的一些具体细节 比如啥 简写形式啥的 若遇到查就行

涨知识
  罗曼蒂葡萄酒 葡萄酒颜色 ...
  阿里的logo 是一开始被马云给淘汰的 但是最后又从垃圾桶里捡回来 发现它还不错
  淘宝红 #f40 的由来 听说这颜色值 是当时由很多心理鉴定师鉴定后的结果
```

- [border mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/border)

```
border 是一条简写属性
   border: border-width border-style border-color;

   border: 1px dashed black;
   等价于:
     border-width: 1px;
     border-style: dashed;
     border-color: black;
```

**画三角形**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>lesson2</title>
    <style>
        div {
            width: 0;
            height: 0;
            border: 100px solid transparent;
            border-bottom-color: red;
        }
    </style>
</head>

<body>
    <div></div>
</body>

</html>
```

![20210313172546](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313172546.png)

## 4.4 `css企业开发经验及习惯` `盒子模型` `层模型`

1. CSS属性

> 继续讲 CSS 属性

- [text-align mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)

```
left 默认值 文本左对齐
center 文本居中对齐
right 文本右对齐
```

- [line-height mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)

```
font-size 和 line-height
  font-size
    设置的是文字的高度
  line-height
    设置的是单行文本的高度 (也就是我们在编辑word时所设置的行高)

line-height 的常见用法
  实现单行文本垂直居中 令 line-height 等于 heiht

问: 1.2倍行高如何设置?
答: line-height: 1.2em;
```

- [text-indent mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent)

```
text-indent 常见用法
  首行缩进2个字符
    text-align: 2em;

    PS: 我们在一段中文文本中 首行缩进俩个汉字 感觉上可以通过html编码中的空格 &nbsp; 来实现 不够就多加 过了就少加
    但是实际上这是实现不了的 因为空格这个字符 到底多宽 受很多因素的影响 比如: 操作系统 全角 半角 ...

单位 1em 表示的是一个 font-size 它是一个相对单位 px 也是一个相对单位
  问: 我们前面介绍到了 font-size 表示的是一个字体的高度 那么 text-indent: 2em; 表示的那不就是两个字体的高度 而非两个字体的宽度嘛? 那有如何实现首行缩进两个字符的效果呢?
  答: 实际上 互联网上的通用字体 它们对于汉字的处理 都是让每一个汉字的宽度与它的高度值相等的 所以咋们使用 text-indent: 2em; 来实现首行缩进2个字符 是没问题滴.

屏幕的分辨率是如何定义的呢?
  屏幕上 从上到下 一个英寸的长度 包含的像素点的个数
```

> 绝对单位 和 相对单位 ==> 《从0到1 CSS进阶之旅》/第1章 基础知识/1.2 CSS单位

- [text-decoration mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)

**a标签去除下划线**

```
a标签默认带有 text-decoration: underline;
  问: 如何去除a标签默认的下划线
  答: text-decoration: none;
```

**一些 html 元素身上的默认样式**

```
前面在介绍 html 的 del 标签时 会发现被他包裹的内容 会带有一条中划线
实际上就是因为 它身上就默认带有 text-decoration: line-throgh; 这条 css 声明

我们在实际开发中 一般都不会使用del标签 因为 HTML 只要让它负责好结构就行了 del标签带有的这种效果
我们通常会采用 span标签 来实现 然后给对应的span标签添加上对应的 text-decioration: line-through; 即可

还有很多标签也默认带有一些 css 声明, 比如 strong 默认带有 font-weight: bold; i 标签默认带有 font-style: italic;
然而 很多时候, 我们是不希望标签默认有自带样式的, 我们希望样式就交给 css 来实现, html 管好结构方面的事儿就好

所以 我们说 div 和 span 这两个标签是很好的容器, 因为它们身上很 "干净";
而且 我们之后或许会看到一些名为 reset.css 的文件, 这些文件的作用就是 重置 html 标签身上的默认样式

但是 如果有一些标签的语义化实在很好...  那即便它带有一些咋们不想要的默认样式 咋们还是会用它的
这部分好像还涉及到一些有关 SEO 搜索引擎优化部分的相关知识点(比如标题标签) 目前阶段 先做了解即可
```

**补充**

```
CSS 注释
  语法: /* Comment */
  快捷键: Ctrl + /
```

1. 伪类选择器

- `:hover`

```html
<a href="#" id="link">dahuyou</a>
```

```css
a {
    color: red;
}

a:hover {
    color: green;
}
```

![20210313195232](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313195232.png)

![20210313195728](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313195728.png)

`鼠标悬停 正常变绿`

```css
a#link {
    color: red;
}

a:hover {
    color: green;
}
```

![20210313195232](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313195232.png)

![20210313195232](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313195232.png)

`鼠标悬停 还是红的`

```
记录一个遇到的 bug... 权重问题
    a { color: red; }
    a:hover { color: green; }
问: 为什么当鼠标悬停在a元素上时 咋们添加到 a:hover 上的样式就可以展示出来?
答: 因为样式发生了冲突 并且后者的权重是比前者大的
    a#link { color: red; }
    a:hover { color: green; }
问: 为什么当鼠标悬停在a元素上时 我们添加到 a:hover 上的样式就展示不出来?
答: 因为样式发生了冲突 并且前者的权重比后者大

后续若遇到明明写了样式 却不生效 这样的情况, 记得检查一下, 看看是否是权重出现了问题
```

3. 行级元素 和 块级元素

```
行级元素的特点:
    内容决定元素所占位置(尺寸)
    不可以通过css改变宽高

块级元素的特点:
    独占一行
    可以通过css改变宽高
```

**互联网公司常见一面题**

```
请你列出常见的4个行级元素 4个块级元素
    行级
       span a strong em  del
    块级
       div p ul li ol form address
注意
   img 是行级块元素 即: inline-block
   inline-block元素的特点
      内容决定大小
      可以改变宽高
```

4. inline-block元素之间的间隙问题

```
凡是 带有inline的元素 都具有文字特性
    带有inline的元素
       也就是指: display: inline; 和 display: inline-block; 的元素
    具有文字特性
       在这里所强调的就是 多个连续不可见字符 会被识别为一个空格
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>inline-block元素之间的间隙问题</title>
    <style>
        .wrapper {
            text-align: center;
            /* font-size: 0px; */
        }

        span {
            display: inline-block;
            width: 100px;
            height: 100px;
            line-height: 100px;
            text-align: center;
            font-size: 32px;
            border: 1px solid #000;
        }

        .item1,
        .item3 {
            background-color: #008c8c;
        }

        .item2 {
            background-color: #f40;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <span class="item1">1</span>
        <span class="item2">2</span>
        <span class="item3">3</span>
    </div>
</body>

</html>
```

`会发现 span 与 span 之间存在间隙`

![20210313200947](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313200947.png)

`把 .wrapper 中的 font-size: 0px 这条注释给取消之后, 展示效果如下:`

![20210313200941](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313200941.png)

**解决方式**

```
1. 使用 margin-left: -?px; (数值通过控制台来微调)
   不推荐
      原因是 我们写好的代码 上传到服务器之前 一般都会对代码进行压缩
      我们通常采用去空格和回车(等不可见字符)的方式来对咋们写的代码进行压缩
      这样的话 多个inline-block元素之间的间隙 自然就被压缩掉了
      所以用户那边看到的 其实一开始就是正常的 然后咋们在开发的时候 又添加上了一个负margin值 那么一旦到线上 就不准了
2. 改变结构 让每一个inline-block之间没有空白文本
   不推荐 (不符合开发习惯)
3. 给父级添加上 font-size: 0; 子元素重新定义 font-size 属性值
   推荐 (开发的时候就能看到上线后的效果)
   PS: 这个技巧 在接下来接触到的淘宝首页开发中会着重介绍
```

5. **编程思维**

`先定义功能 后选配功能`

```
先定义功能 后选配功能
   也就是将一些常用的样式 给它提取出来 然后需要用到该样式的元素 咋们给它添上对应的类名儿就好
   在企业中 这种方式也是非常常用的 就是用前辈们写好的东西 直接引入到自己的项目中来就可以了
   所以说 在企业中 咋们一般第一个月 都是不写代码的 而是读代码 读前辈写的文档
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>lesson2</title>
    <style>
        .green {
            background: green;
        }

        .red {
            background: red;
        }

        .blue {
            background: blue;
        }

        .size1 {
            width: 30px;
            height: 30px;
        }

        .size2 {
            width: 50px;
            height: 50px;
        }

        .size3 {
            width: 100px;
            height: 100px;
        }
    </style>
</head>

<body>
    <div class="green size1"></div>
    <div class="red size2"></div>
    <div class="blue size3"></div>
    <div class="blue size2"></div>
    <div class="red size1"></div>
</body>

</html>
```

![20210313201750](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313201750.png)

6. 初始化样式

`通配符选择器常用于初始化样式`

```
* { padding: 0; margin: 0; }
  初始化样式 优点在于通配符选择器的权重是 0 其他随便啥选择器的优先级都比它高
```

7. 盒模型

[CSS 盒子模型 菜鸟教程](https://www.runoob.com/css/css-boxmodel.html)

8. 简介 如何在chrome控制台查看 html和css

9. padding 和 margin 和 border-width

```
属性值不同个数之间的区别:
   一个值 上右下左
   两个值 上下、左右
   三个值 上、左右、下
   四个值 上、右、下、左
```

10. 模拟远视图效果

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>模拟远视图</title>
    <style>
        .box4 {
            width: 10px;
            height: 10px;
            background: #fff;
        }

        .box3 {
            width: 10px;
            height: 10px;
            padding: 10px;
            background: #0f0;
        }

        .box2 {
            width: 30px;
            height: 30px;
            padding: 10px;
            background: #fff;
        }

        .box1 {
            width: 50px;
            height: 50px;
            padding: 10px;
            background: #0f0;
        }
    </style>
</head>

<body>
    <div class="box1">
        <div class="box2">
            <div class="box3">
                <div class="box4"></div>
            </div>
        </div>
    </div>
</body>

</html>
```

![20210313202435](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313202435.png)

11. 定位

- [CSS 定位详解 阮一峰](http://www.ruanyifeng.com/blog/2019/11/css-position.html)
- [demo1](https://jsbin.com/fegiqoquki/edit?html,css,output)
- [demo2](https://jsbin.com/decemanohe/edit?html,css,output)

```
阮一峰老师除了讲解了 position的 static absolute relative fixed 4个属性 还介绍了一个新的 sticky 定位
  大概看了一遍 sticky可以实现两个经典的应用场景
    demo1. 堆叠效果
    demo2. 表格的表头锁定

每一个 absolute定位的元素 都位于一个不同的层
  即: 脱离原来的层 和原来的层没关系了 原来占据的那块空间相当于不存在了

relative定位的元素
  相对于自身的原始位置进行定位
  和 absolute 定位的元素的不同点在于
    relative定位的元素会保留原始位置
    也就是说 它原来占据的那块空间依旧存在

涨知识
  21克的灵魂 与 2.1克拉的钻戒 2.1克拉的灵魂伴侣

弄清楚 relative absolute fixed 是相对于什么进行定位的
    relative 相对于自身的原始位置进行定位
    absolute 相对于最近的有定位(position属性值非static)的父级进行定位 若父级都没有定位 那么则相对于文档进行定位
      我们在实际开发中 一般将relative作为参照物 用absolute进行定位
    fixed 相对于浏览器视口进行定位
```

12. body 自带 margin 8px

13. 页面广告 垂直水平居中显示

```
目前了解到以下三种实现方式
    1. position: absolute; left: 50%; top: 50%; margin-left: -width/2; margin-top: -height/2;
    2. position: absolute; left: calc(50% - width/2); top: calc(50% - height/2);
    3. display: flex; justify-content: center: align-items: center;

notes
    前面两种是写在需要居中显示的元素身上
    第 3 种 是写在定位元素的父级身上 (flex布局是CSS3中的知识点)
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>水平垂直居中显示</title>
    <style>
        div {
            width: 100px;
            height: 100px;
            background-color: #ddd;
        }

        .box {
            position: absolute;
            left: 50%;
            top: 50%;
            margin-left: -50px;
            margin-top: -50px;
        }
    </style>
</head>

<body>
    <div class="box"></div>
</body>

</html>
```

![20210313203449](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313203449.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>水平垂直居中显示</title>
    <style>
        div {
            width: 100px;
            height: 100px;
            background-color: #ddd;
        }

        .box {
            position: absolute;
            left: calc(50% - 100px/2);
            top: calc(50% - 100px/2);
        }
    </style>
</head>

<body>
    <div class="box"></div>
</body>

</html>
```

![20210313203449](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313203449.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>水平垂直居中显示</title>
    <style>
        html,
        body {
            height: 100%;
        }

        .wrapper {
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .box {
            width: 100px;
            height: 100px;
            background-color: #ddd;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <div class="box"></div>
    </div>
</body>

</html>
```

![20210313203709](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313203709.png)

> 不知为何会出现滚动条...

14. 本节作业 写一个五环

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>五环</title>
    <style>
        .wrapper {
            position: relative;
            width: 500px;
            height: 300px;
            border: 1px solid #ddd;

            overflow: hidden;
            resize: both;
        }

        .circle {
            width: 80px;
            height: 80px;
            border: 5px solid;
            border-radius: 50%;
            position: absolute;
        }

        .blue {
            border-color: blue;
            top: 100px;
            left: 100px;
        }

        .black {
            border-color: black;
            top: 100px;
            left: 200px;
            z-index: 1;
        }

        .red {
            border-color: red;
            top: 100px;
            left: 300px;
        }

        .yellow {
            border-color: yellow;
            top: 150px;
            left: 150px;
        }

        .green {
            border-color: green;
            top: 150px;
            left: 250px;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <div class="circle blue"></div>
        <div class="circle black"></div>
        <div class="circle red"></div>
        <div class="circle yellow"></div>
        <div class="circle green"></div>
    </div>
</body>

</html>
```

![20210313203940](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313203940.png)

# 5. html - css lesson3高级篇

## 5.1 `实例: 居中五环` `两栏布局` `两个经典bug` `BFC`

1. 命名规范(语义化)

> from: 《从0到1 CSS进阶之旅》/第2章 CSS规范/2.2 命名规范

- **CSS文件命名**

文件名 | 说明
---|---
reset.css | 重置样式 重置元素默认样式
global.css | 全局样式 全站公用 定义页面基础样式
theme.css | 主题样式 用于实现换肤功能
module.css | 模块样式 用于模块的样式
master.css | 母版样式 用于母版页的样式
column.css | 专栏样式 用于专栏的样式
form.css | 表单样式 用于表单的样式
mend.css | 补丁样式 用于维护、修改的样式
print.css | 打印样式 用于打印的样式

- **网页主体部分命名**

网页部分 | 命名
---|---
最外层 | wrapper(一般用于包裹整个页面内)
头部 | header
侧栏 | sidebar
栏目 | column
热点 | hot
新闻 | news
下载 | download
标志 | logo
导航条 | nav
主体 | main
左侧 | main-left
右侧 | main-right
底部 | footer
友情链接 | friendlink
加入我们 | joinus
版权 | copyright
服务 | service
登录 | login
注册 | register

- **网页细节部分命名**

1. **导航**

网页部分 | 命名
---|---
主导航 | main-nav
子导航 | sub-nav
边导航 | side-nav
右导航 | leftside-nav
右导航 | rightside-nav
顶导航 | top-nav

2. **菜单**

网页部分 | 命名
---|---
菜单 | menu
子菜单 | submenu


3. **其他**

网页部分 | 命名
---|---
标题 | title
摘要 | summary
登录条 | loginbar
搜索 | search
标签页 | tab
广告 | banner
小技巧 | tips
图标 | icon
法律声明 | siteinfolegal
网站地图 | sitemap
工具条 | homepage
子页 | subpage
合作伙伴 | parter
帮助 | help
指南 | guild
滚动 | scroll
提示信息 | msg
投票 | vote
相关文章 | related
文章列表 | list

- **CSS属性书写顺序**

属性类别 | 举例
---|---
影响文档流属性(布局属性) | `display`、`position`、`float`、`clear`等
自身盒模型属性 | `width`、`height`、`padding`、`margin`、`border`、`overflow`等
文本性属性 | `font`、`line-height`、`text-align`、`text-indent`、`vertical-align`等
装饰性属性 | `color`、`background-color`、`opacity`、`cursor`等
其他属性 | `content`、`list-style`、`quotes`等

2. 居中五环

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>五环居中 成哥版</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }

        .plat {
            position: absolute;
            left: 50%;
            top: 50%;
            margin-left: -190px;
            margin-top: -93px;
            height: 186px;
            width: 380px;
        }

        .circle1,
        .circle2,
        .circle3,
        .circle4,
        .circle5 {
            position: absolute;
            width: 100px;
            height: 100px;
            border: 10px solid;
            border-radius: 50%;
        }

        .circle1 {
            border-color: red;
            left: 0;
            top: 0;
        }

        .circle2 {
            border-color: green;
            left: 130px;
            top: 0;
            z-index: 3;
        }

        .circle3 {
            border-color: yellow;
            left: 260px;
            top: 0;
        }

        .circle4 {
            border-color: blue;
            left: 65px;
            top: 70px;
        }

        .circle5 {
            border-color: purple;
            left: 195px;
            top: 70px;
        }
    </style>
</head>

<body>
    <div class="plat">
        <div class="circle1"></div>
        <div class="circle2"></div>
        <div class="circle3"></div>
        <div class="circle4"></div>
        <div class="circle5"></div>
    </div>
</body>

</html>
```

![20210313210100](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313210100.png)

3. 两栏布局

- 写法1

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>两栏布局</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }

        .right {
            position: absolute;
            right: 0;
            width: 100px;
            height: 100px;
            background-color: #fcc;
            opacity: .5;
        }

        .left{
            margin-right: 100px;
            height: 100px;
            background-color: #123;
        }
    </style>
</head>

<body>
    <!--注意点: 这种实现方式 html的结构 必须是 定位的写在前面 设置margin的写在后面-->
    <div class="right"></div>
    <div class="left"></div>
</body>

</html>
```

![20210313210317](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313210317.png)

- 写法2

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>两栏布局 也可以利用 -margin技术来实现</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }

        .right {
            /* position: absolute;
            right: 0; */
            display: inline-block;
            width: 100px;
            height: 100px;
            background-color: #fcc;
            opacity: .5;
        }

        .left{
            display: inline-block;
            width: 100%;
            margin-right: -100px;
            height: 100px;
            background-color: #123;
        }
    </style>
</head>

<body>
    <div class="left"></div><div class="right"></div>
</body>

</html>
```

![20210313210427](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313210427.png)

- 写法3

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>两栏布局 也可以利用 calc技术来实现</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }

        .right {
            /* position: absolute;
            right: 0; */
            display: inline-block;
            width: 100px;
            height: 100px;
            background-color: #fcc;
            opacity: .5;
        }

        .left{
            display: inline-block;
            width: calc(100% - 100px);
            height: 100px;
            background-color: #123;
        }
    </style>
</head>

<body>
    <!-- 注意 inline-block元素之间的间隙问题 -->
    <div class="left"></div><div class="right"></div>
</body>

</html>
```

![20210313210317](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313210317.png)

4. margin塌陷 和 margin合并

> 回顾《从0到1 CSS进阶之旅》3.4 外边距叠加 即可 书上说的 margin叠加 实际上就包括了这里提到的 margin塌陷 和 margin合并

- margin塌陷

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>margin塌陷</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }

        .wrapper {
            margin-left: 100px;
            margin-top: 100px;
            width: 100px;
            height: 100px;
            background-color: #000;

            /* 触发BFC 解决margin塌陷的问题 */
            overflow: hidden;
        }

        .content {
            margin-left: 50px;
            margin-top: 50px;
            width: 50px;
            height: 50px;
            background-color: #0f0;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <div class="content"></div>
    </div>
</body>

</html>
```

![20210313210929](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313210929.png)

![20210313211032](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313211032.png)

**notes**

```
解决margin塌陷这个问题的几种方式
  1. overflow: hidden;
  2. display: inline-block;
  3. position: absolute;

问: 上面这些方法 虽然都可以解决margin塌陷的问题 但是如何取舍呢?
答: 这一点得视情况而定 虽然这些方式都可以解决margin塌陷的问题
    但是它们也多多少少会造成一些影响 如果这些影响与当前的需求无关 那就OK
```

- margin合并

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>mamrgin合并</title>
    <style>
        .box1 {
            color: red;
            border: 1px solid #ddd;
            margin-right: 100px;
        }

        .box2 {
            color: blue;
            border: 1px solid #ddd;
            margin-left: 100px;
        }

        .demo1 {
            color: green;
            border: 1px solid #ddd;
            margin-bottom: 100px;
        }

        .demo2 {
            color: purple;
            border: 1px solid #ddd;
            margin-top: 100px;
        }
    </style>
</head>

<body>
    <span class="box1">123</span>
    <span class="box2">234</span>
    <div class="demo1">1</div>
    <div class="demo2">2</div>
</body>

</html>
```

![20210313211517](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313211517.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>mamrgin合并</title>
    <style>
        .box1 {
            color: red;
            border: 1px solid #ddd;
            margin-right: 100px;
        }

        .box2 {
            color: blue;
            border: 1px solid #ddd;
            margin-left: 100px;
        }

        .demo1 {
            color: green;
            border: 1px solid #ddd;
            margin-bottom: 100px;
        }

        .demo2 {
            color: purple;
            border: 1px solid #ddd;
            /* margin-top: 100px; */
            margin-top: 150px;
        }
    </style>
</head>

<body>
    <span class="box1">123</span>
    <span class="box2">234</span>
    <div class="demo1">1</div>
    <div class="demo2">2</div>
</body>

</html>
```

![20210313211525](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313211525.png)

```html
<div class="wrapper" style="overflow: hidden;">
    <div class="demo2">2</div>
</div>
```

```
会发现 .demo1 和 demo2 垂直方向上的 margin 合并了
为了防止它们的 margin 合并 我们可以给其中一个添加上父级
父级上设置 overflow: hidden; 触发一下BFC 即可解决
但是这种做法通常都是不允许的 也就是为了改一个bug 而特意去修改 html结构
所以这个问题 咋们一般不解决 如果想要实现效果 我们可以直接把 margin 值加在一个元素上
比如上述案例 我们就可以直接将 .demo1 的 margin-bottom 值 加上 .demo2 的margin-top 值 的结果 设置在 .demo2 的 margin-top 上即可
```

5. **BFC**

> 《从0到1 CSS进阶之旅》/12.4 BFC 和 IFC

```
1. block format context (块级格式化上下文)
2. 什么是BFC (书上的说法)
   BFC 全称 Block Formatting Context (块级格式上下文) 它是一个独立的渲染区域
   只有块盒子 (block-level box) 参与 块级格式上下文规定了内部的块盒子是如何布局的
   并且这个渲染区域与外部区域毫不相关
3. 如何创建一个BFC(书上的说法)
    1. 根元素
    2. float属性除了none以外的值
       也就是 left 和 right
    3. position属性除了static和relative之外的值
       也就是 absolute 和 fixed
    4. overflow属性除了 visible 以外的值
       也就是 auto hidden scroll
    5. 元素类型 (即 display属性) 为 inline-block table-caption tabl-cell
    满足上述其中一个条件即可
```

6. float

- [CSS 浮动 W3school](https://www.w3school.com.cn/css/css_positioning_floating.asp)
- [浮动元素容器的clearing问题 阮一峰](http://www.ruanyifeng.com/blog/2009/04/float_clearing.html)
- [浮动 mdn](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Floats)

**认识浮动**

```
浮动是CSS2.0提出的一种布局方式
  浮动布局最初的目的是为了让网页能展示出报纸形式的布局效果
  文字环绕图片 直接给图片设置 float 浮动即可

浮动元素会产生浮动流
  所有产生了浮动流的元素 块级元素看不到他们
  产生了bfc的元素和文本类属性(inline 和 inline-block)的元素 以及 文本 都能看到浮动元素
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>只有块级元素看不到浮动元素</title>
    <style>
        .box {
            float: left;
            width: 100px;
            height: 100px;
            background-color: #000;
            opacity: 0.5;
        }

        .demo {
            /* 设置 float: left/right 触发BFC
            令块级元素看到浮动元素 */
            /* float: left; */
            width: 150px;
            height: 150px;
            background-color: green;
        }
    </style>
</head>

<body>
    <div class="box"></div>
    <div class="demo"></div>
</body>

</html>
```

![20210313212409](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313212409.png)

![20210313212456](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313212456.png)

**清除浮动三件套**

```css
.clearfix::after{
    content: "";
    display: block;
    clear: both;
}
```

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <title>清除浮动</title>
    <style type="text/css">
        #wrapper {
            width: 250px;
            margin: 100px auto;
            border: 1px solid purple;
            /* overflow: hidden; */
        }

        #first,
        #second {
            width: 100px;
            height: 50px;
            border: 1px solid red;
        }

        #first {
            float: left;
        }

        #second {
            float: right;
        }

        .clearfix::after{
            content: "";
            display: block;
            clear: both;
        }

        /* #clear {
            clear: both;
        } */
    </style>
</head>

<body>
    <div id="wrapper" class="clearfix">
        <div id="first"></div>
        <div id="second"></div>
        <!-- <div id="clear"></div> -->
    </div>
</body>

</html>
```

![20210313212735](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313212735.png)

![20210313212804](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313212804.png)

**一共有三种常见的清除浮动的方式**

```
1. 父元素上声明 overflow: hidden;
   优点
      代码量少
   缺点
      会隐藏溢出内容
      (有时候我们想让溢出内容不被隐藏 那么这种方式就有点不适用了)

2. 在父元素的最后一个子元素上设置 clear: both;
   优点
      几乎没啥优点
   缺点
      需要修改html结构 非常不推荐

3. 利用 ::after 伪元素 来清除浮动
   优点
      .clearfix::after 的三件套 写一遍就够了 需要清除浮动的父元素 直接加上它就可以清除浮动;
      相对于第一种方式 overflow: hidden; 而言 .clearfix::after 不会对溢出内容产生影响;
   缺点
      得背...
```

## 5.2 简短而重要的环节

`简短的课程大纲介绍`

## 5.3 css 高级篇-包裹浮动元素 开发实例 经验

1. 浮动(补充)

`继续讲解 5.1 中的浮动内容`

[伪元素 mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-elements)

- ::after

`在介绍清除浮动三件套前 先要认识一下 ::after 伪元素`

```
什么是伪元素?
   伪元素是一个附加至选择器末的关键词，允许你对被选中元素的特定部分修改样式。

有关伪元素的注意事项
  1. 一个选择器中只能使用一个伪元素。
  2. 伪元素必须紧跟在语句中的简单选择器/基础选择器之后。
  3. 按照规范，应该使用双冒号（::）而不是单个冒号（:），以便区分伪类和伪元素。
     但是，由于旧版本的 W3C 规范并未对此进行特别区分，因此目前绝大多数的浏览器都同时支持使用这两种方式来表示伪元素。

notes
  1. 伪元素是本来就存在于元素上的 我们使用伪元素选择器 是选中了伪元素 而非 创造了伪元素
  2. 伪元素的内容
     通过 content 属性来定义
  3. 伪元素默认是 inline 元素
  4. ::before 伪元素 和 ::after 伪元素
     ::before 伪元素 在逻辑最前
     ::after 伪元素 在逻辑最后
```

**清除浮动三件套**

```css
.clearfix::after{
    content: "";
    /* 如果想让 clear属性 生效 那么该元素必须是一个块级元素 */
    display: block;
    clear: both;
}
```

**补充**

```
凡是设置了 position: absolute; float: right/left; 的元素 会自动转换为 inline-block类型的元素
所以我们如果是使用触发 BFC 的方式来清除浮动的话 那么我们会发现 父元素的border 会紧紧地包裹住浮动元素 ( 因为inline-block元素的尺寸有内容决定 )
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>bfc清除浮动</title>
    <style>
        .wrapper {
            border: 10px dashed red;
            /* 触发父级BFC 清除浮动 */
            position: absolute;
            /*
            凡是设置了
            1. position: absolute;
            2. float: right/left;
            的元素 会自动转换为 inline-block类型的元素
             */
        }

        .float-box {
            width: 100px;
            height: 100px;
            border: 1px solid #008c8c;
            line-height: 100px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
            color: white;
            background-color: #000;
            float: left;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <div class="float-box">1</div>
        <div class="float-box">2</div>
        <div class="float-box">3</div>
    </div>
</body>

</html>
```

![20210313214014](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313214014.png)

---

`利用浮动 模拟淘宝导航栏效果 (前面在讲 html 无序列表那部分的时候 写过一遍 效果差差不多)`

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>模拟淘宝导航栏效果</title>
    <style>
        a {
            text-decoration: none;
        }

        .nav {
            list-style: none;
        }


        .nav .list-item {
            float: left;
            margin: 0 10px;
            height: 30px;
            line-height: 30px;
            /* border: 1px solid black; */
        }

        .nav .list-item a {
            display: inline-block;
            padding: 0 5px;
            border-radius: 15px;
            height: 30px;
            color: #f40;
            font-weight: bold;
        }

        .nav .list-item a:hover {
            background-color: #f40;
            color: #fff;
        }

        .clearfix::after{
            content: "";
            display: block;
            clear: both;
        }
    </style>
</head>

<body>
    <ul class="nav">
        <li class="list-item">
            <a href="#">天猫</a>
        </li>
        <li class="list-item">
            <a href="#">聚划算</a>
        </li>
        <li class="list-item">
            <a href="#">天猫超市</a>
        </li>
    </ul>
</body>

</html>
```

![20210313214133](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313214133.png)

# 6. html - css lesson4升华篇

## 6.1 文字溢出处理 背景图片处理 企业开发经验

1. 单行文本溢出打点显示

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>单行文本溢出打点显示</title>
    <style>
        p {
            width: 200px;
            height: 20px;
            line-height: 20px;
            border: 1px solid #ddd;

            /* 溢出内容打点显示 */
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
    </style>
</head>

<body>
    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
</body>

</html>
```

`展示效果:`

<p style="
width: 200px;
height: 20px;
line-height: 20px;
border: 1px solid #ddd;
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;">Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>

> 会发现无法选中结尾的那 3 个点 ...

**单行文本溢出打点显示 三件套**

```css
selector {
   white-space: nowrap;
   overflow: hidden;
   text-overflow: ellipsis;
}
```

**细节**

```
尝试选中最后的那三个小点 ...
   会发现如果是使用三件套来实现的单行文本溢出打点显示 那么这3个点是无法选中的
   但是 页面中的 多行文本溢出打点显示 会发它的点是可以选中的

   实际上它的实现手法和单行文本是完全不一样的 那3个点 是输入进去的 也就是手敲的

多行文本 溢出内容打点显示的实现方式: (猜的)
   前端先大致的估算一下容器大概可以容纳多少个汉字 然后要求后端传递过来的文字 再将要溢出容器的时候 将文字删掉 添上3个点 ...

PS: 多行文本溢出打点显示 这个技术实际上是有的 在CSS3中会介绍 但是 那仅仅适用于移动端
```

2. 多行文本溢出截断处理

```
问: 盒子的 content 内容区 所能容纳的文本行数计算
答: 由 height = n * line-height (容器的高度 = 文本的行数 * 文本的行高)
    得 容器内容区放 n 行文本
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>多行文本溢出截断处理</title>
    <style>
        p {
            width: 200px;
            height: 40px;
            line-height: 20px;
            border: 1px solid #ddd;

            /* 多行文本溢出截断处理 */
            overflow: hidden;
            text-overflow: ellipsis;
        }
    </style>
</head>

<body>
    <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sed, doloremque.</p>
</body>

</html>
```

<p style="
width: 200px;
height: 40px;
line-height: 20px;
border: 1px solid #ddd;
overflow: hidden;
text-overflow: ellipsis;">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sed, doloremque.</p>

`多行文本溢出截断处理两件套`

```css
selector {
   overflow: hidden;
   text-overflow: ellipsis;
}
```

3. `background`

[background mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background)

**background-position 和 position**

```
作用对象上的区别
   background-position 作用于 定位背景图片
   position 作用于 定位元素

若要实现垂直水平居中效果
    background-position: 50% 50%;
       我们只需要 50% 50% 即可实现
       效果等价于 center center (如果想要居中显示 咋们还是直接写 center center 好一些 不然可能会和 position 记混)
    position: absolute;
    top: calc(50% - 1/2的 height)
    left: calc(50% - 1/2的 width)
       绝对定位的元素 需要居中显示 我们需要 50% 减二分之一的宽高才行
```

4. 以图换字

```
去除淘宝网的全部 CSS 也能正常实现购物功能 这种需求 是一些大型互联网公司会考虑的点
当用户的网速不好的时候 页面只加载了 html 但是还没加载 css
那么我们要求展示文字 为了达到这种效果 我们可以使用以图换字的写法来实现
```

- 方式1

```css
selector {
    text-indent: -9999px;
}
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>以图换字</title>
    <style>
        a {
            text-decoration: none;
            color: inherit;
        }

        .img-box {
            display: inline-block;
            width: 286px;
            height: 118px;
            background-image: url(//gw.alicdn.com/tfs/TB176rg4VP7gK0jSZFjXXc5aXXa-286-118.png);
            /* 隐藏文本 */
            text-indent: -9999px;
        }
    </style>
</head>

<body>
    <h1>
        <a href="http://www.taobao.com" class="img-box">
            淘宝网
        </a>
    </h1>
</body>

</html>
```

![20210313232453](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313232453.png)

**原理**

```
text-indent: -9999px;
  正常情况下, 用户的屏幕宽度不会达到 9999px
  所以设置文本缩进 9999px 就能确保用户屏幕上看不到文本 从而达到隐藏文本的效果
```

- 方式2

```css
selector {
    text-indent: 大于图片宽度值;
    white-space: nowrap;
    overflow: hidden;
}
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>以图换字</title>
    <style>
        a {
            text-decoration: none;
            color: inherit;
        }

        .img-box {
            display: inline-block;
            width: 286px;
            height: 118px;
            background-image: url(//gw.alicdn.com/tfs/TB176rg4VP7gK0jSZFjXXc5aXXa-286-118.png);

            /* 隐藏文本 */
            text-indent: 300px;
            white-space: nowrap;
            overflow: hidden;
        }
    </style>
</head>

<body>
    <h1>
        <a href="http://www.taobao.com" class="img-box">
            淘宝网
        </a>
    </h1>
</body>

</html>
```

**原理**

```
text-indent: 大于图片宽度值;
  设置 text-indent 把文本内容推到容器之外 让文字溢出
white-space: nowrap;
  不能让它换行 不然的话 它会换行显示 而不会溢出
overflow: hidden;
  最后把溢出的内容隐藏接即可
```

- 方式3

```css
selector {
    padding-top: 图片的高度;
    height: 0;
    overflow: hidden;
}
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>以图换字</title>
    <style>
        a {
            text-decoration: none;
            color: inherit;
        }

        .img-box {
            display: inline-block;
            width: 286px;
            /* 若采用这种方式来实现, 那么不需要设置 图片容器的 height (因为设置到了 padding 上)
            height: 118px; */
            height: 0px;
            background-image: url(//gw.alicdn.com/tfs/TB176rg4VP7gK0jSZFjXXc5aXXa-286-118.png);

            /* 隐藏文本 */
            height: 0px;
            padding-top: 118px;
            overflow: hidden;
        }
    </style>
</head>

<body>
    <h1>
        <a href="http://www.taobao.com" class="img-box">
            淘宝网
        </a>
    </h1>
</body>

</html>
```

**原理**

```
利用 padding 实现以图换字效果的方式 需要我们充分理解 默认情况下 背景图片的填充范围 是包含contentBox 和 paddingBox 的
padding 上是可以加 背景图片 和 背景颜色 滴
但是内容是在内容盒中的 不能加到 padding 中
淘宝用的就是这种实现方式
```

![20210313234847](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313234847.png)

> `text-indent: -9999px;` 这条 CSS 声明 加或者不加 效果都一样 关键在于 height: 0px; padding-top: 图片高度; (这个淘宝的 logo 的高度是 59px)

4. 两个特殊的 html 标签

```
1. p标签 里面不能套块级元素
   我们知道 行级元素只能嵌套行级元素 而 块级元素 即可以嵌套行级元素 也可以嵌套块级元素
   但是 p是一个比较特殊的块级元素
   比如: <p><div></div></p> 我们让p嵌套一个div 那么浏览器解析后 这个p会被砍成两个p
2. a标签 里不允许嵌套 a标签
   比如: <a href="#"><a href="#"></a></a> 我们让a标签里面嵌套a标签 那么浏览器解析后
   这两个a标签会呈现并列关系 而非父子关系
```

```html
<!-- 这是我们所写的 html 结构 -->
<a href="#"><a href="#"></a></a>
```

![20210313235634](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210313235634.png)

## 6.2 一个特别的辅助工具

`推送渡一的微信公众号`

![20210314000132](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210314000132.png)

## 6.3 css 升华篇 - css要点补充说明

`本节讲解的内容 主要是为了后续的淘宝静态首屏开发做准备`

1. 浏览器宽度改变 保持 content 部分不变

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>浏览器宽度改变 保持content部分不变</title>
    <style>
        .wrapper {
            height: 30px;
            background-color: #123;
        }

        .content {
            margin: 0 auto;
            width: 1000px;
            height: 30px;
            background-color: #0f0;
        }
    </style>
</head>
<body>
    <div class="wrapper">
        <div class="content"></div>
    </div>
</body>
</html>
```

![20210314000334](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210314000334.png)

2. inline-block间隙问题

`老生常谈了... 父级 font-size: 0; 自身重新定义 font-size的值`

> 注意 自身别用 em 作为单位... 因为它是相对父级的 font-size 来计算的

3. 回顾 `inline-block` 部分知识点

> 设置了 `position: absolute;` 或者 `float: left/right;` 的 html 元素会自动转化为 `inline-block` 类型的元素

4. 对齐问题

- 文本与文本之间 底部对齐

```html
<div>
    哈哈哈<span style="font-size: 50px;">呵呵</span>
</div>
```

`展示效果:`

<div>
    哈哈哈<span style="font-size: 50px;">呵呵</span>
</div>

- 文本与图片之间 底部对齐

```html
<img src="//gw.alicdn.com/tfs/TB176rg4VP7gK0jSZFjXXc5aXXa-286-118.png" style="border: 1px solid #ddd;">呵呵
```

![20210314001021](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210314001021.png)

- inline-block 和 文本
    - 若 inline-block 中没有文本 那么和 inline-block 的底部对齐
    - 若 inline-block 中有文本 那么和 inline-block 中的文本的底部对齐
- inline-block 无文本

```html
<span style="display: inline-block;width: 100px;height: 100px;background-color: #f00;"></span>呵呵
```

`展示效果:`

<span style="display: inline-block;width: 100px;height: 100px;background-color: #f00;"></span>呵呵

- inline-block有文本

```html
<span style="display: inline-block;width: 100px;height: 100px;background-color: #f00;font-size: 50px;">123</span>呵呵
```

`展示效果:`

<span style="display: inline-block;width: 100px;height: 100px;background-color: #f00;font-size: 50px;">123</span>呵呵

5. vertical-align

`vertical-align 用于定义周围元素 相对于该元素的对齐方式`

[vertical-align mdn](https://developer.mozilla.org/zh-CN/docs/Web/CSS/vertical-align)

> vertical-align 和 字体 水太深了... 水平不够 不能仔细研究... 浪费了好多时间 还没弄懂

6. 左浮动 and 右浮动 实现 导航栏布局

```html
<div class="nav">
    <ul style="float:left;">
        <!-- 左侧导航的内容 -->
    </ul>
    <ul style="float:right;">
        <!-- 右侧导航的内容 -->
    </ul>
</div>
```

## 6.4 css 升华篇 - 项目演练

1. 做一个小的页面效果

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>成哥贴吧</title>
    <style>
        div {
            width: 200px;
            height: 20px;
            line-height: 20px;
            font-size: 12px;
            background: linear-gradient(to bottom, blue, lightblue); /* 颜色渐变效果 */
            color: rgba(255, 255, 255, 0.8);
            padding: 0 5px;
        }

        div::before {
            content: "";
            display: inline-block;
            width: 12px;
            height: 11px;
            /* background-image: url(../baidu.jpg); */
            /* 这张图找不到了... 展示效果中的 logo 是另外上网搜的 */
            background-image: url('https://pic.17qq.com/uploads/hhnphdgklv.jpeg');
            background-size: cover;
            background-repeat: no-repeat;
            margin-right: 5px;
            vertical-align: -1px;
        }

        div::after {
            content: ">";
            float: right;
            background-size: cover;
            width: 6.5px;
            height: 11.5px;
        }
    </style>
</head>

<body>
    <div>成哥贴吧</div>
</body>

</html>
```

![20210314002713](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210314002713.png)

2. 相关面试题讲解

- **模拟报纸布局效果(面试题)**

```
要求
    1. p.content1 最多两行 20px #333 顶部对齐图片 底部间距8px
    2. p.content2 12px #666 行高1.2
    3. 使用语义化标签完成以下布局 考虑模块化和拓展性 容器默认宽度 320px
    4. hover时 容器宽度变成400px
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>模拟报纸布局效果</title>
    <style>
        .clearfix::after {
            content: "";
            display: block;
            clear: both;
        }

        .wrapper {
            /* 容器默认宽度 320px */
            width: 320px;
        }

        .wrapper:hover {
            width: 400px; /* hover时宽度变为 400px */
            transition: all 0.3s; /* 实现一个过渡效果 */
        }

        .wrapper img {
            width: 100px;
            height: 100px;
            padding-right: 10px;
            float: left;
        }

        .content1 {
            font-size: 20px;
            height: 40px;
            color: #333;

            /* 多行文本溢出截断处理 */
            line-height: 20px;
            overflow: hidden;
            /* 底部间距8px */
            margin-bottom: 8px;
        }

        .content2 {
            font-size: 12px;
            color: #666;
            line-height: 1.2em;
        }
    </style>
</head>

<body>
    <div class="wrapper clearfix">
        <img src="http://hubei.sinaimg.cn/2013/0123/U7189P1190DT20130123175801.jpg" alt="海贼王女帝">
        <p class="content1">波雅·汉库克，日本漫画《海贼王》及其衍生作品中的女性角色。</p>
        <p class="content2">女儿岛亚马逊·百合王国的皇帝，同时也是”九蛇海贼团的船长，人称：海贼女帝。其绝世的容颜被世人评价为“世界第一美女。也是原王下七武海之一。
        </p>
    </div>
</body>

</html>
```

![20210314003806](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210314003806.png)

![20210314003813](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210314003813.png)

# 7. IT职业发展之路

## 7.1 大学篇

> 跳过了...

## 7.2 职业篇

> 跳过了...

# 8. 渡一风采

## 8.1 桃李不言 下自成蹊

> 跳过了...

# 9 + 10

> 重头到尾写一遍后 再更新上来