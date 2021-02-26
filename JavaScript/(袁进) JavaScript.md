# 一、概述

## 1. 课程概述

```
本课程老师: 袁进 (成都人)

该课程对比成哥的JS课程:
    1. 形式上: 成哥 (线下授课录制) 袁老 (线上视频录制)
    2. 侧重点: 成哥 (全面) 袁老 (学术 干货)

本课程所使用的代码编辑器是: VSCode

笔记: 用 markdown 记的笔记

学习该课程的前提: 掌握 html + css 的相关知识点 (相关免费课程链接: duyi.ke.qq.com)

课程难度: 由浅入深, 有一定的难度

课程内容分类:
    1. 必学课程: 直接以课程名称命名的课程;
    2. 扩展课程: 课程名称前面有 [扩展] (若不学, 不影响开发);
    3. 作业课程: 课程名称前面有 [作业讲解] (尝试写好对应的作业后再观看)

学习周期: 如果一天学习 8 小时, 大部分学员学完该课程 (包括所有练习、项目、知识点) 所需时间是 一个月;

视频中主要介绍的JS版本: 本视频讲解的是 ES5 (2009) 版本, 不包括 ES6 (2015) 版本;

学习方法推荐:
    1. 细化目标 + 正面反馈
    2. 重视练习 (编程属于工科 重视实践)
```

## 2. JS语言概述

**JS语言的一些历史**

```
1. JS语言的起源
    网景（Netscape Communication Corperation），1994年，推出第一款商用浏览器，网景浏览器（Netscape Navigator）. 1995年，网景公司决定在浏览器中加入一门语言，可以作交互效果，提高用户体验。最终决定独立开发一门新的语言，聘请Brendan Eich，10天后，新的语言诞生 LiveScript -> JavaScript (JS)
    JS语言之父：Brendan Eich
2. 第一次浏览器大战
    网景公司打算在浏览器中加入网络操作系统，影响到微软的利益，引起了微软的注意. 1995年，微软发布IE浏览器。JS语言推出之后，网景获得极大的竞争优势。微软对JS语言反编译，借鉴JS语言，退出了JScript、VBScript. 第一次浏览器大战是标准之争. 1997，网景公司将javascript1.1版本提交给ECMA（European Computer Manufacturers Association 欧洲计算机制造协会）IE3发布，并绑定windows操作系统。1998年，网景公司，被收购。**ECMA收录了JavaScript，并提交给ISO，经过修改，成为了第一个JS的标准版本，成为ECMAScript，简称ES**
3. 第二次浏览器大战
    IE4、IE5、IE6（windows xp）. 微软决定解散浏览器团队。Brendan Eich，带领团队成立Mozilla基金会，并决定，将网景浏览器开源。长时间内，世界的技术爱好者，对网景浏览器，进行维护和打补丁 2002，Mozilla推出firefox浏览器。2008，谷歌推出chrome浏览器，苹果推出safari，ASA公司推出opera. chrome浏览器搭载JS执行引擎V8（V8引擎，可以将JS代码直接转换为字节码，理论上，JS代码的执行速度已经接近汇编语言）于是，JS具备了编写大型应用程序的能力，甚至服务器应用;
    V8，将JS的执行推向了一个新的台阶
    Ryan Dahl 准备写一个服务器端的框架，直接利用V8引擎完成了该框架，该框架，称为nodejs
4. ES标准的发展
    - ES1，1997年
    - ES2，1998年
    - ES3，1999年
    - ES5，2009年，习惯上，不再区分 javascript （JS） 和 ECMAScript （ES）
    - ES6，2015年，ECMA宣布，从ES6开始，使用年号作为版本号，ES6的真正称呼为：ES2015
    - ES7，2016年，ES2016
    notes:
      ES制定语言标准，不涉及语言的运行环境。正是因为ES避免了运行环境，就让ES有机会在各种环境中执行。ES成为了通用编程语言。
      比如本课程所使用的编译器 VScode 就是用 js 写的。
      本课程学习的是，ES的通用语法、浏览器环境为其注入的新功能。
      通常，把ES运行的环境称之为，宿主环境 (host environment) 。
      本课程涉及的宿主环境是在 浏览器 这个宿主环境上的；之后还会有 服务器、手机端 等宿主环境。
```

**JS语言的一些特点**

```
JS是弱类型语言 而非 强类型语言
    1. 弱类型：存放的数据类型可变。
        优点：灵活、易上手
        缺点：不严谨
    2. 强类型：存放的数据类型不可变。
        优点：严谨
        缺点：不灵活、不易上手
JS是解释型语言 而非 编译型语言
    1. 常见的解释型语言: js、php. 解释型语言没有编译结果;
        优点: 跨平台；部署简单；
        缺点: 执行速度稍慢；
    2. 常见的编译型语言：C语言、C++、java语言、C#语言. 编译型语言会经过一个翻译的过程，负责翻译的叫做编译器，翻译的结果，叫做编译结果。
        优点：执行速度快
        缺点：某个编译结果，难以适用于各种环境（跨平台障碍），部署繁琐；
notes:
    1. 通常, 将弱类型的解释型语言, 称为脚本语言 (如 js 就是脚本语言)
    2. 单线程
        同步现象：上一件事情没有做完，下一件事情必须等待。
    3. 异步
        提高单线程的执行效率。
```


## 3. 开发环境的准备

```
在正式课程开始前, 需要提前安装好以下内容
    1. 浏览器: 推荐使用 chrome
    2. 代码编辑器: 推荐使用 VSCode (Visual Studio Code 可视化代码编辑器)
        其他常见的Web前端开发所用的编辑器: ATom、WebStorem、sublime、windows记事本 (大神级别)
    3. VSCode上常用的插件:
        1. 语言包：Chinese (Simplified) Language Pack for Visual Studio Code
        2. Beautify：美化代码的作用
        3. vscode-icons：美化图标
        4. Live Server：自动搭建本地服务器，启动网页
        5. Markdown Preview Enhanced：markdown的增强插件
        6. Markdown All in One: 在markdown适用快捷键
notes: 本节课主要介绍如何开发环境的搭建
```

# 二、JS语法基础

## 1. 第一个JS程序

```
1. 掌握在浏览器环境中，代码书写的位置
    1. 直接书写到页面中的script元素的内部
    2. 书写到外部的js文件，在页面中引用 [推荐]
       代码分离：内容、样式、功能，三者分离，更加容易维护和阅读
    PS:
      页面中，可以存在多个 script 元素，执行顺序从上到下
      如果一个 script 元素引用了外部文件，内部不能书写任何代码 (书写的话 并不会报错 但是浏览器会无视这些代码)
      script 元素有一个可选的属性，type ，该属性用于指定代码的类型，该属性值是 MIME 格式
2. 基本语法常识
    1. 语法部分必须都是英文符号
    2. js代码由多条语句构成，每个语句用英文分号结束 (语句结尾加分号 并非强制要求 不过还是建议加上)
       每条语句以分号结束, 当然, 也可以不加分号, 程序依旧可以执行, 并不会报错, 由此可见, js里面有很多地方都是比较松散的;
    3. js代码从上到下同步执行
    4. js语言大小写敏感
3. 认识输出语句 (所有的输出语句都不是ES标准)
    1. console.log(); // 该语句用于将数据显示到控制台 [学习时 推荐多使用这种方式来测试输出结果]
    2. document.write(); // 该语句用于将数据输出到页面
    3. alert(); // 该语句用于将数据用弹窗的形式显示到页面
       它还有一个阻塞后续代码执行的作用, 即: 点击"确定"之后,该alert语句才算执行结束,后续代码才能继续执行;
4. 认识输入语句 (所有的输入语句都不是ES标准)
    1. prompt();
       参数: 是一个用于提示用户输入的字符串, 如: prompt("请输入您的年龄: ");
       返回值: 也是一个字符串, 是用户输入的内容
5. 认识注释
    注释: 提供给代码阅读者使用，不会参与执行;
    单行注释: // This is comment
    多行注释:
    /*
    This is comment
    This is comment
    This is comment
    */
    注释的快捷键:
       在VSCode中，使用快捷键 ctrl + / 可以快速生成和取消 单行注释
       使用快捷键 alt + shift + a 可以快速生成和取消 多行注释
    PS: 还有一个函数文档注释, 开始在讲解函数那部分的时候 也许会接触到
       JavaScript中函数文档注释的格式:
          /** 方法说明
          * @method 方法名
          * @for 所属类名
          * @param {参数类型} 参数名 参数说明
          * @return {返回值类型} 返回值说明
          */
       快捷生成方式: 在 .js 文件中的某个定义好的函数的前一行 输入 /** 然后按回车 即可
notes:
    1. 有关代码的书写位置问题,在实际的开发中,基本上都是将`html` `css` `js`书写于独立的文件下,然后引入就好;
    2. 有关基本语法,基本上是不会写错的;
    3. 输出和输入语句,都是基于宿主环境的,并非ES标准;
    4. 对于输出语句,通常常用来调试;
    5. 至于注释,只需要记住两组快捷键就好了;

    Q: 搜狗输入法如何在中文模式下使用英文标点
    A: 右键搜狗输入法 -> 属性设置 -> 常用 -> 中文时使用英文标点 (勾上即可)
```

**作业**

- [x] 1. 在网页中书写多个script元素，在元素内部书写多种输出语句，然后运行页面查看效果。
- [x] 2. 将代码提取到一个独立的js文件中，然后在页面中使用。

---

- [x] 作业1

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- 1. 在网页中书写多个script元素，在元素内部书写多种输出语句，然后运行页面查看效果。 -->
    <script>
        alert("2020年8月31日");
    </script>
    <script>
        console.log("2020年8月31日");
    </script>
    <script>
        document.write("2020年8月31日");
    </script>
</body>

</html>
```

- [x] 作业2

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- 2. 将代码提取到一个独立的js文件中，然后在页面中使用。 -->
    <script src="./作业2/index.js"></script>
</body>

</html>
```

```js
alert("2020年8月31日");
console.log("2020年8月31日");
document.write("2020年8月31日");
```

### test.html

```html

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- test1.html -->
    <!--
        1. 掌握代码的书写位置
     -->

    <!-- test2.html -->
    <!--
        1. 掌握如何以相对路径的形式引入js文件
        2. 学会使用 document.write() 输出语句
     -->

    <!-- test3.html -->
    <!--
        1. alt + shift + f 格式化代码
        2. 学会使用 alter() 输出语句
     -->

    <!-- test4.html -->
    <!--
        1. 学会使用 console.log() 输出语句
     -->

    <!-- test5.html -->
    <!--
        1. 学会使用 prompt() 输入语句
     -->


</body>

</html>
```


## 2. 数据和数据类型

```
1. 数据 和 数据类型 之间的区别
    - 数据：有用的信息 (数据 ≠ 数字)
    - 数据类型：数据的分类
2. JS中的数据类型
    JS中的数据类型主要分为两大类: 原始数据类型 ＋ 引用数据类型
       1. 原始类型(基本类型 原始类型指不可再细分的类型,也就是最基本的类型)
        number、string、boolean、undefined、null
       2. 引用类型
        object、function
3. 字面量: 直接书写的具体的数据，叫做字面量
4. 检测数据类型

notes:
    1. 数据指的是有用的信息,数据不等于数字;
    2. 原始类型不能有属性
       但是给 number、string、boolean类型的变量赋予属性, 程序并不会报错(相当于啥也没做 若我们再次访问我们添加的那个属性的值 是啥也访问不到的), 这是涉及后续的 基本包装类 的相关知识

    数据和数据类型这一部分的知识点实际上是蛮复杂的,引用类型 object 下面还可以继续细分,本节介绍的仅仅是其中的一小部分;

    3. 需要掌握不同数据类型的字面量如何书写;
    4. 通过 typeof 可以检测数据类型 , 不过这并不好用 , 后期可能有些需求无法满足 , 因为它对于引用类型 , 返回值都是 object ; 后期一般不会直接使用 typeof 来检测数据类型 , 而是会封装一个功能更加完善的方法来代替它;
```

- [x] demo1

数字类型 `number`

```js
// 对于数字而言 直接书写数字即可
console.log(10);    // 10
// [补充]数字类型可以加上前缀， 来表示不同的进制
// 0： 表示8进制
console.log(010);   // 8
// 0x： 表示16进制
console.log(0x10);  // 16
// 0b: 表示2进制
console.log(0b10);  // 2
```

- [x] demo2

字符串类型 `string`

```js
// 字符串是指一长串文本（可能是0个文本,也可能是多个文本）
// 用下面3个符号包裹字符串
// 1. 单引号 '
// 2. 双引号 "
// 3. 模板字符串 `
// [特殊字符]转义符（\）可用来表示特殊字符
console.log('hello \'world\'');
console.log("hello \"world\"");
console.log("hello \\");
console.log("hello \nworld"); //\n表示换行符
console.log("\t12\t34\n\ta\tb"); //\t表示制表符
console.log(`
            'hello'
            \`
            "world"`);
```

![demo2 string](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210223171550.png)

- [x] demo3

布尔类型 `boolean`

布尔类型 只有两个值: `true` 或 `false`

```js
// 布尔类型用于表达真或假两种状态
// true， 表示真
// false， 表示假
console.log(true); // true
console.log(false); // false
```

- [x] demo4

undefined类型

```js
// undefined 表示未定义(不存在)。
// 只有一种数据书写方式： undefined
console.log(undefined);
```

- [x] demo5

null类型

```js
// null 表示空(不存在)。
// 只有一种数据书写方式： null
console.log(null);
```

```
实际上有了undefined类型后,并不需要`null`这个东西,没啥用;可以理解为是大神被公司逼出来的一种数据类型;公司要求大神借鉴面向对象的编程语言,而仅花10天就开发出JavaScript的大神却始终更倾向于面向函数,可能是在写好JavaScript之后,然后才把`null`这个数据类型给加上的,`null`也就是面向对象的里面的一种数据类型;
```

- [x] dmeo6

扩展: 区分某些长数字和字符串

要读出 千 百 这样的计量单位的 我们一般使用数字类型, 比如金额; 其余通常用 字符串;

```js
// 如果按照数字的方式阅读，则使用数字类型；否则使用字符串类型
// 手机号是数字还是字符串？字符串
console.log("13812341234");
// 身份证号是数字还是字符串？字符串
// 学号是数字还是字符串？字符串
// 年龄是数字还是字符串？数字
// 年份是数字还是字符串？数字(使用更多) or 字符串
```

- [x] demo7

两种引用类型：`object`&`function`

- 对象 `object` （事物，东西，玩意儿）
  - 对象属性：指的是对象的成员
- 函数 function [是后面的知识点 后续再做介绍]

原始类型中不存在属性;

![20210223173116](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210223173116.png)

`undefined`是一个原始类型,原始类型显然是不能有属性的,所以在赋值时会报错;

```
注意: 此时如果将 var user; 改为 var user = 2; 那么是不会报错的,这一点属于后续的知识,涉及到`基本包装类型`等相关概念;
总之现在记住一点: Number Boolean String 这三个基本类型是比较特殊的;
```

```js
console.log({
    name: "姬成",
    nickName: "成哥",
    age: 108,
    gender: true, //true表示男，false表示女
    address: {
        country: "中国",
        province: "黑龙江",
        city: "哈尔滨",
        detail: "那嘎达二街11号"
    },
    girlFriend: undefined
});
// 可以认为，对象，是由多个基本类型组合而成的。
```

![20210223173338](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210223173338.png)

- [x] demo8

得到(检测)数据的类型, 在数据前加上 `typeof` 即可;

```
js的bug（特征）： `typeof null`，得到的是`"object"`
有的书籍将`null`视为`object`(对象)类型,而有的书籍将null视为一种单独的null类型,没有必要纠结这个东西,只要知道利用`typeof`关键字检测`null`得到的是`"object"`即可;
```

```js
console.log(typeof 12);     // 'number'
console.log(typeof "12");   // 'string'
console.log(typeof true);   // 'boolean'
console.log(typeof undefined);  // 'undefined'
console.log(typeof null);       // 'object'
console.log(typeof {
    name: "姬成",
    nickName: "成哥",
    age: 108,
    gender: true, //true表示男，false表示女
    address: {
        country: "中国",
        province: "黑龙江",
        city: "哈尔滨",
        detail: "那嘎达二街11号"
    },
    girlFriend: undefined
});     // 'object'
```


**作业**

- [x] 1. 将自己作为一个对象，书写合适的对象属性，输出该对象。



```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- 将自己作为一个对象，书写合适的对象属性，输出该对象。 -->
    <script>
        var TaoJiaLe = {
            name: '陶家乐',
            gender: 1, // 1表示男,0表示女
            age: 21,
            tele: '15157722155',
            address: {
                province: '浙江',
                city: '温州',
                detail: 'secret'
            },
            girFriend: null
        };
        console.log(TaoJiaLe);
    </script>
</body>

</html>
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- test1.html -->
    <script>
        // 对于数字而言 直接书写数字即可
        console.log(10); // 10
        // [补充]数字类型可以加上前缀， 来表示不同的进制
        // 0: 表示8进制
        console.log(010); // 8
        // 0x: 表示16进制
        console.log(0x10); // 16
        // 0b: 表示2进制
        console.log(0b10); // 2
    </script>





    <!-- test2.html -->
    <script>
        // 字符串是指一长串文本（可能是0个文本,也可能是多个文本）
        // 用下面3个符号包裹字符串
        // 1. 单引号 '
        // 2. 双引号 "
        // 3. 模板字符串 `
        // [特殊字符]转义符（\）可用来表示特殊字符
        console.log('hello \'world\'');
        console.log("hello \"world\"");
        console.log("hello \\");
        console.log("hello \nworld"); //\n表示换行符
        console.log("\t12\t34\n\ta\tb"); //\t表示制表符
        console.log(`
'hello'
\`
"world"`);
    </script>




    <!-- test3.html -->
    <script>
        // 布尔类型用于表达真或假两种状态
        // true， 表示真
        // false， 表示假
        console.log(true); // true
        console.log(false); // false
    </script>




    <!-- test4.html -->
    <script>
        // 表示未定义(不存在)。
        // 只有一种数据书写方式： undefined
        console.log(undefined);
    </script>

    <script>
        // 表示空(不存在)。
        // 只有一种数据书写方式： null
        console.log(null);
    </script>



    <!-- test5.html -->
    <!-- 区分某些长数字和字符串 -->
    <script>
        // 手机号是数字还是字符串？字符串
        console.log("13812341234");
        // 身份证号是数字还是字符串？字符串
        // 学号是数字还是字符串？字符串
        // 年龄是数字还是字符串？数字
        // 年份是数字还是字符串？数字(使用更多) or 字符串
    </script>


    <!-- 可以认为，对象，是由多个基本类型组合而成的。 -->
    <!-- test6.html -->
    <script>
        console.log({
            name: "姬成",
            nickName: "成哥",
            age: 108,
            gender: true, //true表示男，false表示女
            address: {
                country: "中国",
                province: "黑龙江",
                city: "哈尔滨",
                detail: "那嘎达二街11号"
            },
            girlFriend: undefined
        });
    </script>


    <!-- test7.html -->
    <script>
        console.log({
            type: "笔记本",
            productYear: 2018,
            corporation: "小米",
            cpu: {
                hz: "2GHZ",
                type: "Intel"
            },
            isStopSell: false //是否停止销售
        });
    </script>




    <!-- test8.html -->
    <!-- typeof 得到数据的类型 -->
    <script>
        console.log(typeof 12); // 'number'
        console.log(typeof "12"); // 'string'
        console.log(typeof true); // 'boolean'
        console.log(typeof undefined); // 'undefined'
        console.log(typeof null); // 'object'
        console.log(typeof {
            name: "姬成",
            nickName: "成哥",
            age: 108,
            gender: true, //true表示男，false表示女
            address: {
                country: "中国",
                province: "黑龙江",
                city: "哈尔滨",
                detail: "那嘎达二街11号"
            },
            girlFriend: undefined
        }); // 'object'
    </script>
</body>

</html>
```

## 3. 变量

```
1. 什么是变量?
    变量实际上就是一块内存空间 可用于存放数据
      计算机：CPU、内存、硬盘、输入输出设备;
      内存：存取速度快，数据易丢失;
      硬盘：存取速度慢，数据永久保存;
      计算机程序的运行，仅与内存打交道;
2. 如何使用变量
    1. 声明（定义）变量
      var a; // 变量声明后，它的值为undefined
    2. 给变量赋值 (向变量的内存空间中存放数据)
      var a = 1; // 给变量赋值
3. 变量的值是可变的 (变量可以被重新赋值，新的值会覆盖原来的值)
4. 变量的名称 (标识符)
    在开发中，凡是需要自行命名的位置，叫做标识符
5. 标识符的规范：
   - [必]只能以英文字母、下划线 _ 、美元符 $ 开头
   - [必]其他位置可以出现数字、英文字母、下划线、$
   - [必]不可以与关键字、保留词重复
   - [选]标识符应该做到望文知义
     比如: 宽度：width，高度：height，区域：area （quyu 使用拼音也行）
   - [选]如果有多个单词，使用驼峰命名法，单词首字母大写
     小驼峰: 除了第一个单词的首字母不用大写, 后续单词的首字母都要大写; (目前，使用的标识符都是小驼峰命名法。)
     大驼峰：每个单词首字母大写;
6. 声明和赋值合并
    变量的声明和赋值可以一条语句书写 (语法糖)。
    语法糖仅仅是为了方便代码书写或记忆，并不会有实质性的改变。
7. 多个变量可以合并声明并赋值 (语法糖)
8. 任何可以书写数据的地方，都可以书写变量
9. 若使用一个未声明(不存在)的变量，会导致错误
    例外：使用typeof检测变量的数据类型时，可以是未声明的变量，得到的结果是undefined
10. JS中存在变量提升
    所有变量的声明，会自动的提到代码的最顶部
    但是，这种提升，不会超越脚本块。

notes:
    本节的关键词是 变量 , 大概就是如下几点

    1. 知识点
      变量实际上就是一块内存空间;
      变量声明实际上就是开辟一块内存;
      变量赋值实际上就是往这块内存空间里面放数据;

    2. 细节
      变量重复赋值如何处理;
      变量声明提升的相关细节;
      开发中对于变量的命名规范;
      对于尚未声明的变量, 只能利用 typeof 关键字来检测其类型;
      省略 var 声明的变量, 归 window 所有;

    3. 操作
      一次性可以声明多个变量;
      声明变量的同时可以对变量进行赋值;
```

- [ ] demo1

JS中存在变量提升

```html
<script>
    console.log(a, b); // Uncaught ReferenceError: a is not defined
</script>
<script>
    /* console.log(a, b); // undefined undefined
    var a = 1;
    var b = 3; */
    // 等效于
    var a;
    var b;
    console.log(a, b); // undefined undefined
    a = 1;
    b = 3;
</script>
<script>
    console.log(a, b); // 1 3
</script>
```

- [x] demo2

JS中允许定义多个同名变量, 同名变量，提升后会变成一个。

```js
// var a = 1;
// console.log(a);
// var a = 3;
// console.log(a);
// 等价于
var a;
a = 1;
console.log(a); // 1
a = 3;
console.log(a); // 3
```

---


**作业**

- [x] 1. 定义三个变量，分别保存用户姓名、用户年龄、用户是否是vip，然后输出它们。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- 定义三个变量，分别保存用户姓名、用户年龄、用户是否是vip，然后输出它们。 -->
    <script>
        var userName = 'JiaLe',
            userAge = 21,
            isVip = true;
        console.log(userName, userAge, isVip); // JiaLe 21 true
    </script>
</body>

</html>
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- test1.html -->
    <!-- 变量实际上就是一块内存空间 可用于存放数据 -->
    <script>
        var pid; // 声明了一个变量，名称为pid，目前，变量为undefined
        pid = "43532423425465434"; //将 xvxcvxcvxx(任意数据) 存放到变量pid中
        console.log(pid); // "43532423425465434" ==> 输出变量pid的值（pid中存放的数据）
        console.log(typeof pid); // "string" ==> 输出变量pid的类型
    </script>





    <!-- test2.html -->
    <!-- 变量的声明 + 赋值 + 命名 -->
    <script>
        var $abc_312$; // 变量的声明
        console.log($abc_312$, typeof $abc_312$); // undefined "undefined"
        $abc_312$ = 1; // 变量的赋值
        console.log($abc_312$, typeof $abc_312$); // 1 "number"
        $abc_312$ = "bcdd"; // 变量的重新赋值
        console.log($abc_312$, typeof $abc_312$); // "bcdd" "string"
        $abc_312$ = undefined; // 变量的重新赋值
        console.log($abc_312$, typeof $abc_312$); // undefined "undefined"
    </script>




    <!-- test3.html -->
    <!-- 变量声明与赋值合并 -->
    <script>
        // 一个变量，用于记录一个矩形(rectangle)的宽度(width)
        var rectWidth = 100; // 声明并完成赋值

        // 等效于
        // var rectWidth;
        // rectWidth = 100;
    </script>




    <!-- test4.html -->
    <!-- 多变量同时声明并赋值 -->
    <script>
        // var a;
        // var b;
        // var c;
        // a = 1;
        // b = 2;
        // c = 3;

        // 等效于
        // var a, b, c;
        // a = 1;
        // b = 2;
        // c = 3;

        // 等效于 (单一 var 模式)
        var a = 1,
            b = 2,
            c = 3;

        console.log(a, b, c); // 1 2 3
    </script>




    <!-- test5.html -->
    <!-- 任何可以书写数据的地方都可以写变量 -->
    <script>
        var a = "hello";
        var b = a; // 将变量a的数据复制到变量b中
        b = "world"; // 不会影响a
        console.log(a, b);
    </script>




    <!-- test6.html -->
    <!-- 未经声明的变量只能使用 typeof 关键字来检测其数据类型 -->
    <script>
        console.log(typeof a); // "undefined"
    </script>




    <!-- test7.html -->
    <!-- js中存在变量提升 -->
    <script>
        // console.log(a, b);
        // var a = 1;
        // var b;
        // b = 3;

        //等效于
        var a;
        var b;
        console.log(a, b); // undefined undefined
        a = 1;
        b = 3;
    </script>
    <script>
        console.log(a, b); // 1 3
    </script>




    <!-- test8.html -->
    <!-- js中允许声明多个同名变量 经提升后 合并为一个 -->
    <script>
        var a;
        a = 1;
        console.log(a); // 1
        a = 3;
        console.log(a); // 3
    </script>


</body>

</html>
```


## 4. 变量和对象

```
1. 回顾数据类型
    原始类型：number、string、boolean、null、undefined
    引用类型：object、function
2. 在变量中存放对象
    1. 通过变量，读取对象中的某个属性
       变量名.属性名
    2. 当读取的属性不存在时，会得到undefined
    [扩展]
       由此可知,若想删除一个对象上的某个属性时, 有两种可行的方式:
       1. 可以用 `delete 对象名.属性名` 的形式来删除 --- 直接将对象中的某个属性给删除了,属性不存在了;
       2. 还可以直接赋值 `对象名.属性名 = undefined;` --- 重新给对象中的某个属性赋值,属性依旧存在,不过值是 undefined;
       这两种方式都有对应的使用场景
    3. 当读取属性的对象不存在（ undefined 或 null）时，程序报错
        有统计数据显示,js报错排名第一的,就是从 undefined 或 null 中读取属性;
    4. 通过变量，更改对象中的某个属性, 当赋值的属性不存在时，会添加属性;
    5. 删除属性 `delete 对象名.属性名;`
    6. 属性表达式
        给属性赋值，或读取属性时，可以使用下面的格式操作
        对象名["属性名"]
    7. 某些属性名中包含特殊字符
    实际上，JS对属性名的命名要求并不严格，属性可以是任何形式的名字
    属性的名字只能是字符串，如果你书写的是数字，会自动转换为字符串
    console.log(obj[0]); 等价于 console.log(obj["0"]);

    var obj = {};
    obj[0] = '123';     // { "0": "123" }
    obj["0"] = '234';   // { "0": "234" }
    console.log(obj[0], obj["0"]);  // 234 234

    [总结]
    以属性表达式对象名["属性名"]的形式来读取对象属性时,使用起来更加的灵活;
    对象名["属性名"] 使用这种方式来操作对象上的属性, 在之后的学习中,你会发现这种写法有大用途;
3. 全局对象
   JS大部分的宿主环境，都会提供一个特殊的对象，该对象可以直接在JS代码中访问，该对象叫做全局对象
   在浏览器环境中，全局对象为window，表示整个窗口
   全局对象中的所有属性，可以直接使用，而不需要写上全局对象名
   开发者定义的所有变量，实际上，会成为window对象的属性(这种说法是不严谨的,在学习函数那一部分知识点时,还会详细说明)
   如果变量没有被赋值，则该变量不会覆盖window对象上的同名属性。
   [即]若仅声明了一个变量,没有给变量赋值,并且该变量名与window的属性名同名,那么相当于没有定义这个变量,该声明语句就跟不存在一样(知道这些对于开发而言,实际上帮助可能不大,不过面试题很可能会考察这些看似不重要的玩意儿)

    var name;
    console.log(name); // 不会报错 , 控制台啥也没输出
    // 原因在于 window对象 下面也有一个属性名为 name 的属性 , 默认值是空字符串 ''
    // 这个 name 属性比较特殊 , 赋给 name 属性的任何值 , 都会转化为 string 类型
    var name = 1;
    console.log(name); // "1"
    console.log(typeof name); // string
    // 后期遇到类似的情况, 注意看看是否是window对象上已经存在的属性

notes:
    "变量和对象" 这一节实际上是对上一节 "变量" 的补充

    1. 知识点
       1. 对象的相关操作 增 删 改 查;
       2. 属性表达式 对象名["属性名"];
       3. 变量(对象名)中存放的对象 , 实际上存放的是这个对象的地址;
    2. 细节
       1. 读取对象中不存在的属性 , 不会报错 , 而是返回 undefined;
       2. 从一个不存在的对象中读取属性 , 会报错;
       3. 修改对象中不存在的属性 , 实际上是给对象添加属性;
       4. 如果在全局环境创建了与 window 全局对象属性同名的变量 , 且对变量进行了赋值 , 那么新创建的变量将会覆盖 window 全局对象中的那个属性;
```

**练习**

```js
//1. 定义一个变量，存放对象，包含姓名、年龄、性别、女朋友（姓名、年龄、性别）
var cheng = {
   name: "成哥",
   age: 18,
   gender: "男",
   girlFriend: {
       name: "小花",
       age: 50,
       gender: "女"
   }
};
//2. 定义一个变量，存放对象，包含姓名、年龄、性别、女朋友，女朋友和第一个变量的女朋友是一样的
var deng = {
   name: "邓哥",
   age: 53,
   gender: "男"
};
deng.girlFriend = cheng.girlFriend;
//3. 输出：成哥女朋友的姓名，邓哥女朋友的姓名
console.log(cheng.girlFriend.name, deng.girlFriend.name);

//4. 邓哥和女朋友分手了
deng.girlFriend = undefined;
console.log(deng); // {name: "邓哥", age: 53, gender: "男", girlFriend: undefined}

// delete deng.girlFriend;
// console.log(deng); // {name: "邓哥", age: 53, gender: "男"}
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月15日</title>
</head>

<body>


    <!-- 对象的基本操作 -->

    <!-- 在变量中存放对象.html -->
    <script>
        var user = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18
        };

        // console.log(user, typeof user);
        // 输出对象的账号
        // console.log(user.account, typeof user.account);
        // 输出对象的年龄
        console.log(user.age, typeof user.age); // 18 "number"

        console.log(user.sex, typeof user.sex); // undefined "undefined"

        var user2;

        console.log(user2.account); // 报错 Uncaught TypeError: Cannot read property 'account' of undefined
    </script>



    <!-- 在变量中存放对象.1.html -->
    <script>
        var user = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18
        };
        console.log(user.pwd); // "123456"
        user.pwd = "654321"; // 将密码改为654321
        console.log(user.pwd); // "654321"
    </script>

    <script>
        var user = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18
        };

        user.tradePwd = "abcdfasdf"; // 相当于添加了属性tradePwd
    </script>

    <!-- 读取属性的对象不存在(undefined or null) ==> 报错 -->
    <script>
        var user = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18
        };

        var user2;
        user2.account = "abcded"; // 报错，原始类型undefined中不可以有属性
        // Uncaught TypeError: Cannot set property 'account' of undefined
        console.log(user2); // 不会执行
    </script>

    <!-- 读取对象上不存在的属性 ==> 得到 undefined -->
    <script>
        var user = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18
        };

        console.log(user.name); // undefined
    </script>



    <!-- 在变量中存放对象.2.html -->
    <!-- 对象里面可以继续嵌套对象 -->
    <script>
        var user = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18,
            address: {
                country: "中国",
                city: "成都"
            }
        };
        // 输出用户的所在城市
        console.log(user.address);
    </script>




    <!-- 在变量中存放对象.3.html -->
    <!-- 对象之间相互赋值 -->
    <script>
        var user1 = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18,
            address: {
                country: "中国",
                city: "成都"
            }
        };

        var user2 = {}; // user2 是一个空对象
        user2.addr = user1.address; // 往 user2 这个空对象里面赋值

        console.log(user2, user1);

        /* 等价于:
        var user2 = {
            account: user1.account
        };

        console.log(user1.account, user2.account); */
    </script>




    <!-- 在变量中存放对象.4.html -->
    <!-- 以属性表达式的形式来获取对象上的属性 -->
    <script>
        var user = {
            account: "abc",
            pwd: "123456",
            gender: "男",
            isVip: false,
            age: 18,
            address: {
                country: "中国",
                city: "成都"
            }
        };
        //用属性表达式读取用户的性别属性
        var prop = "account";
        // console.log(user.gender);
        console.log(user[prop]); // "abc"
    </script>




    <!-- 在变量中存放对象.5.html -->
    <!-- 属性表达式中的属性 只能是字符串 -->
    <script>
        var obj = {};
        obj[0] = "123"; // { "0": "123" } 宿主环境会自动将数字转换为字符串
        obj["0"] = "234"; // { "0": "234" }

        console.log(obj[0], obj["0"]); // "234" "234"
    </script>




    <!-- 全局对象.html -->

    <script>
        console.log("abc");
        alert("abc");
        document.write("abc");
    </script>

    <script>
        window.console.log("abc");
        window.alert("abc");
        window.document.write("abc");
        /*
        console 和 document 是 window 下面的属性
        alert 是 window 下面的方法 */
    </script>

    <script>
        var a;
        console.log(window); // 发现window里面新增了一个属性 a
        console.log(a); // undefined
        // 因为，window之前没有属性a，前一条声明语句 令a成为了window对象的属性 而读取一个对象中所不存在的属性时 返回 undefined (这就是为啥声明一个变量 而不赋值 它的默认值为 undefined 的原因了)
    </script>

    <script>
        var console = undefined;
        alert(window.console); // undefined
        // 由于，console有赋值，因此，覆盖了window的属性console
    </script>

    <script>
        var console;
        console.log(console); // f() ...
        // 由于，console没有赋值，因此，没有覆盖window的属性console
    </script>

    <script>
        // why? 为什么输出的不是 undefined
        var name;
        console.log(name); // ""
        // window对象下有一个name属性(默认值是空字符串) 所以window并不会新增name属性
    </script>

    <script>
        var name = null; // name 属性比较特殊，赋值的任何内容，都会被转换为字符串
        console.log(name); // "null"
        console.log(typeof name); // "string"
        console.log(window); // window.name 属性的值变成 "null"
    </script>

    <script>
        console.log(typeof alert); // "function"
        var alert = undefined;
        console.log(typeof alert); // "undefined"
    </script>

</body>

</html>
```

## 5. 引用类型

```
1. 原始类型 引用类型（对象、函数）
    原始类型的变量，存放的具体的值
    引用类型的变量，存放的是内存地址

notes:
    1. 但凡是出现对象字面量的地方, 一定在内存中开辟了一段空间, 用于存放对象 ;
    2. 垃圾回收, 若一个对象没有变量指向它, 那么它将被视为垃圾, 这段内存空间将会被回收 ;
```

- [x] demo1

仅创建了一个对象

```js
//obj1 指向 xx 对象
//obj1 持有 xx 对象的引用(地址)
var obj1 = {
    name: "123",
    age: 10
}; // 出现对象字面量的位置，会新开辟一块内存空间，用于存放对象的内容
/* 说明:
左边 = 右边; // 运算顺序是: 先执行赋值符号右边的表达式,再将得到的结果赋给左边的变量
此时赋值符号右边是 {
    name: "123",
    age: 10
};
右边的这一部分会在内存中开辟一段内存空间,这段内存空间里面存放的就是 {name:"123",age:10} 这个对象;
且右边的运算结果是在这段内存空间的地址,所以左边的变量将会存放执行这段内存空间的地址;
*/
// obj2 和 obj1 指向同一个对象
// obj2 和 obj1 持有相同的引用(地址)

var obj2 = obj1;
obj2.name = "456";
console.log(obj1.name, obj2.name); // 456 456
```

![20210223195607](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210223195607.png)

- [ ] demo2

创建了两个对象

```js
var obj1 = {
    name: "123",
    age: 10
};
var obj2 = obj1;
obj2 = {
    name: "456"
};
console.log(obj1.name, obj2.name); // 123 456
```

![20210223195738](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210223195738.png)

- [x] demo3

创建了3个对象

```js
var user1 = {
    name: "u1",
    address: {
        country: "中国",
        city: "哈尔滨"
    }
};
var user2 = {
    name: "u2",
    address: user1.address
};
user2.name = "user2";
user2.address.city = "成都";
console.log(user1.name, user2.name); // u1 user2
console.log(user1.address.city, user2.address.city); // 成都 成都
```

![20210223195847](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210223195847.png)

- [x] demo4

创建了3个对象

```js
var obj1 = {
    a: "123",
    b: "456",
    sub: {
        s1: "abc",
        s2: "bcd"
    }
};
var temp = obj1.sub;
var obj2 = obj1;
obj2.sub = {
    s1: "s",
    s2: "ddd"
};
console.log(obj1.sub.s1, obj2.sub.s1, temp.s1);// s s abc
```

![20210223195938](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210223195938.png)

- [x] demo5

[扩展]JS中的垃圾回收

垃圾回收器，会定期的发现内存中无法访问到的对象，该对象称之为垃圾，垃圾回收器会在合适的时间将其占用的内存释放。

```js
// 补充：在JS中，变量在使用时可以不写var
// 不写var直接赋值，相当于给window的某个属性直接赋值
a = 1;
console.log(a, window.a); // 1 1
```

- [x] **练习**

```html
<!-- 练习1.html -->
<script>
  //说出以下程序是否有问题，问题在哪？
  //中国象棋中有4个马，每个马是一个对象，为了方便对象的创建，写出如下代码
  var horse1 = {
      name: "马",
      position: { //马在棋盘上的位置
          x: 1,
          y: 9
      },
      color: "red" //马的颜色
  };

  var horse2 = horse1;
  horse2.position.x = 7;

  var horse3 = horse1;
  horse3.name = "馬";
  horse3.position.y = 0;
  horse3.color = "black";

  var horse4 = horse3;
  horse4.position.x = 7;

  // 答: 上述4个horse 操作的实际上都是同一匹马

  console.log(horse1.color, horse1 === horse2, horse1 === horse3, horse1 === horse4); // "black" true true true
</script>




<!-- 练习2.html -->
<script>
  //以下程序的输出结果是什么
  var obj1 = {
      a: "a1",
      subObj: {
          prop: "p1"
      }
  };

  var obj2 = {
      a: "a2",
      subObj: {
          prop: "p2"
      }
  };

  obj2.subObj = obj1.subObj;
  obj2.subObj.prop = "p3";
  console.log(obj1.subObj.prop, obj2.subObj.prop); // "p3" "p3"
</script>




<!-- 练习3.html -->
<script>
  var a = 3,
      b = 5;
  //将两个变量交换
  var temp = a;
  a = b;
  b = temp;
</script>

<script>
  var a = 3,
      b = 5;
  //将两个变量交换
  a = a + b;
  b = a - b;
  a = a - b;
</script>

<script>
  var item = {
      name: "foo",
      parent: {
          name: "bar"
      },
      child: {
          name: "goo"
      }
  };
  // 将item的parent和child互换，不可创建新对象

  // item.parent  item.child
  var temp = item.parent;
  item.parent = item.child;
  item.child = temp;
  // item ==> {name: "foo", parent: {…}, child: {…}}
  // child: {name: "bar"}
  // parent: {name: "goo"}
</script>

<!-- 下面这种写法无效 不要拿地址作运算 -->
<script>
  var item = {
      name: "foo",
      parent: {
          name: "bar"
      },
      child: {
          name: "goo"
      }
  };
  item.parent = item.parent + item.child;
  item.child = item.parent - item.child;
  item.parent = item.parent - item.child;
  // item ==> {name: "foo", parent: NaN, child: NaN}
</script>
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- 引用类型赋值问题 -->
    <!-- test1.html -->
    <script>
        var a = "123";
        var b = a;
        b = "456";
        console.log(a, b); // "123" "456"
        //obj1 指向 xx 对象
        //obj1 持有 xx 对象的引用
        var obj1 = {
            name: "123",
            age: 10
        }; // 出现对象字面量的位置，会新开辟一块内存空间，用于存放对象的内容

        // obj2 和 obj1 指向同一个对象
        // obj2 和 obj1 持有相同的引用
        var obj2 = obj1;
        obj2.name = "456";
        console.log(obj1.name, obj2.name); // "456" "456"
    </script>




    <!-- 凡是出现对象字面量的位置 都一定在内存中创建了一个新对象 -->
    <!-- test2.html -->
    <script>
        var obj1 = {
            name: "123",
            age: 10
        };
        var obj2 = obj1;
        obj2 = {
            name: "456"
        };
        console.log(obj1.name, obj2.name); // "123" "456"
    </script>




    <!-- test3.html -->
    <script>
        var user1 = {
            name: "u1",
            address: {
                country: "中国",
                city: "哈尔滨"
            }
        };

        var user2 = {
            name: "u2",
            address: user1.address
        };
        user2.name = "user2";
        user2.address.city = "成都";
        console.log(user1.name, user2.name); // "u1" "user2"
        console.log(user1.address.city, user2.address.city); // "成都" "成都"
    </script>




    <!-- test4.html -->
    <script>
        var obj1 = {
            a: "123",
            b: "456",
            sub: {
                s1: "abc",
                s2: "bcd"
            }
        };
        var temp = obj1.sub;
        var obj2 = obj1;
        obj2.sub = {
            s1: "s",
            s2: "ddd"
        };

        console.log(obj1.sub.s1, obj2.sub.s1, temp.s1); // "s" "s" "abc"
    </script>



    <!-- 垃圾回收问题 -->
    <!-- test5.html -->
    <script>
        var obj = {
            a: "123",
            b: "456",
            sub: {
                s: "asdf"
            }
        };

        var temp = obj.sub;

        obj = {
            a: "abc",
            b: "bcd"
        };
    </script>




    <!-- test6.html -->
    <script>
        // 补充：在JS中，变量在使用时可以不写var
        // 不写var直接赋值，相当于给window的某个属性直接赋值

        a = 1;
        console.log(a, window.a); // 1 1
        console.log(window.a === a); // true
    </script>

</body>

</html>
```

# 三、运算符

## 1. 运算符概述

```
1. 对比第2章
   第2章：变量和数据类型，解决数据存放问题
   第3章：运算符，解决数据运算的问题，面试题密集
2. 操作符和操作数
    操作符: 运算符, 参与运算的符号
        操作符不一定仅有一个符号
    操作数: 参与运算的数据, 也称之为 "元"
3. 操作符出现在不同的位置，可能具有不同的含义
   1-2; // 表示 1 减 2 此时操作符 - 表示的是 减
   -1.2; // 表示 负 1.2 此时操作符 - 表示的是 负
4. 目前接触到的操作符
    1.  =   赋值符号，将右边的数据赋值给左边
    2.  .   访问符号，用于访问对象的属性
    3.  []  访问符号，用于访问对象的属性
    4.  ()  函数调用
5. 操作符的分类
    - 按操作数数量区分：
      1. 一元（目）运算符：`()`  `.`  `[]`
      2. 二元（目）运算符: `+`  `-`  `/` `*` `%` `=`
      3. 三元（目）运算符: `? :`
    - 功能区分：(按照功能区分,并没有官方标准)
      1. 算术运算符（数学）
      2. 比较运算符
      3. 逻辑运算符
      4. 位运算符
      5. 其他
6. 表达式 = 操作符 + 操作数
7. 返回值 和 返回值类型
    每个表达式都有一个运算结果, 该结果叫做 返回值, 返回值的类型叫做 返回类型
    由于每个表达式都具有返回值, 所以所有的表达式都可以当作数据使用。
8. 目前学习的运算符的返回值和类型
    1. =    该表达式，返回赋值的结果;
    2. .    属性访问表达式，返回的是属性的值;
    3. []   属性访问表达式，返回的是属性的值;
    4. ()   函数调用表达式，返回的结果取决于函数的运行;
    5. 声明 加 赋值的表达式，返回结果为`undefined`;

notes:
    Chrome 控制台 REPL环境
    REPL：Read Eval Print Loop，读-执行-打印-循环
    当直接在控制台书写代码时，除了运行代码之外，还会输出该表达式的返回值

    第二章 解决数据存放的问题 VS 第三章 解决数据运算的问题 --- 第三章的知识点实际上并不难 ( 如果只是为了达到开发的需求 ) , 但是面试题特别爱考这里头的细节 ;

    1. 操作数指的是数据, 操作符指的是处理数据的一系列符号;
    2. 操作符 + 操作数 ==> 表达式;
    3. 表达式可以当做数据来使用;
    4. 认识 Chrome 浏览器控制台的 REPL环境;
    5. [细节] 声明 加 赋值的表达式返回 `undefined`
```

- [x] demo1

赋值表达式返回赋值的结果

```js
var a;
console.log( a = 1 ); // 1
// a = 1 这个表达式的返回值是赋值的结果 ==> 1
```

- [x] demo2

赋值表达式返回赋值的结果

```js
var a, b, c, d;
a = b = c = d = 1;
// 1. d = 1; // 返回值 ==> 1
// 2. c = 1; // 返回值 ==> 1
// 3. b = 1; // 返回值 ==> 1
// 4. a = 1; // 返回值 ==> 1
console.log(a, b, c, d); // 1 1 1 1
```

---

- [x] demo3

声明的同时进行赋值的表达式返回`undefined`

![20210224232038](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210224232038.png)

- [x] demo4

`console.log();` 的返回值是 `undefined`

![20210224232541](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210224232541.png)

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>

    <!-- test1.html -->
    <script>
        var obj = {
            a: 3
        };
        console.log(obj["a"] * obj.a); // 9
    </script>


    <!-- test2.html -->
    <!-- 赋值表达式 ==> 返回赋值的结果 -->
    <script>
        var a, b, c, d;
        a = b = c = d = 1;
        console.log(a, b, c, d); // 1 1 1 1
        /*
            d:1
            c:1
            b:1
            a:1
         */
    </script>


    <!-- test3.html -->
    <script>
        // console.log函数调用的返回结果为undefined
        console.log(console.log()); // undefined
    </script>


</body>

</html>
```


## 2. 算术运算符

```
数学运算符
    1. + - * /
    2. + -
    3. %
    4. ++ -- (下节课讨论)
    5. ** 幂
细节问题
    1. 数字运算是不精确的 (小数运算是不精确的,这是大多数编程语言的通病 若想深入了解原因 可以看[拓展课程])
    2. 除数为0
       - 如果被除数是正数，得到结果 Infinity （正无穷）
       - 如果被除数是负数，得到结果 -Infinity （负无穷）
       - 如果被除数是0，得到结果 NaN （Not a Number，非数字）
    3. 求余(求模)`%`
        余数的符号，与被除数相同。
        求余和求模的区别([扩展]课程讲解)
```

- [x] demo1

```
幂运算符
```

```js
5 ** 2; // 25
5 ** 3; // 125
-5 ** 2; // Uncaught SyntaxError: Unary operator used immediately before exponentiation expression. Parenthesis must be used to disambiguate operator precedence (没看懂)
-(5 ** 2); // -25
(-5) ** 2; // 25
```

- [x]  demo2

```
NaN 不是有限的 而是无限的
```

```js
console.log(isFinite(NaN)); // false
```


- [x] demo3

```
除数为0的情况
NaN虽然是数字，但它和任何数字作任何运算，得到的结果都是NaN
```

```js
1 / 0; // Infinity
typeof(1/0); // "number"
typeof 1/0; // NaN 因为先执行的是 typeof 1 得到结果是 "number" 然后再用该结果 "number" / 0
typeof 1; // "number"
"number" / 0; // NaN
```


- [x] demo4

```
余数的符号与被除数相同
被除数 % 除数 === 余数
```

```js
10 % 3; // 1
10 % -3; // 1
-10 % 3; // -1
-10 % -3; // -1
```

---

```
其他类型使用算术运算
  1. 除加号之外的算术运算符
     将原始类型转换为数字类型（自动完成转换），然后进行运算。
  2. 加号运算符
     加号一边有字符串，含义变为字符串拼接
     加号两边都没有字符串，但一边有对象，将对象转换为字符串，然后按照上面的规则进行
     其他情况和上面的数学运算一致
```

- [x] demo5

```
boolean -> number
true -> 1
false -> 0
```

```js
+ true; // 1
+ false; // 0
```

- [x] demo6

```
string -> number
  1. 如果字符串内部是一个正确的数字，直接变为数字;
  2. 如果是一个非数字，则得到NaN（能识别Infinity，不能把字符串内部的东西当作表达式）;
  3. 如果字符串是一个 空字符串，转换为0
     空字符串: 没有任何内容(包括空格)的字符串
  4. 字符串转换时，会忽略前后空格。
```

```js
+ "123"; // 123
+ "123.4"; // 123.4
+ "123.4.5"; // NaN
+ "123abc"; // NaN
+ "Infinity"; // Infinity
+ "-Infinity"; // -Infinity
+ ""; // 0
+ "    123.4    "; // 123.4
```

- [x] demo7

```
null -> number
  null 转化为数字是 0
undefined -> number
  undefined 转化为数字是 NaN
Object -> number (细节问题)
  将对象类型先转换为字符串类型，然后再将该字符串转换为数字类型
  对象类型 -> "[object Object]" -> NaN
  对象转为数字是 NaN 的具体原因 -> [扩展]
```

```js
+ null; // 0
+ undefined; // NaN
+ { name: 'abc' }; // NaN
```

```js
{} * 5; // Uncaught SyntaxError: Unexpected token '*' --- 代码块 * 5 这显然是不符合语法规范的
({} * 5); // NaN 因为加了小括号, 所以此时小括号内的内容会被识别为一个表达式; 所以 空对象 {} 会先被识别为 NaN, 然后再 NaN * 5 结果自然就是 NaN 了
```

- [x] demo8

```js
({} + 123); // "[object Object]123"
// 除了应付面试, 记住这个也许还真没啥用;
/* 原因猜测:
首先, 对象类型若参与了数字运算, 那么它会先调用自身的 toString 方法 再进行运算
  eg:
      var obj = {};
      obj.toString(); // "[object Object]"
*/
```


- [x] demo9

```
练习: 说出下面的输出结果
```

```js
console.log(1 + 2 * 3); // 7
console.log(1 + 3 % 2); // 2
console.log("" + 3 % 2);// "1"
console.log(+"" + 3 % 2); // 1 注意,当+充当单目运算符(正)来使用时,其优先级高于乘 除 取余
console.log(+{} + ""); // "NaN" --- +"[object Object]" + "" --- NaN + "" --- "NaN"
console.log(100 % 4 / 0); // NaN
console.log(null / null); // NaN
var a;
console.log(a + {} + 123); // undefined[object Object]123
console.log(1 + "" + 2 + 3); // "123"
console.log({} * null); // NaN
console.log(+"" + 100); // 100
```

### 作业

- [x] 1. 温度转换器

设置一个变量，保存摄氏温度（C），将其转换为华氏温度（F）

公式: `F = (9/5)C + 32`

```js
/* 单词:
华氏度 ==> fahrenheit
摄氏度 ==> centigrade */
var centigrade = 37.0;
fahrenheit = (9 / 5) * centigrade + 32;
console.log(fahrenheit); // 98.60000000000001
```

- [x] 2. 利息计算器

设置变量，分别存放本金、月数、年利率，计算利息

```js
/* 单词:
本金: principal
月数: months
年利率: annual interest rate
月利率: monthly interest rate
利息: interest */
var prin = 100000000, // 一个亿
    months = 27, // 两年多
    annIRate = 0.015;
var monIRate = annIRate / 12;
var interest = prin * (months * monIRate);
console.log(interest); // 3375000 三百三十七万五千元
```

**小结**

```
知识点
  1. 字符串转数字
     - 正常的数字 ==> 直接转 ;
     - 非数字 ==> `NaN` ;
     - 空 ==> `0` ;
  2. 对象转字符串 ==> `[object Objecct]` ;
  3. 对象转数字 ==> `NaN` ;
细节问题 (特多)
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>

    <!-- test.html -->
    <!-- Boolean 参与数学运算 -->
    <script>
        var b = true,
            c = false;
        b = +b;
        var num = c + 10;

        console.log(b, typeof b); // 1 "number"
        console.log(num, typeof num); // 10 "number"
    </script>

    <!-- 对象转字符串 -->
    <script>
        document.write({
            name: "aadsfas"
        }); // [object Object]
    </script>

    <!-- 对象参与数学运算 -->
    <script>
        console.log({}* 5); // NaN ==> 计算过程 先将 {} 转换为 "[Object object]" 再转换为数字 NaN
        console.log({} + 5); // "[object Object]5" ==> 计算过程 先将 {} 转换为 "[Object object]" 再转换为数字 NaN
    </script>


    <!-- 练习.html -->
    <script>
        // 说出下面的输出结果
        console.log(1 + 2 * 3); // 7
        console.log(1 + 3 % 2); // 2
        console.log("" + 3 % 2); // "1"
        console.log(+"" + 3 % 2); // 1
        console.log(+{} + ""); // "NaN"
        console.log(100 % 4 / 0); // NaN
        console.log(null / null); // NaN
        var a;
        console.log(a + {} + 123); // undefined[object Object]123
        console.log(1 + "" + 2 + 3); // "123"
        console.log({}* null); // NaN
        console.log(+"" + 100); // 100
    </script>

</body>

</html>
```

## 3. [作业讲解]算术运算符

- [x] 作业1

```js
var C = 27.5;
var F = 9 / 5 * C + 32;
console.log("摄氏温度为" + C + "度，华氏温度为" + F + "度");
// 摄氏温度为27.5度，华氏温度为81.5度
```

- [x] 作业2

```js
var money = 100000,
    month = 3,
    rate = 5.6; //利率百分比
var earnMoney = money * rate / 100 / 12 * month;
console.log("本金:" + money + ", 存储月数：" + month + ", 年利率:" + rate + "%, 赚取利息：" + earnMoney);
// 本金:100000, 存储月数：3, 年利率:5.6%, 赚取利息：1400
// 目前先不考虑复利,等学完循环语句后,再对作业进行扩展;
```


## 4. 自增和自减

```
自增和自减 是 一元运算符

基本功能
    ++：将某个变量的值自增1
    --：将某个变量的值自减1

细节
    自增自减表达式
        x++: 将变量x自增1，得到的表达式的值是自增之前的值。
        ++x: 将变量x自增1，得到的表达式的值是自增之后的值。
        x--: 将变量x自减1，得到的表达式的值是自减之前的值。
        --x: 将变量x自减1，得到的表达式的值是自减之后的值。
    优先级
        从高到底依次是：
            ++ --
            * / %
            + -
        优先级的运算细节：
            从左到右依次查看
            如果遇到操作数，将数据的值直接取出
            如果遇到相邻的两个运算符，并且左边的运算符优先级大于等于右边的运算符，则直接运行左边的运算符。
```

- [x] demo1

```
优先级的运算细节
案例中的 `++x` 和 `x++` 都是表达式,不能视作操作数直接将数据取出,而且,表达式的返回值也并非自变量的值;
```

```js
var x = 1;
var y = x + x++ * ++x; // 1 + 1 * 3
console.log(y); // 4

/* 过程分析:
1. x ==> 1
y = 1 + x++ * ++x; // 从左到右依次查看,遇到了第一个操作数 x ==> 1 将数据的值直接取出;
2. x ==> 1
y = 1 + 1 * ++x; // 第1次遇到两个相邻的运算符 [左边]+ 小于 [右边]++ ; 继续往后查看; 第2次遇到两个相邻的运算符 [左边]++ 的优先级 大于 [右边]* 的优先级; 直接运行左边的运算符 ++ ==> 执行 x++ ==> 得到表达式的值是自增之前的值 1
3. x ==> 2
y = 1 + 1 * 3; // 第1次遇到两个相邻的运算符 [左边]+ 小于 [右边]* ; 继续往后查看; 第2次遇到两个相邻的运算符 [左边]* 的优先级 小于 [右边]++ 的优先级; 因为无法再往后继续查看,所以直接运行右边的运算符 ++ ==> 执行 ++x ==> 得到表达式的值是自增之后的值 3
4. x ==> 3
y = 1 + 3; // 第1次遇到两个相邻的运算符 [左边]+ 小于 [右边]* ; 继续往后查看; 第2次遇到两个相邻的运算符 [左边]+ 的优先级 小于 [右边]* 的优先级; 因为无法再往后继续查看,所以直接运行右边的运算符 * ==> 执行 1 * 3 ==> 得到表达式的返回值是 3
5. y = 4; // 最后将赋值符号右边的最终结果 4 赋值为变量 y
*/
```

- [x] 练习1

```js
var x = 1;
var y = x++ + ++x + x++ * ++x + ++x; // 1 + 3 + 3 * 5 + 6
console.log(y); // 25
```

- [x] 练习2

```js
var x = 1;
var y = x + ++x * ++x + x; // 1 + 2 * 3 + 3
console.log(y); // 10
```

- [x] 练习3

```js
var x = 1;
var y = x + x++ * (x = x + x++ * ++x) + x; // 1 + 1 * (x = 2 + 2 * 4) + 10
console.log(y); // 21
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- test1.html -->
    <script>
        var x = 0;
        console.log(x); // 0
        console.log(x--); // 0
        console.log(--x); // -2
    </script>


    <!-- test2.html -->
    <script>
        var x = 0;
        console.log(x--); // 0
        console.log(x); // -1
    </script>



    <!-- test3.html -->
    <script>
        var x = 1;
        var y = ++x + 1;
        console.log(y); // 3
        console.log(x); // 2
    </script>




    <!-- 优先级

    从高到底依次是：

    1. ```++ --```
    2. ```* / %```
    3. ```+ -``` -->

    <!-- 优先级的运算细节：

    1. 从左到右依次查看
    2. 如果遇到操作数，将数据的值直接取出
    3. 如果遇到相邻的两个运算符，并且左边的运算符优先级大于等于右边的运算符，则直接运行左边的运算符。 -->

    <!-- test4.html -->
    <script>
        var x = 1;
        var y = x + x++ * ++x;
        console.log(y); // 4
    </script>

    <script>
        var x = 1;
        var y = x++ + ++x + x++ * ++x + ++x;
        console.log(y); // 25
    </script>

    <script>
        var x = 1;
        var y = x + ++x * ++x + x;
        console.log(y); // 10
    </script>

    <script>
        var x = 1;
        var y = x + x++ * (x = x + x++ * ++x) + x;
        console.log(y); // 21
    </script>


    <!-- test5.html -->
    <script>
        var x = 1;
        var y = x + x * x / 2 + 6;
        console.log(y); // 7.5
    </script>


</body>

</html>
```

## 5. 比较运算符

```
1. 比较运算符的分类:
    大小比较：> < >= <=
    相等比较：== != === !==
    >>> 比较运算符的返回类型：boolean
    >>> 算术运算符的优先级 高于 比较运算符

2. 大小比较
   1. 两个字符串比较大小
      比较的是字符串的字符编码
   2. 两个都是原始类型，至少一个不是字符串
      将它们都转换为数字进行比较
         NaN与任何数字比较，得到的结果都是false
         Infinity比任何数字都大
         -Infinity比任何数字都小
   3. 如果其中一个是对象
      将对象转换为原始类型然后，按照规则1或规则2进行比较
      目前，对象转换为原始类型后，是字符串 "[object Object]"

3. 相等比较
   == 和 != (相等 和 不相等)
   == 比较两个数据是否相等
   != 比较两个数据是否不相等

   首先看两边的数据类型是否相同
      1. 两端的类型相同，直接比较两个数据本身是否相同
         两个对象比较的是地址
      2. 两端的类型不同
         1). null 和 undefined， 它们之间相等， 和其他原始类型比较， 则不相等。
         2). 原始类型，比较时先转换为数字，再进行比较
         3). NaN与任何数字比较，都是false，包括自身
         4). Infinity和-Infinity，只能和自身相等
         5). 对象比较时，要先转换为原始类型后，再进行比较

   >>> 由于相等和不相等比较，对于不同类型的数据比较违反直觉，因此，通常我们不适用这种比较方式，而是使用更加接近直觉的严格相等和严格不相等比较

    === 和 !== （严格相等 和 严格不相等）
    === 两端的数据和类型必须相同
    !== 两端的数据或类型不相同

   两端类型相同，规则和相等比较一致,直接比较两个数据本身是否相同
   两端类型不同，为false

   数字之间的比较规则：
      1). NaN与任何数字比较，都是false，包括自身
      2). Infinity和-Infinity，只能和自身相等
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- test1.html -->
    <script>
        var a = 5,
            b = 4;
        console.log(2 + 3 >= 5); // true
        console.log('AB' > 'AC'); // false
        console.log("11" > "1"); // true
        console.log(a > b); // true
    </script>



    <!-- test2.html -->
    <script>
        console.log('1' >= 10); // false
        console.log('2' > true); // true
        // NaN与任何数字比较，得到的结果都是false
        console.log(NaN > 0); // false
        console.log(3 > {}); // false
        console.log(null > -1); // true null 转化为数字是0
        console.log(undefined > -1); // false undefined 转化为数字是NaN
    </script>



    <!-- test3.html -->
    <script>
        var a = {};
        var b = {};
        console.log(1 == 1); // true
        console.log(1 != 1); // false
        console.log("abc" === "abc"); // true
        console.log("abc " !== "abc"); // true
        // 引用类型 比较的是地址
        console.log(a == b); // false

        console.log(null == undefined); // true
        console.log(null != undefined); // false
        console.log(null == 0); // false
        console.log(undefined == 0); //false

        console.log('1' == 1); // true
        console.log(true == 1); //true
        console.log(true == 2); //false
        console.log(true == '1'); // true

        console.log({} == 0); // false
    </script>

    <!-- null的大小比较 和 null的相等比较 -->
    <script>
        console.log(null > -1); // true
        console.log(null == 0); // false
    </script>


    <!-- test4.html -->
    <script>
        console.log(1 === true); // false
    </script>



</body>

</html>
```

## 6. 逻辑运算符

```
1. 与（并且）
    符号：&&
    书写方式： 表达式1 && 表达式2
    1. 将表达式1 进行 boolean 判定
    2. 如果表达式1的判定结果为假，则直接返回表达式1，而不执行表达式2；否则，返回表达式2的结果。 （短路规则）
2. 或
    符号：||
    写法：表达式1 || 表达式2
    将表达式1 进行 boolean 判定
    如果表达式1为真，直接返回表达式1，不运行表达式2；否则，返回表达式2
3. 非
    符号：!
    写法: !数据
    一元运算符
    将数据的boolean判定结果直接取反，非运算符一定返回boolean类型。

notes:
   以下数据均判定为false, 其他数据全部为真
    null
    undefined
    false
    NaN
    ''
    0
```

**作业**

- [x] 1. 用一个变量保存成绩，输出该成绩是否及格（true 或 false）

```js
var score = 59;
console.log(score >= 60); // false
```

- [x] 2. 用一个变量保存年份，得到该年份2月的天数

```js
var year = 2020;
var result = (year % 4 === 0 && year % 100) || year % 400;
result && console.log('今年是闰年 二月的天数为29天'); // 执行
result || console.log('今年是平年 二月的天数为28天');
```


- [x] 3. 利息计算器

设置变量，分别存放本金、月数、年利率，计算利息

如果本金存放量超过了10万，年利率上浮20%（比如，年利率为4%，上浮后的年利率 4% * 1.2）

```js
var capital = 1000000, // 本金100万
   months = 24, // 存放两年
   rate = 0.04; // 4%的年利率
capital > 100000 && (rate = rate * 1.2);
var earnMoney = capital * rate / 12 * months;
console.log(earnMoney); // 96000
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>


    <!-- test1.html -->
    <script>
        console.log(5 > 3 && 3 > 2); // true
        console.log(5 > 3 && 100); // 100
        console.log(0 && 2); // 0
    </script>

    <script>
        var x = 1;
        console.log(x > 2 && x++ > 0); // false
        console.log(x); // 1
    </script>

    <script>
        console.log(1 && 2 && 3 && 4 && 0 && 5 && 6 && 7); // 0
    </script>

    <script>
        var age = -10;
        // 如果年龄为负数，则将其设置为0
        age < 0 && (age = 0); // 难以阅读和理解
        console.log(age); // 0
    </script>

    <script>
        var x = 1;
        console.log(x++ >= 1 && x++ >= 2 && x++ >= 4 && x++ >= 4); // false
        console.log(x); // 4
    </script>


    <!-- test2.html -->
    <script>
        // || 找值为 true 的表达式
        console.log(1 > 3 || 10); // 10
        console.log(undefined || 'abc'); // 'abc'
        console.log(0 || null || undefined || 1 || null || NaN); // 1
    </script>

    <script>
        var obj = {
            name: "xxx",
            gender: "男"
        };
        // 对象中如果没有年龄，则将年龄赋值为18
        obj.age = obj.age === undefined && 18;
        console.log(obj.age); // 18
    </script>

    <script>
        var obj = {
            name: "xxx",
            gender: "男"
        };
        // 对象中如果没有年龄，则将年龄赋值为18
        obj.age = obj.age || 18;
        console.log(obj.age); // 18
    </script>


    <!-- test3.html -->
    <script>
        console.log(!true); // false
        console.log(!undefined); // true
        console.log(!2 + 1); // 1
    </script>

    <!-- 6个视作 false 的值 -->
    <script>
        console.log(!!false);
        console.log(!!0);
        console.log(!!null);
        console.log(!!undefined);
        console.log(!!'');
        console.log(!!NaN);
    </script>


    <!-- test4.html -->
    <!-- 优先级
        && > ||
    -->
    <script>
        // 在变量中存放年份
        var year = 2004;

        // 用逻辑运算，判断该年是否是闰年
        // 闰年规则：4年一闰，百年不闰；400年一闰
        var result = year % 4 === 0 && year % 100 !== 0 || year % 400 === 0;
        // 如果是闰年，则输出闰年，否则，输出平年
        result && console.log("闰年");
        result || console.log("平年");
    </script>


</body>

</html>
```

## 7. [作业讲解]逻辑运算符

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 1. 用一个变量保存成绩，输出该成绩是否及格（true 或 false） -->
    <script>
        var score = 50;
        console.log(score >= 60);
    </script>


    <!-- 2. 用一个变量保存年份，得到该年份2月的天数 -->
    <script>
        var year = 2001;
        //是否是闰年
        var isLeap = year % 4 === 0 && year % 100 !== 0 || year % 400 === 0;

        isLeap && console.log(29 + "天");
        isLeap || console.log(28 + "天");
    </script>

    <!-- 3. 利息计算器

    设置变量，分别存放本金、月数、年利率，计算利息

    如果本金存放量超过了10万，年利率上浮20%（比如，年利率为4%，上浮后的年利率 4% * 1.2） -->
    <script>
        var money = 200000,
            month = 12,
            rate = 4;
        money > 100000 && (rate = rate * 1.2);
        var lixi = money * rate / 100 / 12 * month;
        console.log("利息：" + lixi);
    </script>
</body>

</html>
```


## 8. 三目运算符

```
书写方式： 表达式1 ? 表达式2 : 表达式3
    1. 对表达式1进行boolean判定
    2. 如果判定结果为真，返回表达式2；否则，返回表达式3。
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- test1.html -->
    <!-- 根据年份 返回这一年二月份的天数 -->
    <script>
        var year = 2000;
        //是否是闰年
        var isLeap = year % 4 === 0 && year % 100 !== 0 || year % 400 === 0;
        //得到该年份二月的天数
        var days = isLeap ? 29 : 28;
        console.log("二月的天数为：" + days);
    </script>

    <!-- test2.html -->
    <!--  -->
    <script>
        var x = 1;
        x = x++ >= 1 ? x++ * x++ : ++x * ++x;
        console.log(x); // 6
    </script>

</body>

</html>
```

## 9. 运算符补充

```
1. `模板字符串`
2. 前面提到的类型转换不会影响原本的数据
3. 复合的赋值运算符
   +=  -=  /=  *=  %=  **=
4. void 运算符 (一元)
    写法:
        a. 普通写法： void 表达式
        b. 函数写法： void(表达式)
    作用: 运行表达式，然后返回undefined
5. typeof 运算符 (一元)
    写法:
        a. 普通写法： typeof 表达式
        b. 函数写法： typeof(表达式)
    作用: typeof 运算，返回表达式的类型，是一个字符串。
6. 逗号运算符
    写法: 表达式1, 表达式2
    作用: 依次运行两个表达式，返回表达式2
    注意: 逗号运算符的优先级比赋值更低
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 模板字符串.html -->
    <script>
        var user = {
            age: 18,
            name: "成哥",
            gender: "男"
        };

        // 输出： 我叫xxx，今年xxx岁了，性别是xxx，目前已成年（未成年）
        console.log("我叫" + user.name +
            "，今年" + user.age +
            "岁了，性别是" + user.gender +
            "，目前" + (user.age >= 18 ? "已成年" : "未成年")); // 我叫成哥，今年18岁了，性别是男，目前已成年
        // 运算符处可以换行

        console.log(`我叫${user.name}，今年${user.age}岁了，性别是${user.gender}，目前${user.age>=18?"已成年":"未成年"}`);
        // 我叫成哥，今年18岁了，性别是男，目前已成年
    </script>

    <!-- 类型转换.html -->
    <script>
        // 类型转换不会影响原本的数据
        var x = '1';
        var y = x * 2;
        console.log(y, typeof y); // 2 "number"
        console.log(x, typeof x); // 1 "string"
    </script>

    <!-- 复合的赋值运算符.html -->
    <script>
        var x = 2;
        x += 3; // 等同于 x = x + 3;
        console.log(x); // 5
    </script>

    <script>
        var x = 2;
        x *= 1 + 2; // 等同于 x = x * (1 + 2);
        console.log(x); // 6
    </script>

    <script>
        var x = 2;
        x *= x++ + 2; // 等同于 x = x * (x++ + 2);
        console.log(x); // 8
    </script>

    <!-- 将复合赋值运算符用于字符串的拼接 -->
    <script>
        var user = {
            age: 18,
            name: "成哥",
            gender: "男"
        };

        // 输出： 我叫xxx，今年xxx岁了，性别是xxx，目前已成年（未成年）
        var result = "我叫";
        result += user.name;
        result += "，今年";
        result += user.age;
        // ....

        console.log(result); // 我叫成哥，今年18
    </script>

    <!-- 逗号运算符.html -->
    <!-- [注] 逗号运算符的优先级比赋值更低 -->
    <script>
        var x = 1;
        x = (x++ * 2, x++ * 2, x++ * 2); // 需加小括号
        // 逗号运算符 ==> 返回最后一个表达式的值
        console.log(x); // 6
    </script>


</body>

</html>
```

`PS: 以下是拓展课程 还没看过`

---

## 10. [扩展]数字的存储

**在对精度要求很高的系统中，或要对小数的运算结果进行比较时，需要特别谨慎**

### 问题

1. JS中的小数运算是精确的吗？

不一定

2. JS中的整数运算是精确的吗？

不一定

3. JS中表示的整数是连续的吗？

不是，当JS的数字很大的时候，不再连续。

4. JS中表示的最大数字是多少？

最大连续整数：9007199254740991

5. JS中能表示的数字的有效位数是多少？

16 ~ 17



### 二进制

现实世界中：十进制，10个数字，逢十进一

计算机世界中：二进制，2个数字，逢二进一

二进制 -> 十进制

```math
1101 = 1*2^3 + 1*2^2 + 0*2^1 + 1*2^0 = 13

11.01 = 1*2^1 + 1*2^0 + 0*2^{-1} + 1*2^{-2} = 3.25
```

十进制 -> 二进制

13 -> 1101

```
13 / 2  商 6    余  1
6  / 2  商 3    余  0
3  / 2  商 1    余  1
1  / 2  商 0    余  1
余数从下往上看
```

3.25 -> 11.01

整数部分一样

小数部分

```
0.25 * 2    0.5     整数部分：0
0.5  * 2    1.0     整数部分：1
整数部分从上往下看
```

### 为什么JS的小数运算不精确

十进制的小数，转换为二进制后，可能是无限小数，但是计算机对数字的存储能力有限，因此会丢失一些数据。

十进制数 0.3 -> 0.010011001100110011001.....

```
0.3*2   0.6     0
0.6*2   1.2     1
0.2*2   0.4     0
0.4*2   0.8     0
0.8*2   1.6     1
0.6*2   1.2     1
0.2*2   0.4     0
......
整数部分从上往下看
```

### JS如何存储数字

整数法、浮点法

JS中，存储的所有数字，都按照浮点法存放。

浮点法存放的数字，叫做浮点数（float），浮点数分为单精度和双精度。

JS中，使用双精度存放浮点数，IEEE 754。

**存放方式**

JS在计算机中，给每个数字开辟一块内存空间，尺寸固定为64位

> 在计算机中，位（bit）是最小的存储单位，简称为bit
> 1 byte = 8 bit
> 1 KB = 1024 byte
> 1 MB = 1024 KB
> 1 GB = 1024 MB

```
[第1段][第2段][第3段]

第1段：1位，表示符号位，如果为1，是负数，如果为0，是正数
第2段：11位，表示指数位，这里的指数是2为底的指数，而不是10
第3段：52位，表示有效数字
```

举例

```
0     1000 0000 011    1111 0000 0000 0000....
```
相当于： $1.1111 * 2 ^ {1027 - 1023} $

**特殊情况**

1. 指数为0，尾数为0，表示数字 0
2. 符号为0，指数为2047，尾数为0，表示正无穷

```
Infinity: 0 11111111111 00000000000...
```

3. 符号为1，指数为2047，尾数为0，表示负无穷

```
-Infinity: 1 11111111111 00000000000...
```

4. 指数为2047，尾数不为0，表示NaN

```
NaN: 1 11111111111 01001010000...
```

**一个正常的数字，指数部分最多是2046**

### 能表示的最大数字

```
0 11111111110 1111111111.........
```

相当于： $1.1111111111... * 2 ^ 1023 $

### 能表示的最大的安全整数

安全数字：从1开始到该数字，均是连续的整数，并且该数字的下一个整数是存在的。

```
0 xxxxx 1111111111....
```

相当于： $2^53 - 1$

下一位： $2^53$   ```0  xxxxx  0000000000000```


### 本节代码


<html>
<!--在这里插入内容-->

    <!-- Q: JS中的小数运算是精确的吗？-->
    <!-- A: 不一定 -->
    <script>
        console.log(0.1 + 0.2); // 0.30000000000000004
        console.log(0.1 + 0.2 === 0.3); // false
        console.log(0.5 + 0.5); // 1
        console.log(0.25 + 0.5); // 0.75
    </script>

    <!-- Q: JS中的整数运算是精确的吗？ -->
    <!-- A: 不一定 -->
    <script>
        // 数字很大的情况下 整数运算不一定是精确的
        console.log(23425463452345243234 + 1); //23425463452345240000
    </script>

    <!-- Q: JS中表示的整数是连续的吗？ -->
    <!-- A: 不是，当JS的数字很大的时候，不再连续。 -->

    <!-- Q: JS中表示的最大数字是多少？ -->
    <!-- A: 最大连续整数：9007199254740991 -->
    <script>
        console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
        // 最大的连续整数 ==> 从1开始数到它不间断 而且从它开始还可以继续向下数一个
        console.log(Number.MAX_SAFE_INTEGER + 1); // 9007199254740992
        console.log(Number.MAX_SAFE_INTEGER + 2); // 9007199254740992
    </script>

    <!-- Q: JS中能表示的数字的有效位数是多少？ -->
    <!-- A: 16 ~ 17 -->
    <!-- 表示整数的话 只有16位
    如果加上小数位数 可以达到17位 -->
</html>

## 11. [扩展]位运算

将一个整数的二进制格式进行运算

js中，如果对一个数据进行位运算，它首先会将其转换为一个整数，并且按照32位的整数二进制排列

举例

```
2.7 -> 2 -> 0000 0000 0000 0000 0000 0000 0000 0010

NaN -> 0

Infinity -> 0

-Infinity -> 0
```

### 与运算

符号：&

写法：整数1 & 整数2

将两个整数每一位进行比较，如果都为1，结果为1，否则结果为0.

### 或运算

符号：|

写法：整数1 | 整数2

将两个整数每一位进行比较，如果都为0，结果为0，否则结果为1.

### 否（非）运算

符号：~

写法：~整数

将该整数按位取反

**负数的存储方式**

-1

真码：1000 0000 0000 0000 0000 0000 0000 0001
反码：1111 1111 1111 1111 1111 1111 1111 1110  真码取反
补码：1111 1111 1111 1111 1111 1111 1111 1111  反码加1  最终的存储方案

取反的快速运算：-数字 - 1

JS中最快速的取整的方式：``` ~~整数 ```

### 异或运算

符号：^

写法：数字1 ^ 数字2

将数字1和数字2按位比较，不同取1，相同取0

### 应用场景

位的叠加（开关）

### 位移运算

左位移： <<

写法： 数字1 << 数字2   结果： 数字1 * 2 ^ 数字2

将数字1的二进制（除符号之外，左移动数字2的次数）

右位移：>>

写法： 数字1 >> 数字2   结果： 整数(数字1 / 2 ^ 数字2)

全右位移：>>>

与右位移的区别，在于全右位移会导致符号位跟着位移。

## 12. [扩展]求余和求模

% ：求余

x % y

1. 求余 x rem y:  x - n * y, n表示商取整（直接去掉小数，向0取整）

```js
x = 7, y = 3   x rem y = x - n * y = 7 - 2 * 3 = 1

n = x / y = 2.333333 ≈ 2
```

```js
x = 7, y = -3

n = 7 / -3 = -2.33333 ≈ -2

x rem y = x - n * y = 7 - (-2)*(-3) = 7 - 6 = 1
```

```js
x = -7, y = 3

n = -7 / 3 = -2.33333 ≈ -2

x rem y = x - n * y = -7 - (-2)*3 = -7 + 6 = -1
```


**余数和被除数的符号相同**

2. 求模 x mod y:  x - n * y, n表示商取整（向下取整）

```js
x = 7, y = -3

x mod y = x - n * y = 7 - (-3)*(-3) = 7 - 9 = -2

n = 7 / -3 = -2.3333 ≈ -3
```

```js
x = -7, y = 3

x mod y = x - n * y = -7 - (-3)*3 = -7 + 9 = 2

n = -7 / 3 = -2.3333 ≈ -3
```

**求模的符号与除数相同**


# 四、流程控制

## 1. 流程图

```
1. 流程图是啥?
    一套的标准的图形，用于描述程序的逻辑
    通常使用流程图分析程序的流程
2. 如何在 markdown 中画流程图?
    可以使用 mermaid 语法来实现
    eg: (在GitHub上渲染不出来)
      graph TD
      start((开始))-->if{判断}
      if--true-->A[adsfasf]
      if--false-->ed((结束))
      A-->ed
```

![20210225200944](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210225200944.png)

- [x] 邓哥的思维：

```
graph TD
st((开始)) --> buyPeach[买两个桃子]
buyPeach-->if{是否碰到卖西瓜的}
if--true-->buyXigua[买一个西瓜]
if--false-->ed((结束))
buyXigua-->ed
```

![20210225202008](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210225202008.png)

- [x] 成哥的思维：

```
graph TD
st((开始)) --> if{是否碰到卖西瓜的}
if--true-->买一个桃子
if--false-->买两个桃子
买一个桃子-->ed((结束))
买两个桃子-->ed
```

![20210225202230](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210225202230.png)


## 2. if判断

```js
if(条件1){
    // 代码块
}
else if(条件2){
    // 代码块
}
else if(条件3){
    // 代码块
}
//....
else{
    // 以上条件都不满足执行的代码块
}
```

```
1. 如果某个条件满足，则直接忽略后面的所有条件
2. else if 可以有多个 (包含0个)
3. else可以有1个或0个
4. else可以换行，可以不换行 (看公司要求)
5. 如果代码块只有一条语句，可以省略花括号 (不推荐)
6. if只能出现一次
```

**补充**

```
1. prompt("提示文本");
    若用户点击的是确定, 那么返回用户输入的内容(字符串形式)
    若用户点击的是取消, 那么返回 null
2. 利用 操作符 + 将字符串转换成数字
    +字符串
    +字符串 === Number(字符串)
3. 得到一个随机数
    Math.random() 该表达式返回一个0~1之间的随机数字（无法取到1）
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>

    <!-- 被视为false的六个值 -->
    <script>
        console.log(!!null); // false
        console.log(!!undefined); // false
        console.log(!!false); // false
        console.log(!!NaN); // false
        console.log(!!0); // false
        console.log(!!''); // false
    </script>


    <!-- test1.html -->
    <script>
        var score = 95;
        // A：>=90  B: >=70 <90  C: >=50 <70  D: <50
        if (score >= 90) {
            console.log("A");
        } else if (score >= 70) {
            console.log("B");
        } else if (score >= 50) {
            console.log("C");
        } else {
            console.log("D");
        }
    </script>

    <script>
        var score = 66;
        // 单用if语句
        if (score >= 90) {
            console.log("A");
        }
        if (score >= 70 && score < 90) {
            console.log("B");
        }
        if (score >= 50 && score < 70) {
            console.log("C");
        }
        if (score < 50) {
            console.log("D");
        }
    </script>





    <!-- test2.html [面试题] -->
    <script>
        if (!x) {
            x = 0;
        }
        if (x++ >= 1) {
            var x;
            x++;
        } else if (++x >= 2) {
            x++;
        } else {
            x--;
        }
        console.log(x); // 3
    </script>


    <!--
    1. 用户输入: prompt("提示文本")

    该表达式返回结果：null 或 字符串

        1. null：表示用户点击了取消
        2. 用户输入的字符串：表示用户点击了确定，得到用户输入的结果 -->


    <!-- 2. 将字符串转换成数字：+字符串 -->


    <!-- test3.html -->
    <script>
        // 等待用户操作（确定，取消），将用户操作的结果保存到变量result中
        // 让用户输入一个数字，如果点击了取消，输出取消，如果点击了确定，根据输入的内容判断输入是否正确
        var result = prompt("请输入你的年龄");
        if (result === null) {
            console.log("点击了取消");
        } else {
            result = +result; //转换为数字
            if (isNaN(result)) { // 如果 result 转换为数字是 NaN 那么执行if语句块的内容
                // 不是正常的数字
                console.log("输入有误");
            } else {
                console.log(result, typeof result);
            }
        }
    </script>


    <!--
    3. 得到一个随机数

    Math.random() 该表达式返回一个0~1之间的随机数字（无法取到1） -->

    <!-- test4.html -->
    <script>
        console.log(Math.random());
    </script>


</body>

</html>
```

## 3. [作业讲解]if判断

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 作业部分 -->

    <!-- 1. 提示用户输入一个三位数，若不是三位数，则提示用户输入有误；若是三位数，则判断该数能否被13整除。 -->
    <script>
        var input = +prompt("请输入一个三位数");
        if (isNaN(input)) {
            console.log("输入有误");
        } else {
            if (input > 100 && input < 1000) {
                console.log('您输入的数字是:', input, input % 13 === 0 ? '能被13整除' : '不能被13整除');
            } else {
                console.log("输入有误");
            }
        }
    </script>

    <!-- 袁老师版 -->
    <script>
        var number = +prompt("请输入一个三位数");
        if (isNaN(number) || number < 100 || number > 999) {
            console.log("输入有误");
        } else {
            if (number % 13 === 0) {
                console.log("能被13整除")
            } else {
                console.log("不能被13整除")
            }
        }
    </script>




    <!-- 2. 让用户输入一个成绩（0-100），判断这个成绩属于哪个范围并输出结果（A:90-100 B:70-89 C:60-69 D:40-59 E:0-39），若用户输入的不是0-100的数字，则输出输入有误。 -->
    <script>
        var input = +prompt('请输入成绩(0-100): ');
        if (isNaN(input)) {
            console.log("输入有误");
        } else {
            if (input >= 0 && input <= 100) {
                if (input >= 90) {
                    console.log("A");
                } else if (input >= 70) {
                    console.log("B");
                } else if (input >= 60) {
                    console.log("C");
                } else if (input >= 40) {
                    console.log("D");
                } else {
                    console.log("E");
                }
            } else {
                console.log("输入有误");
            }
        }
    </script>

    <!-- 袁老师版 -->
    <script>
        var score = +prompt("请输入一个成绩（0~100）");
        if (isNaN(score) || score < 0 || score > 100) {
            console.log("输入有误");
        } else {
            if (score >= 90) {
                console.log("A")
            } else if (score >= 70) {
                console.log("B")
            } else if (score >= 60) {
                console.log("C")
            } else if (score >= 40) {
                console.log("D")
            } else {
                console.log("E");
            }
        }
    </script>


    <!-- 3. 根据世界卫生组织推荐的计算方法，
    男性标准体重计算方法为（身高cm－80）×70﹪
    女性标准体重计算方法为（身高cm－70）×60﹪
    标准体重正负10%为正常体重，低于标准体重的10%为过瘦，高于标准体重的10%为过重
    编写程序，让用户输入性别、身高、体重，判断用户的健康状况

    健康状况有3种：

    1) 你的体重正常，请继续保持
    2) 你的身体偏瘦，请加强营养
    3) 你的身体偏胖，请加强锻炼 -->

    <script>
        // standard weight 标准体重
        var height = +prompt("请输入您的身高(cm): "),
            weight = +prompt("请输入您的体重(kg): "),
            gender = prompt("请输入您的性别(男/女)"),
            standardWeight;

        if (isNaN(height) || isNaN(weight) || (gender !== '男' && gender !== '女')) {
            console.log('输入有误');
        } else {
            if (gender === '男') {
                standardWeight = (height - 80) * 0.7;
            } else if (gender === '女') {
                standardWeight = (height - 70) * 0.6;
            }
            if (weight > standardWeight * 1.1) {
                console.log('你的身体偏胖，请加强锻炼');
            } else if (weight < standardWeight * 0.9) {
                console.log('你的身体偏瘦，请加强营养');
            } else {
                console.log('你的体重正常，请继续保持');
            }
        }
    </script>


    <!-- 袁老师版 -->
    <script>
        var height = +prompt("请输入身高(cm)");
        var weight = +prompt("请输入体重(kg)");
        var gender = prompt("请输入性别（男，女）");
        if (isNaN(height) || isNaN(weight) || gender !== "男" && gender !== "女") {
            console.log("输入有误");
        } else {
            var standardWeight; //标准体重
            if (gender === "男") {
                standardWeight = (height - 80) * 0.7;
            } else {
                standardWeight = (height - 70) * 0.6;
            }

            if (weight < standardWeight * 0.9) {
                console.log("你的身体偏瘦，请加强营养");
            } else if (weight > standardWeight * 1.1) {
                console.log("你的身体偏胖，请加强锻炼")
            } else {
                console.log("你的体重正常，请继续保持");
            }
        }
    </script>


    <!-- 4. 某理财公司推出一种理财服务，服务规则如下：
    若用户的理财金额在50万元以下，则每年的收益按照4%计算。
    若用户的理财金额在50万元以上（包括50万），则每年收益按照4.5%计算。
    若用户的理财金额超过200万，除了理财收益外，还要额外给予用户收益金额的10%
    编写程序，让用户输入理财金额和理财年限，计算到期后的收益 -->

    <script>
        var money = +prompt("请输入您的理财金额(万): "),
            year = +prompt("请输入您的理财年限(年): "),
            earnMoney;
        if (isNaN(money) || isNaN(year)) {
            console.log('输入有误');
        } else {
            if (money < 50 && money > 0) {
                earnMoney = Math.ceil(money * 0.04 * year);
                console.log("到期后, 您的收益约为(万): ", earnMoney);
            } else if (money > 50 && money < 200) {
                earnMoney = Math.ceil(money * 0.045 * year);
                console.log("到期后, 您的收益约为(万): ", earnMoney);
            } else {
                earnMoney = Math.ceil((money * 0.045 * year) * 1.1);
                console.log("到期后, 您的收益约为(万): ", earnMoney);
            }
        }
    </script>



    <!-- 袁老师版 -->
    <script>
        var money = +prompt("请输入理财金额");
        var year = +prompt("请输入理财年限");
        if (isNaN(money) || isNaN(year) || money <= 0 || year <= 0) {
            console.log("输入有误");
        } else {
            var rate = 0.04; // 年利率4%
            if (money >= 500000) {
                rate = 0.045;
            }
            var earnMoney = money * rate * year; // 收益
            if (money >= 2000000) {
                earnMoney += earnMoney * 0.1;
            }
            console.log(`总收益为：${earnMoney}`);
        }
    </script>



    <!-- 5. 编写一个用户和计算机猜拳的游戏，用户输入剪刀、石头或布，与计算机的出拳进行比较，判断胜负 -->
    <script>
        var userInput = prompt("请输入(石头/剪刀/布): "),
            ran = Math.random() * 3,
            computer;

        if (ran < 1) {
            computer = "石头";
            if (userInput === "石头") {
                console.log("平局");
            } else if (userInput === "布") {
                console.log("胜");
            } else {
                console.log("负");
            }
        } else if (ran < 2) {
            computer = "剪刀";
            if (userInput === "剪刀") {
                console.log("平局");
            } else if (userInput === "石头") {
                console.log("胜");
            } else {
                console.log("负");
            }
        } else {
            computer = "布";
            if (userInput === "布") {
                console.log("平局");
            } else if (userInput === "剪刀") {
                console.log("胜");
            } else {
                console.log("负");
            }
        }

        console.log("您的出是: " + userInput);
        console.log("计算机出的是: " + computer);
    </script>


    <!-- 袁老师版 -->
    <script>
        var fist = prompt("请出拳（剪刀、石头、布）");
        if (fist === "剪刀" || fist === "石头" || fist === "布") {
            //正确
            //1. 模拟计算机出拳
            var rad = Math.random(); // 0~1
            var pcFist; //计算机出拳结果
            if (rad < 0.333) {
                pcFist = "剪刀";
            } else if (rad < 0.6666) {
                pcFist = "石头";
            } else {
                pcFist = "布";
            }
            //2. 比较胜负
            console.log(`你的出拳：${fist}, 电脑出拳：${pcFist}`);
            if (fist === "剪刀" && pcFist === "布" ||
                fist === "布" && pcFist === "石头" ||
                fist === "石头" && pcFist === "剪刀") {
                console.log("你胜利了！");
            } else if (fist === pcFist) {
                console.log("平局");
            } else {
                console.log("电脑胜利！");
            }
        } else {
            console.log("输入有误")
        }

        // if (fist !== "剪刀" && fist !== "石头" && fist !== "布") {
        //     console.log("输入有误")
        // } else {
        //     //正常
        // }
    </script>
</body>

</html>
```


## 4. switch 开关

switch的语法始终可以使用if结构替代。

```js
switch(表达式){
    case 数据1:
        代码块
    case 数据2:
        代码块
    //...
    default:
        代码块
}
```

```
1. 计算表达式的返回值，依次和case后面的数据进行严格相等的比较，如果某个相等，停止比较，然后运行其内部的代码块，再然后，依次运行之后的所有代码块。
2. 在case分支内部，使用break语句，可以立即停止switch结构。
3. default表示前面的所有case都不匹配时运行。可以省略
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- test.html -->
    <script>
        var x = 20;
        switch (x) {
            case 1:
                console.log("1");
                break;
            case 20:
                console.log("20");
                break;
            case 30:
                console.log("30");
                break;
            default:
                console.log("default");
                break;
        }

        // switch的语法始终可以使用if结构替代。 ==> 开发中很少使用 switch 语句 (甚至有的公司禁止使用)

        // 1. 计算表达式的返回值， 依次和case后面的数据进行严格相等的比较， 如果某个相等， 停止比较， 然后运行其内部的代码块， 再然后， 依次运行之后的所有代码块。
        // 2. 在case分支内部， 使用break语句， 可以立即停止switch结构。
        // 3. default表示前面的所有case都不匹配时运行。 可以省略 ==> 相当于 if-else 里面的 else

        // [补充] JavaScript中的switch语句和其他编程语言的switch语句有蛮大差别的, 传入的参数形式多样
    </script>

</body>

</html>
```

## 5. 循环

重复的运行一段代码

JS支持3种循环结构：while循环、do-while循环、**for循环**

> 在学习 ES6 之前 , 只接触到这三种循环结构

**while循环**

```js
while(条件){
    代码块（循环体）
}
```

![20210226080626](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226080626.png)

```
死循环：条件永远满足，永远无法退出循环。
```

**do-while循环**

```js
do{
    循环体
} while(条件);
```

![20210226080718](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226080718.png)


**for循环**

```js
for(初始化表达式; 条件; 条件改变表达式){
    循环体
}
```

![20210226080746](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226080746.png)


**循环中的关键字**

```
循环控制语句
    break; 跳出循环
    continue; 停止当前循环体，进入下一次循环。
```

### test.html


```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 本节只介绍循环结构的语法知识 重难点在于循环的实际应用[下一小节讲解] -->


    <!-- 输出100个hello world -->

    <!-- test1.html -->
    <script>
        var i = 0; //当前输出的次数，初始化
        while (i < 100) {
            console.log("hello world");
            i++;
        }
    </script>

    <script>
        for (var i = 0; i < 100; i++) {
            console.log("hello world");
        }

        console.log("循环结束", i);
    </script>

    <!-- test2.html -->
    <script>
        var i = 0; //当前输出的次数
        do {
            console.log("hello world");
            i++;
        } while (i < 100);
        console.log("循环结束");
    </script>


    <!-- test3.html -->

    <!-- 输出 100-1 的所有数字 -->
    <script>
        for (var i = 1; i <= 100; i++) {
            // 在循环体中，i的值从1变化到100
            console.log(i);
        }
    </script>

    <script>
        for (var i = 100; i >= 1; i--) {
            console.log(i);
        }
    </script>

    <!-- 输出 1-100 的所有奇数 - 1 -->
    <script>
        for (var i = 1; i <= 100; i++) {
            // 判断i是不是奇数
            if (i % 2 !== 0) {
                console.log(i);
            }
        }
    </script>

    <!-- 输出 1-100 的所有奇数 - 2 -->
    <script>
        for (var i = 1; i <= 100; i += 2) {
            console.log(i);
        }
    </script>

    <!-- 循环控制语句中的关键字

    break ==> 跳出循环
    continue ==> 停止当前循环体，进入下一次循环。 -->

    <!-- test4.html -->

    <script>
        var i = 0;
        while (i < 10) {
            if (i === 3) {
                i++;
                break; // 跳出循环
            }
            console.log(i); // 打印整数 0 1 2
            i++;
        }
    </script>

    <script>
        for (var i = 0; i < 10; i++) {
            if (i === 3) {
                break; // 跳出循环
            }
            console.log(i); // 打印整数 0 1 2
        }
    </script>

    <script>
        var i = 0;
        while (i < 10) {
            if (i === 3) {
                i++;
                continue; // 停止当前循环体，进入下一次循环 ==> 一旦执行 continue 那么本轮循环不会再执行后续代码
            }
            console.log(i); // 打印整数 0 ~ 9 (不包括3)
            i++;
        }
    </script>

    <script>
        for (var i = 0; i < 10; i++) {
            if (i === 3) {
                continue; // 停止当前循环体，进入下一次循环 ==> 一旦执行 continue 那么本轮循环不会再执行后续代码
            }
            console.log(i); // 打印整数 0 ~ 9 (不包括3)
        }
    </script>

    <script>
        for (var i = 0; i < 3; i++) {
            for (var j = 0; j < 3; j++) {
                console.log(i, j);
                if (i + j >= 2) {
                    break;
                }
            }
        }
    </script>


</body>

</html>
```

## 6. 循环应用

**累计**

```
举例：将1-100的所有数字相加之和
思路：准备一个变量，初始值为0，然后1-100循环，每次循环，将数字累加到变量中。
```

**查找**

```
举例：135~145之间是否存在能整除26的数字
思路：准备一个变量，记录false，表示没有找到，然后135-145进行循环，如果发现满足条件的数字，重新记录变量为true，表示找到了，然后退出循环。
```

**嵌套的循环**

```
分开分析两层循环
```

### test.html


```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 累计.html -->
    <!-- 1-100 数字相加 -->
    <script>
        var sum = 0; //最终的和
        for (var i = 1; i <= 100; i++) {
            sum += i;
        }
        console.log(sum); // 5050
    </script>

    <!-- 1-10 数字相乘 -->
    <script>
        var sum = 1;
        for (var i = 1; i <= 10; i++) {
            sum *= i;
        }
        console.log(sum); // 3628800
    </script>

    <!-- 1-100 所有奇数相加 -->
    <script>
        var sum = 0;
        for (var i = 1; i <= 100; i++) {
            if (i % 2 !== 0) {
                sum += i;
            }
        }
        console.log(sum); // 2500
    </script>


    <!-- 查找.html -->

    <!-- 135-145 之间是否存在 能整除26的数字 -->
    <script>
        // 注意这种编程思想 不要把打印语句写在循环体内部 可以先定义一个变量 来记录状态
        var isFind = false; // 是否找到
        var min = 135,
            max = 145;
        for (var i = min; i <= max; i++) {
            if (i % 26 === 0) {
                isFind = true;
                break;
            }
        }
        if (isFind) {
            console.log("存在");
        } else {
            console.log("不存在");
        }
    </script>

    <!-- 打印135-185之间所有能整除26的数字 -->
    <script>
        for (var i = 135; i <= 185; i++) {
            if (i % 26 === 0) {
                console.log(i);
            }
        }
    </script>

    <!-- 打印135-185之间第一个能整除26的数字，如果不存在，输出不存在 -->
    <script>
        var isFind = false;
        for (var i = 135; i <= 185; i++) {
            if (i % 26 === 0) {
                console.log(i);
                isFind = true;
                break;
            }
        }
        if (!isFind) {
            console.log("不存在");
        }
    </script>

    <!--
        判断一个数是不是素数（质数）
        素数：一个大于1的整数，只能被1和自身整除
        比如：2是一个素数
        比如：4不是一个素数
        思路：从1循环到这个数，记录有多少个数字能整除它
     -->
    <!-- 法1 -->
    <script>
        var num = 11;
        var record = 0; //记录整除数量
        for (var i = 1; i <= num; i++) {
            if (num % i === 0) {
                record++;
            }
        }
        if (record === 2) {
            console.log("是素数")
        } else {
            console.log("不是素数");
        }
    </script>

    <!-- 法2 -->
    <script>
        var num = 11;
        var isFind = false; // 没有找到
        for (var i = 2; i < num - 1; i++) { // 这里应该写 i <= num - 1 不过写成 < 也不影响结果...
            if (num % i === 0) {
                isFind = true;
                break;
            }
        }
        if (num <= 1 || isFind) {
            console.log("不是素数");
        } else {
            console.log("是素数");
        }
    </script>


    <!-- 嵌套的循环.html -->
    <!-- 打印1-100的所有素数 -->
    <script>
        for (var i = 1; i <= 100; i++) {
            // 判断i是不是素数
            var isFind = false; //没有找到 (从2到i-1 没有找到任何一个数能被i整除)
            for (var j = 2; j < i - 1; j++) {
                if (i % j === 0) {
                    isFind = true;
                    break;
                }
            }
            if (i > 1 && !isFind) {
                console.log(i);
            }
        }
    </script>
</body>

</html>
```

## 7. [作业讲解]循环应用

**作业**

- [ ] 1. 在控制台中输出100个*

```js
for (var i = 0; i < 100; i++) {
    console.log("*");
}
```

- [ ] 2. 让用户输入*号的数量，然后输出对应数量的*

```js
var num = +prompt("请输入*的数量");
for (var i = 0; i < num; i++) {
    console.log("*");
}
```

- [ ] 3. 输出一个3行5列的*号

```js
var r = 3,
    c = 5;
for (var i = 0; i < r; i++) {
    //循环r次
    //在一行内输出c个*号
    var str = "";
    for (var j = 0; j < c; j++) {
        str += "*";
    }
    console.log(str);
}
```

- [ ] 4. 用*号输出一个5行的直角三角形

```
*
**
***
****
*****
```

```js
var r = 15;
for (var i = 1; i <= r; i++) {
    //输出一行星号，数量为i
    var str = "";
    for (var j = 0; j < i; j++) {
        str += "*";
    }
    console.log(str);
}
```

- [ ] 5. 用*号输出一个5行的等腰三角形

```
    *
   ***
  *****
 *******
*********
```

```js
var r = 15;
for (var i = 1; i <= r; i++) {
    // 输出1行
    var str = "";
    // 1. 拼接空格，数量为r-i
    for (var j = 0; j < r - i; j++) {
        str += " ";
    }
    // 2. 拼接星号，数量为2*i-1
    for (var j = 0; j < 2 * i - 1; j++) {
        str += "*";
    }
    console.log(str);
}
```

- [ ] 6. 输出1-100的所有数字

```js
for (var i = 0; i < 100; i++) {
    console.log(i + 1);
}
```

- [ ] 7. 输出1-100的所有奇数

```js
for (var i = 1; i < 100; i += 2) {
    console.log(i);
}
```

- [ ] 8. 求1-100之间所有数字之和

```js
var sum = 0;
for (var i = 1; i <= 100; i++) {
    sum += i;
}
console.log(sum); // 5050
```

- [ ] 9. 求1-100之间所有奇数之和

```js
var sum = 0;
for (var i = 1; i <= 100; i++) {
    if (i % 2 !== 0) {
        sum += i;
    }
}
console.log(sum); // 2500
```

- [ ] 10. 求1-10之间所有数字的积

```js
var sum = 1;
for (var i = 1; i <= 10; i++) {
    sum *= i;
}
console.log(sum); // 3628800
```

- [ ] 11. 判断数字233是不是素数。

素数是指一个数（大于1）仅能被1和自身整除

`题目改成: 改成 判断 1-233 哪些数是素数`

```js
var num = 233;
var isFind = false;
for (var i = 2; i <= num - 1; i++) {
    if (num % i === 0) {
        isFind = true;
        break;
    }
}
if (num <= 1 || isFind) {
    console.log(`${num} 不是一个素数`);
} else {
    console.log(`${num} 是一个素数`);
}
```

- [ ] 12. 输出1-100中的所有素数

```js
for (var j = 1; j <= 100; j++) {
    var isFind = false;
    for (var i = 2; i <= j - 1; i++) {
        if (j % i === 0) {
            isFind = true;
            break;
        }
    }
    if (j <= 1 || isFind) {
        continue;
        // console.log(`${j} 不是一个素数`);
    } else {
        console.log(`${j} 是一个素数`);
    }
}
```

- [ ] 13. 求1-100之间的所有素数之和

```js
var sum = 0; //记录和
for (var i = 2; i <= 100; i++) {
    //i是不是素数
    var isFind = false; // 默认没有找到能被1和自身整数的其余的除数 是素数
    for (var j = 2; j < i - 1; j++) {
        if (i % j === 0) {
            isFind = true; // 找到能被1和自身整数的其余的除数 不是素数
            break;
        }
    }
    if (!isFind) {
        sum += i;
    }
}

console.log(sum);
```

- [ ] 14. 输出99乘法表，效果如下：

```
1*1=1
1*2=2	2*2=4
1*3=3	2*3=6	3*3=9
1*4=4	2*4=8	3*4=12	4*4=16
1*5=5	2*5=10	3*5=15	4*5=20	5*5=25
1*6=6	2*6=12	3*6=18	4*6=24	5*6=30	6*6=36
1*7=7	2*7=14	3*7=21	4*7=28	5*7=35	6*7=42	7*7=49
1*8=8	2*8=16	3*8=24	4*8=32	5*8=40	6*8=48	7*8=56	8*8=64
1*9=9	2*9=18	3*9=27	4*9=36	5*9=45	6*9=54	7*9=63	8*9=72	9*9=81
```

```js
for (var i = 1; i <= 9; i++) {
    // 输出1行
    // 拼接i个等式
    var str = "";
    for (var j = 1; j <= i; j++) {
        str += `${j}*${i}=${i*j}\t`;
    }
    console.log(str);
}
```

- [ ] 15. 将猜拳游戏升级，记录系统和玩家的积分，获胜者加1分，平局和输者不计分

可参考以下效果：

```
游戏开始
==============第1轮==============
系统：0分，玩家：0分
你的出拳：剪刀
系统出拳：布
你赢了！
==============第2轮==============
系统：0分，玩家：1分
你的出拳：石头
系统出拳：布
你输了！
==============游戏结束==============
系统：1分，玩家：1分
```

```js
console.log("游戏开始");
var round = 1, //轮次
    pcScore = 0, //系统分数
    playerScore = 0; //玩家分数
while (true) {
    // 1轮游戏
    console.log(`==============第${round}轮==============`);
    console.log(`系统：${pcScore}分，玩家：${playerScore}分`);
    var fist = prompt("请出拳（剪刀、石头、布）");
    if (fist === null) {
        //取消
        break;
    }
    //没有取消
    if (fist !== "剪刀" && fist !== "石头" && fist !== "布") {
        //出拳无效
        console.log("出拳无效，请重新出拳！");
        continue;
    }
    //出拳有效
    console.log(`你的出拳：${fist}`);
    var pcFist = Math.random(); //系统随机出拳
    if (pcFist < 0.3333) {
        pcFist = "剪刀";
    } else if (pcFist < 0.6666) {
        pcFist = "石头";
    } else {
        pcFist = "布";
    }
    console.log(`系统出拳：${pcFist}`);
    //判断胜负
    if (fist === "剪刀" && pcFist === "布" ||
        fist === "布" && pcFist === "石头" ||
        fist === "石头" && pcFist === "剪刀") {
        //玩家胜利
        playerScore++;
        console.log("你赢了！");
    } else if (fist === pcFist) {
        console.log("平局");
    } else {
        pcScore++;
        console.log("系统胜利！");
    }
    //轮次+1
    round++;
}

console.log("==============游戏结束==============");
console.log(`系统：${pcScore}分，玩家：${playerScore}分`);
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 1. 在控制台中输出100个* -->
    <script>
        for (var i = 0; i < 100; i++) {
            console.log("*");
        }
    </script>

    <!-- 2. 让用户输入*号的数量，然后输出对应数量的* -->
    <script>
        var num = +prompt("请输入*的数量");
        for (var i = 0; i < num; i++) {
            console.log("*");
        }
    </script>

    <!-- 3. 输出一个3行5列的*号 -->
    <script>
        var r = 3,
            c = 5;
        for (var i = 0; i < r; i++) {
            //循环r次
            //在一行内输出c个*号
            var str = "";
            for (var j = 0; j < c; j++) {
                str += "*";
            }
            console.log(str);
        }
    </script>

    <!-- 4. 用*号输出一个5行的直角三角形


    *
    **
    ***
    ****
    *****
    -->
    <script>
        var r = 15;
        for (var i = 1; i <= r; i++) {
            //输出一行星号，数量为i
            var str = "";
            for (var j = 0; j < i; j++) {
                str += "*";
            }
            console.log(str);
        }
    </script>

    <!-- 5. 用*号输出一个5行的等腰三角形


        *
       ***
      *****
     *******
    *********
     -->
    <script>
        var r = 15;
        for (var i = 1; i <= r; i++) {
            // 输出1行
            var str = "";
            // 1. 拼接空格，数量为r-i
            for (var j = 0; j < r - i; j++) {
                str += " ";
            }
            // 2. 拼接星号，数量为2*i-1
            for (var j = 0; j < 2 * i - 1; j++) {
                str += "*";
            }
            console.log(str);
        }
    </script>

    <!-- 6. 输出1-100的所有数字 -->
    <script>
        for (var i = 0; i < 100; i++) {
            console.log(i + 1);
        }
    </script>

    <!-- 7. 输出1-100的所有奇数 -->
    <script>
        for (var i = 1; i < 100; i += 2) {
            console.log(i);
        }
    </script>

    <!-- 8. 求1-100之间所有数字之和 -->
    <script>
        var sum = 0;
        for (var i = 1; i <= 100; i++) {
            sum += i;
        }
        console.log(sum); // 5050
    </script>


    <!-- 9. 求1-100之间所有奇数之和 -->
    <script>
        var sum = 0;
        for (var i = 1; i <= 100; i++) {
            if (i % 2 !== 0) {
                sum += i;
            }
        }
        console.log(sum); // 2500
    </script>

    <!-- 10. 求1-10之间所有数字的积 -->
    <script>
        var sum = 1;
        for (var i = 1; i <= 10; i++) {
            sum *= i;
        }
        console.log(sum); // 3628800
    </script>

    <!-- 11. 判断数字233是不是素数。

    素数是指一个数（大于1）仅能被1和自身整除 -->
    <script>
        var num = 233;
        var isFind = false;
        for (var i = 2; i <= num - 1; i++) {
            if (num % i === 0) {
                isFind = true;
                break;
            }
        }
        if (num <= 1 || isFind) {
            console.log(`${num} 不是一个素数`);
        } else {
            console.log(`${num} 是一个素数`);
        }
    </script>

    <!-- 12. 输出1-100中的所有素数 -->
    <script>
        for (var j = 1; j <= 100; j++) {
            var isFind = false;
            for (var i = 2; i <= j - 1; i++) {
                if (j % i === 0) {
                    isFind = true;
                    break;
                }
            }
            if (j <= 1 || isFind) {
                continue;
                // console.log(`${j} 不是一个素数`);
            } else {
                console.log(`${j} 是一个素数`);
            }
        }
    </script>

    <!-- 13. 求1-100之间的所有素数之和 -->
    <script>
        var sum = 0; //记录和
        for (var i = 2; i <= 100; i++) {
            //i是不是素数
            var isFind = false;
            for (var j = 2; j < i - 1; j++) {
                if (i % j === 0) {
                    isFind = true;
                    break;
                }
            }
            if (!isFind) {
                sum += i;
            }
        }

        console.log(sum);
    </script>

    <!-- 14. 输出99乘法表，效果如下：


    1*1=1
    1*2=2 2*2=4
    1*3=3 2*3=6 3*3=9
    1*4=4 2*4=8 3*4=12 4*4=16
    1*5=5 2*5=10 3*5=15 4*5=20 5*5=25
    1*6=6 2*6=12 3*6=18 4*6=24 5*6=30 6*6=36
    1*7=7 2*7=14 3*7=21 4*7=28 5*7=35 6*7=42 7*7=49
    1*8=8 2*8=16 3*8=24 4*8=32 5*8=40 6*8=48 7*8=56 8*8=64
    1*9=9 2*9=18 3*9=27 4*9=36 5*9=45 6*9=54 7*9=63 8*9=72 9*9=81
    -->
    <script>
        for (var i = 1; i <= 9; i++) {
            // 输出1行
            //拼接i个等式
            var str = "";
            for (var j = 1; j <= i; j++) {
                str += `${j}*${i}=${i*j}\t`;
            }
            console.log(str);
        }
    </script>

    <!-- 15. 将猜拳游戏升级，记录系统和玩家的积分，获胜者加1分，平局和输者不计分

    可参考以下效果：


    游戏开始
    ==============第1轮==============
    系统：0分，玩家：0分
    你的出拳：剪刀
    系统出拳：布
    你赢了！
    ==============第2轮==============
    系统：0分，玩家：1分
    你的出拳：石头
    系统出拳：布
    你输了！
    ==============游戏结束==============
    系统：1分，玩家：1分
    -->
    <script>
        console.log("游戏开始");
        var round = 1, //轮次
            pcScore = 0, //系统分数
            playerScore = 0; //玩家分数
        while (true) {
            // 1轮游戏
            console.log(`==============第${round}轮==============`);
            console.log(`系统：${pcScore}分，玩家：${playerScore}分`);
            var fist = prompt("请出拳（剪刀、石头、布）");
            if (fist === null) {
                //取消
                break;
            }
            //没有取消
            if (fist !== "剪刀" && fist !== "石头" && fist !== "布") {
                //出拳无效
                console.log("出拳无效，请重新出拳！");
                continue;
            }
            //出拳有效
            console.log(`你的出拳：${fist}`);
            var pcFist = Math.random(); //系统随机出拳
            if (pcFist < 0.3333) {
                pcFist = "剪刀";
            } else if (pcFist < 0.6666) {
                pcFist = "石头";
            } else {
                pcFist = "布";
            }
            console.log(`系统出拳：${pcFist}`);
            //判断胜负
            if (fist === "剪刀" && pcFist === "布" ||
                fist === "布" && pcFist === "石头" ||
                fist === "石头" && pcFist === "剪刀") {
                //玩家胜利
                playerScore++;
                console.log("你赢了！");
            } else if (fist === pcFist) {
                console.log("平局");
            } else {
                pcScore++;
                console.log("系统胜利！");
            }
            //轮次+1
            round++;
        }

        console.log("==============游戏结束==============");
        console.log(`系统：${pcScore}分，玩家：${playerScore}分`);
    </script>

</body>

</html>
```

## 8. 数组

`数组用于存放多个数据`

**创建一个数组**

```
1. new Array(长度)
    长度: 数组里面的数据总数，长度一定是一个非负整数
        new Array(数据, 数据, 数据....)
        创建一个数组，并初始化其每一项的值
    数组项: 数组其中的一项数据

2. [数据,数据,数据,....]
    创建一个数据，并初始化其每一项的值
```

**认识数组的本质**

```
数组的本质是一个对象
   - length属性：数组的长度，会自动变化，值为最大下标+1
   - 数字字符串属性：叫做下标，也叫做索引，相当于数组中每个数据的编号，下标从0开始排列
连续下标的取值范围：0 ~ length -1，如果给length直接赋值，会导致数组可能被截断
实际开发中，不要给length赋值。
```

**下标**

```
通常情况下，下标是连续的。
下标不连续的数组，叫做稀松数组。(讲稀松数组 , 主要是为了面试)
```

**数组的常见操作**

```
1. 添加数组项
   - 数组[长度] = 数据：向数组末尾添加一个数据
   - 数组.push(数据): 向数组末尾添加一个数据
   - 数组.unshift(数据)：向数组起始位置添加一个数据，会导致数组每一项的下标向后移动
   - 数组.splice(下标, 0, 添加的数据): 从指定下标位置开始，删除0个，然后在该位置插入添加的数据，如果下标超过范围，则按照范围的边界进行处理。
   PS: push、unshift、splice 也可以添加多个数据

2. 删除数据
   - delete 数组[下标]: 这种做法不会导致数组其他的属性发生变化，因此，该做法会导致产生稀松数组，所以不推荐使用该做法。
   - 数组.pop(): 删除数组的最后一项，该表达式返回最后一项的数据(若数组本身是空 , 那么返回的是 `undefined`)
   - 数组.shift()：删除数组第一项，该表达式返回第一项的数据(若数组本身是空 , 那么返回的是 `undefined`)
   - 数组.splice(下标, 删除的数量, 添加的数据): 从指定下标位置开始，删除指定数量，然后在该位置插入添加的数据，如果下标超过范围，则按照范围的边界进行处理。返回一个新数组，该数组记录被删除的数据。

3. 其他操作
   - 数组.slice(起始位置下标, 结束位置下标)：将起始位置到结束位置之间的数据拿出来，得到一个新的数组，该函数不会改变原数组；注意：结束下标取不到
     下标可以写负数，如果是负数，则从数组的末尾开始计算。
     如果不写结束下标，则直接取到末尾。
   - 数组清空
     数组.splice(0, 数组.length);
     数组.length = 0;
   - 查找数组中某一项的下标
     数组.indexOf(数据)
     从数组中依次查找对应的数据，查找时使用严格相等进行比较。找到第一个匹配的下标，返回。如果没有找到，则得到-1；
     数组.lastIndexOf(数据)
     功能和indexOf类似，只是查找的是最后一个匹配的下标
   - 数组.fill
     数组.fill(数据)：将数组的所有项，填充为指定的数据
     数组.fill(数组, 开始下标): 将数组从开始下标起，到数组的末尾，填充为指定的数据
     数组.fill(数组, 开始下标，结束下标): 将数组从开始下标起，到数组的结束下标（取不到），填充为指定的数据
```

**语法补充**

```
1. in关键字
   判断某个属性在对象中是否存在
   属性名 in 对象

2. for-in  foreach 循环
   for(var prop in 对象){
       //循环体
   }
   取出对象的所有属性名，每次循环将其中一个属性名赋值给变量prop，运行循环体。
```

### test.html


```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 数组这一章节实际上并不属于流程控制的知识点
        不过由于JavaScript中的数组比较好理解 所以就提到这里讲了 -->


    <!-- test1.html -->
    <script>
        var arr = new Array(20);
        console.log(arr); // (20) [empty × 20]
    </script>

    <script>
        var arr = new Array(1, 5, 354, 234, 11);
        console.log(arr); // (5) [1, 5, 354, 234, 11]
    </script>

    <script>
        var arr = [1, 5, 354, 234, 11];
        console.log(arr); // (5) [1, 5, 354, 234, 11]
    </script>

    <script>
        var arr = [34, "asdf", true, null, undefined, {
            x: 1,
            y: 34
        }];
        console.log(typeof arr); // "object" 数组的本质就是对象
        console.log(arr.length); // 6
        // 得到数组第1项数据
        console.log(arr[0]); // 34
        // 得到数组第6项数据
        console.log(arr[5].x); // 1
    </script>

    <!-- 面试题 -->
    <script>
        var arr = [3, 6, 23, 4];
        arr[0] = 10; // 0 会自动转换为 "0"
        arr["0"] = 5;
        console.log(arr[0], arr["0"]); // 5 5
    </script>

    <script>
        var arr = [3, 6, 23, 4, 66, 232, 44];
        console.log(arr); // (7) [3, 6, 23, 4, 66, 232, 44]

        // 可以给数组加属性 [不影响索引值]
        arr.abc = "asdfasdfsadf";
        console.log(arr); // (7) [3, 6, 23, 4, 66, 232, 44, abc: "asdfasdfsadf"]

        // 可以给数组加索引
        arr[7] = 333; // 给数组的第8项赋值 333
        console.log(arr); // (8) [3, 6, 23, 4, 66, 232, 44, 333, abc: "asdfasdfsadf"]
    </script>

    <!-- ## 认识数组的本质

    数组的本质是一个对象

    - length属性：数组的长度，会自动变化，值为最大下标+1
    - 数字字符串属性：叫做下标，也叫做索引，相当于数组中每个数据的编号，下标从0开始排列


    连续下标的取值范围：0 ~ length -1，如果给length直接赋值，会导致数组可能被截断

    实际开发中，不要给length赋值。 -->

    <!-- test2.html -->
    <script>
        var obj = {
            "0": "asdfasdf",
            "1": "asdfasfsdgfffd",
            length: 2
        };

        console.log(obj); // {0: "asdfasdf", 1: "asdfasfsdgfffd", length: 2}
        // console.log(obj.0); // 0不是合法的标识符
        console.log(obj["0"]); // "asdfasdf" 属性表达式
        console.log(obj[0]); // "asdfasdf" 0 ==> "0"
    </script>

    <!-- ## 下标

    通常情况下，下标是连续的。

    下标不连续的数组，叫做稀松数组。 -->

    <!-- test3.html -->
    <script>
        var arr = [3, 6, 7, 82, 2, 1];
        arr[10] = "abc"; // 稀松数组 不存在下标为 6 ~ 10 的数组成员
        console.log(arr); // (11) [3, 6, 7, 82, 2, 1, empty × 4, "abc"]
    </script>

    <script>
        var arr = [, , , "abc"]; // 稀松数组 不存在下标为 0 1 2 的数组成员 [不存在 ≠ undefined]
        console.log(arr); // (4) [empty × 3, "abc"]
    </script>

    <script>
        var arr = new Array(100); // 稀松数组 下标为 0 ~ 99 的数组成员
        console.log(arr); // (100) [empty × 100]
    </script>

    <!-- ## 数组的常见操作 -->

    <!-- ### 添加数组项

    - 数组[长度] = 数据：向数组末尾添加一个数据
    - 数组.push(数据): 向数组末尾添加一个数据
    - 数组.unshift(数据)：向数组起始位置添加一个数据，会导致数组每一项的下标向后移动
    - 数组.splice(下标, 0, 添加的数据): 从指定下标位置开始，删除0个，然后在该位置插入添加的数据，如果下标超过范围，则按照范围的边界进行处理。

    push、unshift、splice一次可以添加多个数据 -->

    <!-- test4.html -->
    <script>
        var arr = [1, 2, 3, 4];
        // 数组[长度] = 数据：向数组末尾添加一个数据
        arr[arr.length] = "afasf"; // 向末尾添加一项 [不建议的写法]arr[4] = "afasf"; // 这样就写死了
        arr[arr.length] = "afasf1"; // 向末尾添加一项
        arr[arr.length] = "afasf2"; // 向末尾添加一项
        arr[arr.length] = "afasf3"; // 向末尾添加一项

        console.log(arr); // (8) [1, 2, 3, 4, "afasf", "afasf1", "afasf2", "afasf3"]
    </script>

    <script>
        var arr = [1, 2, 3, 4];
        // 数组.push(数据): 向数组末尾添加一个数据数组.push(数据): 向数组末尾添加一个数据
        arr.push("abc", "bcd"); // 一次可以添加多个数据
        arr.push("bcd");
        arr.push({
            name: "Adsf",
            age: 18
        });
        console.log(arr); // (8) [1, 2, 3, 4, "abc", "bcd", "bcd", {…}]
    </script>

    <script>
        var arr = [1, 2, 3, 4];
        // 数组.unshift(数据)：向数组起始位置添加一个数据，会导致数组每一项的下标向后移动
        arr.unshift(1, 2, 3); // 一次可以添加多个数据
        console.log(arr); // (7) [1, 2, 3, 1, 2, 3, 4]
    </script>

    <script>
        var arr = [1, 2, 3, 4];
        arr.splice(2, 0, "abc", "bcd"); // 使用splice加数据
        console.log(arr); // (6) [1, 2, "abc", "bcd", 3, 4]
        arr.splice(100, 0, "AAA", "BBB"); // 下标越界的情况 ==> 直接在末尾添加数据 类似于 push
        console.log(arr); // (8) [1, 2, "abc", "bcd", 3, 4, "AAA", "BBB"] ==> 不会生成稀松数组
    </script>

    <!-- ### 删除数据

    - delete 数组[下标]: 这种做法不会导致数组其他的属性发生变化，因此，该做法会导致产生稀松数组，所以不推荐使用该做法。
    - 数组.pop(): 删除数组的最后一项，该表达式返回最后一项的数据
    - 数组.shift()：删除数组第一项，该表达式返回第一项的数据
    - 数组.splice(下标, 删除的数量, 添加的数据): 从指定下标位置开始，删除指定数量，然后在该位置插入添加的数据，
    如果下标超过范围，则按照范围的边界进行处理。返回一个新数组，该数组记录被删除的数据。 -->
    <!-- test5.html -->
    <script>
        var arr = [1, 2, 3, 4];
        // delete 数组[下标]: 这种做法不会导致数组其他的属性发生变化，因此，该做法会导致产生稀松数组，所以不推荐使用该做法。
        delete arr[3];
        console.log(arr); // (4) [1, 2, 3, empty]
    </script>

    <script>
        var arr = ['a', 'b', 'c', 'd'];
        // 数组.pop(): 删除数组的最后一项，该表达式返回最后一项的数据
        var n = arr.pop();
        console.log(arr); // (3) ["a", "b", "c"]
        console.log(n); // "d"
    </script>

    <script>
        var arr = ['a', 'b', 'c', 'd'];
        // 数组.shift()：删除数组第一项，该表达式返回第一项的数据
        var n = arr.shift();
        console.log(arr); // (3) ["b", "c", "d"]
        console.log(n); // "a"
    </script>

    <script>
        var arr = ['a', 'b', 'c', 'd'];
        // 数组.splice(下标, 删除的数量, 添加的数据): 从指定下标位置开始，删除指定数量，然后在该位置插入添加的数据，
        // 如果下标超过范围，则按照范围的边界进行处理。返回一个新数组，该数组记录被删除的数据。
        var n = arr.splice(1, 2);
        console.log(arr, n); // (2) ["a", "d"] (2) ["b", "c"]
    </script>

    <script>
        var arr = ['a', 'b', 'c', 'd'];
        // 数组.splice(下标, 删除的数量, 添加的数据): 从指定下标位置开始，删除指定数量，然后在该位置插入添加的数据，
        // 如果下标超过范围，则按照范围的边界进行处理。返回一个新数组，该数组记录被删除的数据。
        var n = arr.splice(1, 1000); // 等效于: arr.splice(1, arr.length - 1)
        console.log(arr, n); // ["a"] (3) ["b", "c", "d"]
    </script>

    <!-- ### 其他操作

    - 数组.slice(起始位置下标, 结束位置下标)：将起始位置到结束位置之间的数据拿出来，得到一个新的数组，该函数不会改变原数组；注意：结束下标取不到

    下标可以写负数，如果是负数，则从数组的末尾开始计算。

    如果不写结束下标，则直接取到末尾。

    - 数组清空

    数组.splice(0, 数组.length);

    数组.length = 0;

    - 查找数组中某一项的下标

    数组.indexOf(数据)

    从数组中依次查找对应的数据，查找时使用严格相等进行比较。找到第一个匹配的下标，返回。如果没有找到，则得到-1；

    数组.lastIndexOf(数据)

    功能和indexOf类似，只是查找的是最后一个匹配的下标

    - 数组.fill

    数组.fill(数据)：将数组的所有项，填充为指定的数据

    数组.fill(数组, 开始下标): 将数组从开始下标起，到数组的末尾，填充为指定的数据

    数组.fill(数组, 开始下标，结束下标): 将数组从开始下标起，到数组的结束下标（取不到），填充为指定的数据 -->

    <!-- test6.html -->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        // 数组.slice(起始位置下标, 结束位置下标)：将起始位置到结束位置之间的数据拿出来，得到一个新的数组，该函数不会改变原数组；注意：结束下标取不到
        var newArr = arr.slice(3, 6); // slice 是复制操作 splice 是剪切操作
        console.log(newArr, arr); // (3) [4, 5, 6] (7) [1, 2, 3, 4, 5, 6, 7]
    </script>

    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        var newArr = arr.splice(3, 3); // slice 是复制操作 splice 是剪切操作
        console.log(newArr, arr); // (3) [4, 5, 6] (4) [1, 2, 3, 7]
    </script>

    <!-- slice() -->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        var newArr = arr.slice(-4, -1); // 从倒数第4个复制到倒数第1个(不包括)[注意:只能从左到右]
        console.log(newArr, arr); // (3) [4, 5, 6] (7) [1, 2, 3, 4, 5, 6, 7]
    </script>

    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        var newArr = arr.slice(-4, 0); // 取到的 newArr 是一个空数组 啥也没有 因为不能从右向左取
        console.log(newArr, arr); // [] (7) [1, 2, 3, 4, 5, 6, 7]
    </script>

    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        var newArr = arr.slice(-4, arr.length); // 放一个不存在的下标 直接取到最后一个成员
        console.log(newArr, arr); // (4) [4, 5, 6, 7] (7) [1, 2, 3, 4, 5, 6, 7]
    </script>

    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        var newArr = arr.slice(-4); // 如果不写结束下标，则直接取到末尾。 结果同上
        console.log(newArr, arr); // (4) [4, 5, 6, 7] (7) [1, 2, 3, 4, 5, 6, 7]
    </script>


    <!-- splice() -->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        var newArr = arr.splice(-4, 3); // slice 是复制操作 splice 是剪切操作
        console.log(newArr, arr); // (3) [4, 5, 6] (4) [1, 2, 3, 7]
    </script>

    <!-- 数组清空 ==> 数组.splice(0, 数组.length);-->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        arr.splice(0, arr.length);
        console.log(arr); // []
    </script>

    <!-- 数组清空 ==> 数组.length = 0;-->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7];
        arr.length = 0;
        console.log(arr); // []
    </script>


    <!-- test7.html -->
    <!-- indexOf() -->
    <script>
        var arr = [1, 2, 3, 4, 3, 6, 3];
        var index1 = arr.indexOf(3);
        console.log(arr, index1); // (7) [1, 2, 3, 4, 3, 6, 3] 2
        var index2 = arr.indexOf("3");
        console.log(arr, index2); // (7) [1, 2, 3, 4, 3, 6, 3] -1
    </script>

    <!-- lastIndexOf() -->
    <script>
        var arr = [1, 2, 3, 4, 3, 6, 3];
        // 数组.lastIndexOf(数据)
        // 功能和indexOf类似， 只是查找的是最后一个匹配的下标
        var index = arr.lastIndexOf(3);
        console.log(arr, index); // (7) [1, 2, 3, 4, 3, 6, 3] 6
    </script>

    <!--
    数组.fill
    数组.fill(数据)： 将数组的所有项， 填充为指定的数据
    数组.fill(数组, 开始下标): 将数组从开始下标起， 到数组的末尾， 填充为指定的数据
    数组.fill(数组, 开始下标， 结束下标): 将数组从开始下标起， 到数组的结束下标（ 取不到）， 填充为指定的数据
    -->

    <!-- test8.html -->
    <!-- fill() -->
    <script>
        var arr = new Array(5);
        arr.fill("abc");
        console.log(arr); // (5) ["abc", "abc", "abc", "abc", "abc"]
    </script>

    <!-- ## 语法补充 -->

    <!-- ### in关键字

    判断某个属性在对象中是否存在

    属性名 in 对象

    [注意: 属性名是string类型]
    -->

    <!-- in关键字.html -->
    <script>
        var obj = {
            a: 1,
            b: 324,
            c: "asdfas"
        };
        console.log("a" in obj); // true
    </script>

    <!-- 面试题 -->
    <script>
        var arr = [23, 65, 7, 7];
        console.log(arr); // (4) [23, 65, 7, 7]
        console.log(23 in arr); // false
        // 注意: in关键字判断的是一个属性名是否存在 数组本质上是一个对象 在这个数组中 存在的属性名有:
        // 0
        // 1
        // 2
        // 3
        // length
        // __proto__
    </script>


    <!-- ### for-in foreach 循环

        for(var prop in 对象){
        //循环体
        }

    取出对象的所有属性名，每次循环将其中一个属性名赋值给变量prop，运行循环体。 -->

    <!-- forin循环.html -->
    <script>
        var obj = {
            a: 1,
            b: 32,
            c: "asd"
        };
        // 取出对象的所有属性名，每次循环将其中一个属性名赋值给变量prop，运行循环体。
        for (var prop in obj) {
            console.log(prop); // "a" "b" "c"
        }
        // 输入 forin 可以快速生成模板
    </script>

    <!-- 面试题 ==> for 和 forin 的区别? ==> 答: 最大的区别就是遍历稀松数组 -->

    <!-- for -->
    <script>
        var arr = ["abc", "bcd", "234", , , , 54, 2, 1];
        console.log(arr); // (9) ["abc", "bcd", "234", empty × 3, 54, 2, 1]

        var newArr = [];
        // 稀松数组 ==> for ==> 不会忽略不存在的成员
        for (var i = 0; i < arr.length; i++) {
            newArr.push(arr[i]);
        }

        console.log(newArr); // (9) ["abc", "bcd", "234", undefined, undefined, undefined, 54, 2, 1]
    </script>

    <!-- forin -->
    <script>
        var arr = ["abc", "bcd", "234", , , , 54, 2, 1];
        console.log(arr); // (9) ["abc", "bcd", "234", empty × 3, 54, 2, 1]

        var newArr = [];

        // 稀松数组 ==> forin ==> 忽略不存在的成员
        for (var index in arr) {
            newArr.push(arr[index]);
            console.log(index, typeof index, arr[index]);
        }
        console.log(newArr); // (6) ["abc", "bcd", "234", 54, 2, 1]
        /*
        "0" "string" "abc"
        "1" "string" "bcd"
        "2" "string" "234"
        "6" "string" 54
        "7" "string" 2
        "8" "string" 1
         */
    </script>


    <!-- test8.html -->

    <!-- 面试题 ==> 创建一个长度为100的数组，给数组的每一项赋值为"abc" -->

    <!-- 错误写法 forin -->
    <script>
        var arr = new Array(100); // 创建一个长度为100的数组

        for (var index in arr) {
            arr[index] = "abc";
            // console.log(1); // 一个1都不会打印  该循环体不会执行
        }

        console.log(arr); // (100) [empty × 100]
    </script>

    <!-- 正确写法 for -->
    <script>
        var arr = new Array(100);

        for (var i = 0; i < arr.length; i++) {
            arr[i] = "abc";
            // console.log(1); // 打印100个1
        }

        console.log(arr); // (100) ["abc".....(共100个).....]
    </script>
</body>

</html>
```

**notes**

`这一部分的 test.html 内容过长了 得把它们给拆分到本节对应的知识点下面`

## 9. 数组应用

**作业**

```
1. 提示用户输入数组的长度，以及数组每一项的值，然后输出该数组
2. 初始化一个数字数组，然后求该数组所有项之和
3. 初始化一个数字数组，然后输出数组中所有的奇数
4. 初始化一个数字数组，然后输出数组中所有的素数
5. 斐波拉契数列是这样一种数列：1  1  2  3  5  8  13 ......
   数列前两位为1，第n位=第n-1位+第n-2位
   让用户输入斐波拉契数列的长度，在控制台中打印该长度的斐波拉契数列
6. 定义一个用户数组，数组的每一项是一个用户对象，用户对象中包含账号和密码，随意初始化一些对象放入数组中。然后提示用户输入账号和密码，判断是否登录成功
7. 初始化一个5*5的二维数组，数组每一项是一个数字，计算对角线之和
8. 初始化一个数字数组（数据随意），对该数组进行升序排序，然后输出结果
   思路提示：
      数组的排序有多种算法可以完成，这里介绍其中一种：冒泡排序算法
   冒泡排序算法的原理如下：
      - 比较相邻的元素。如果第一个比第二个大，就交换他们两个。
      - 对每一对相邻元素做同样的工作，从开始第一对到结尾的最后一对。在这一点，最后的元素应该会是最大的数。
      - 针对所有的元素重复以上的步骤，除了已排好序的元素。
9. 有一个数组，存放了一些数字，找出出现频率最高的数字
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 预备知识 -->

    <!-- test1.html -->
    <!-- 面试题 ==> 数组的本质：对象 （引用类型） -->
    <script>
        var arr1 = [3, 5, 7, 8, 2]; // arr1中存放的是地址
        var arr2 = arr1; // arr2中存放的是地址
        arr2[0] = 5;
        console.log(arr1 === arr2); // true
        console.log(arr1[0], arr2[0]); // 5 5
    </script>

    <!-- 如何复制（克隆，产生一个全新的对象） -->
    <script>
        var arr1 = [3, 5, 7, 8, 2];
        var arr2 = arr1.slice();
        arr2[0] = 5;
        console.log(arr1 === arr2); // false
        console.log(arr1[0], arr2[0]); // 3 5
    </script>

    <!-- test2.html -->
    <!-- 对数组求和 -->
    <script>
        var arr = [3, 7, 6, 4, 5];
        var sum = 0;
        for (var i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        console.log(sum); // 25
    </script>

    <!-- test3.html -->
    <!-- 二维数组：数组中的每一项是一个数组 -->
    <script>
        // 3*3的二维数组
        var arr = [
            [1, 2, 3],
            [4, 5, 6],
            [7, 8, 9]
        ];

        // 输出二维数组的每一项
        for (var i = 0; i < arr.length; i++) {

            for (var j = 0; j < arr[i].length; j++) {
                console.log(arr[i][j]);
            }

        }

        // 对二维数组求和
        var sum = 0;
        for (var i = 0; i < arr.length; i++) {
            for (var j = 0; j < arr[i].length; j++) {
                sum += arr[i][j];
            }
        }
        console.log(sum); // 45
    </script>

    <!-- test4.html -->
    <!-- 将数组的每一项进行字符串拼接 -->
    <script>
        var arr = [3, 4, 6, 1, 3];

        // 输出：3, 4, 6, 1, 3
        var str = "";
        for (var i = 0; i < arr.length; i++) {
            str += arr[i];
            if (i < arr.length - 1) {
                str += ",";
            }
        }
        console.log(str); // "3,4,6,1,3"
    </script>

    <script>
        var arr = [3, 4, 6, 1, 3];
        // 数组.join(分隔符)，该函数返回一个字符串
        var str = arr.join(",");
        console.log(str); // "3,4,6,1,3"
    </script>

    <!-- test5.html -->
    <!-- 数组 与 数组 拼接 -->
    <script>
        var arr1 = [34, 5, 2, 1];
        var arr2 = ["abc", "bcd"];
        // 数组1.concat(数组2)
        // 将数组2的所有元素 拼接到 数组1 的末尾，产生一个新数组返回，该表达式不会对原数组造成任何影响
        var arr3 = arr1.concat(arr2);
        console.log(arr1); // (4) [34, 5, 2, 1]
        console.log(arr2); // (2) ["abc", "bcd"]
        console.log(arr3); // (6) [34, 5, 2, 1, "abc", "bcd"]
    </script>


</body>

</html>
```

## 10. [作业讲解]数组应用

[JS数组去重的10种方法 csdn](https://blog.csdn.net/weixin_42412046/article/details/81459294)

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月16日</title>
</head>

<body>
    <!-- 1. 提示用户输入数组的长度，以及数组每一项的值，然后输出该数组 -->
    <!-- 本题的目的: 我们需要知道 大多数情况下 数组中的值不是我们自己确定的 而是用户输入的值 -->
    <script>
        var len = +prompt("请输入数组的长度: "),
            arr = [];
        for (var i = 0; i < len; i++) {
            item = +prompt(`请输入第${i+1}项: `); // bug ==> 输入的数据不一定都是数字
            arr.push(item);
        }
        console.log(arr);
    </script>

    <!-- 袁老师 -->
    <script>
        var len = +prompt("请输入数组的长度");
        if (isNaN(len) || len < 0) {
            console.log("输入有误");
        } else {
            //输入正确
            var arr = []; // var arr = new Array(len);
            for (var i = 0; i < len; i++) {
                // 提示用户输入数组的这一项的值
                arr[i] = prompt("请输入数组第" + (i + 1) + "项的值"); // 若 i + 1 不加括号 那么会先拼接 i 再拼接 1
            }
            console.log(arr);
        }
    </script>

    <!-- 2. 初始化一个数字数组，然后求该数组所有项之和 -->
    <script>
        var arr = [1, 2, 3, 3, 3, 2, 1],
            sum = 0;
        for (var i = 0; i < arr.length; i++) {
            sum += arr[i];
        }

        console.log(sum); // 15
    </script>

    <!-- 3. 初始化一个数字数组，然后输出数组中所有的奇数 -->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, 7],
            oddArr = [];
        for (var i = 0; i < arr.length; i++) {
            if (arr[i] % 2 === 1) {
                oddArr.push(arr[i]);
            }
        }
        console.log(oddArr); // (4) [1, 3, 5, 7]
    </script>
    <!-- 袁老师 -->
    <script>
        var arr = [234, 6, 23, 211, 23];
        for (var index in arr) {
            if (arr[index] % 2 !== 0) {
                console.log(arr[index]);
            }
        }
    </script>

    <!-- 4. 初始化一个数字数组，然后输出数组中所有的素数 -->
    <script>
        var arr = [], // 存放 1-100所有整数
            newArr = []; // newArr 存放素数
        var record = 0;
        // 初始化 arr
        for (var i = 0; i < 100; i++) {
            arr.push(i + 1);
        }

        for (var i = 0; i < arr.length; i++) {
            record = 0;
            for (var j = 1; j <= arr[i]; j++) {
                if (arr[i] % j == 0) {
                    record++;
                }
            }
            if (record === 2) {
                newArr.push(arr[i]);
            }
        }
        console.log(
            newArr
        ); // (25) [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97]
    </script>
    <!-- 袁老师 -->
    <script>
        var arr = [234, 2, 6, 23, 211, 23];
        for (var index in arr) {
            // 判断arr[index]是不是素数
            var isFind = false;
            for (var i = 2; i < arr[index] - 1; i++) {
                if (arr[index] % i === 0) {
                    isFind = true;
                    break;
                }
            }
            if (!isFind && arr[index] >= 2) {
                console.log(arr[index]);
            }
        }
    </script>

    <!-- 5. 斐波拉契数列是这样一种数列：1 1 2 3 5 8 13 ......
    数列前两位为1，第n位=第n-1位+第n-2位
    让用户输入斐波拉契数列的长度，在控制台中打印该长度的斐波拉契数列 -->
    <script>
        var len = +prompt("请输入斐波拉契数列的长度: "),
            arr = [];
        for (var i = 0; i < len; i++) {
            if (i === 0 || i === 1) {
                arr.push(1);
            } else {
                arr.push(arr[i - 1] + arr[i - 2]);
            }
        }
        console.log(arr); // (7) [1, 1, 2, 3, 5, 8, 13]
    </script>
    <!-- 袁老师 -->
    <script>
        var len = +prompt("请输入斐波拉契数列的长度");
        if (isNaN(len) || len < 0) {
            console.log("输入有误");
        } else {
            //输入正确
            var arr = [];
            for (var i = 0; i < len; i++) {
                if (i === 0 || i === 1) {
                    arr[i] = 1;
                } else {
                    arr[i] = arr[i - 1] + arr[i - 2];
                }
            }

            console.log(arr);
        }
    </script>

    <!-- 6. 定义一个用户数组，数组的每一项是一个用户对象，用户对象中包含账号和密码，随意初始化一些对象放入数组中。
        然后提示用户输入账号和密码，判断是否登录成功 -->
    <script>
        var uerArr = [{
                name: 'A',
                age: 18,
                count: '111',
                pwd: '222'
            },
            {
                name: 'B',
                age: 19,
                count: '222',
                pwd: '333'
            },
            {
                name: 'C',
                age: 20,
                count: '333',
                pwd: '444'
            },
        ];
        var inputCount = prompt("请输入账号: ");
        var inputpwd = prompt("请输入密码: ");
        for (var i = 0; i < uerArr.length; i++) {
            if (inputCount === uerArr[i].count && inputpwd === uerArr[i].pwd) {
                console.log("登录成功");
                break;
            } else if (i === uerArr.length - 1) {
                console.log("登录失败");
            }
        }
    </script>
    <!-- 袁老师 -->
    <script>
        var users = [{
                loginId: "abc",
                loginPwd: "123"
            },
            {
                loginId: "abc1",
                loginPwd: "1234"
            },
            {
                loginId: "abc2",
                loginPwd: "1235"
            },
            {
                loginId: "abc3",
                loginPwd: "1236"
            }
        ];

        // 不能使用 indexOf() 来查找
        // var index = user.indexOf({ // 返回值永远都是 -1
        //     loginId,
        //     loginPwd
        // })
        // indexOf() 比较时用的是严格相等 对象之间的比较比较的是地址 它们之间的地址是不可能相等的
        // 查找对象不能使用 indexOf() 但是基本类型可以 比如 数字 字符串 ...

        var loginId = prompt("请输入账号");
        var loginPwd = prompt("请输入密码");

        // 查找问题
        var isFind = false;
        for (var i = 0; i < users.length; i++) {
            var u = users[i];
            if (u.loginId === loginId && u.loginPwd === loginPwd) {
                isFind = true;
                break;
            }
        }

        if (isFind) {
            console.log("登录成功");
        } else {
            console.log("登录失败");
        }
    </script>

    <!-- 7. 初始化一个5*5的二维数组，数组每一项是一个数字，计算对角线[两条]之和 -->
    <script>
        // Two-dimensional array 二维数组
        var tdArr = [
            [1, 2, 3, 4, 5],
            [1, 2, 3, 4, 5],
            [1, 2, 103, 4, 5],
            [1, 2, 3, 4, 5],
            [1, 2, 3, 4, 5]
        ];
        var sum = 0;
        for (var r = 0; r < tdArr.length; r++) {
            for (var c = 0; c < tdArr[r].length; c++) {
                if (r === c || r + c === tdArr.length - 1) {
                    sum += tdArr[r][c];
                }

            }
        }

        console.log(sum); // 230
    </script>
    <!-- 袁老师 -->
    <script>
        var arr = [
            [5, 2, 3, 1, 7],
            [8, 0, 6, 7, 8],
            [4, 0, 6, 2, 0],
            [3, 0, 6, 8, 1],
            [2, 0, 4, 5, 9]
        ];

        // 对角线之和
        var sum = 0;
        for (var i = 0; i < arr.length; i++) {
            // arr[i] 是一个数组
            for (var j = 0; j < arr[i].length; j++) {
                // arr[i][j]
                if (i === j || i + j === arr.length - 1) {
                    sum += arr[i][j];
                }
            }
        }

        console.log(sum);
    </script>

    <!-- 8. 初始化一个数字数组（数据随意），对该数组进行升序排序，然后输出结果

    思路提示：

    数组的排序有多种算法可以完成，这里介绍其中一种：冒泡排序算法

    冒泡排序算法的原理如下：
    - 比较相邻的元素。如果第一个比第二个大，就交换他们两个。
    - 对每一对相邻元素做同样的工作，从开始第一对到结尾的最后一对。在这一点，最后的元素应该会是最大的数。
    - 针对所有的元素重复以上的步骤，除了已排好序的元素。 -->
    <script>
        // 升序 ==> 从头到尾 越来越大
        var arr = [93, 27, 84, 34, 75, 63];
        for (var i = 0; i < arr.length; i++) {
            for (var j = 0; j < arr.length - 1 - i; j++) {
                if (arr[j] > arr[j + 1]) {
                    var temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
        console.log(arr); // (6) [27, 34, 63, 75, 84, 93]
    </script>
    <!-- 袁老师 -->
    <script>
        var nums = [23, 2, -34, 3563, 111, 44, 5, 8, 1];

        for (var i = 1; i < nums.length; i++) {
            // 第i次排序
            for (var j = 0; j < nums.length - i; j++) {
                // 比较 j 和 j+1 两个位置的数字
                if (nums[j] > nums[j + 1]) {
                    //交换
                    var temp = nums[j];
                    nums[j] = nums[j + 1];
                    nums[j + 1] = temp;
                }
            }
        }

        console.log(nums);

        /*
            第1次：排了5次，比较的位置从0~4
            2，23，44，5，8，1
            2，23，44，5，8，1
            2，23，5，44，8，1
            2，23，5，8，44，1
            2，23，5，8，1，44
        */

        /*
            第2次：排了4次，比较的位置从0~3
            2，23，5，8，1，44
            2，5，23，8，1，44
            2，5，8，23，1，44
            2，5，8，1，23，44
        */

        /*
            第3次：排了3次，比较的位置从0~2
            2，5，8，1，23，44
            2，5，8，1，23，44
            2，5，1，8，23，44
        */

        /*
            第4次：排了2次，比较的位置从0~1
            2，5，1，8，23，44
            2，1，5，8，23，44
        */

        /*
            第5次：排了1次，比较的位置从0~0
            1，2，5，8，23，44
        */
    </script>

    <!-- 9. 有一个数组，存放了一些数字，找出出现频率最高的数字 [面试题考过很多次] -->
    <script>
        var arr = [1, 2, 3, 3, 2, 2, 4, 4, 4, 4, 2, 2, 2],
            maxRateNum,
            newArr = []; // 去重后的新数组

        // 数组去重
        for (var i = 0; i < arr.length; i++) {
            var item = arr[i];
            for (var j = 0; j < newArr.length || newArr.length === 0; j++) {
                if (item === newArr[j]) {
                    break;
                } else if (j === newArr.length - 1 || newArr.length === 0) {
                    newArr.push(item);
                    break;
                }
            }
        }
        // console.log(newArr);
        var count = 0,
            maxCount = 0;
        for (var j = 0; j < newArr.length; j++) {
            count = 0;
            // console.log(newArr[j]);
            for (var i = 0; i < arr.length; i++) {
                if (newArr[j] === arr[i]) {
                    count++;
                }
            }
            if (count > maxCount) {
                maxRateNum = newArr[j];
                maxCount = count;
            }
        }
        console.log(maxRateNum);
    </script>
    <!-- 袁老师 -->
    <script>
        var nums = [2, 3, 4, 5, 234, 5, 5, 5, 5, 5, 5, 5, 5, 2, 2, 2, 2, 3, 3, 3, 5];

        // 输出：2出现频率最高，出现5次
        // 得到记录对象

        var record = {}; //记录对象
        for (var i = 0; i < nums.length; i++) {
            var n = nums[i];
            if (record[n]) {
                record[n]++;
            } else {
                record[n] = 1;
            }
        }

        var result; //结果对象
        for (var prop in record) {
            if (!result || record[prop] > result.frequency) {
                result = {
                    number: prop,
                    frequency: record[prop]
                }
            }
        }

        console.log(`${result.number}出现频率最高，出现${result.frequency}次`); // 5出现频率最高，出现10次
    </script>

    <!-- 补充作业: 初始化一个数组 , 求数组中的最大值 -->
    <script>
        var arr = [11, 75, 36, 92, 36, 54];
        var max = arr[0];
        for (var i = 1; i <= arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        console.log(max); // 92
    </script>
    <!-- 袁老师 -->
    <script>
        var nums = [23, 6, 1, 1, 666, 324];
        // 求最大值
        var max = nums[0];
        for (var i = 1; i < nums.length; i++) {
            if (nums[i] > max) {
                max = nums[i];
            }
        }

        console.log(max); // 666
    </script>
</body>

</html>
```

# 五、函数

```
重点:
    5. [作业讲解]函数表达式和this
       掌握回调函数的使用
    8. 递归
       掌握递归的思想
```

## 1. 函数语法

```
重复代码：让程序难以维护
函数主要用于减少重复代码
```

**创建（定义、声明）函数**

```js
function 函数名(){
    // 函数体
}
```

```
函数体的代码不会直接运行，必须要手动调用函数，才能运行其中的代码。
```

**调用函数**

```js
函数名(); // 运行函数体
```

**函数提升**

```
通过字面量声明的函数，会提升到 脚本块 的顶部。
通过字面量声明的函数，会成为全局对象的属性。
```

**其他特点**

```
通过typeof 函数名，得到的结果是"function"
函数内部声明的变量：
    1. 如果不使用var声明，和全局变量一致，表示给全局对象添加属性
    2. 如果使用var声明，变量提升到所在函数的顶部，函数外部不可以使用该变量
注意: 函数中声明的变量，仅能在函数中使用，在外部无效
    函数内部可以访问全局作用域中的变量 但是全局不能访问函数局部作用域中的变量 [进阶课程 ==> 作用域] (现阶段不做详细说明)
```

**参数**

```
参数表示函数运行的未知条件，需要调用者告知的数据
```

```js
// 参数的有效返回在函数体中
function 函数名(形参1, 形参2, ...){ // 函数声明时 确认好形参

}

函数名(实参); // 函数调用时传入实参
// 如果实参没有传递，则对应的形参为undefined
```

**返回值**

```
函数运行后，得到的结果，调用函数时，调用表达式的值就是函数的返回值
return 会直接结束整个函数的运行
return 后面如果不跟任何数据，返回undefined
如果函数中没有书写return，则该函数会在末尾自动return undefined。
```

**文档注释**

```
操作: 在 .js 文件下输入 /** 后 按 回车 就会自动生成文档注释
```

```js
/**
 *
 *
*/
```

**作业**

```
通用函数编写, 新建一个js文件，编写以下函数

1. 写一个函数，该函数用于判断某个数是不是奇数
    函数名参考：isOdd

2. 写一个函数，该函数用于判断某个数是不是素数
    函数名参考：isPrime

3. 写一个函数，该函数用于对数组求和
    函数名参考：sumOfArray

4. 写一个函数，该函数用于得到数组中的最大值
    函数名参考：maxOfArray

5. 写一个函数，该函数用于得到数组中的最小值
    函数名参考：minOfArray

6. 写一个函数，该函数用于判断数组是否是稀松数组
    函数名参考：hasEmptyInArray

7. 写一个函数，判断该某年是否是闰年
    函数名参考：isLeap

8. 写一个函数，得到某年某月的天数
    函数名参考：getDays

9. 写一个函数，得到某个数字数组中出现次数最多的数字和频率
    函数名参考：getTopFreqInArray
```

**函数使用**

```
1. 利用上面的某些函数，实现哥德巴赫猜想
    任一大于2的偶数都可写成两个质数之和，比如：8 = 3 + 5
    让用户输入一个大于2的整数，输出其等于哪两个素数相加

2. 让用户输入一个年份，输出该年每个月的天数
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月13日</title>
</head>

<body>
    <script src="./Myfunctions.js"></script>

    <!-- test1.html -->
    <script>
        function printSplitor() {
            console.log("********************"); //输出分隔符
        }
        // 如果两个script脚本块调换位置 那么函数将无法正常调用 [函数提升不会跨脚本块]
    </script>

    <script>
        printSplitor(); // ********************
        // 函数体的代码不会直接运行，必须要手动调用函数，才能运行其中的代码。
        console.log("asdfasdfa");
        console.log(234);
        printSplitor(); // ********************
        console.log({
            x: 234,
            y: "asdf"
        });
        console.log("344535");
        printSplitor(); // ********************
        console.log(window.printSplitor); // 通过字面量声明的函数，会成为全局对象的属性。
    </script>

    <script>
        printSplitor(); // ********************
        // 函数声明整体提升 ==> 在函数声明之前可以正常调用函数
        function printSplitor() {
            console.log("********************"); //输出分隔符
        }
        // 如果两个script脚本块调换位置 那么函数将无法正常调用 [函数提升不会跨脚本块]
    </script>


    <!-- test2.html -->
    <!-- 在局部作用域声明全局变量 -->
    <script>
        console.log(typeof test); // "function"

        function test() {
            a = 3;
            console.log(a); // 3
            console.log(a === window.a); // true
        }
        test(); // 函数执行后 为全局对象 window 添加了一个属性 a 值是 3
        console.log(a); // 3
        console.log(a === window.a); // true
    </script>

    <!-- 在局部作用域声明局部变量 -->
    <script>
        function test() {
            // var a; ==> 变量声明提升到所在函数的顶部
            console.log(a); // undefined
            var a = 3;
            a--; // AO 的a ==> 2
            console.log(a); // 2
            console.log(a === window.a); // false
        }
        var a = 5; // GO 的a ==> 5
        test();
        console.log(a); // 5
        console.log(a === window.a); // true
    </script>

    <!-- test3.html -->
    <!-- 参数的形式 -->
    <script>
        function isOdd(n) { // 形参
            // 参数 n 的有效区域在函数体中
            if (n % 2 === 0) {
                console.log(n + "不是奇数");
            } else {
                console.log(n + "是奇数");
            }
        }

        // 如果实参没有传递，则对应的形参为undefined
        isOdd(); // undefined是奇数

        var nums = [324, 4, 2, 1, 3, 45, 332];
        for (var i = 0; i < nums.length; i++) {
            isOdd(nums[i]); // 实参 nums[i]
        }

        isOdd(3); // 实参 3
        isOdd(100 + 3 * 4); // 实参 100 + 3 * 4 实参也可以是一个表达式
    </script>

    <!-- 参数的个数 -->
    <script>
        // 输出两个数相加的结果
        function sum(a, b) {
            console.log(`${a}+${b}=${a+b}`);
        }

        sum(234); // 参数传少了 未传的是 undefined ==> 234+undefined=NaN
        sum(3, 5); // 3+5=8
        sum(234, 234, 435345, 4352); // 参数传多了 多传的直接忽略 ==> 234+234=468
    </script>

    <!-- 对一个数组求和 -->
    <script>
        function sumOfArray(arr) {
            var sum = 0;
            for (var i = 0; i < arr.length; i++) {
                sum += arr[i];
            }
            console.log("和为：" + sum);
        }

        sumOfArray([32, 4, 5, 32, 1]); // 和为：74
        var nums = [345, 43, 45, 23, 234, 234, 423, 435, 435, 435];
        sumOfArray(nums); // 和为：2652
    </script>

    <!-- 删除数组末尾的指定数量的数据 -->
    <script>
        function deleteArray(arr, number) {
            arr.splice(-number, number);
        }
        var nums = [1, 2, 3, 4, 5];
        deleteArray(nums, 3); // nums 引用传递 传的是地址

        console.log(nums); // (2) [1, 2]
    </script>


    <!-- test4.html -->
    <!-- 判奇数 -->
    <script>
        function isOdd(n) {
            if (n % 2 === 0) {
                return false;
            }
            return true;
        }
    </script>

    <!-- 数组中奇数求和 -->
    <script>
        var nums = [1, 2, 3, 4, 5, 6, 7, 8];
        var sum = 0;
        for (var i = 0; i < nums.length; i++) {
            if (isOdd(nums[i])) { // 直接调用上面声明好的函数
                sum += nums[i];
            }
        }
        console.log(sum); // 16
    </script>




    <!-- test5.html -->
    <!-- 对一个数组求和 -->
    <script>
        function sumOfArray(arr) {
            var sum = 0;
            for (var i = 0; i < arr.length; i++) {
                sum += arr[i];
            }
            return sum;
        }

        var num1 = [1, 2, 3, 4];
        var num2 = [5, 6, 7];

        console.log(sumOfArray(num1) + sumOfArray(num2)); // 28
    </script>

    <!-- 判断一个数是不是素数 -->
    <script>
        function isPrime(n) {
            if (n < 3) {
                return n > 1;
            }
            for (var i = 2; i < n - 1; i++) {
                if (n % i === 0) {
                    return false;
                }
            }
            return true;
        }
    </script>

    <!-- 对数组nums中的素数求和 -->
    <script>
        var nums = [1, 2, 3, 4, 5, 6, 7];
        var sum = 0;
        for (var i = 0; i < nums.length; i++) {
            if (isPrime(nums[i])) {
                sum += nums[i];
            }
        }
        console.log(sum); // 17 ==> 2 + 3 + 5 + 7
    </script>


    <!-- test6.js -->
    <script>
        /**
         * nums：一个数字的数组
         */
        var nums = [23, 56, 65, 746];

        /**
         * 两个求和
         * @param {number} a 第一个数字
         * @param {number} b 第二个数字
         * @returns {number} 相加的结果
         */
        function sum(a, b) {
            return a + b;
        }

        /**
         * 判断一个数是不是素数
         * @param {number} n 要判断的数
         * @returns {boolean} 是否是素数
         */
        function isPrime(n) {
            //..
        }

        var s = sum(1, 3);
    </script>


    <!-- ====================================================================== -->

    <!-- 作业部分 -->

    <!-- isOdd -->
    <script>
        var Myfunctions = {
            isOdd: function (num) {
                return num % 2 !== 0;
            }
        }
    </script>

    <script>
        console.log(Myfunctions.isOdd(2)); // false
        console.log(Myfunctions.isOdd(32)); // false
        console.log(Myfunctions.isOdd(11)); // true
        console.log(Myfunctions.isOdd(27)); // true
    </script>

    <!-- isPrime -->
    <script>
        var Myfunctions = {
            isPrime: function (num) {
                if (num <= 3) {
                    return num > 1;
                }
                for (var i = 2; i <= num - 1; i++) {
                    if (num % i === 0) {
                        return false;
                    }
                }
                return true;
            }
        }
    </script>

    <script>
        var arr = [];
        for (var i = 0; i < 100; i++) {
            arr[i] = i + 1;
        }
        var sum = 0;
        var newArr = [];
        for (var i = 0; i < 100; i++) {
            if (Myfunctions.isPrime(arr[i])) {
                sum += arr[i];
                newArr.push(arr[i]);
            }
        }
        console.log(`1~100中共有 ${newArr.length} 个素数\t ${newArr} \t总和为 ${sum} `);
        // 1~100中共有 25 个素数	 2,3,5,7,11,13,17,19,23,29,31,37,41,43,47,53,59,61,67,71,73,79,83,89,97
        // 总和为 1060
    </script>

    <!-- sumOfArray -->
    <script>
        var Myfunctions = {
            sumOfArray: function (arr) {
                var sum = 0;
                for (var i = 0; i < arr.length; i++) {
                    sum += arr[i];
                }
                return sum;
            }
        }
    </script>

    <script>
        var arr = [];
        for (var i = 0; i < 100; i++) {
            arr[i] = i + 1;
        }
        var sum = Myfunctions.sumOfArray(arr);
        console.log(sum); // 5050
    </script>


    <!-- maxOfArray -->
    <script>
        var Myfunctions = {
            maxOfArray: function (arr) {
                var max = arr[0];
                for (var i = 1; i < arr.length; i++) {
                    if (arr[i] > max) {
                        max = arr[i];
                    }
                }
                return max;
            }
        }
    </script>

    <script>
        var arr = [32, 13, 46, 73, 25, 62];
        var maxNum = Myfunctions.maxOfArray(arr);
        console.log(maxNum); // 73
    </script>


    <!-- minOfArray -->
    <script>
        var Myfunctions = {
            minOfArray: function (arr) {
                var min = arr[0];
                for (var i = 1; i < arr.length; i++) {
                    if (arr[i] < min) {
                        min = arr[i];
                    }
                }
                return min;
            }
        }
    </script>

    <script>
        var arr = [32, 13, 46, 73, 25, 62];
        var minNum = Myfunctions.minOfArray(arr);
        console.log(minNum); // 13
    </script>


    <!-- hasEmptyInArray -->
    <script>
        var Myfunctions = {
            hasEmptyInArray: function (arr) {
                for (var i = 0; i < arr.length; i++) {
                    if (!(i in arr)) {
                        return true;
                    }
                }
                return false;
            }
        }
    </script>

    <script>
        var arr1 = [, , , 2, 3, 4, , 1];
        var arr2 = [];
        arr2[10] = 1;
        var arr3 = new Array(100);
        var arr4 = [1, 2, 3, 4, 5];
        console.log(Myfunctions.hasEmptyInArray(arr1)); // true
        console.log(Myfunctions.hasEmptyInArray(arr2)); // true
        console.log(Myfunctions.hasEmptyInArray(arr3)); // true
        console.log(Myfunctions.hasEmptyInArray(arr4)); // false
    </script>



    <!-- isLeap -->
    <script>
        var Myfunctions = {
            isLeap: function (year) {
                return (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
            }
        }
    </script>

    <script>
        console.log(1999); // false
        console.log(2020); // true
    </script>


    <!-- getDays -->
    <script>
        var Myfunctions = {
            getDays: function (year, month) {
                if (this.isLeap(year) && month === 2) {
                    return 29;
                } else if (!this.isLeap(year) && month === 2) {
                    return 28;
                } else if ((this.isOdd(month) && month < 8) || (!this.isOdd(month) && month >= 8)) {
                    return 31;
                } else {
                    return 30;
                }
            }
        }
    </script>

    <script>
        for (var i = 0; i < 12; i++) {
            console.log(`2020 - ${i+1}月 共有 ${Myfunctions.getDays(2020, i + 1)}天`);
        }
    </script>


    <!-- getTopFreqInArray -->
    <script>
        var Myfunctions = {
            /**
             * 获取数组中出现频率最高的数 及其出现次数
             * @param {*} arr
             * @return {Object} {num: 出现最多的数, fre: 该数出现的次数}
             */
            getTopFreqInArray: function (arr) {
                var recordObj = {};
                for (var i = 0; i < arr.length; i++) {
                    if (arr[i] in recordObj) {
                        recordObj[arr[i]]++;
                    } else {
                        recordObj[arr[i]] = 1;
                    }
                }
                var resultObj = {
                    num: arr[0],
                    fre: recordObj[arr[0]]
                };
                for (var i = 0; i < arr.length; i++) {
                    if (resultObj.fre < recordObj[arr[i]]) {
                        resultObj.num = arr[i];
                        resultObj.fre = recordObj[arr[i]];
                    }
                }
                return resultObj;
            }
        }
    </script>

    <script>
        var arr = [1, 5, 3, 3, 5, 2, 4, 3, 5, 5];
        var result = Myfunctions.getTopFreqInArray(arr);
        console.log(result); // {num: 5, fre: 4}
    </script>



    <!-- 哥德巴赫猜想 -->
    <script>
        var inputNum = +prompt('请输入一个大于2的偶数: ');
        if (isNaN(inputNum) || Myfunctions.isOdd(inputNum)) {
            console.log("输入错误");
        } else {
            for (var i = 1; i < inputNum; i++) {
                var j = inputNum - i;
                if (Myfunctions.isPrime(i) && Myfunctions.isPrime(j)) {
                    console.log(`${inputNum} = ${i} + ${j}`);
                }
            }
        }
    </script>


    <!-- 根据用户输入的年份 ==> 打印这一年每个月的天数 -->
    <script>
        var inputYear = +prompt('请输入一个年份: ');
        for (var i = 0; i < 12; i++) {
            console.log(`${inputYear} - ${i+1}月 共有 ${Myfunctions.getDays(inputYear, i + 1)}天`);
        }
    </script>
</body>

</html>
```

**Myfunctions.js**

```js
var Myfunctions = {
    /**
     * 判奇数
     * @param {*} num
     */
    isOdd: function (num) {
        return num % 2 !== 0;
    },
    /**
     * 判素数
     * @param {*} num
     */
    isPrime: function (num) {
        if (num <= 3) {
            return num > 1;
        }
        for (var i = 2; i <= num - 1; i++) {
            if (num % i === 0) {
                return false;
            }
        }
        return true;
    },
    /**
     * 数组求和
     * @param {*} arr
     */
    sumOfArray: function (arr) {
        var sum = 0;
        for (var i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    },
    /**
     * 返回数组中的最大值
     * @param {*} arr
     */
    maxOfArray: function (arr) {
        var max = arr[0];
        for (var i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        return max;
    },
    /**
     * 返回数组中的最小值
     * @param {*} arr
     */
    minOfArray: function (arr) {
        var min = arr[0];
        for (var i = 1; i < arr.length; i++) {
            if (arr[i] < min) {
                min = arr[i];
            }
        }
        return min;
    },
    /**
     * 判稀松数组
     * @param {*} arr
     */
    hasEmptyInArray: function (arr) {
        for (var i = 0; i < arr.length; i++) {
            if (!(i in arr)) {
                return true;
            }
        }
        return false;
    },
    /**
     * 判闰年
     * @param {*} year
     */
    isLeap: function (year) {
        return (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
    },
    /**
     * 返回指定年月的天数
     * @param {*} year
     * @param {*} month
     */
    getDays: function (year, month) {
        if (this.isLeap(year) && month === 2) {
            return 29;
        } else if (!this.isLeap(year) && month === 2) {
            return 28;
        } else if ((this.isOdd(month) && month < 8) || (!this.isOdd(month) && month >= 8)) {
            return 31;
        } else {
            return 30;
        }
    },
    /**
     * 获取数组中出现频率最高的数 及其出现次数
     * @param {*} arr
     * @return {Object} {num: 出现最多的数, fre: 该数出现的次数}
     */
    getTopFreqInArray: function (arr) {
        var recordObj = {};
        for (var i = 0; i < arr.length; i++) {
            if (arr[i] in recordObj) {
                recordObj[arr[i]]++;
            } else {
                recordObj[arr[i]] = 1;
            }
        }
        var resultObj = {
            num: arr[0],
            fre: recordObj[arr[0]]
        };
        for (var i = 0; i < arr.length; i++) {
            if (resultObj.fre < recordObj[arr[i]]) {
                resultObj.num = arr[i];
                resultObj.fre = recordObj[arr[i]];
            }
        }
        return resultObj;
    }
}
```

## 2. [作业讲解]函数语法

### test.html

```html
<!-- # 通用函数编写

新建一个js文件，编写以下函数 -->

<script src="../1. 函数语法/Myfunctions.js"></script>
<!-- Mr. Yuan 编写的代码位于 common 文件夹中的 myfunction.js 文件内部 -->



<!-- 1. 写一个函数，该函数用于判断某个数是不是奇数

函数名参考：isOdd -->
<!-- Mr. Tao -->
<script>
    /**
     * 判奇数
     * @param {number} num 被判断的数字
     * @return {boolean} 是奇数返回true 不是奇数返回 false
     */
    function isOdd(num) {
        return num % 2 !== 0;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 判断一个数是不是奇数
     * @param {number} n 要判断的数字
     * @returns {boolean}
     */
    function isOdd(n) {
        return n % 2 !== 0;
    }
</script>
<script>
    console.log(isOdd(1)); // true
    console.log(isOdd(10)); // false
</script>




<!-- 2. 写一个函数，该函数用于判断某个数是不是素数

函数名参考：isPrime -->
<!-- Mr. Tao -->
<script>
    /**
     * 判素数
     * @param {num} num 被判断的数字
     * @return {boolean} 是素数 ==> true 非素数 ==> false
     */
    function isPrime(num) {
        if (num < 3) {
            return num > 1;
        }
        for (var i = 2; i <= num - 1; i++) {
            if (num % i === 0) {
                return false;
            }
        }
        return true;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 判断一个数是不是素数
     * @param {*} n
     */
    function isPrime(n) {
        if (n < 2) {
            return false;
        }
        for (var i = 2; i < n; i++) {
            if (n % i === 0) {
                return false;
            }
        }
        return true;
    }
</script>
<script>
    var arr = [];
    // 初始化 arr 赋值 1~100
    for (var i = 0; i < 100; i++) {
        arr[i] = i + 1;
    }
    // 遍历 arr 求素数和
    var sum = 0;
    for (var i = 0; i < 100; i++) {
        if (isPrime(arr[i])) {
            sum += arr[i];
        }
    }
    console.log(sum); // 1060
</script>




<!-- 3. 写一个函数，该函数用于对数组求和

函数名参考： sumOfArray -->
<!-- Mr. Tao -->
<script>
    /**
     * 对数组求和
     * @param {Array} arr 求和的数组
     * @return {Number} 返回求和的结果
     */
    function sumOfArray(arr) {
        var sum = 0;
        for (var i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 对数组求和
     * @param {*} arr
     */
    function sumOfArray(arr) {
        var sum = 0;
        for (var i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    }
</script>
<script>
    var nums = [11, 26, 2, 38, 61];
    console.log(sumOfArray(nums)); // 138
</script>





<!-- 4. 写一个函数，该函数用于得到数组中的最大值

函数名参考：maxOfArray -->
<!-- Mr. Tao -->
<script>
    /**
     * 返回数组中的最大值 若数组长度是0 则返回 undefined
     * @param {Array} arr
     */
    function maxOfArray(arr) {
        if (arr.length === 0) {
            return;
        }
        maxNum = arr[0];
        for (var i = 1; i < arr.length; i++) {
            if (arr[i] > maxNum) {
                maxNum = arr[i];
            }
        }
        return maxNum;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 得到数组中的最大值，如果数组长度为0，则返回undefined
     * @param {*} arr
     */
    function maxOfArray(arr) {
        if (arr.length === 0) {
            return;
        }
        var max = arr[0];
        for (var i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        return max;
    }
</script>
<script>
    var nums = [11, 26, 2, 38, 61];
    console.log(maxOfArray(nums)); // 61
</script>




<!-- 5. 写一个函数，该函数用于得到数组中的最小值

函数名参考：minOfArray -->
<!-- Mr. Tao -->
<script>
    /**
     * 返回数组中的最小值 若数组长度是0 则返回 undefined
     * @param {Array} arr
     */
    function minOfArray(arr) {
        if (arr.length === 0) {
            return;
        }
        minNum = arr[0];
        for (var i = 1; i < arr.length; i++) {
            if (arr[i] < minNum) {
                minNum = arr[i];
            }
        }
        return minNum;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 得到数组中的最小值，如果数组长度为0，则返回undefined
     * @param {*} arr
     */
    function minOfArray(arr) {
        if (arr.length === 0) {
            return;
        }
        var min = arr[0];
        for (var i = 1; i < arr.length; i++) {
            if (arr[i] < min) {
                min = arr[i];
            }
        }
        return min;
    }
</script>
<script>
    var nums = [11, 26, 2, 38, 61];
    console.log(minOfArray(nums)); // 2
</script>




<!-- 6. 写一个函数，该函数用于判断数组是否是稀松数组

函数名参考：hasEmptyInArray -->
<!-- Mr. Tao -->
<script>
    /**
     * 判稀松数组
     * @param {Array} arr
     * @return {Boolean} 是稀松数组 ==> true 非稀松数组 ==> false
     */
    // 稀疏数组 就是包含从0开始的不连续索引的数组。
    function hasEmptyInArray(arr) {
        for (var i = 0; i < arr.length; i++) {
            if (!(i in arr)) {
                return true;
            }
        }
        return false;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 判断一个数组是不是稀松数组
     * @param {*} arr
     */
    function hasEmptyInArray(arr) {
        // 稀松数组的特点：下标连续
        for (var i = 0; i < arr.length; i++) {
            if (!(i in arr)) {
                return true;
            }
        }
        return false;
    }
</script>
<script>
    console.log(hasEmptyInArray(new Array(3))); // true
    console.log(hasEmptyInArray([3, 4, 2, 6])); // false
</script>




<!-- 7. 写一个函数，判断该某年是否是闰年

函数名参考：isLeap -->
<!-- Mr. Tao -->
<script>
    /**
     * 判闰年
     * @param {number} year 年份
     */
    function isLeap(year) {
        return (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 判断某年是不是闰年
     * @param {*} year
     */
    function isLeap(year) {
        // 4年一闰，百年不闰；400年一闰
        return year % 4 === 0 && year % 100 !== 0 || year % 400 === 0;
    }
</script>
<script>
    console.log(isLeap(2019));
    console.log(isLeap(2020));
</script>



<!-- 8. 写一个函数，得到某年某月的天数

函数名参考：getDays -->
<!-- Mr. Tao -->
<script>
    /**
     * 计算某年某月的天数
     * @param {number} year 年份
     * @param {number} month 月份
     * @return {number} 某年某月的天数
     */
    function getDays(year, month) {
        if (month === 2) {
            // 闰年 ==> 2月 ==> 29天
            return isLeap(year) ? 29 : 28;
        } else {
            if ((month < 8 && isOdd(month)) || (month >= 8 && !isOdd(month))) {
                // 大月
                return 31;
            } else {
                // 小月
                return 30;
            }
        }
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 得到某年某月的天数
     * @param {*} year
     * @param {*} month
     */
    function getDays(year, month) {
        if (month === 2) {
            return isLeap(year) ? 29 : 28;
        } else if (month < 8 && isOdd(month) || month >= 8 && !isOdd(month)) {
            return 31;
        } else {
            return 30;
        }
    }
</script>
<script>
    console.log(getDays(2020, 2)); // 29
    console.log(getDays(2020, 9)); // 30
</script>





<!-- 9. 写一个函数，得到某个数字数组中出现次数最多的数字和频率

函数名参考：getTopFreqInArray -->
<!-- Mr. Tao - 1 -->
<script>
    /**
     * 得到某个数字数组中出现次数最多的数字和频率
     * @param {Array} arr
     * @return {Object} key ==> 出现最多的数字 value ==> 出现的次数
     */
    function getTopFreqInArray(arr) {

        // 记录对象
        var obj = {};
        for (var i = 0; i < arr.length; i++) {
            if (obj[arr[i]]) {
                obj[arr[i]]++;
            } else {
                obj[arr[i]] = 1;
            }
        }
        // 结果对象
        // console.log(obj);
        var maxFre = obj[arr[0]],
            maxFreIndex = 0;
        for (var i = 1; i < arr.length; i++) {
            if (maxFre < obj[arr[i]]) {
                maxFreIndex = i;
                maxFre = obj[arr[i]];
            }
        }
        var resultObj = {
            num: +arr[maxFreIndex],
            fre: maxFre
        }
        return resultObj;
    }
</script>
<!-- Mr. Tao - 2 -->
<script>
    function getTopFreqInArray(arr) {
        var recordObj = {}; // 记录
        for (var i = 0; i < arr.length; i++) {
            if (recordObj[arr[i]]) {
                recordObj[arr[i]]++;
            } else {
                recordObj[arr[i]] = 1;
            }
        }
        // console.log(recordObj);
        var resultObj = {
            maxNum: arr[0],
            maxFre: recordObj[arr[0]]
        }; // 结果
        console.log();
        for (prop in recordObj) {
            if (recordObj[prop] > resultObj.maxFre) {
                resultObj = {
                    maxNum: prop,
                    maxFre: recordObj[prop]
                }
            }
        }
        return resultObj;
    }
</script>
<!-- Mr. Yuan -->
<script>
    /**
     * 得到数组中出现频率最高的数字和频率
     * 返回一个对象
     * @param {*} arr
     */
    function getTopFreqInArray(arr) {
        var records = {}; //记录出现频率
        for (var i = 0; i < arr.length; i++) {
            var n = arr[i];
            if (records[n]) {
                records[n]++;
            } else {
                records[n] = 1;
            }
        }
        var result; //记录最终结果的对象
        for (var prop in records) {
            if (!result || records[prop] > result.frequency) {
                result = {
                    number: +prop,
                    frequency: records[prop]
                };
            }
        }
        return result;
    }
</script>
<script>
    var arr = [1, 3, 2, 6, 6, 6, 7, 5, 2, 3];
    var obj = getTopFreqInArray(arr);
    console.log(`出现最多的数字是: ${obj.num}\t出现的次数是: ${obj.fre}次`);
</script>




<!-- =============================================== -->


<!-- # 函数使用 -->




<!-- 1. 利用上面的某些函数，实现哥德巴赫猜想

任一大于2的偶数都可写成两个质数之和，比如：8 = 3 + 5

让用户输入一个大于2的偶数，输出其等于哪两个素数相加 -->
<!-- Mr. Tao -->
<script>
    var inputNum = +prompt("请输入一个大于2的偶数: ");
    if (inputNum > 2) {
        // 随机生成两个满足条件的素数
        while (true) {
            var primeNum1 = Math.ceil(Math.random() * inputNum),
                primeNum2 = inputNum - primeNum1;
            if (isPrime(primeNum1) && isPrime(primeNum2)) {
                break;
            } else {
                continue;
            }
        }
        console.log(`${inputNum}=${primeNum1}+${primeNum2}`);
    } else {
        console.log("输入错误");
    }
</script>
<!-- Mr. Yuan 1.html -->
<script>
    function begin() {
        var num = +prompt("请输入一个大于2的偶数");
        if (isNaN(num) || num <= 2 || isOdd(num)) {
            console.log("输入有误");
            return;
        }
        //输入正确
        for (var i = 2; i <= num - 2; i++) {
            var j = num - i;
            //判断两个数字是否都是素数
            if (isPrime(i) && isPrime(j)) {
                console.log(`${num} = ${i} + ${j}`);
            }
        }
    }

    begin();
</script>


<!-- 2. 让用户输入一个年份，输出该年每个月的天数 -->
<!-- Mr. Tao -->
<script>
    var inputYear = +prompt("请输入一个年份: ");
    var sum = 0; // 统计这一年的总天数
    for (var i = 1; i <= 12; i++) {
        console.log(`${inputYear}年的${i}月 ==> ${getDays(inputYear, i)}天`);
        sum += getDays(inputYear, i);
    }
    console.log(`${inputYear}年的总天数 ==> ${sum}天`);
</script>
<!-- Mr. Yuan 2.html -->
<script>
    // function begin() {
    //     var year = +prompt("请输入一个年份（1990~2100）");
    //     if (isNaN(year) || year < 1990 || year > 2100) {
    //         console.log("输入有误");
    //         return;
    //     }
    //     //输入正确
    //     for (var m = 1; m <= 12; m++) {
    //         console.log(`${year}年${m}月：${getDays(year, m)}`);
    //     }
    // }

    // begin();

    (function begin() {
        var year = +prompt("请输入一个年份（1990~2100）");
        if (isNaN(year) || year < 1990 || year > 2100) {
            console.log("输入有误");
            return;
        }
        //输入正确
        for (var m = 1; m <= 12; m++) {
            console.log(`${year}年${m}月：${getDays(year, m)}`);
        }
    }());
</script>
```

## 3. 作用域和闭包

**作用域**

```
目前只介绍两种作用域 学到ES6后 再介绍第3种作用域
作用域表示一个代码区域，也表示一个运行环境
JS中，有两种作用域：
    1. 全局作用域
       直接在脚本中书写的代码
       在全局作用域中声明的变量，会被提升到脚本块的顶部，并且会成为全局对象的属性。
    2. 函数作用域
       函数中的代码
       在函数作用域中声明的变量，会被提升到函数的顶部，并且不会成为全局对象的属性.
       因此，函数中声明的变量不会导致全局对象的污染
       尽量的把功能封装在函数中
       但是，当函数成为一个表达式时，它既不会提升，也不会污染全局对象。
       将函数变为一个函数表达式的方式之一，将函数用小括号括起来。
       然而，这样一来，函数无法通过名称调用。
       如果书写一个函数表达式，然后将立即调用，该函数称之为立即执行函数 IIFE（Imdiately Invoked Function Expression）。
       由于大部分情况下，函数表达式的函数名没有实际意义，因此，可以省略函数名。
       没有名字的函数，称之为匿名函数
```

**作用域中可以使用的变量**

```
全局作用域只能使用全局作用域中声明的变量（包括函数）
函数作用域不仅能使用自身作用域中声明的变量（包括函数），还能使用外部环境的变量（包括函数）
注意: 外部环境 ≠ window
有的时候，某个函数比较复杂，在编写的过程，可能需要另外一些函数来辅助它完成一些功能，而这些函数仅仅会被该函数使用，不会在其他位置使用，则可以将这些函数声明到该函数的内部。
函数内部声明的变量和外部冲突时，使用内部的。
```

**闭包**

```
闭包(closure), 是一种现象，内部函数，可以使用外部函数环境中的变量。
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月13日</title>
</head>

<body>

    <!-- test1.html -->
    <script>
        // var a, b;
        var a = 234;
        var b = "234234";

        function test() {
            // var c, d;
            var c = 2342;
            var d = "345345345";
        }

        test();

        console.log("a" in window); // true
        console.log("b" in window); // true
        console.log("c" in window); // false
        console.log("d" in window); // false
    </script>

    <!-- test2.html -->
    <script>
        // 函数表达式 不会污染全局对象 window
        (function test() {
            var a = 1,
                b = 2,
                c = 3;
            console.log(a, b, c);
        });
        // test(); // test in not defined at ...
    </script>

    <script>
        // 立即执行函数
        (function () {
            var a = 1,
                b = 2,
                c = 3;
            console.log(a, b, c);
        }()); // () 可以放里面 也可以放外面
    </script>

    <script>
        // 立即执行函数
        (function () {
            var a = 1,
                b = 2,
                c = 3;
            console.log(a, b, c);
        })(); // () 可以放里面 也可以放外面
    </script>

    <!-- test3.html -->
    <script>
        // 里面的可以拿到外面的 外面的无法拿到里面的
        var g = "Abc";

        function A() {
            var a = 234;
            console.log(a, g); // 234 Abc

            function B() {
                var b = 567;
                console.log(b, a, g); // 567 234 Abc
            }

            B();
        }

        A();
    </script>





    <!-- test4.html -->
    <!-- 函数内可嵌套函数 -->
    <script>
        (function () {

            // 非常复杂，需要声明函数完成功能

            function helper1() {

            }

            function helper2() {

            }
        })();
    </script>

    <!-- test5.html -->
    <script>
        // 函数内部声明的变量和外部冲突时，使用内部的。
        // [这一块的内容比较复杂 在进阶课程会详细讲解]
        var test = "Asdfasf";
        var a = "abc";

        function B() {
            console.log('window');
        }

        function A() {
            var a = 'bcd';
            console.log(test); // "Asdfasf"
            function B() {
                console.log(a); // "bcd"
            }
            B();
        }

        A();
    </script>

    <script>
        var a = 0;

        function A() {
            var a = 1;

            function B() {
                console.log(a); // 1
                // 内部函数B 使用外部函数A 中的变量a
            }
            B();
        }
        A();
    </script>
</body>

</html>
```

## 4. 函数表达式和this

**函数表达式**

```
JS中，函数也是一个数据，语法上，函数可以用于任何需要数据的地方
JS中，函数是一等公民
函数是一个引用类型，将其赋值给某个变量时，变量中保存的是函数的地址
函数表达式的函数名可以省略 因为没有意义 没啥用
函数表达式的值就是函数本身
函数表达式不会提升 but 函数声明会提升
```

**this关键字**

```
在全局作用域中，this关键字固定指向全局对象。
在函数作用域中，取决于函数是如何被调用的
函数直接调用，this指向全局对象
通过一个对象的属性调用，格式为对象.属性()或对象["属性"]()，this指向对象
注意: this无法赋值
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月13日</title>
</head>

<body>
    <!-- test1.html -->
    <!-- 函数表达式 -->
    <script>
        var a; // 只提升了变量
        a(); // 函数声明不会提升 ==> 不可以在函数字面量之前调用函数 ==> a is not a function
        console.log(a); // undefined

        var a = function () { // 创建一个函数，将其赋值给变量a
            console.log("asdasdf");
        }
    </script>

    <script>
        var a = function () {
            console.log("asdasdf");
        }
        var b = a;
        console.log(a === b); // true
        b(); // asdasdf
    </script>

    <!-- 函数字面量 -->
    <script>
        a(); // 函数声明会提升 ==> 可以在函数字面量之前调用函数
        function a() {
            console.log("asdasdf");
        }
    </script>

    <script>
        function a() {
            console.log("asdasdf");
        }
        var b = a;
        console.log(a === b); // true
        b(); // asdasdf
    </script>


    <!-- test2.html -->
    <script>
        var obj = {
            a: "asfd",
            b: 234,
            c: function () {
                console.log("ccccc");
            },
            d: function () {
                console.log("dddd");
            }
        };

        console.log(obj.c, typeof obj.c); // f () {...} "function"

        var b = obj.c;
        b(); // ccccc
        obj.d(); // dddd
        // console.log ==> console 是一个对象 log 是该对象里面的一个属性 该属性的值是一个函数表达式
    </script>


    <!-- test3.html -->
    <script>
        var arr = [34, 45454, "Asdf", {}, function () {
            console.log("数组中的函数");
        }];

        var func = arr[4];
        func(); // "数组中的函数"
    </script>


    <!-- test4.html -->
    <!-- 回调函数 -->
    <script>
        function test(callback1, callback2) {
            console.log("test运行");
            callback1();
            callback2();
        }


        test(function () {
            console.log("1");
        }, function () {
            console.log("2");
        });
        // test(参数1,参数2);
        // 此时 参数1 和 参数2 都是函数表达式
        // 表达式的值就是函数本身
        // 就好比
        // var callback1 = function () {console.log("1");}
        // var callback2 = function () {console.log("2");}
    </script>

    <script>
        function test(obj) {
            obj.func1();
            obj.func2();
        }

        test({
            func1: function () {
                console.log("func1");
            },
            func2: function () {
                console.log("func2");
            }
        });
    </script>


    <!-- test5.html -->
    <!-- 在全局直接调用函数 -->
    <script>
        function test() {
            console.log(this);
        }

        var b = test;

        b(); // window
    </script>

    <!-- test6.html -->
    <!-- 通过对象的属性调用 -->
    <script>
        function test() {
            console.log(this);
        }

        var b = test;
        var arr = [b, test];
        arr[0](); // (2) [f, f]
        // this 指向数组 arr
    </script>

    <!-- [注意]在函数未被调用之前 this 的指向是未知的 this 的指向是在函数被调用的时候才确定的 -->
    <script>
        var obj = {
            a: function () {
                console.log(this);
            },
            b: {
                x: 2342,
                func: function () {
                    console.log(this);
                }
            }
        };

        obj.a(); // this ==> obj
        obj.b.func(); // this ==> obj.b
        var b = obj.a;
        b(); // this ==> window
    </script>


    <!-- test7.html -->
    <!-- 对象里面的函数建议不要拿出来放在全局中再调用 -->
    <script>
        var obj = {
            firstName: "袁",
            lastName: "进",
            age: 18,
            sayHello: function () {
                console.log(`我叫${this.firstName}${this.lastName}，今年${this.age}岁了`);
            }
        };
        var b = obj.sayHello;
        b(); // 我叫undefinedundefined，今年undefined岁了
    </script>

    <script>
        var obj = {
            firstName: "袁",
            lastName: "进",
            age: 18,
            sayHello: function () {
                console.log(`我叫${this.firstName}${this.lastName}，今年${this.age}岁了`);
            }
        };

        obj.sayHello(); // 我叫袁进，今年18岁了

        obj.firstName = "姬";
        obj.lastName = "成";
        obj.age = 108;
        obj.sayHello(); // 我叫姬成，今年108岁了
    </script>

    <!-- 写 this.firstName 而不直接写 obj.firstName 的原因 -->
    <script>
        var obj = {
            firstName: "袁",
            lastName: "进",
            age: 18,
            sayHello: function () {
                console.log(`我叫${this.firstName}${this.lastName}，今年${this.age}岁了`);
            }
        };

        var obj2 = obj;
        obj = 234;

        // 将变量保存一下 然后将它的值重新改变 这样的操作在开发中很常见
        obj.sayHello(); // Uncaught TypeError: obj.sayHello is not a function

        obj2.sayHello(); // 我叫袁进，今年18岁了
    </script>

    <script>
        var obj = {
            firstName: "袁",
            lastName: "进",
            age: 18,
            sayHello: function () {
                console.log(`我叫${obj.firstName}${obj.lastName}，今年${obj.age}岁了`);
            }
        };

        var obj2 = obj;
        obj = 234;

        obj2.firstName = "姬";
        obj2.lastName = "成";
        obj2.age = 108;
        obj2.sayHello(); // 我叫undefinedundefined，今年undefined岁了
    </script>
</body>

</html>
```

## 5. [作业讲解]函数表达式和this

```
新建一个BetterFunction.js,将之前的MyFunction.js改造成为单对象模式。
    注意: 函数调用处 需要在函数名前面加上 `this.`
本次作业的要点在于体验回调函数的使用
    就是把 事件处理函数a 以参数的形式 传递给另一个 事件处理函数b
    在 事件处理函数b 内部来调用 事件处理函数a
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月13日</title>
</head>

<body>
    <!-- 2. 写一个函数，为数组排序 要考虑到这个数组的所有可能 ==> sort -->
    <script>
        var MyFunctions = {
            sort: function (arr, compare) {
                // 若没有自定义的比较规则 则使用如下默认规则
                if (!compare) {
                    compare = function (a, b) {
                        if (a > b) {
                            return 1;
                        } else if (a === b) {
                            return 0;
                        } else {
                            return -1;
                        }
                        // return  a - b;
                    }
                }
                for (var i = 1; i < arr.length; i++) {
                    for (var j = 0; j < arr.length - i; j++) {
                        if (compare(arr[j], arr[j + 1]) > 0) {
                            var temp = arr[j];
                            arr[j] = arr[j + 1];
                            arr[j + 1] = temp;
                        }
                    }
                }
            }
        }

        var arr = [{
                name: 'b',
                age: 18,
                weight: 66
            },
            {
                name: 'a',
                age: 21,
                weight: 70
            },
            {
                name: 'd',
                age: 20,
                weight: 59
            },
        ];
        // console.log(arr);

        // 按体重升序
        MyFunctions.sort(arr, function (a, b) {
            return a.weight - b.weight;
        })

        // 按年龄升序
        MyFunctions.sort(arr, function (a, b) {
            return a.age - b.age;
        })

        // 按姓名的字符编码 升序
        MyFunctions.sort(arr, function (a, b) {
            if (a.name > b.name) {
                return 1;
            } else if (a.name === b.name) {
                return 0;
            } else {
                return -1;
            }
        })

        /* 比较规则的多样性 */
        MyFunctions.sort(arr, function (a, b) {
            return (a.age + a.weight) - (b.age + b.weight);
        })
    </script>

    <!-- 3. 写一个函数，按照指定的条件对某个数组进行筛选 ==> filter -->
    <script>
        var MyFunctions = {
            filter: function (arr, callback) {
                var newArr = [];
                for (var i = 0; i < arr.length; i++) {
                    if (callback(arr[i], i)) {
                        newArr.push(arr[i]);
                    }
                }
                return newArr;
            }
        }

        // 返回是奇数的项
        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357]
        var newArr = MyFunctions.filter(arr, function (item) {
            return item % 2 !== 0;
        });

        // 返回下标为奇数的项
        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357]
        var newArr = MyFunctions.filter(arr, function (item, index) {
            return index % 2 !== 0;
        });

        // 返回是素数的数
        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357];
        var newArr = MyFunctions.filter(arr, MyFunctions.isPrime);


        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357]
        var newArr = MyFunctions.filter(arr, this.Prime);
    </script>

    <!-- 4. 写一个函数，按照指定的条件，得到某个数组中第一个满足条件的元素 ==> find -->
    <script>
        var MyFunctions = {
            find: function (arr, callback) {
                for (var i = 0; i < arr.length; i++) {
                    if (callback(arr[i], i)) {
                        return arr[i];
                    }
                }
            }
        };

        // 查找数组中第一个能被15整除的项
        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357];
        var elm = MyFunctions.find(arr, function (item) {
            return item % 15 === 0;
        });

        // 查找数组中第一个素数
        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357];
        var elm = MyFunctions.find(arr, function (num) {
            if (num === 1) {
                return false;
            }
            if (num === 2) {
                return true;
            }
            for (var i = 2; i < num; i++) {
                if (num % i === 0) {
                    return false;
                }
            }
            return true;
        });

        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357];
        var elm = MyFunctions.find(arr, MyFunctions.isPrime);
    </script>

    <!-- 5. 写一个函数，按照指定的条件，得到某个数组中满足条件的元素数量 ==> count -->
    <script>
        var MyFunctions = {
            count: function (arr, callback) {
                var num = 0;
                for (var i = 0; i < arr.length; i++) {
                    if (callback(arr[i], i)) {
                        num++;
                    }
                }
                return num;
            }
        };

        // 统计数组中素数的个数
        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357];
        var num = MyFunctions.count(arr, function (num) {
            if (num === 1) {
                return false;
            }
            if (num === 2) {
                return true;
            }
            for (var i = 2; i < num; i++) {
                if (num % i === 0) {
                    return false;
                }
            }
            return true;
        });

        var arr = [13, 452, 656, 34546, 32, 345, 143, 547, 357];
        var num = MyFunctions.find(arr, MyFunctions.isPrime);
    </script>
</body>

</html>
```

## 6. 构造函数

> 对象中的属性，如果是一个函数，也称该属性为对象的方法

**用于创建对象的函数**

用函数创建对象，可以减少繁琐的对象创建流程

1. 函数返回一个对象
2. 构造函数：构造函数专门用于创建对象

```js
new 函数名(参数);
```

如果使用上面的格式创建对象，则该函数叫做构造函数。

1) 函数名使用大驼峰命名法

> 构造函数的命名尽量不要出现 v.(动词) new 表示 创建 已经有一个动词了
> > new CreateUser(); ==> new User();

2) ==构造函数内部，会自动创建一个新对象，this指向新创建的对象，并且自动返回新对象==

> 可以理解为 `this = {}` // 当然 这样的写法显然是不对的 因为 this 不能被赋值 但是可以这么理解

3) 构造函数中如果出现返回值，如果返回的是原始类型，则直接忽略；如果返回的是引用类型，则使用返回的结果
4) 所有的对象，最终都是通过构造函数创建的


**new.target**

该表达式在函数中使用，返回的是当前的构造函数，但是，如果该函数不是通过new调用的，则返回undefined

通常用于判断某个函数是否是通过new在调用。

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月17日</title>
</head>

<body>

    <!-- 创建一个用户 -->

    <!-- test1.html -->
    <script>
        function createUser(name, age, gender) {
            return {
                name, // name: name,
                age, // age: age,
                gender, // gender: gender,
                sayHello() { // sayHello: function() {...},
                    console.log(`我叫${this.name}，年龄${this.age}岁，性别${this.gender}`);
                }
            };
        }

        var u1 = createUser("张三", 18, "男");
        u1.sayHello(); // 我叫张三，年龄18岁，性别男
        var u2 = createUser("姬成", 20, "男");
        u2.sayHello(); // 我叫姬成，年龄20岁，性别男
        console.log(u1 === u2); // false
    </script>

    <!-- test2.html -->
    <script>
        function User(name, age, gender) {
            // 自动生成 this ==> 指向当前构造函数
            this.name = name;
            this.age = age;
            this.gender = gender;
            this.sayHello = function () {
                console.log(`我叫${this.name}，年龄${this.age}岁，性别${this.gender}`);
            }
            // return this;
        }

        var u1 = new User("张三", 18, "男");
        u1.sayHello(); // 我叫张三，年龄18岁，性别男
        var u2 = new User("姬成", 20, "男");
        u2.sayHello(); // 我叫姬成，年龄20岁，性别男

        console.log(u1 === u2); // false
    </script>



    <!-- test3.html -->
    <script>
        var arr = new Array(3, 4, 5);
    </script>

    <script>
        arr = [3, 5, 7, 2]; // 语法糖

        // 相当于

        var arr = new Array(3, 5, 7, 2);
    </script>

    <script>
        var obj = {
            name: "asdf",
            age: 234,
            gender: "男"
        };

        // 相当于

        var obj = new Object();
        obj.name = "asdf";
        obj.age = 234;
        obj.gender = "男";
    </script>



    <!-- test4.html -->
    <script>
        // 创建一个用户
        function User(name, age, gender) {
            var temp = function () {
                console.log(`我叫${this.name}，年龄${this.age}岁，性别${this.gender}`);
            };
            // 正常的构造函数调用
            if (new.target === User) {
                this.name = name;
                this.age = age;
                this.gender = gender;
                this.sayHello = temp;
            } else {
                // 构造函数当做普通函数调用 (兼容处理)
                return {
                    name,
                    age,
                    gender,
                    sayHello: temp
                }
            }
        }
        // 正常的构造函数调用
        var u1 = new User("ss", 18, "女");
        console.log(u1);
        // 将构造函数当做普通函数调用
        var u2 = User('sss', 108, '女');
        console.log(u2);

        // new Array(10);
        // Array(10);
        // 得到的结果是相同的 处理方式和这个User类似 加了一个 if-else 判断
    </script>
</body>

</html>
```

### 作业.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>2020年9月13日</title>
</head>

<body>
    <!-- Mr. Yuan -->
    <!-- 英雄打怪兽的小游戏

    英雄和怪兽都具有攻击力、防御力、生命值、暴击几率（暴击时伤害翻倍）

    攻击伤害 = 攻击力 - 防御力

    伤害最少为1.

    创建一个英雄和一个怪兽，让它们互相攻击，直到一方死亡，输出整个攻击过程。 -->
    <!-- <script src="./作业.js"></script> -->


    <!-- Mr. Tao -->
    <script>
        console.log("============游戏开始===========");

        function Charactor(name, attack, defence, hp, critRate) {
            this.name = name;
            this.attack = attack;
            this.defence = defence;
            this.hp = hp;
            this.critRate = critRate;

            this.print = function () {
                console.log(
                    `姓名: ${this.name} 攻击力: ${this.attack} 防御力: ${this.defence} 剩余生命值: ${this.hp} 暴击率: ${this.critRate}`
                );
            }

            this.hit = function (target) {
                var damage = this.attack - target.defence;

                // 判断是否有暴击
                var isCrit = this.critRate > Math.random();
                if (isCrit) {
                    damage *= 2;
                }

                // damage 最小是1
                if (damage < 1) {
                    damage = 1;
                }

                target.hp -= damage;

                if (target.hp < 0) {
                    target.hp = 0;
                }

                console.log(
                    `${isCrit ? "暴击！" : ""}【${this.name}】攻击【${target.name}】，造成【${damage}】点伤害，对方当前血量为【${target.hp}】`
                    );

                return target.hp === 0;
            }

        }

        var hero = new Charactor('hero', 100, 50, 1000, 0.5);
        hero.print();
        var monster = new Charactor('monster', 80, 70, 1100, 0.4);
        monster.print();

        while (1) {
            if (hero.hit(monster) || monster.hit(hero)) {
                break;
            }
        }

        hero.print();
        monster.print();

        console.log("============游戏结束===========");
    </script>
</body>

</html>
```

### 作业.js

```js
/**
 * 游戏角色的构造函数
 * @param {*} name 角色名
 * @param {*} attack 攻击力
 * @param {*} defence 防御力
 * @param {*} hp 生命值
 * @param {*} critRate 暴击率（0~100）
 */
function Charactor(name, attack, defence, hp, critRate) {
    this.name = name;
    this.attack = attack;
    this.defence = defence;
    this.hp = hp;
    this.critRate = critRate;

    //函数

    /**
     * 打印信息
     */
    this.print = function () {
        console.log(`${this.name}\t生命：${this.hp}\t攻击：${this.attack}\t防御：${this.defence}\t暴击率：${this.critRate}%`);
    }

    /**
     * 攻击，返回对方是否死亡
     * @param {*} ctor 攻击对象
     */
    this.hit = function (ctor) {
        var damage = this.attack - ctor.defence;
        //判断是否有暴击
        var rate = this.critRate / 100;
        var rad = Math.random();
        var isCrit = false; //是否暴击
        if (rad <= rate) {
            isCrit = true;
            //有暴击
            damage *= 2; //伤害翻倍
        }
        //伤害至少为1
        if (damage < 1) {
            damage = 1;
        }
        ctor.hp -= damage;
        if (ctor.hp < 0) {
            ctor.hp = 0;// 血量至少为0
        }
        console.log(`${isCrit ? "暴击！" : ""}【${this.name}】攻击【${ctor.name}】，造成【${damage}】点伤害，对方当前血量为【${ctor.hp}】`);
        //对方是否死亡
        return ctor.hp === 0;
    }
}
var hero = new Charactor("成哥", 100, 20, 500, 30);
hero.print();
console.log("VS");
var monster = new Charactor("邓哥", 120, 40, 400, 5);
monster.print();

while (true) {
    if (hero.hit(monster)) {
        break;
    }
    if (monster.hit(hero)) {
        break;
    }
}
console.log("=========================");
hero.print();
monster.print();
console.log("游戏结束");
```

## 7. 函数的本质


```
函数的本质就是对象。
某些教程中，将构造函数称之为构造器
所有的对象都是通过关键字new出来的，new 构造函数()
所有的函数，都是通过new Function创建。
由于函数本身就是对象，因此函数中，可以拥有各种属性。
```

**包装类**

```
JS为了增强原始类型的功能，为boolean、string、number分别创建了一个构造函数：
    1. Boolean
    2. String
    3. Number
如果语法上，将原始类型当作对象使用时（一般是在使用属性时），JS会自动在该位置利用对应的构造函数，创建对象来访问原始类型的属性。
```

```js
var a = 3.1415926535; // a 是原始类型 Number
console.log(a.toFixed(2)); // 将原始类型当做对象来使
// 等价于: console.log(new Number(3.1415926535).toFixed(2));
// 最终结果: 3.14
```

```
类：在JS中，可以认为，类就是构造函数
成员属性（方法）、实例属性（方法）：表示该属性是通过构造函数创建的对象调用的。
静态属性（方法）、类属性（方法）：表示该属性是通过构造函数本身调用的。
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月17日</title>
</head>

<body>

    <!-- test1.html -->
    <script>
        function sum(a, b) {
            return a + b;
        }

        console.log(typeof sum); // "function"
        console.log(sum(3, 5)); // 8
    </script>

    <script>
        var sum = new Function("a", "b", "return a+b");

        console.log(typeof sum); // "function"
        console.log(sum(3, 5)); // 8
    </script>


    <!-- test2.html -->
    <script>
        function User(firstName, lastName) {
            this.firstName = firstName;
            this.lastName = lastName;
            this.fullName = this.firstName + " " + this.lastName;
        }

        console.log(new User("袁", "进")); // User {firstName: "袁", lastName: "进", fullName: "袁 进"}
    </script>


    <!-- test3.html -->
    <script>
        function User(firstName, lastName) {
            this.firstName = firstName;
            this.lastName = lastName;
            this.fullName = this.firstName + " " + this.lastName;
        }

        User.abc = 123;
        console.log(User.abc); // 123


        User.test = function () {
            console.log(this.abc);
        }
        User.test(); // 123
    </script>


</body>

</html>
```

## 8. 递归

```
函数直接或间接调用自身

避免无限递归，无限递归会导致执行栈溢出。

对比死循环

- 死循环不会报错，也不会导致栈溢出
- 无限递归会导致栈溢出
```

**执行栈**

```
任何代码的执行都必须有一个执行环境，执行环境为代码的执行提供支持

执行环境是放到执行栈中的。

每个函数的调用，都需要创建一个函数的执行环境，函数调用结束，执行环境销毁。

执行栈有相对固定的大小，如果执行环境太多，执行栈无法容纳，会报错
```

**尾递归**

```
如果一个函数最后一条语句是调用函数，并且调用函数不是表达式的一部分，则该语句称为尾调用，如果尾调用是调用自身函数，则称为尾递归。

某些语言或执行环境会对尾调用进行优化，它们会理解销毁当前函数，避免执行栈空间被占用。

在浏览器执行环境中，尾调用没有优化。但在nodejs环境中有优化。
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月13日</title>
</head>

<body>
    <!-- 斐波拉契数列.html -->
    <script>
        //求斐波拉契数列第n位的值
        //1  1  2  3  5  8  13  21  ...
        //f(n) = f(n-1) + f(n-2)

        //斐波拉契数列的第n位
        function f(n) {
            if (n === 1 || n === 2) {
                return 1;
            }
            return f(n - 1) + f(n - 2);
        }

        console.log(f(5));
        // f(5) = f(4) + f(3)

        /* 下面开始求f(4) */
        // f(4) = f(3) + f(2)
        // f(3) = f(2) + f(1)
        // f(3) = 1 + f(1)
        // f(3) = 1 + 1
        // f(4) = 2 + f(2)
        // f(4) = 2 + 1
        // f(5) = 3 + f(3)

        /* 下面开始求f(3) */
        // f(3) = f(2) + f(1)
        // f(3) = 1 + f(1)
        // f(3) = 1 + 1
        // f(5) = 3 + 2
        // f(5) = 5
    </script>

    <!-- 执行栈.html -->
    <!-- 执行栈 call stack -->
    <script>
        // 一旦遇到函数调用 就会创建一个执行环境 结束后就销毁
        function A() {
            console.log("A begin"); // 2
            B();
            console.log("A over"); // 7
        }

        function B() {
            console.log("B begin"); // 3
            C();
            console.log("B over"); // 6
        }

        function C() {
            console.log("C begin"); // 4
            console.log("C over"); // 5
        }

        console.log("global begin"); // 1
        A();
        console.log("global over"); // 8
    </script>

    <!-- 阶乘.html -->
    <script>
        // 5! = 5*4*3*2*1
        // f(n)
        // f(1) = 1
        // f(2) = 2*f(1)
        // f(3) = 3*f(2)
        // n的阶乘 n!
        function fhelper(n, total) {
            if (n === 1) {
                return total;
            }
            // 注意递归的终止条件 若无限递归 则会溢出执行栈
            // Uncaught RangeError: Maximum call stack size exceeded
            return fhelper(n - 1, n * total);
        }

        function f(n) {
            return fhelper(n, 1);
        }

        console.log(f(5));

        // fhelper(5, 1) === fhelper(4, 5)
        // fhelper(4, 5) === fhelper(3, 20)
        // fhelper(3, 20) === fhelper(2, 60)
        // fhelper(2, 60) === fhelper(1, 120)
        // fhelper(1, 120) === 120
        // 尾递归优化: 最后一步直接返回结果
        // [but] 在浏览器中不会优化... 但在nodejs里面有
    </script>

    <!-- 无限循环和无限递归.html -->
    <script>
        // 死循环不会报错，也不会导致栈溢出 [会卡死 不会报错]
        function A() {
            while (true) {
                console.log("1");
            }
        }
        A();
    </script>

    <script>
        // 无限递归会导致栈溢出 [会报错 不会卡死]
        function A() {
            A();
        }

        A();
    </script>

    <!-- 汉诺塔.html -->
    <script>
        function hannuo(no1, no2, no3, n) {
            if (n === 1) {
                console.log(`${no1}->${no3}`);
            } else {
                hannuo(no1, no3, no2, n - 1);
                console.log(`${no1}->${no3}`);
                hannuo(no2, no1, no3, n - 1);
            }
        }

        hannuo('A', 'B', 'C', 5);
    </script>

</body>

</html>
```


# 六、标准库

```
本章的主要任务就是学会使用别人编写好的 API
```

## 1. Object和Function

**标准库（标准API）**

```
库：liberary
API：应用程序编程接口，Application Programing Interface
标准：ECMAScript标准
```

**Object**

```
1. 静态成员
   keys(某个对象)，得到某个对象的所有属性名数组
   values(某个对象)，得到某个对象的所有属性值数组
   entries(某个对象)，得到某个对象的所有属性名和属性值的数组
2. 实例成员
   实例成员可以被重写

   所有对象，都拥有Object的所有实例成员

   toString方法：得到某个对象的字符串格式
   默认情况下，该方法返回"[object Object]";

   valueOf方法：得到某个对象的值
   默认情况下，返回该对象本身

   在JS中，当自动的进行类型转换时，如果要对一个对象进行转换，实际上是先调用对象的valueOf方法，然后调用返回结果的toString方法，将得到的结果进行进一步转换。
```

**Function**

```
所有函数都具有Function中的实例成员

语法：arguments：在函数中使用，获取该函数调用时，传递的所有参数

arguments是一个类数组（也称为伪数组：没有通过Array构造函数创建的类似于数组结构的对象），伪数组会缺少大量的数组实例方法

arguments数组中的值，会与对应的形参映射

实例成员
   length属性，得到函数形参数量
   apply方法：调用函数，同时指定函数中的this指向，参数以数组传递
   call方法：调用函数，同时指定函数中的this指向，参数以列表传递
   bind方法：得到一个新函数，该函数中的this始终指向指定的值。
   通常，可以利用apply、call方法，将某个伪数组转换伪真数组。
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月14日</title>
</head>

<body>


    <!-- # 1. Object和Function

    [toc]

    ## 标准库（标准API）

    - 库：liberary
    - API：应用程序编程接口，Application Programing Interface
    - 标准：ECMAScript标准


    ## Object

    ### 静态成员(成员 包括 属性 + 方法)

    - keys(某个对象)，得到某个对象的所有属性名数组
    - values(某个对象)，得到某个对象的所有属性值数组
    - entries(某个对象)，得到某个对象的所有属性名和属性值的数组 -->



    <!-- test1.html -->
    <!-- 静态方法 通过构造函数来调用 -->
    <script>
        var obj = {
            x: 123,
            y: "Asdfaf",
            z: true
        };

        var arr = Object.keys(obj);
        console.log(arr); // (3) ["x", "y", "z"]
    </script>

    <script>
        var obj = [234, 65, 2, 2, 3444, 111];

        var arr = Object.values(obj);
        console.log(arr); // (6) [234, 65, 2, 2, 3444, 111]
    </script>

    <script>
        var obj = [234, 65, 2, 2, 3444, 111];

        var arr = Object.entries(obj);
        console.log(arr); // (6) [Array(2), Array(2), Array(2), Array(2), Array(2), Array(2)]
    </script>






    <!-- ### 实例成员

    > 实例成员可以被重写

    **所有对象，都拥有Object的所有实例成员**

    - toString方法：得到某个对象的字符串格式

    默认情况下，该方法返回"[object Object]"; -->



    <!-- test2.html -->
    <!-- 实例方法 通过构造函数所创建的实例对象来调用 -->
    <!-- 通过实例对象来调用实例方法 -->
    <script>
        var obj = {
            x: 1234,
            y: 'abcd'
        }

        console.log(obj.toString()); // "[object Object]"
    </script>

    <!-- 实例对象重写实例方法 -->
    <script>
        var obj = {
            x: 1234,
            y: 'abcd'
        }
        obj.toString = function () {
            return this.x + ',' + this.y;
        }

        console.log(obj.toString()); // "1234,abcd"
    </script>

    <!-- 所有对象，都拥有Object的所有实例成员 -->
    <script>
        var arr = [12, 3, 34, 2, 6, 245, 6];
        // 数组本质上也是一个对象

        console.log(arr.toString()); // "12,3,34,2,6,245,6"
        // 发现数组里面的 toString 输出结果和 对象的不同 说明数组中的 toString 方法被重写了
    </script>

    <!-- 基本包装类中的 Number 里面的toString也被重写了 -->
    <script>
        var num = new Number(123);

        console.log(num.toString()); // "123"
    </script>


    <!-- 模拟Number中的toString -->
    <script>
        function MyNumber(n) {
            // ...
            this.toSting = function () {
                return "" + n;
            };
        }

        var num = new MyNumber(234);
        console.log(num.toSting()); // "234"
    </script>

    <!-- 函数也是对象 ==> 函数也拥有 toSting 方法 -->
    <script>
        function MyNumber(n) {
            // ...
            this.toSting = function () {
                return "" + n;
            };
        }

        console.log(MyNumber.toSting());
        /*
        function MyNumber(n) {
            // ...
            this.toSting = function () {
                return "" + n;
            };
        }
        */
    </script>




    <!-- - valueOf方法：得到某个对象的值

    默认情况下，返回该对象本身

    > 在JS中，当自动的进行类型转换时，如果要对一个对象进行转换，实际上是先调用对象的valueOf方法，然后调用返回结果的toString方法，将得到的结果进行进一步转换。 -->




    <!-- test3.html -->
    <script>
        var obj = {
            x: 13,
            y: 34534,
        }

        console.log(obj.valueOf() === obj); // true
    </script>

    <!-- 模拟 Object 构造函数内部的 valueOf 方法 -->
    <script>
        var obj = {
            x: 13,
            y: 34534,
        }

        function Object() {
            this.valueOf = function () {
                return this;
            }
        }

        console.log(obj.valueOf() === obj); // true
    </script>


    <!-- 在JS中，当自动的进行类型转换时，如果要对一个对象进行转换，
        实际上是先调用对象的valueOf方法，
        然后调用返回结果的toString方法，
        将得到的结果进行进一步转换。 -->
    <script>
        var obj = {
            x: 13,
            y: 34534
        }

        console.log(obj + 1); // "[object Object]1"
        // console.log(obj.valueOf().toString() + 1); // "[object Object]1"
    </script>



    <script>
        var obj = {
            x: 13,
            y: 34534,
            toString() {
                return "hello";
            }
        }

        console.log(obj + 1); // "hello1"
        // 如果调用了valueOf已经得到了原始类型，则不再调用toString
        console.log(obj.valueOf().toString() + 1); // "hello1"
    </script>

    <!-- 面试题 -->
    <script>
        var obj = {
            x: 13,
            y: 34534,
            valueOf() {
                return 123;
            }
        }

        console.log(obj + 1); // 124
        // 知识点: 如果调用了valueOf已经得到了原始类型，则不再调用toString
        console.log(obj.valueOf().toString() + 1); // "1231"
    </script>





    <!-- ## Function

    **所有函数都具有Function中的实例成员**

    **语法：arguments：在函数中使用，获取该函数调用时，传递的所有参数**

    **arguments是一个类数组（也称为伪数组：没有通过Array构造函数创建的类似于数组结构的对象），伪数组会缺少大量的数组实例方法**

    **arguments数组中的值，会与对应的形参映射 [有传参 则有映射 否则没有映射]**

    ### 实例成员

    - length属性，得到函数形参数量
    - apply方法：调用函数，同时指定函数中的this指向，参数以数组传递
    - call方法：调用函数，同时指定函数中的this指向，参数以列表传递
    - bind方法：得到一个新函数，该函数中的this始终指向指定的值。

    通常，可以利用apply、call方法，将某个伪数组转换伪真数组。 -->




    <!-- test4.html -->
    <!-- 有传参 -->
    <script>
        var test = function abc(a, b) {
            arguments[0] = "abc";
            b = 123;

            console.log(a, b); // "abc" 123
            console.log(arguments); // Arguments(2) ["abc", 123, callee: ƒ, Symbol(Symbol.iterator): ƒ]
        }

        test(1, 2);
    </script>

    <!-- 不传参 -->
    <script>
        var test = function abc(a, b) {
            arguments[0] = "abc";
            b = 123;

            console.log(a, b); // undefined 123
            console.log(arguments); // Arguments [0: "abc", callee: ƒ, Symbol(Symbol.iterator): ƒ]
        }

        test();
    </script>

    <!-- 有传参 -->
    <script>
        var test = function abc(a, b) {
            arguments[0] = "abc";
            b = 123;

            console.log(a, b); // "abc" 123
            console.log(arguments); // Arguments(2) ["abc", 123, callee: ƒ, Symbol(Symbol.iterator): ƒ]
        }

        test(undefined, 2);
    </script>

    <!-- length属性，得到函数形参数量 -->
    <script>
        var test = function abc(a, b) {}
        console.log(test.length); // 2
    </script>


    <!-- 改变this指向.html -->
    <script>
        function sayHello(a, b) {
            console.log(this.name, this.age);
        }

        var user1 = {
            name: "asfd",
            age: 123
        };
        /* 要求打印user1中的name和age */

        sayHello(); // 因为 this ==> window 所以不行
        user1.sayHello(); // 因为 user1里面没有sayHello这个函数 所以不行
    </script>




    <!-- apply方法 ：调用函数，同时指定函数中的this指向，参数以数组传递 -->
    <!-- call方法：调用函数，同时指定函数中的this指向，参数以列表传递 -->
    <script>
        function sayHello(a, b) {
            console.log(this.name, this.age);
        }

        var user1 = {
            name: "asfd",
            age: 123
        };

        var user2 = {
            name: "546345",
            age: 11
        };

        sayHello.apply(user1); // "asfd" 123
        sayHello.call(user2); // "546345" 11
    </script>


    <script>
        function sayHello(a, b) {
            console.log(this.name, this.age);
            console.log(a, b);
        }

        var user1 = {
            name: "asfd",
            age: 123
        };

        var user2 = {
            name: "546345",
            age: 11
        };

        sayHello.apply(user1, [1, 2]);
        sayHello.call(user2, 1, 2);
    </script>


    <!-- bind方法：得到一个新函数，该函数中的this始终指向指定的值。 -->
    <script>
        function sayHello(a, b) {
            console.log(this.name, this.age);
            console.log(a, b);
        }

        var user1 = {
            name: "asfd",
            age: 123
        };

        var user2 = {
            name: "546345",
            age: 11
        };

        var newFunc = sayHello.bind(user1, 1, 2);
        newFunc();
        // "asfd" 123
        // 1 2
        var newFunc2 = sayHello.bind(user1);
        newFunc2(1, 2);
        // "asfd" 123
        // 1 2
    </script>

    <!-- test5.html -->
    <!-- 通常，可以利用apply、call方法，将某个伪数组转换伪真数组。 -->
    <script>
        function test() {
            console.log(arguments);
            //将arguments转换为真数组
            var newArr = [].slice.call(arguments)
            console.log(newArr);
        }

        test(23, 5, 6, 2, 233, 5, 6, 7);
    </script>

</body>

</html>
```

## 2. Array构造器

凡是通过Array构造函数创建的对象，都是数组

**静态成员**

- from方法：可以将一个伪数组转换为真数组
- isArray方法：判断一个给定的数据，是否为一个真数组
- of方法：类似于中括号创建数组，依次赋予数组每一项的值

**实例成员**

- fill方法：用某个数据填充数组
- pop
- push
- reverse：将当前数组颠倒顺序
- shift
- sort：对数组进行排序
- splice
- unshift

纯函数、无副作用函数：不会导致当前对象发生改变

- concat
- includes: 数组中是否包含满足条件的元素
- join
- slice
- indexOf
- lastIndexOf
- forEach: 遍历数组
- every：是否所有元素都满足条件
- some：是否至少有一个元素满足条件
- filter：过滤，得到满足条件的元素组成的新数组
- find: 查找第一个满足条件的元素，返回元素本身，如果没有找到，返回undefined
- findIndex: 查找第一个满足条件的元素，返回元素的下标
- map：映射，将数组的每一项映射称为另外一项
- reduce：统计，累计


[Array.prototype.reduce() mdn](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

![20210226102951](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226102951.png)

**作业**

var arr = [1, 2, 3, 4, 5, 6, -1, -2, -3, -4, -5, -6];

去掉数组中的负数，然后对每一项平方，然后再对每一项翻倍，然后求和 不许使用循环

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mr. Tao</title>
</head>

<body>
    <!--
        var arr = [1, 2, 3, 4, 5, 6, -1, -2, -3, -4, -5, -6];

    去掉数组中的负数，然后对每一项平方，然后再对每一项翻倍，然后求和 不许使用循环 -->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, -1, -2, -3, -4, -5, -6];
        var result = arr.filter(function (item) {
            return item >= 0;
        }).map(function (item) {
            return item * item;
        }).map(function (item) {
            return item * 2;
        }).reduce(function (sum, item) {
            return sum += item;
        }, 0)
        console.log(result);
    </script>
</body>

</html>
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月14日</title>
</head>

<body>
    <!-- test1.html -->
    <!-- from方法：可以将一个伪数组转换为真数组 -->
    <!-- isArray方法：判断一个给定的数据，是否为一个真数组 -->
    <script>
        function test() {
            console.log(arguments, Array.isArray(arguments));
            // Arguments(6) [1, 4, 6, 57, 89, 33, callee: ƒ, Symbol(Symbol.iterator): ƒ] false
            var newArr = Array.from(arguments);
            console.log(newArr, Array.isArray(newArr)); // (6) [1, 4, 6, 57, 89, 33] true
        }

        test(1, 4, 6, 57, 89, 33)
    </script>



    <!-- fill方法：用某个数据填充数组 -->
    <script>
        var arr = new Array(10)
        console.log(arr); // (10) [empty × 10]

        arr.fill("abc");
        console.log(arr); // (10) ["abc", "abc", "abc", "abc", "abc", "abc", "abc", "abc", "abc", "abc"]
    </script>


    <!-- reverse：将当前数组颠倒顺序 -->
    <script>
        var arr = [1, 2, 8, 34, 3, 3]
        arr.reverse();
        console.log(arr); //(6) [3, 3, 34, 8, 2, 1]
    </script>


    <!-- test2.html -->
    <!-- sort：对数组进行排序 -->
    <script>
        var arr = [3, 1, 2, 4, 6, 5];
        arr.sort();
        console.log(arr); // (6) [1, 2, 3, 4, 5, 6]
    </script>


    <script>
        var arr = [3, 211, 32, 11, 5, 4];
        arr.sort();
        console.log(arr); // (6) [11, 211, 3, 32, 4, 5]
    </script>



    <script>
        var arr = [3, 211, 32, 11, 5, 4];
        arr.sort(function (a, b) {
            return a - b; // a - b ==> 升序
            // return b - a; // b - a ==> 降序
        });
        console.log(arr); // (6) [3, 4, 5, 11, 32, 211]
    </script>


    <script>
        var arr = [3, 211, 32, 11, 5, 4];
        arr.sort(function (a, b) {
            return b - a;
        });
        console.log(arr); // (6) [211, 32, 11, 5, 4, 3]
    </script>


    <script>
        var arr = [3, 211, 32, 11, 5, 4];
        //随机打乱顺序(洗牌)
        arr.sort(function (a, b) {
            return Math.random() - 0.5;
        });
        console.log(arr); // (6) [3, 4, 32, 211, 5, 11]
    </script>




    <!-- 纯函数、无副作用函数：不会导致当前对象发生改变 -->

    <!-- test3.html -->
    <script>
        var arr1 = [1, 2, 3];
        var arr2 = [4, 5, 6];
        var arr3 = [7, 8, 9];

        var newArr = arr1.concat(arr2, arr3);
        console.log(newArr); // (9) [1, 2, 3, 4, 5, 6, 7, 8, 9]
        console.log(arr1); // (3) [1, 2, 3]
        console.log(arr2); // (3) [4, 5, 6]
        console.log(arr3); // (3) [7, 8, 9]
    </script>






    <!-- test4.html -->
    <!-- includes: 数组中是否包含满足条件的元素 -->
    <script>
        var arr = [32, 6, 67, 5, 23, 4];
        // 从数组下标3的位置开始寻找，目标是67
        console.log(arr.includes(67)); // true 从下标为0的位置开始找67
        console.log(arr.includes(67, 3)); // false 从下标为3的位置开始找67 // 从数字5开始
    </script>



    <script>
        // 对象没法找
        var arr = [{
                x: 1,
                y: 2
            },
            {
                x: 3,
                y: 4
            }
        ];

        console.log(arr.includes({
            x: 1,
            y: 2
        })); // false
    </script>




    <!-- 迭代方法 -->
    <!-- 可以接收三个参数 function (item, index, array) {} -->

    <!-- test5.html -->
    <!-- forEach: 遍历数组 -->
    <script>
        var arr = [234, 65, 2, 423, 5];
        arr.forEach(function (item) {
            console.log(item);
        });
    </script>






    <!-- test6.html -->
    <!-- every：是否所有元素都满足条件 -->
    <script>
        var arr = [77, 65, 68, 55, 80];
        // 判断是否所有同学都及格
        var result = arr.every(function (item) {
            return item >= 60;
        });
        console.log(result); // false
    </script>


    <!-- some：是否至少有一个元素满足条件 -->
    <script>
        var arr = [37, 25, 48, 55, 30];
        //判断是否至少有一个同学及格
        console.log(arr.some(function (item) {
            return item >= 60;
        })); // false
    </script>

    <!-- 小结
    every ==> 判 所有
    some ==> 判 存在
     -->



    <!-- test7.html -->
    <!-- filter：过滤，得到满足条件的元素组成的新数组 -->
    <script>
        var arr = [77, 25, 88, 55, 30];
        //得到所有及格的分数
        var newArr = arr.filter(function (item) {
            return item >= 60;
        });

        console.log(newArr); // (2) [77, 88]
    </script>




    <!-- test8.html -->
    <!-- findIndex: 查找第一个满足条件的元素，返回元素的下标 // 没找到 ==> -1 -->
    <script>
        var arr = [{
            name: "a",
            age: 11,
            score: 55
        }, {
            name: "b",
            age: 12,
            score: 65
        }, {
            name: "c",
            age: 22,
            score: 85
        }];
        // 得到及格的学生（找第一个的下标）
        var index = arr.findIndex(function (item) {
            return item.score >= 60
        });
        console.log(index); // 1
    </script>



    <!-- find: 查找第一个满足条件的元素，返回元素本身，如果没有找到，返回undefined -->
    <script>
        var arr = [{
            name: "a",
            age: 11,
            score: 55
        }, {
            name: "b",
            age: 12,
            score: 65
        }, {
            name: "c",
            age: 22,
            score: 85
        }];

        //得到及格的学生（找第一个）
        var result = arr.find(function (item) {
            return item.score >= 60
        });
        console.log(result); // {name: "b", age: 12, score: 65}
    </script>



    <script>
        var arr = [{
            name: "a",
            age: 11,
            score: 55
        }, {
            name: "b",
            age: 12,
            score: 65
        }, {
            name: "c",
            age: 22,
            score: 85
        }];

        //得到及格的学生
        var result = arr.filter(function (item) {
            return item.score >= 60
        });

        console.log(result); // (2) [{0: {name: "b", age: 12, score: 65}}, {1: {name: "c", age: 22, score: 85}}]
    </script>






    <!-- test9.html -->
    <!-- map：映射，将数组的每一项映射称为另外一项 -->

    <script>
        var arr = [55, 66, 22, 33, 44, 88];

        //得到一个新数组，新数组的每一项是一个对象
        //对象中包含两个属性：name、score

        var newArr = arr.map(function (item, i) {
            return {
                name: "学生" + (i + 1),
                score: item
            }
        });
        console.log(newArr); // (6) [{…}, {…}, {…}, {…}, {…}, {…}]
    </script>


    <script>
        var arr = [55, 66, 22, 33, 44, 88];
        var newArr = arr.map(function (item, i) {
            return {
                name: "学生" + (i + 1),
                score: item
            }
        });
        //得到一个学生的姓名数组
        newArr = newArr.map(function (item) {
            return item.name;
        });

        console.log(newArr); // (6) ["学生1", "学生2", "学生3", "学生4", "学生5", "学生6"]
    </script>



    <script>
        var arr = [55, 66, 22, 33, 44, 88];
        var newArr = arr.map(function (item, i) {
            return {
                name: "学生" + (i + 1),
                score: item
            }
        }).map(function (item) {
            return item.name;
        });

        console.log(newArr); // (6) ["学生1", "学生2", "学生3", "学生4", "学生5", "学生6"]
    </script>



    <!-- test10.html -->
    <!-- reduce：统计，累计 -->
    <script>
        var arr = [1, 2, 5, 3];

        var sum = arr.reduce(function (s, item) {
            console.log("回调", s, item);
            return s + item;
        }, 0); // 第二个参数 0 作为一个初始值传给 s
        // 第二个参数可以防止数组为空 ==> error
        // 如果写了第二个参数 那么当数组为空时 直接将第二个参数作为结果返回
        console.log(sum); // 11

        /*
         回调 0 1
         回调 1 2
         回调 3 5
         回调 8 3 // 表达式的值 ==> 最后一次 return 的结果
         11
        */
    </script>






    <!-- test11.html -->
    <!-- 链式编程：每一个函数调用返回的类型一致 -->
    <script>
        var arr = [22, 33, 44, 55, 66, 77, 88];

        // 先对数组进行随机排序
        // 只取及格的分数
        // 得到学生对象的数组（每个学生对象包含姓名和分数）

        var result = arr.sort(function () {
            return Math.random() - 0.5;
        }).filter(function (item) {
            return item >= 60;
        }).map(function (item, i) {
            return {
                name: `学生${i+1}`,
                score: item
            }
        });
        console.log(result); // (3) [{…}, {…}, {…}]
        /*
        0: {name: "学生1", score: 77}
        1: {name: "学生2", score: 66}
        2: {name: "学生3", score: 88}
        length: 3
        */
    </script>


</body>

</html>

```

## 3. [作业讲解]Array构造器

**作业**

var arr = [1, 2, 3, 4, 5, 6, -1, -2, -3, -4, -5, -6];

去掉数组中的负数，然后对每一项平方，然后再对每一项翻倍，然后求和 不许使用循环

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mr. Tao</title>
</head>

<body>
    <!--
        var arr = [1, 2, 3, 4, 5, 6, -1, -2, -3, -4, -5, -6];

    去掉数组中的负数，然后对每一项平方，然后再对每一项翻倍，然后求和 不许使用循环 -->
    <script>
        var arr = [1, 2, 3, 4, 5, 6, -1, -2, -3, -4, -5, -6];
        var result = arr.filter(function (item) {
            return item >= 0;
        }).map(function (item) {
            return item * item;
        }).map(function (item) {
            return item * 2;
        }).reduce(function (sum, item) {
            return sum += item;
        }, 0)
        console.log(result); // 182
    </script>
</body>

</html>
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Mr. Yuan</title>
</head>

<body>
    <script>
        var arr = [1, 2, 3, 4, 5, 6, -1, -2, -3, -4, -5, -6];
        // 去掉数组中的负数， 然后对每一项平方， 然后再对每一项翻倍， 然后求和
        // 不许使用循环

        var result = arr.filter(function(item) {
            return item >= 0;
        }).map(function(item) {
            return item ** 2;
        }).map(function(item) {
            return item * 2;
        }).reduce(function(s, item) {
            return s + item;
        }, 0);

        console.log(result); // 182
    </script>
</body>

</html>
```

## 4. 原始类型包装器

```
- new 包装器(值)：返回的是一个对象
- 包装器(值)：返回的是一个原始类型
```

**Number**

```
1. 静态成员
   isNaN
   isFinite
   isInteger：判断一个数据是否是整数
   parseFloat: 将一个数据转换为小数
   parseInt：将以一个数据转换为整数，直接舍去小数部分
   parseInt、parseFloat要求参数是一个字符串，如果不是字符串，则会先转换为字符串。
   从字符串开始位置进行查找，找到第一个有效的数字进行转换，如果没有找到，则返回NaN，左右空白字符会忽略

   parseInt，可以传入第二个参数，表示将给定的字符串，识别为多少进制。

2. 实例成员
   toFixed方法：会有四舍五入
   toPrecision：以指定的精度返回一个数字字符串
```

**Boolean**

```
...
```

**String**

```
1. 静态成员
   fromCharCode：通过unicode编码创建字符串
2. 实例成员
   length：字符串长度
   字符串是一个伪数组

   charAt：得到指定位置的字符
   var s = "abc";
   s.cahrAt(0); // "a"
   s[0]; // "a"
   // 区别
   s.charAt(10); // ""
   s[10]; // undefined
   charCodeAt
   concat
   includes
   endsWith
   startsWith
   indexOf
   lastIndexOf
   padStart
   padEnd
   repeat
   slice：从某个位置取到某个位置；位置可以是负数；
   substr: 从某个位置开始取，取指定的长度；位置可以是负数；
   substring：从某个位置取到某个位置；不可以是负数；参数位置是可调换的。
   toLowerCase
   toUpperCase
   split：分割字符串
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月17日</title>
</head>

<body>

    <!-- test.html -->
    <script>
        var a = 111.123;
        var num = a.toFixed(2);
        // new Number(a).toFixed(2);
        console.log(num); // 111.12
    </script>


    <!-- window 里面也有 isNaN -->
    <script>
        console.log(Number.isNaN); // ƒ isNaN() { [native code] }
        console.log(isNaN); // ƒ isNaN() { [native code] }
        console.log(Number.isNaN === isNaN); // false
        console.log(isNaN === window.isNaN); // true
    </script>






    <!-- 随机数.html -->
    <script>
        var MyFunctions = {
            getRandom: function (min, max) {
                return Math.floor(Math.random() * (max - min + 1) + min);
            }
        }
        console.log(MyFunctions.getRandom(5, 8));
    </script>

    <!-- 以下是常见的问题写法 -->
    <script>
        var MyFunctions = {
            getRandom: function (min, max) {
                return parseInt(Math.random() * (max - min) + min); // 取不到最大值 [若是负数 会有bug]
                // return parseInt(Math.random() * (max + 1 - min) + min); // 可取最大值
            }
        }
        console.log(MyFunctions.getRandom(5, 8)); // 5 或 6 或 7
    </script>


    <script>
        var MyFunctions = {
            // Math.floor() 向左取整
            getRandom: function (min, max) {
                return Math.floor(Math.random() * (max - min) + min); // 取不到最大值 [负数 也一样]
                // return parseInt(Math.random() * (max + 1 - min) + min); // 可取最大值
            }
        }
        console.log(MyFunctions.getRandom(5, 8)); // 5 或 6 或 7
    </script>


    <!-- test2.html -->
    <script>
        console.log(`abc
def`);
        /*
abc
def
        */

        console.log(`abc\
def`); // abcdef

        console.log("abcdef"); // abcdef
        console.log("abc\
def"); // abcdef

        // 下面这种写法是错误的
        /*
        console.log("abc
def");
        */
    </script>

    <script>
        // String.fromCharCode() 将字符编码转换成字符
        var str = "";
        for (var i = 65; i < 65 + 26; i++) {
            str += String.fromCharCode(i);
        }
        console.log(str); // "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    </script>




    <!-- 随机字符串 ==> 指定长度的 由字母(包括大小写)和数字组成的  -->
    <script>
        var MyFunctions = {
            getRandom: function (min, max) {
                return Math.floor(Math.random() * (max - min + 1) + min);
            },
            getRanString: function (len) {
                var temp = "",
                    str = "";
                for (var i = 65; i < 65 + 26; i++) {
                    temp += String.fromCharCode(i);
                }
                for (var i = 97; i < 97 + 26; i++) {
                    temp += String.fromCharCode(i);
                }
                for (var i = 48; i < 48 + 10; i++) {
                    temp += String.fromCharCode(i);
                }
                for (var i = 0; i < len; i++) {
                    str += temp[this.getRandom(0, 26 + 26 + 10 - 1)];
                }
                return str;
            }
        }
        for (var i = 0; i < 10; i++) {
            console.log(MyFunctions.getRanString(5));
        }
    </script>


    <!-- 字符串其实就是一个伪数组 -->
    <script>
        var str = "a撒旦发";
        // 控制台输入 new String("a撒旦发"); // 查看返回值
        for (var i = 0; i < str.length; i++) {
            console.log(str[i]);
        }
    </script>

    <script>
        var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        for (var i = 0; i < str.length; i++) {
            console.log(str[i]); // 依次输出 A 到 Z
        }
    </script>

    <script>
        var hour = 12,
            minute = 8,
            second = 20;

        console.log(`${hour.toString().padStart(2, "0")}:\
${minute.toString().padStart(2, "0")}:\
${second.toString().padStart(2, "0")}`); // 02:08:20
    </script>


    <!-- 实例方法 ==> padStart示例 -->
    <script>
        'abc'.padStart(10); // "       abc"
        'abc'.padStart(10, "foo"); // "foofoofabc"
        'abc'.padStart(6, "123465"); // "123abc"
        'abc'.padStart(8, "0"); // "00000abc"
        'abc'.padStart(1); // "abc"
    </script>

</body>

</html>
```

## 5. [作业讲解]原始类型包装器

以下练习可以使用之前书写的通用函数

1. 找到某个字符串中出现最多的字符，打印字符和它出现的次数

```html
    <script>
        var s = "absadfgsDfafgsdfgsdfgsadfasdasvasdfsadfasdfa"; // 字符串本质上是一个数组
        // 将s变成数组
        var arr = Array.from(s); // Array.from() ==> 伪数组 转 真正数组
        var obj = MyFunctions.getTopFreqInArray(arr);
        console.log(obj);
    </script>
```

2. 将一个字符串中单词之间的空格去掉，然后把每个单词首字母转换成大写

比如："hello world"  ->  "HelloWorld"  大驼峰命名法

```html
    <script>
        var s = "hello      woRld        js";

        function bigCamel(s) {
            var result = "";
            var empties = " \t\r\n"; //记录所有的空白字符
            for (var i = 0; i < s.length; i++) {
                if (!empties.includes(s[i])) {
                    //判断s[i]是否是首字母 ==> s[i-1]是否是空白字符
                    if (empties.includes(s[i - 1]) || i === 0) {
                        result += s[i].toUpperCase();
                    } else {
                        result += s[i];
                    }
                }
            }
            return result;
        }
        console.log(bigCamel(s));
    </script>
```

```html
    <script>
        // 目前只要求考虑空格
        var s = "hello      woRld        js";

        function bigCamel(s) {
            return s.split(" ").filter(function (item) {
                return item.length > 0;
            }).map(function (item) {
                return item[0].toUpperCase() + item.substring(1).toLowerCase();
            }).join("");
        }

        console.log(bigCamel(s));
    </script>
```

3. 书写一个函数，产生一个指定长度的随机字符串，字符串中只能包含大写字母、小写字母、数字

```html
    <script>
        function getRandomString(len) {
            var template = "";
            for (var i = 65; i < 65 + 26; i++) {
                template += String.fromCharCode(i);
            }
            for (var i = 97; i < 97 + 26; i++) {
                template += String.fromCharCode(i);
            }
            for (var i = 48; i < 48 + 10; i++) {
                template += String.fromCharCode(i);
            }

            var result = "";
            for (var i = 0; i < len; i++) {
                //从模板中随机取出一位字符
                var index = MyFunctions.getRandom(0, template.length);
                result += template[index];
            }
            return result;
        }

        console.log(getRandomString(20));
    </script>
```

4. 将字符串按照字符编码的顺序重新升序排序

```html
    <script>
        var s = "bffdgwfafagfdgsfafa";
        var result = Array.from(s).sort().join("");
        console.log(result);
    </script>
```

> 如果是降序

```html
    <script>
        var s = "bffdgwfafagfdgsfafa";
        var result = Array.from(s).sort().reverse().join("");
        console.log(result);
    </script>
```

5. 从一个标准的身份证号中取出用户的出生年月日和性别，保存到对象中

> 例如，"524713199703020014"
>
> 得到对象：
>
> birthYear: 1997
>
> birthMonth: 3
>
> birthDay: 2
>
> gender: "男"  // 性别看倒数第二位，奇数为男，偶数为女

```html
    <script>
        function getInfoFromPID(pid) {
            return {
                birthYear: parseInt(pid.substr(6, 4)),
                birthMonth: parseInt(pid.substr(10, 2)),
                birthDay: parseInt(pid.substr(12, 2)),
                gender: pid[pid.length - 2] % 2 === 0 ? "女" : "男"
            }
        }

        console.log(getInfoFromPID("524713199703020014"));
    </script>
```

## 6. Math对象

```
提供了一系列与数学相关的成员

常量：永远不会变化的数据。常量一般命名时所有字母大写，如果有多个单词，用下划线分割。

random方法: 产生一个0~1之间的随机数
PI属性：得到圆周率
abs方法：求绝对值
floor方法：对一个数向下取整
ceil方法：对一个数向上取整
max方法：得到一组数字的最大值；如果无参，得到-Infinity
min方法：得到一组数字的最小值；如果无参，得到Infinity
pow方法：求一个数字的幂次方
round方法：得到一个四舍五入的整数
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月15日</title>
</head>

<body>

    <!-- Math 是对象  不是构造函数 -->
    <script>
        // Math对象
        console.log(typeof Math); // "object"
    </script>

    <!-- PI属性：得到圆周率 -->
    <script>
        console.log(Math.PI); // 3.141592653589793
        // 常量：永远不会变化的数据。常量一般命名时所有字母大写，如果有多个单词，用下划线分割。
    </script>

    <!-- Math 对象上的常用方法 -->
    <script>
        // random方法: 产生一个0~1 之间的随机数


        // abs方法： 求绝对值
        console.log(Math.abs(-1)); // 1


        // floor方法： 对一个数向下取整
        Math.floor(1.2); // 1
        parseInt(1.2); // 1
        /* Math.floor() 和 parseInt() 正数两者等效 但负数则不同 */
        Math.floor(-1.2); // -2
        parseInt(-1.2); // -1


        // ceil方法： 对一个数向上取整


        // max方法： 得到一组数字的最大值； 如果无参， 得到 - Infinity
        console.log(Math.max()); // -Infinity
        console.log(Math.max(1, 2, 32, 11, 52, 63)); // 63

        // min方法： 得到一组数字的最小值； 如果无参， 得到 Infinity
        console.log(Math.min()); // Infinity
        console.log(Math.min(1, 2, 32, 11, 52, 63)); // 1

        // pow方法： 求一个数字的幂次方
        console.log(Math.pow(2, 3)); // 8
        console.log(2 ** 3); // 8

        // round方法： 得到一个四舍五入的整数
        Math.round(0.5); // 1
        Math.round(1.2); // 1
        Math.round(-1.5); // -1
        Math.round(-1.4); // -1
    </script>


</body>

</html>
```

## 7. Date构造器

**术语**

```
1. 时间单位
   年（year）
   月（month）
   日（date）
   小时（hour）
   分钟（minute）
   秒（second） = 1000ms
   毫秒（millisecond，ms） = 1000 us
   微秒（microsecond，us） = 1000 ns
   纳秒（nanosecond，ns）

2. UTC和GMT
   世界划分为24个时区，北京在东8区，格林威治在0时区。
   GMT：Greenwish Mean Time 格林威治世界时。太阳时，精确到毫秒。
   UTC：Universal Time Coodinated 世界协调时。以原子时间为计时标准，精确到纳秒。
   UTC和GMT之间误差不超过0.9秒
   GMT+0800 东8区

3. 时间戳
   数字
   1970-1-1 凌晨 到 某个时刻 所经过的毫秒数
```

**创建时间对象**

```
直接调用函数（不适用new），忽略所有参数，直接返回当前时间的字符串。
new Date(): 创建日期对象
无参，当前时间
1个参数，参数为数字，表示传入的是时间戳
两个参数以上，分别表示：年、月、日、时、分、秒、毫秒
注意：月份的数字从0开始计算。

如果缺失参数，日期部分默认为1，时分秒毫秒默认为0。

月、日、时、分、秒、毫秒，均可以传递负数，如果传递负数，会根据指定日期进行计算。
```

**实例成员**

```
getDate方法：得到日期部分

getDay方法：得到星期几，0表示星期天

getFullYear方法：得到年份

getHours方法：得到小时部分

getMinutes方法：得到分钟部分

getSeconds方法：得到秒部分

getMilliseconds方法：得到毫秒部分

getTime方法：得到时间戳

getMonth方法：得到月，从0开始计算

setDate方法：设置日期

setMonth方法：设置月份

setFullYear方法：设置年

setMinutes方法

setSeconds方法

setMilliseconds方法

setTime方法：重新设置时间戳

toDateString方法：将日期部分转换为可读的字符串。

toISOString方法：将整个对象转换为ISO标准的字符串格式。

toLocaleDateString方法：根据当前系统的地区设置，将日期部分转换为可读的字符串

toLocaleString方法：根据当前系统的地区设置，将整个日期对象转换为可读的字符串

toLocaleTimeString方法：根据当前系统的地区设置，将时间部分转换为可读的字符串
```

**日期的运算**

```
日期对象重写了Object中的valueOf方法，返回的是一个数字，表示时间戳

因此，日期对象可以进行数学运算
```

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月15日</title>
</head>

<body>
    <!-- 创建时间对象 -->
    <!-- test.html -->
    <script>
        // 直接调用函数（不适用new），忽略所有参数，直接返回当前时间的 字符串(注意 是字符串 而非实例对象) 。
        var now = Date();
        console.log(now); // Tue Sep 15 2020 19:30:51 GMT+0800 (中国标准时间)
    </script>

    <script>
        // new Date(): 创建日期对象
        // 1. 无参， 当前时间
        var d = new Date();
        console.log(d); // Tue Sep 15 2020 19:34:11 GMT+0800 (中国标准时间)

        // 2. 1个参数， 参数为数字， 表示传入的是时间戳
        var d = new Date(1000);
        console.log(d); // Thu Jan 01 1970 08:00:01 GMT+0800 (中国标准时间)

        var d = new Date(-1000);
        console.log(d); // Thu Jan 01 1970 07:59:59 GMT+0800 (中国标准时间)
        /* 因为将格林威治时间转换成了北京时间 所以在初始时间的基础上 加了8小时 */

        // 3. 两个参数及以上， 分别表示： 年、 月、 日、 时、 分、 秒、 毫秒
        var d = new Date(2015, 5, 1, 13, 14, 15, 200); // 这里传入的时间是北京时间
        console.log(d); // Mon Jun 01 2015 13:14:15 GMT+0800 (中国标准时间)

        /* 注意：月份的数字从0开始计算。
        如果缺失参数，日期部分默认为1，时分秒毫秒默认为0。 */

        var d = new Date(2015, 5);
        console.log(d); // Mon Jun 01 2015 00:00:00 GMT+0800 (中国标准时间)

        // 月、日、时、分、秒、毫秒，均可以传递负数，如果传递负数，会根据指定日期进行计算。
        var d = new Date(2015, 0, 1);
        console.log(d); // Thu Jan 01 2015 00:00:00 GMT+0800 (中国标准时间)

        /* 日期是从1开始的 */
        var d = new Date(2015, 0, 0); // 提前1天
        console.log(d); // Wed Dec 31 2014 00:00:00 GMT+0800 (中国标准时间)


        var d = new Date(2015, 0, -1); // 提前2天
        console.log(d); // Tue Dec 30 2014 00:00:00 GMT+0800 (中国标准时间)
    </script>


    <!-- 实例成员 -->
    <!-- get -->
    <script>
        var d = new Date();
        // getDate方法： 得到日期部分(1-31)
        console.log(d.getDate()); // 15
        // getDay方法： 得到星期几(0-6)， 0 表示星期天
        console.log(d.getDay()); // 2 ==> 周三
        // getFullYear方法： 得到年份
        console.log(d.getFullYear()); // 2020
        // getHours方法： 得到小时部分
        console.log(d.getHours()); // 19 ==> 晚上7点
        // getMinutes方法： 得到分钟部分
        console.log(d.getMinutes()); // 48 ==> 48分
        // getSeconds方法： 得到秒部分
        console.log(d.getSeconds()); // 10 ==> 10秒
        // getMilliseconds方法： 得到毫秒部分
        console.log(d.getMilliseconds()); // 588 ==> 588毫秒
        // getTime方法： 得到时间戳
        console.log(d.getTime()); // 1600170490588
        // getMonth方法： 得到月， 从0开始计算
        console.log(d.getMonth()); // 8 ==> 9月
    </script>

    <!-- set -->
    <script>
        var d = new Date();
        console.log(d); // Tue Sep 15 2020 19:51:31 GMT+0800 (中国标准时间)
        // setDate方法： 设置日期
        console.log(d.setDate(14)); // 1600084394946
        console.log(d); // Mon Sep 14 2020 19:53:14 GMT+0800 (中国标准时间)
        // setMonth方法： 设置月份
        // setFullYear方法： 设置年(也可以同时设置年月日)
        // setMinutes方法
        // setSeconds方法
        // setMilliseconds方法
        // setTime方法： 重新设置时间戳
    </script>

    <!-- 转换为字符串 -->
    <script>
        var d = new Date();
        // toDateString方法： 将日期部分转换为可读的字符串。
        console.log(d.toDateString()); // Tue Sep 15 2020
        // toISOString方法： 将整个对象转换为ISO标准的字符串格式。
        console.log(d.toISOString()); // 2020-09-15T11:57:53.979Z
        // toLocaleDateString方法： 根据当前系统的地区设置， 将日期部分转换为可读的字符串
        console.log(d.toLocaleDateString()); // 2020/9/15
        // toLocaleString方法： 根据当前系统的地区设置， 将整个日期对象转换为可读的字符串
        console.log(d.toLocaleString()); // 2020/9/15 下午7:57:53
        // toLocaleTimeString方法： 根据当前系统的地区设置， 将时间部分转换为可读的字符串
        console.log(d.toLocaleTimeString()); // 下午7:57:53
    </script>


    <!-- 友好的日期字符串.html -->
    <script>
        // 年-月-日 时:分:秒
        function getDateString(date) {
            var year = date.getFullYear().toString().padStart(4, "0");
            var month = (date.getMonth() + 1).toString().padStart(2, "0");
            var day = date.getDate().toString().padStart(2, "0");

            var hour = date.getHours().toString().padStart(2, "0");
            var minute = date.getMinutes().toString().padStart(2, "0");
            var second = date.getSeconds().toString().padStart(2, "0");

            return `${year}-${month}-${day} ${hour}:${minute}:${second}`;
        }

        console.log(getDateString(new Date())); // 2020-09-15 20:00:08
    </script>

    <!-- 日期的运算 -->

    <!-- 日期对象重写了Object中的valueOf方法，返回的是一个数字，表示时间戳 ==> 日期对象可以进行数学运算 -->
    <script>
        var d = new Date();
        console.log(d); // Tue Sep 15 2020 20:11:38 GMT+0800 (中国标准时间)
        d.setTime(d.valueOf() + 24 * 60 * 60 * 1000);
        console.log(d); // Wed Sep 16 2020 20:11:38 GMT+0800 (中国标准时间)
    </script>

    <script>
        var d = new Date();
        console.log(d); // Tue Sep 15 2020 20:11:38 GMT+0800 (中国标准时间)

        d.setTime(d.getDate() + 1); // d.getDate() + 1 ==> 16
        console.log(d); // Thu Jan 01 1970 08:00:00 GMT+0800 (中国标准时间)
    </script>


</body>

</html>
```

**作业**
```
1. 编写一个函数，用于返回一个友好的日期字符串格式

   年-月-日 时:分:秒

2. 给定用户的生日（年、月、日），计算该用户的年龄

3. 根据系统当前的月份，输出这一个月每一天的星期

   2019年6月1日：星期六
   2019年6月2日：星期日
   .....
   2019年6月30日：星期日
```

## 8. [作业讲解]Date构造器

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2020年9月17日</title>
</head>

<body>

    <script src="./Myfunctions.js"></script>

    <!-- 1. 编写一个函数，用于返回一个友好的日期字符串格式

    年-月-日 时:分:秒 -->
    <script>
        function getDateString(date) {
            var year = date.getFullYear().toString().padStart(4, "0");
            var month = (date.getMonth() + 1).toString().padStart(2, "0");
            var day = date.getDate().toString().padStart(2, "0");

            var hour = date.getHours().toString().padStart(2, "0");
            var minute = date.getMinutes().toString().padStart(2, "0");
            var second = date.getSeconds().toString().padStart(2, "0");

            return `${year}-${month}-${day} ${hour}:${minute}:${second}`;
        }

        var now = new Date();
        console.log(getDateString(now)); // 2020-09-16 12:35:31
    </script>




    <!-- 2. 给定用户的生日（年、月、日），计算该用户的年龄 -->
    <script>
        var MyFunctions = {
            isLeap: function (year) {
                return (year % 4 === 0 && year % 100 !== 0) || year % 400 === 0;
            },
            getAge: function (year, month, day) {
                //得到当前日期
                var now = new Date();
                var nowAge = now.getFullYear() - year; // 默认生日已过
                // 处理闰年 ==> 若生日是在闰年的2月29号 那么默认在平年时 生日是 2月28号
                if (month === 2 && day === 29 && !this.isLeap(now.getFullYear())) {
                    // 条件1: month === 2 && day === 29 在闰年的2月29号出生
                    // 条件2: !this.isLeap(now.getFullYear()) 今年是平年
                    // [平年也得过生日 若是在平年 那么把生日给改成 2月28号]
                    day = 28;
                }
                // 得到今年的生日
                var birthdayThisYear = new Date(now.getFullYear(), month - 1, day);
                // 目前还没到生日那天
                if (now < birthdayThisYear) {
                    nowAge--;
                }
                return nowAge;
            }
        }

        console.log(MyFunctions.getAge(2000, 2, 29));
    </script>



    <!-- 2.1 计算还有多少天过生日 -->
    <script>
        function getDaysToBirthday(month, day) {
            // var thisYear = new Date().getFullYear();
            var now = new Date();
            var thisYear = now.getFullYear();

            // 今年的生日
            var birthdayThisYear = new Date(thisYear, month - 1, day);
            // 生日已过
            if (birthdayThisYear < now) {
                // 生日过了  那么下一个生日就是下一年
                birthdayThisYear.setFullYear(now.getFullYear() + 1);
            }
            var timeDec = birthdayThisYear - now;
            var days = timeDec / (24 * 60 * 60 * 1000);
            return Math.ceil(days);
        }

        console.log(getDaysToBirthday(8, 27));
    </script>


    <!-- 3. 根据系统当前的月份，输出这一个月每一天的星期

    2019年6月1日：星期六
    2019年6月2日：星期日
    .....
    2019年6月30日：星期日 -->

    <!-- 用到了回调函数 -->
    <script>
        //打印当前月每一天的星期
        function print() {
            var now = new Date();
            var m = now.getMonth() + 1;
            var y = now.getFullYear();
            var days = new Date(y, m, 0).getDate(); // days 本月的总天数 0 表示上个月的最后一天
            // [月份 m 不用减 1 实际上获取的就是这个月的总天数]
            for (var i = 1; i <= days; i++) {
                console.log(`${y}年${m}月${i}日：星期${getDayOfWeek(y, m, i)}`);
            }
        }

        function getDayOfWeek(year, month, day) {
            var d = new Date(year, month - 1, day);
            var day = d.getDay(); //得到星期(0[周日]-6[周六])
            switch (day) {
                case 0:
                    return "日";
                case 1:
                    return "一";
                case 2:
                    return "二";
                case 3:
                    return "三";
                case 4:
                    return "四";
                case 5:
                    return "五";
                case 6:
                    return "六";
            }
        }

        print();
    </script>
</body>

</html>
```

## 9. 正则表达式

==有很多和字符串相关的需求 都可以使用正则表达式来实现 以下相关案例 在实际开发中如果想要用正则来实现 那么代码量可能会少很多==

正则表达式是国际标准，跨越语言

正则表达式是一个规则，用于验证字符串。

### 基础

1. 字面量匹配

规则中直接书写字面量字符

2. 特殊字符

```
.   // 	匹配除换行符 \n 之外的任何单字符。
^   //  匹配输入字符串的开始位置。
$   //  匹配输入字符串的结尾位置。
```

3. 转义符

```
\n // 匹配一个换行符。
\r // 匹配一个回车符。基本使用不到, 和操作系统有关
\t // 匹配一个制表符。等价于 \x09 和 \cI。
\s // 匹配任何空白字符，包括空格、制表符、换页符等等。等价于 [ \f\n\r\t\v]。注意 Unicode 正则表达式会匹配全角空格符。
\S // 匹配任何非空白字符。等价于 [^ \f\n\r\t\v]。
\b // 匹配一个单词边界，即字与空格间的位置。
\B // 非单词边界匹配。
\d // 匹配一个数字字符。等价于 [0-9]。
\D // 匹配一个非数字字符。等价于 [^0-9]。
\w // 匹配字母、数字、下划线。等价于'[A-Za-z0-9_]'。
\W // 匹配非字母、数字、下划线。等价于 '[^A-Za-z0-9_]'。
\un // 匹配 n，其中 n 是一个用四个十六进制数字表示的 Unicode 字符。例如， \u00A9 匹配版权符号 (©)。\u9676\u5bb6\u4e50 ==> 陶家乐
```

转义符可以将特殊字符转义

4. 字符集

```
[字符范围]
[^字符范围] // 对字符范围取反
```

匹配中文： ```[\u4e00-\u9FA5]```

匹配所有字符: ```[\s\S] 或 [\d\D] 等等```

5. 量词

前面的规则出现的次数

```
* // 匹配前面的子表达式零次或多次。例如，zo* 能匹配 "z" 以及 "zoo"。* 等价于{0,}。
+ //
匹配前面的子表达式一次或多次。例如，'zo+' 能匹配 "zo" 以及 "zoo"，但不能匹配 "z"。+ 等价于 {1,}。
? // 匹配前面的子表达式零次或一次。例如，"do(es)?" 可以匹配 "do" 或 "does" 。? 等价于 {0,1}。
{n}: 匹配n个
{n,}: 匹配>=n个
{n,m}: 匹配n~m个
```

### 作业1

1. 写一个正则表达式，匹配手机号

11位，第一位是1

`^1\d{10}$`

2. 姓名必须是3-6位的中文

`^[\u4e00-\u9fa5]{3,6}$`

3. 密码必须是6-12位的字符，只能包含数字、字母、下划线

`^\w{6,12}$`

4. 写一个正则表达式，匹配邮箱

xxxxxx@xxxxx.xxxx.xxxx

`^\w+@\w+(\.\w+){1,2}$`

5. 匹配一个座机号

xxx-xxxxxxxx

前面：1-3个数字
后面：4-8个数字

`^\d{1,3}-\d{4,8}$`

6. 匹配一个正数

`^\d+(\.\d+)?$`

注意两种问题写法:

1. `^\d+\.?\d+$` 1 不能匹配(点可以没有, 但是后面必须还要有数字, 所以为了区分前面和后面的数字 此时点不能没有)

2. `^\d+\.\d*$` 1. 也能匹配(点和后面的数字都可以没有, 但是只有点也能匹配, 这就出问题了)


7. 匹配一个小数

`^-?\d+\.\d+$`

8. 匹配一个整数

`^-?\d+(\.0+)?$` ==> 默认把小数部分都是0的数字也当成是一个整数


### JS中的应用

[RegExp mdn](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/RegExp)

js中，正则表达式表现为一个对象，该对象是通过构造函数RegExp创建的

**创建正则对象**

1. 字面量模式`/直接书写正则表达式/`
2. 构造函数模式`new RegExp("正则表达式")`

> 开发时, 一般情况下, 都是直接书写正则表达式, 也就是采用第一种方式来创建一个正则表达式; 特殊情况: 如果正则表达式是在一个变量里面, 比如: 来自用户输入, 那么会采用第二种方式来创建一个正则表达式;

**正则实例成员**

- global ==> 是否开启了全局匹配 readonly 使用: `reg.global` 返回: `true`或`false`
- ignoreCase ==> 是否开启了忽略大小写 readonly 使用: `reg.ignoreCase` 返回: `true`或`false`
- multiline ==> 是否开启了全局匹配 readonly 使用: `reg.multiline` 返回: `true`或`false`
- source ==> 得到规则字符串
- ==test方法== ==> 验证某个字符串是否满足规则
- ==exec方法== ==> execute，执行匹配，得到匹配结果。`返回的是一个数组, 数组的第一项是匹配的结果.`

> 正则表达式，默认情况下，适用贪婪模式
> 在量词后，加上?，表示进入非贪婪模式

**字符串对象中的正则方法**

- String.prototype.split() // 通过分离字符串成字串，将字符串对象分割成字符串数组。
- String.prototype.replace() // 被用来在正则表达式和字符串直接比较，然后用**新的子串**来替换被匹配的子串。
- String.prototype.search // 对正则表达式和指定字符串进行匹配搜索，返回**第一个**出现的匹配项的下标。
- String.prototype.match() // 使用正则表达式与字符串相比较。

**Simplified (无注释版)**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>贪婪模式 正则表达式的创建 test exec lastIndex</title>
</head>

<body>
    <script>
        var s = "1234abc123ABC";
        var reg = /\d+/gmi;
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 0 true 4
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 4 true 10
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 10 false 0
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 0 true 4
    </script>
    <script>
        var s = "1234abc123ABC";
        var reg = /\d+/gmi;
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 0 true 4
        reg.lastIndex = 0;
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 0 true 4
    </script>
    <script>
        var s = "1234abc123ABC";
        var reg = /\d+/gmi;
        var n = 0;
        while (reg.test(s)) {
            n++;
        }
        console.log(`匹配了${n}次`); // 匹配了2次
    </script>
    <script>
        var reg = /\d+?/gmi;
        var s = "1234abc567ABC";
        var n = 0;
        while (reg.test(s)) {
            n++;
        }

        console.log(`匹配了${n}次`); // 匹配了7次
        while (result = reg.exec(s)) {
            console.log(result[0]); // 依次输出 1234567
        }
    </script>
    <script>
        var reg = /\d+/gmi;
        var s = "1234abc123ABC";
        var n = 0;
        while (reg.test(s)) {
            n++;
        }
        console.log(`匹配了${n}次`); // 匹配了2次
        while (result = reg.exec(s)) {
            console.log(result[0]); // 第一次输出 1234 第二次输出 567
        }
    </script>
</body>

</html>
```

**Include annotated (有注释版)**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>贪婪模式 正则表达式的创建 test exec lastIndex</title>
</head>

<body>
    <script>
        /*
                静态属性
            RegExp.lastIndex
        该索引表示从哪里开始下一个匹配 */
        var s = "1234abc123ABC";
        var reg = /\d+/gmi; // 贪婪模式 没有加量词 ?
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex);
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex);
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex);
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex);
        // 0 true 4
        // 4 true 10
        // 10 false 0 这一次是从A匹配到结尾C 发现没有匹配项 所以 reg.test(s) 返回 false
        // 0 true 4
        /* 说明:
        1. 一开始从下标为0的位置开始匹配 也就是 1
        2. 第一次test结束之后 此时索引为与第一次匹配结束的位置 4 也就是 a
        3. 当匹配到结尾之后 在重头开始匹配
        小结:
        1. 开始索引是0;
        2. 下一次索引是上一次的结束位置;
        3. 匹配到结尾后 会重头开始继续匹配  */
    </script>
    <script>
        // RegExp.lastIndex 是可写的
        var s = "1234abc123ABC";
        var reg = /\d+/gmi;
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 0 true 4
        reg.lastIndex = 0;
        console.log(reg.lastIndex, reg.test(s), reg.lastIndex); // 0 true 4
    </script>
    <script>
        // 计算匹配次数
        var s = "1234abc123ABC";
        var reg = /\d+/gmi;
        var n = 0;
        while (reg.test(s)) {
            n++;
        }
        console.log(`匹配了${n}次`); // 匹配了2次
    </script>
    <script>
        // 加量词 ? => 非贪婪模式
        var reg = /\d+?/gmi; // var reg1 = new RegExp("\d+?","gmi");
        var s = "1234abc567ABC";
        var n = 0;
        while (reg.test(s)) {
            n++;
        }

        console.log(`匹配了${n}次`); // 匹配了7次
        /* 说明:
        1. 不加量词 ? ==> 表示贪婪模式 ==> 也就是会尽可能多的匹配
        2. 加量词 ? ==> 表示非贪婪模式 ==> 也就是会尽可能少的匹配 */
        while (result = reg.exec(s)) {
            console.log(result[0]); // 依次输出 1234567
        }

    </script>
    <script>
        // 不加量词 ? => 贪婪模式
        var reg = /\d+/gmi;
        var s = "1234abc123ABC";
        var n = 0;
        while (reg.test(s)) {
            n++;
        }
        console.log(`匹配了${n}次`); // 匹配了2次
        while (result = reg.exec(s)) {
            console.log(result[0]); // 第一次输出 1234 第二次输出 567
        }
    </script>
</body>

</html>
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>exec</title>
</head>

<body>
    <script>
        var reg = /\d+/g;
        var s = "1234abc567ABC";

        // 得到所有的匹配结果和位置
        while (result = reg.exec(s)) { // result = reg.exec(s) 这整个表达式的返回值是 result 的值
            console.log(`匹配结果：${result[0]}，出现位置：${result.index}`);
        }
        // 匹配结果：1234，出现位置：0
        // 匹配结果：456，出现位置：7
    </script>
</body>

</html>



<!DOCTYPE html>
<html lang="en">

<head>
    <title>字符串对象中的正则方法</title>
</head>

<body>
    <script>
        /* String.prototype.match() ==> 使用正则表达式与字符串相比较。 */
        var s = "1234abc567ABC";
        var result = s.match(/\d+/g); // 将所有匹配结果以字符串数组的形式返回
        console.log(result); // (2) ["1234", "567"]
    </script>



    <script>
        /* String.prototype.search() ==> 对正则表达式和指定字符串进行匹配搜索，返回第一个出现的匹配项的下标。 */
        var s = "abc567ABC";
        var result = s.search(/\d+/g);
        console.log(result); // 3
    </script>



    <script>
        var s = "hello world\tjavascript\nyes";
        var result = s.split(/[, \-\t]/); // 将所有分割结果以字符串数组的形式返回
        console.log(result); // (3) ["hello", "world", "javascript↵yes"]

        // 第二个参数n的作用 ==> 取分割后的前n个
        var result2 = s.split(/[, \-\t]/, 2); // 取前两个
        console.log(result2); // (2) ["hello", "world"]
    </script>



    <script>
        /* String.prototype.replace ==> 被用来在正则表达式和字符串直接比较，然后用新的子串来替换被匹配的子串。 */
        var s = "hello World ! Javascript.";
        // 将第一个空格字符替换为 逗号,
        console.log(s.replace(" ", ",")); // hello,World ! Javascript. (默认非全局)
        // console.log(s.replace(new RegExp(" "),","));
        // replace 不会改变原始字符串 而是返回一个新的字符串
        console.log(s); // hello World ! Javascript.
    </script>



    <script>
        var s = "hello World ! Javascript.";
        // 将全部不可见字符替换为 逗号,
        console.log(s.replace(new RegExp(/\s/, "g"), ",")); // hello,World,!,Javascript.
        // console.log(s.replace(/\s/g,","));
        console.log(s); // hello World ! Javascript.
    </script>



    <script>
        var s = "hello world";
        // 将单词的首字符 替换为 逗号
        s = s.replace(/\b[a-z]/g, ",");
        console.log(s); // ,ello ,orld
    </script>



    <script>
        /* str.replace 语法 ==> 第二个参数可以是一个函数
        str.replace(regexp|substr, newSubStr|function)
        相关参数说明：
        https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace
        */
        var s = "hello world";
        // 将单词的首字符 替换为 逗号
        s = s.replace(/\b[a-z]/g, function (match) {
            console.log(match); // 第一个参数表示匹配的内容
            return ","; // 返回值 作为替换内容
        });
        // h
        // w
        console.log(s); // ,ello ,orld
    </script>



    <script>
        var s = "hello world";
        // 将单词的首字符 变成大写
        s = s.replace(/\b[a-z]/g, function (match) {
            return match.toUpperCase();
        });
        console.log(s); // Hello World
    </script>



    <script>
        var s = "hello world\tjavascript\nyes";
        // 将字符串中的空白字符去掉 并 转换为大驼峰的形式
        s = s.replace(/\s*\b[a-z]\s*/g, function (match) {
            console.log(match); // h w j y
            return match.toUpperCase().trim();
        });
        console.log(s); // HelloWorldJavascriptYes
    </script>
</body>

</html>
```

### 作业2

1. 书写一个正则表达式，去匹配一个字符串，得到匹配的次数，和匹配的结果

2. 得到一个字符串中中文字符的数量

3. 过滤敏感词，有一个敏感词数组，需要将字符串中出现的敏感词替换为四个星号

["共产党", "too young too simple", "营销"]

4. 得到一个html字符串中出现的章节数量

```js
var html = `(h2{第$章}+p*5>lorem100)*10`;
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>作业2</title>
</head>

<body>

    <!-- =====================作业2=========================== -->

    <!-- 1. 书写一个正则表达式，去匹配一个字符串，得到匹配的次数，和匹配的结果 -->
    <!-- 1.html -->
    <script>
        var reg = /\d{3}/g;
        var s = "433afdsaf34542fsdssfsd234";
        var n = 0;
        var str = "";
        while (result = reg.exec(s)) {
            n++;
            str += result[0] + "\n";
        }
        str = `匹配${n}次\n` + str;
        console.log(str);
        /*
        匹配3次
        433
        345
        234
        */
    </script>

    <script>
        var reg = /\d{3}/g;
        var s = "433afdsaf34542fsdssfsd234";
        var arr = s.match(reg);
        console.log(`匹配${arr.length}次`, arr); // 匹配3次 (3) ["433", "345", "234"]
    </script>

    <!-- 2. 得到一个字符串中中文字符的数量 -->
    <!-- 2.html -->
    <script>
        var reg = /[\u4e00-\u9fa5]/g;
        var s = "fgdgg啊手动sdf阀梵蒂冈sd234";
        var n = 0;
        while (reg.test(s)) {
            n++;
        }
        console.log(n); // 7
    </script>

    <script>
        var reg = /[\u4e00-\u9fa5]/g;
        var s = "fgdgg啊手动sdf阀梵蒂冈sd234";
        console.log(`共有${s.match(reg).length}个汉字`); // 共有7个汉字
    </script>

    <!-- 3. 过滤敏感词，有一个敏感词数组，需要将字符串中出现的敏感词替换为四个星号

    ["共产党", "too young too simple", "营销"] -->
    <!-- 3.html -->
    <script>
        // 注意: 正则表达式的创建方式 此时如果还是使用字面量的形式来创建 就不合适了
        var senWords = ["色情", "暴力", "卢本伟", "贸易战"]; // 实际开发中是 从数据库引入 存放在数组中操作
        //将字符串中敏感词汇替换为指定的字符串
        function removeSensitiveWords(s, rep) {
            // var reg = new RegExp(`(${色情|暴力|卢本伟|贸易战})+`, "g"); // 不能写死
            var reg = new RegExp(`(${senWords.join("|")})+`, "g"); // + ==> 连续的敏感词汇 只替换一次
            return s.replace(reg, rep);
        }

        console.log(removeSensitiveWords("sdffs色情暴力sfsfs卢本伟牛逼dsdf贸易战sf", "****"));
        // sdffs****sfsfs****牛逼dsdf****sf
    </script>


    <!-- 4. 得到一个html字符串中出现的章节数量

    var html = `var html = `(h2{第$章}+p*5>lorem100)*10`;`;
    -->

    <!-- 4.html -->
    <script>
        var html = `...`;
        var reg = /<h2>第\d+章<\/h2>/g;
        var result = html.match(reg);
        if (result) {
            console.log(result.length); // 10
        } else {
            console.log(0);
        }
        // console.log(result);
        // (10) ["<h2>第1章</h2>", "<h2>第2章</h2>", "<h2>第3章</h2>", "<h2>第4章</h2>", "<h2>第5章</h2>", "<h2>第6章</h2>", "<h2>第7章</h2>", "<h2>第8章</h2>", "<h2>第9章</h2>", "<h2>第10章</h2>"]
    </script>
</body>

</html>
```

### 进阶

### 捕获组

用小括号包裹的部分叫做捕获组，捕获组会出现在匹配结果中

捕获组可以命名，叫做具名捕获组

非捕获组

### 反向引用

在正则表达式中，使用某个捕获组，```\捕获组编号```

### 正向断言(预查)

检查某个字符后面的字符是否满足某个规则，该规则不成为匹配结果，并且不称为捕获组

### 负向断言(预查)

检查某个字符后面的字符是否不满足某个规则，该规则不成为匹配结果，并且不称为捕获组

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>捕获组</title>
</head>

<body>
    <script>
        // 用小括号包裹起来的部分叫做捕获组, 捕获组会出现在匹配结果中
        var reg = /(\d[a-z])([a-z]+)/g;
        var s = "2afsdf-5fdgdfg-9asddf";
        while (result = reg.exec(s)) {
            console.log(result);
        }
        // (3) ["2afsdf", "2a", "fsdf", index: 0, input: "2afsdf-5fdgdfg-9asddf", groups: undefined]0: "2afsdf"1: "2a"2: "fsdf"groups: undefinedindex: 0input: "2afsdf-5fdgdfg-9asddf"length: 3__proto__: Array(0)
        // (3) ["5fdgdfg", "5f", "dgdfg", index: 7, input: "2afsdf-5fdgdfg-9asddf", groups: undefined]
        // (3) ["9asddf", "9a", "sddf", index: 15, input: "2afsdf-5fdgdfg-9asddf", groups: undefined]
        // 结果数组中下标 0 的成员 仍然表示整个正则表达式的匹配结果
        // 捕获组 ==> 会出现在匹配结果的数组里头
        // 多出来的两个下标 1 和 2 分别表示的是两个小括号() 也就是捕获组 匹配的内容
    </script>
    <script>
        var s = "2015-5-1, 2019-6-19, 2000-04-28";
        // 需求: 得到每一个日期，并得到每个日期的年月日
        var reg = /(\d{4})-(\d{1,2})-(\d{1,2})/g;
        while (result = reg.exec(s)) {
            console.log(result[0], result[1], result[2], result[3]);
        }
        // 2015-5-1 2015 5 1
        // 2019-6-19 2019 6 19
        // 2000-04-28 2000 04 28
    </script>
    <script>
        // 自己试着不用捕获组实现
        var s = "2015-5-1, 2019-6-19, 2000-04-28";
        var newArr = s.split(",");
        let arr = [];
        newArr.forEach(item => {
            arr.push(item.split("-"));
        });
        console.log(arr[0][0], arr[0][1], arr[0][2],
            arr[1][0], arr[1][1], arr[1][2],
            arr[2][0], arr[2][1], arr[2][2]);
        // 2015 5 1  2019 6 19  2000 04 28
    </script>
    <script>
        // 捕获组可以命名 ==> 具名捕获组
        var s = "2015-5-1, 2019-6-19, 2000-04-28";
        var reg = /(?<year>\d{4})-(?<month>\d{1,2})-(?<day>\d{1,2})/g;
        while (result = reg.exec(s)) {
            console.log(result.groups, result.groups.year, result.groups.month, result.groups.day);
        }
        // {year: "2015", month: "5", day: "1"} "2015" "5" "1"
        // {year: "2019", month: "6", day: "19"} "2019" "6" "19"
        // {year: "2000", month: "04", day: "28"} "2000" "04" "28"
    </script>
    <script>
        // 非捕获组模式 ==> ?: ==> 表示这个加小括号的 不是一个捕获组 而仅仅把其看做是一个整体
        // 可以提高执行效率
        var s = "2015-5-1, 2019-6-19, 2000-04-28";
        var reg = /(?:\d{4})-(?:\d{1,2})-(\d{1,2})/g;
        while (result = reg.exec(s)) {
            console.log(result[0], result[1], result[2], result[3]);
        }
        // 2015-5-1 1 undefined undefined
        // 2019-6-19 19 undefined undefined
        // 2000-04-28 28 undefined undefined
    </script>
    <script>
        // 在 replace 中使用捕获组
        var s = "2015-5-1,- 2019-6-19,- 2000-04-28";
        // 需求 年-月-日 ==> 年/月/日
        var reg = /(\d{4})-(\d{1,2})-(\d{1,2})/g;
        s = s.replace(reg, function (match, g1, g2, g3) { // 1: 匹配结果 2: 第一个捕获组 3...
            console.log(match, g1, g2, g3);
            return `${g1}/${g2}/${g3}`;
        })
        console.log(s); // 2015/5/1,- 2019/6/19,- 2000/04/28
    </script>
    <script>
        // 在 replace 中使用捕获组 的另一种写法
        var s = "2015-5-1,- 2019-6-19,- 2000-04-28";
        // 需求 年-月-日 ==> 年/月/日
        var reg = /(\d{4})-(\d{1,2})-(\d{1,2})/g;
        s = s.replace(reg, "$1/$2/$3"); // 利用特殊字符 $1 表示第一个捕获组 $2 ...
        console.log(s); // 2015/5/1,- 2019/6/19,- 2000/04/28
    </script>
</body>

</html>
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>反向引用</title>
</head>

<body>
    <script>
        // 反向引用 ==> 在正则表达式中 使用某个捕获组 ==> 使用: \捕获组编号
        // 捕获组编号 参考 ==> https://blog.csdn.net/tao_sheng_yi_jiu/article/details/80369026
        var reg = /(\d{2})\1\1/;
        var s = "131313";
        var s1 = "202020";
        var s2 = "202120";

        console.log(reg.test(s)); // true
        console.log(reg.test(s1)); // true
        console.log(reg.test(s2)); // false
    </script>
    <script>
        var reg = /(\d{2})\1\1/; // 写法一
        // var reg = /(\d{2})(\d{2})(\d{2})/; // 写法二
        // 第二种写法 有三个捕获组 第一种写法只有一个捕获组
        var s = "131313";

        console.log(reg.exec(s));
        // (2) ["131313", "13", index: 0, input: "131313", groups: undefined]
        // 注意: 此时只有一个捕获组
    </script>
    <script>
        // var reg = /(\d{2})\1\1/; // 写法一
        var reg = /(\d{2})(\d{2})(\d{2})/; // 写法二
        // 第二种写法 有三个捕获组 第一种写法只有一个捕获组
        var s = "131313";

        console.log(reg.exec(s));
        // (4) ["131313", "13", "13", "13", index: 0, input: "131313", groups: undefined]
        // 注意: 此时共有四个捕获组
    </script>
    <script>
        // 反向引用的应用举例 ==> 面试题
        var s = "aaaaaaaabbbbbbbbbccccccdefgggggggg";
        // 需求: 找出该字符串中连续的字符 (不包含只出现一次的字符)
        var reg = /(\w)\1+/g;
        while (result = reg.exec(s)) {
            // console.log(result);
            console.log(result[1]);
        }
        // a
        // b
        // c
        // g
    </script>
    <script>
        // 捕获组如果有名字 那么也可以通过名字来引用
        var s = "aaaaaaaabbbbbbbbbccccccdefgggggggg";
        var reg = /(?<char>\w)\1+/g;
        while (result = reg.exec(s)) {
            console.log(result[1]);
        }
        // a
        // b
        // c
        // g
    </script>
    <script>
        // 捕获组如果有名字 那么也可以通过名字来引用
        var s = "aaaaaaaabbbbbbbbbccccccdefgggggggg";
        var reg = /(?<char>\w)\k<char>+/g;
        while (result = reg.exec(s)) {
            console.log(result[1]);
        }
        // a
        // b
        // c
        // g
    </script>
</body>

</html>
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>预查</title>
</head>

<body>
    <script>
        var s = "sdfsdf3434343sdfsa545454dfsdfsfsd6754";
        var reg = /[a-zA-Z](\d+)/g;
        while (result = reg.exec(s)) {
            console.log(result); // f a d
        }
        // (2) ["f3434343", "3434343", index: 5, input: "sdfsdf3434343sdfsa545454dfsdfsfsd6754", groups: undefined]
        // (2) ["a545454", "545454", index: 17, input: "sdfsdf3434343sdfsa545454dfsdfsfsd6754", groups: undefined]
        // (2) ["d6754", "6754", index: 32, input: "sdfsdf3434343sdfsa545454dfsdfsfsd6754", groups: undefined]
    </script>
    <script>
        // 正向断言(预查) ==> ?= ==> 检查某个字符后面的字符是否满足某个规则, 该规则不成为匹配结果, 并且不称为捕获组
        var s = "sdfsdf3434343sdfsa545454dfsdfsfsd6754";
        // 需求: 找字母 要求此字母的后面是数字
        var reg = /[a-zA-Z](?=\d+)/g;
        while (result = reg.exec(s)) {
            console.log(result); // f a d
        }
        // ["f", index: 5, input: "sdfsdf3434343sdfsa545454dfsdfsfsd6754", groups: undefined]
        // ["a", index: 17, input: "sdfsdf3434343sdfsa545454dfsdfsfsd6754", groups: undefined]
        // ["d", index: 32, input: "sdfsdf3434343sdfsa545454dfsdfsfsd6754", groups: undefined]
    </script>
    <script>
        // Q ==> 尝试用循环来实现
        var s = "334353456";
        // 从右往左 每3位加一个逗号
        var reg = /\B(?=(\d{3})+$)/g;
        s = s.replace(reg, ",");
        console.log(s); // 334,353,456
        // 说明:
        // 1. \B 非单词边界 作用 ==> 防止一开始匹配的时候, 就正好是3的倍数, 避免第一个逗号出现在最前面
        // 2. ?= 预查
        // 3. (\d{3})+ 数字出现3的倍数次 3, 6, 9 ...
        // 4. $ 结尾 ==> 必须从当前位置计算到结尾
    </script>
    <script>
        // 负向断言(预查) ==> 检查某个字符后面的字符是否不满足某个规则, 该规则不成为匹配结果, 并且不称为捕获组
        var s = "afg43223444wr423424243";
        // 需求: 找字母 要求改字母后面跟的不是数字
        var reg = /[a-zA-Z](?!\d+)/g;
        while (result = reg.exec(s)) {
            console.log(result); // a f w
        }
    </script>
    <script>
        // 判断密码强度(预备知识点, 下面将封装函数judgePwd来实现)
        // 要求密码中必须出现小写字母、大写字母、数字、特殊字符(!@#_,.)，6-12位
        var s = "asdfsdAf234.";
        var s1 = "asdfsdAf234";
        var reg = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[!@#_,.]).{6,12}$/;
        // 预查 ==> 注意: 只做检查 不会消耗(也就是说 下一次开始预查的时候 还是从头开始)
        // 这一点不容易理解 举例来说: (?=.*[a-z]) 会从头到尾走一遍 (?=.*[A-Z]) 也会从头到尾走一遍 后面的都会 ...
        console.log(reg.test(s)); // true ==> 预查通过
        console.log(reg.test(s1)); // false ==> 预查不通过
    </script>
    <script>
        // 判断密码强度
        // 密码长度必须是6-12位
        // 出现小写字母、大写字母、数字、特殊字符(!@#_,.)  -> 强
        // 出现小写字母、大写字母、数字  -> 中
        // 出现小写字母、大写字母  -> 轻
        // 其他  -> 不满足要求
        function judgePwd(pwd) {
            if (/^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[!@#_,.]).{6,12}$/.test(pwd)) {
                return "强";
            } else if (/^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{6,12}$/.test(pwd)) {
                return "中";
            } else if (/^(?=.*[a-z])(?=.*[A-Z]).{6,12}$/.test(pwd)) {
                return "轻";
            } else {
                return "不满足要求";
            }
        }

        console.log(judgePwd("asdADFF4.343"));
    </script>
</body>

</html>
```

## 10. 错误处理

JS中的错误分为：

1. 语法错误：会导致整个脚本块无法执行。
2. 运行错误
   1. 运行报错：会导致当前脚本块后续代码无法执行
   2. 运行结果不符合预期

**调试错误**

1. 控制台打印

2. 断点调试

抛出错误

错误在js中本质上是一个对象，抛出错误的语法为：

```js
throw 错误对象;
```

错误对象的构造函数为Error

捕获错误

```js
try{
    //代码块1
}
catch(错误对象){
    //代码块2
}
finally{
    //代码块3
}
```

当运行代码1的时候，如果发生错误，立即停止代码1的执行，转而执行代码2，错误对象为抛出的错误对象。无论代码1和代码2是否，最终都将执行代码3

### test.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>2020年9月18日</title>
</head>

<body>
    <!-- 本章节的第三个视频只看了前面的35min还有后续的25min没有观看 -->
    <script src="test.js"></script>
</body>

</html>
```

### test.js

```js
// function isPrime(n) {
//     if(isNaN(n)){
//         throw new Error("n必须是一个正常的数字");
//     }
//     if (n < 2) {
//         return false;
//     }
//     for (var i = 2; i < n; i++) {
//         if (n % i === 0) {
//             return false;
//         }
//     }
//     return true;
// }

// console.log(isPrime(10));
// console.log(isPrime("abcd"));

function A() {
    console.log(B());
    console.log("a1");
}

function B() {
    try {
        C();
        console.log("b1");
    }
    catch (err) {
        console.log("运行C的时候发生了问题", err)
        return 3;
    }
    finally{
        console.log("处理完成");
    }
}

function C() {
    throw new TypeError("asdfasfasfasfd");
    console.log("c1");
}

A();

console.log("g1");
```

