# 1. 基础理论_互联网起源

**notes:**

```
1. 互联网的起源简介
   1. 1969年
   加利福尼亚大学洛杉矶分校、斯坦福大学、加利福尼亚大学、犹他州大学，这四所大学将各自的网络连接起来，形成了互联网的雏形；互联网 —— Internet、因特网、英特网、网际网路
   2. 1989年
   欧洲粒子物理研究所 —— 协议（格式）—— www（World Wide Web）—— 万维网；
   3. 1991年
   互联网普及，民用；
```

[互联网 (百度百科)](https://baike.baidu.com/item/%E4%BA%92%E8%81%94%E7%BD%91/199186?fr=kg_qa)

看一下一分钟的视频简介, 了解一下互联网的由来

# 2. 基础理论_局域网

## 2.1 局域网的概念

> 以下笔记内容, 都是自己的理解, 很可能是不专业的, 建议多上网找一些专业的文章和书籍来看看;

`Q:` 局域网是啥?
`A:` 顾名思义, 就是一个局部的网络, 处于这个局部网络中的计算机, 它们之间的信息可以实现互通, 但是却无法与其他局域网中的计算机实现信息的互通（通过别的啥技术or手段, 肯定是可以实现局域网之间信息互通的）;

![局域网](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211161920.png)

邓哥家 or 成哥家 这样的一个局部网络 实际上就是一个局域网;

---

## 2.2 计算机的概念

[计算机 (百度百科)](https://baike.baidu.com/item/%E8%AE%A1%E7%AE%97%E6%9C%BA/140338?fr=aladdin)

首先, 明确一点: `计算机 ≠ 电脑`, 手机, 平板, 笔记本, 智能手表, 智能手环, 等等, 都是计算机, 我们现在所说的计算机, 指的是 "冯诺依曼式计算机";

> 科普一下: 计算机 和 计算机科学 不是一个东西
> 冯诺依曼 是 计算机之父;
> 图灵 是 计算机科学之父;

| 计算机的五大组成部分 | 硬件                          |
| -------------------- | ----------------------------- |
| 运算器               | `CPU` `GPU`                   |
| 存储器               | `内存` `硬盘`                 |
| 控制器               | 主板上的一些器件              |
| 输入设备             | `键盘` `鼠标` `麦克风` `网口` |
| 输出设备             | `显示器` `网口`               |

- GPU 也就是显卡
- 内存的特点: 断电数据清空, 读写速度快;
- 硬盘也称作 辅存, 特点是: 数据可以持久化, 读写速度相对较慢;
- `网口` 既是 输入设备 也是 输出设备

---

## 2.3 计算机之间如何实现相互通信

### 阶段1: 打洞 + 接网线

1. 两台计算机之间相互通信: 每台计算机都开一个网口, 用一根网线把它们之间相互连接起来即可; (如下图所示) 这样, 计算机B就能访问到计算机A的数据, 同样, 计算机A也可以访问到计算机B的数据; 此时它们之间的数据通信, 数据是不需要格式的;
   对不需要格式的理解:
   首先, 得清楚格式有什么用, 格式是指数据在传输过程中的格式, 格式也可以理解为协议, 协议中一般都包含一些信息, 比如: 数据的发送方, 数据的接收方, 等等;
   所以说, 不需要格式, 此时可以理解为: 传输的数据中, 不需要包含该数据的发送方是谁, 以及该数据的接收方是谁, 直接把数据内容给传输过去就可以了;
   因为计算机A和计算机B就通过一根网线互相连接, A如果要给B发送数据, A只要从这个网口往外发就行了, 这个网口所连接的计算机也就是计算机B, 计算机B就能接收到来自计算机A发送过来的数据;

![两台计算机之间相互通信](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211130701.png)

2. 三台计算机之间相互通信: 每台计算机都开两个网口, 共需要3根网线, 就能实现3台计算机之间的互联; (如下图所示) 这样, 就能实现三台计算机之间的数据互通, 此时传输的数据也是不需要格式的;
   为何此时依旧不需要格式呢?
   打个比方: 我们给计算机A开了两个网口, 一个是网口A1 连接的是计算机B的网口B1, 一个是网口A2 连接的是计算机C的网口C1, 那么我们如果要让A给B发送数据, 我们只需要通过网口A1来发就行了, 因为只有网口B1能接收到, 所以压根就不需要为我们发送出去的数据添加啥格式, 依旧能很清楚的分辨出, 数据的发送方是谁, 以及数据的接收方是谁;

![三台计算机之间相互通信](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211130932.png)

`Q:` 若需要实现互联的计算机数量很多, 那么上述的方式就不实际了(虽然理论上也可以), 总不能给一台计算机浑身都开满网口吧;

![四台计算机之间相互通信](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211131403.png)

### 阶段2: 路由器

前面我们提到, 计算机如果过多, 那么想要实现计算机之间的相互连接, 就得多开网口, 多拉网线, 这种原始的法子显然就不切实际了;
此时出现了一个法子: 就是让所有想要彼此之间连通的计算机, 都连上同一台中转的计算机 (路由器) , 实现数据的共享;
同时, 这样的做法也会有一定的问题, 那就是此时计算机之间相互传输数据就需要具备一定的格式 (协议) 了, 因为中转计算机并不是最终的数据接收方, 所以就得给传输的原始数据添加上一些格式, 这样才能分辨出数据的发出者和接收者;
在原始的法子中, 比如说计算机A要给计算机B发送数据, 它们之间发送数据是不需要格式的, 因为都是直接通过网线来相连, 所以A发送的数据, B就可以直接接收到, 同样的, B发送的数据, A也可以直接接收到, 所以不存在数据格式的问题;
格式(协议)起码要说明：数据来自谁, 数据发给谁, 数据的内容, 等要素;
并形成一种规范, 也就是我们所说的协议;

![20210211153600](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211153600.png)

中间设备的原理: 就类似于邮局一样, 用户A给用户B写信, 信封上的那些信息, 也就是阶段1中所说的格式, 即: 协议;
协议中包含的基本信息包括: 数据来自谁, 数据发给谁, 数据的内容, 等要素;

# 3. 基础理论_IP地址与公网

若按照下图这种结构, 两家的设备之间是无法进行通信的, 因为他俩处于两个不同的局域网中, 这两个局域网相互独立, 没啥关系;

![局域网](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211161920.png)

## 3.1 IP地址

1. IP地址的格式及组成
   1. 格式: IP地址共分为四个段: `xxx.xxx.xxx.xxx` 每个段0~255, 每个段, 都是由8个0、1组成的。
   2. 组成: ⼀个IP地址由两个部分组成 ==> `⽹络ID` + `主机ID`
2. IP地址的分类
   A类: 0.0.0.0 ~ 127.255.255.255（⼀个⽹络能有1600+万台）
   B类: 128.0.0.0 ~ 191.255.255.255（172.16.0.0 ~ 172.31.255.255）
   C类: 192.0.0.0 ~ 223.255.255.255（192.168.xxx.xxx）
   D类: 多播地址... (不做了解)
   E类: ... (不做了解)
3. 第一位是网络ID, 后三位是主机ID;
4. IP地址类型的划分, 通常是根据一个网络中的设备数量为依据的;
5. 私有网络: 192.168.***.***

![3.1-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211195346.png)

## 3.2 公网

`Q:` 什么是公网?
`A:` [公网IP (百度百科)](https://baike.baidu.com/item/%E5%85%AC%E7%BD%91IP/8881123?fr=aladdin)

`Q:` 公网有什么用?
`A:` 借助公网, 可以实现不同局域网之间设备的相互通信;

# 4. 基础理论_域名与DNS解析过程

网络部分的内容, 太杂乱了, 不知道要掌握些什么知识点, 之后得多上网找一些前端网络部分的面试题来刷一刷, 看看哪些部分是需要我们前端程序员掌握的, 然后在重点学习;

---

**reference:**

1. [DNS 域名系统 (百度百科)](https://baike.baidu.com/item/%E5%9F%9F%E5%90%8D%E7%B3%BB%E7%BB%9F/2251573?fromtitle=dns&fromid=427444)
2. [前端常见面试题（网络）(csdn)](https://blog.csdn.net/qq_38253873/article/details/105158106)

![20210211233357](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211233357.png)

- [ ] 网络部分面试题

`Q:` 从输入URL到页面加载发生了什么?
`A:`

![![20210211215709](httpscdn.jsdelivr.netgh123taojialedahuyou_picture@mainblogs20210211215709.png)](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/![20210211215709](httpscdn.jsdelivr.netgh123taojialedahuyou_picture@mainblogs20210211215709.png).png)

# 5. 基础理论_五层网络模型

校招中可能会问到这个五层网络模型，在实际应用中，只需要大致理解即可。

![5-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211222200.png)

1. 运输层：
   TCP协议：确保数据传输出去，并且目标收到；
   UDP协议：只确保数据传输出去；
   简单的区分一下TCP协议和UDP协议:
   TCP协议: 计算机A给计算机B传输数据, 当A将数据发送出去之后, 计算机A会等待来自计算机B的请求, 当计算机B收到计算机A发送过来的数据后, 会向计算机A发送一个请求, 如果A没有收到来自B的请求, 那么一段时间之后, A还会再发送一遍数据, 所以TCP协议可以确保数据能够送到目标主机;
   UDP协议: 计算机A发送完数据就溜了, 不管B是否能够收到该数据;
2. 应用层：
   发出去的协议一定是HTTP协议，HTTP协议必须伴随着TCP协议、IP协议；
   因为HTTP协议是基于TCP协议的，TCP协议是基于IP协议的；
   解释:
   HTTP协议实际上就是符合某种格式要求的字符串;
   用户向浏览器请求数据:
   1. 发送的数据先包上一层HTTP协议, 也就是在发送的数据前面加上一个请求头 (一堆带有HTTP协议格式的字符串) 用于描述该请求;
   2. 但是浏览器还不能直接在网上进行数据的交互, 浏览器得把这些数据交给操作系统, 通过操作系统的网络往外发数据, 操作系统若想往外发数据, 那么必须再加上一层TCP/IP协议; 所以会在请求头前面再添上一个TCP/IP协议(包含对方的IP(目标主机),自己的IP(源主机),对方的端口(对应的应用程序));
3. 物理层：
   确定介质, 确定数据的传输频率(确定好多少时间间隔传一个数);

![5-2](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211222353.png)

![5-3](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211222423.png)

Request ==> 请求 ==> 表示向服务器发出请求, 从服务器获取数据;
Response ==> 响应 ==> 表示接收服务器端发送过来的数据;

不同的端口对应不同的应用程序

![5-4](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211223900.png)

PC端双击查看
HTTP协议 ==> 也就是上述格式的字符串而已

![5-5](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211224016.png)

浏览器可以包装和解析HTTP协议；
Web服务器也可以包装和解析HTTP协议；
发送请求：浏览器包装HTTP协议、Web服务器解析HTTP协议；
接收请求：Web服务器包装HTTP协议、浏览器解析HTTP协议；

加密：自上而下；
解密：自下而上；

咋们写的程序，都是浏览器 or Web服务器（node.js）上的；

# 6. 基础理论_简述HTTP协议

![6-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211224124.png)

**get**

get请求方式最大的特点：请求的参数都在url里； —— 请求少量数据；

get请求的参数可以不在url里,但是那是理论上的HTTP协议, 如果是在Web环境下,那么请求的参数都在url里; url里显然是存不了多少东西的, 大概在5K左右; 所以也就只能简单的传一些文本, 若想传大量的数据, 那么还是得用 post 请求方式;

比如百度搜索: [hello](https://www.baidu.com/s?wd=hello&rsv_spt=1&rsv_iqid=0x99659004000009f3&issp=1&f=8&rsv_bp=1&rsv_idx=2&ie=utf-8&tn=baiduhome_pg&rsv_enter=1&rsv_dl=tb&rsv_sug3=6&rsv_sug1=5&rsv_sug7=101&rsv_sug2=0&rsv_btype=i&prefixsug=hello&rsp=8&inputT=795&rsv_sug4=1320)

**post**

post请求方式：数据不像get一样放在url里面传，而是放在数据体里头传； —— 请求大量数据；

get请求基本上是不带有啥数据体的，只有post请求会带有大量的数据体；

不要误以为get请求比较危险，post请求比较安全，实际上都是危险的； —— HTTP协议是一种明文传输协议，传输的数据是不会经过加密的，都是明文传输，所以在网络中传输数据，这两种方式都是危险的；判断安全与否, 是指在网络传输这个环境中, 而不是在浏览器中是否能够直接被看见;

![响应头](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211230010.png)

# 7. 基础理论_GET与POST的区别

**在回答这个问题的时候, 得看是基于什么前提的**

1. 如果什么前提都没有，不使用任何规范，只考虑语法和理论上的HTTP协议。
   1. GET和POST几乎没有什么区别,只有名字不一样。
2. 如果是基于RFC规范的。
   1. 理论上的(Specification) :
      1. GET和POST具有相同的语法，但是有不同的语义。
      2. get是用来获取数据的，post是用来发送数据的，其他方面没有区别。
   2. 实现上的(Implementation) ：各种浏览器,就是这个规范的实现者。(也就是在Web环境下)
      1. GET的数据在URL是可见的。POST请求不显示在URL中。
      （url和地址栏不是一个东西，地址栏就是浏览器窗口上面的那个输入域名的框，而url就是路径，路径的信息 —— 控制台 ==> NetWork ==> Request Headers ==> view parsed ==> 请求方式 + URL + 协议版本url里面的数据并不都会展示在地址栏里，所以说GET请求的数据在地址栏里并不一定是可见的）
      2. GET对长度是有限制的，POST长度是无限的。
      3. GET请求的数据可以收藏为书签，POST请求到的数据不可收藏为书签。
      4. GET请求后，按后退按钮、刷新按钮无影响， 而POST请求，数据会被重新提交。
      5. GET编码类型: application/x-www-form-url；POST的编码类型：
      （POST请求可以发送文件，而且post请求的编码类型有很多种，先知道有以下两种）
      encodeapplication/x-www-form-urlencoded （加密的）
      multipart/form-data
      6. GET历史参数会被保留在浏览器里，POST不会保存在浏览器中的。
      7. GET只允许ASCIl编码，POST没有编码限制，而且允许发二进制的。
      （由于post没有编码限制，而且可以发送二进制，所以它可以发送文件，视频，音频等等，这些数据都是以二进制的形式来发送的）
      8. GET与POST相比，GET安全性较差，因为所发的数据是URL的一部分。
      （只是说get较差，post实际上也很差，只不过get更差）
      回答出这8点, 是纯前端的内容;
      但是真正在公司里写后端, 那么前面的那一丢丢内容会经常接触到;

# 8. 基础理论_Cookie与Session

## 8.1 Cookie

**Cookie**

1. 如果我们用JS的变量来存数据,那么在页面关闭的时候,数据就消失了。

2. 保持登录状态是怎么做到的呢?
   按照正常的HTTP协议来说,是做不到的，因为HTTP协议,上下文无关协议。

3. 所以说前端页面上,有可以持久化存储数据的东西。一旦登录成功,数据就记载在这个里面。
   这个东西就是Cookie
   Cookie是有域名限制的 (比如说: 百度就只能往自己的域名下种cookie, 淘宝也只能往自己的域名下种cookie, `cookie不能跨域存储`)
   `Cookie是存在浏览器里的`,不是存在某个页面上的。而且 `Cookie 是可以长期存储的`。
   Cookie即使是保存在浏览器里,也是存放在不同的域名下的。(也就是说: `不同的cookie存放在不同的域名里`)

**简述用户登录过程**

![简述用户登录过程](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211233539.png)

![cookie 百度账号 BAIDUID](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211232758.png)

## 8.2 Session

![Session](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211234942.png)

**轮询:** 比如说后端有10台服务器, 接收到第一个请求后, 打在第一台服务器上, 第二个请求打在第二个服务器上, 以此类推, 可想而知, 利用轮询的方式, 是无法利用Session来实现保持登录状态的;

**IP哈希:** 一个IP打在一个服务器上, 这样就能确保一台客户机仅有一台后端服务器提供服务, 这样便可以利用Session来实现保持登录状态;


**小结:**

1. cookie 是存在浏览器上的 存在浏览器上相对比较危险; session 是存在服务器上的 存在服务器上相对比较安全;


# 9. 基础理论_页面的正确打开方式

![b/s和c/s](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211235754.png)

文件后缀说明:

文件的后缀, 对文件中的内容没影响, 后缀的作用无非就是告诉操作系统, 操作系统应该以什么方式来打开这个文件, 以什么样的方式来打开这个文件; (比如说你写了一个html格式的文件, 然后把后缀给改成 txt 结尾, 然后你依旧选择用浏览器来打开, 页面上展示的效果肯定都是一样的)

![服务器和服务容器](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210211235803.png)

# 10. 实战应用_安装WebSever插件

安装liver sever插件

# 11. 实战应用_发送网络请求

发送网络请求的常见方式有以下几种:

- [ ] 1 在浏览器中直接输入网址。

**缺点:**

 无法用代码控制，需要手动输入；

- [ ] 2 location.href="url", 可以发出网络请求, 但是页面会发生跳转。

`location.href="http://www.taobao.com"`

**缺点:**

页面会跳转, 会直接跳转到淘宝的首页;

而通常, 我们发送网络请求的目的 通常是在当前页面的基础上, 更新当前页面的一些信息用的;

`Q:` 如何保留页面跳转前的网络请求信息?

`A:` 页面发生跳转后, 若想保存之前页面的一些请求信息, 那么我们可以把 `Network` 选项卡下的 `Preserve log` 给勾选上即可;

![2-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212110458.png)

- [ ] 3 带有src属性的标签。

**缺点:**

请求是可以发出的，服务端是可以处理的也是可以返回的。但是返回之后，能否被应用，还要看浏览器。

页面可能无法处理返回结果

img标签下的src属性，那么请求的数据应该是图片；如果请求的是页面，那么将不能被应用；

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>img带有src属性</title>
</head>

<body>
    这是利用img标签的src属性请求过来的数据: <img src="http://www.baidu.com"></img>
</body>

</html>
```

![3-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212112626.png)

> 通过这类发出请求的方式, 我们还可以发出带参数的请求, 比如: `<img src="http://www.baidu.com?a=1&b=2&wd=hello"></img>`
> 带有src属性的标签 还有 script , 如果我们使用 script标签下的src属性来发送请求, 实际上请求也是可以发出的, 而且, 服务器是无法区分 该请求是 script标签下的src属性发出的 还是 img标签下的src属性发出的

- [ ] 4 带有href属性的标签。

**缺点:**

请求是可以发出的，服务端是可以处理的也是可以返回的。但是返回之后，能否被应用，还要看浏览器。

页面可能无法处理返回结果；

> 和 src 类似

- [ ] 5 带有action属性的标签。例如form表单，也可以向后端发出请求。但是form表单发出请求之后，也会页面跳转。

**缺点:**

页面会发生跳转；

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>form表单</title>
</head>

<body>
    <form action="http://www.baidu.com" method="GET">
        <p>
            name: <input type="text" name="name">
        </p>
        <p>
            age: <input type="text" name="age">
        </p>
        <p>
            <input type="submit" value="提交">
        </p>
    </form>
</body>

</html>
```


![5-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212120255.png)

![5-2](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212120519.png)

---

`希望有一种方式，可以用代码发出请求，页面不会跳转，服务端返回的结果我可以用js继续处理。`

- [ ] 6 `ajax`

发出请求的两个要素
1. 请求方式: get,post
2. 请求链接: url

```js
var xhr = null;
if (window.XMLHttpRequest) {
    xhr = new XMLHttpRequest(); // IE6不支持
} else {
     xhr = new ActiveXObject("Microsoft.XMLHttp"); // IE6支持
}
xhr.open("get", "http://developer.duyiedu.com/edu/testAjax"); // 参数1是 请求方式 参数2是请求链接
// http://developer.duyiedu.com/edu/testAjax 渡一提供的一个接口
xhr.send();
// 以 live sever 的方式打开页面
```

直接请求, 是可以请求到的, 但是如果通过 ajax 来请求, 那么会出现跨域问题, 有关跨域问题的内容, 下一节课会讲解;

![6-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212121802.png) ![6-2](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212122003.png)

![6-3](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212130705.png)

# 12. 实战应用_跨域

1. 访问网上的哪些资源可能会发生跨域?
2. 跨域需要具备的条件是?
3. 跨域这一行为发生在哪一个环节?
4. 如果跨域了, 但依旧想要获取到数据, 那么有哪些对应的处理方式?

**跨域访问资源**

1. 哪些东⻄属于资源？
   js⽂件算吗？js⽂件肯定是算资源的，但是js⽂件是允许被跨域请求的。
   css⽂件，jpg,png等都算是资源。
2. 哪些资源是允许被跨域请求的?
   1. src属性的资源都是可以被跨域请求的。
   2. href资源⼤部分都是可以被跨域请求的。
3. 哪些资源算跨域请求的资源？
   1. 后端接⼝的数据。
   2. 其它域的cookie
   3. 其它域的缓存
4. 什么是其它的域？怎么样算跨域？
   ⻚⾯本身：有协议（http/https）,域名，端⼝
   要请求的数据：`http://www.baidu.com:80`
   协议，域名，端⼝这三个，有任意⼀个不⼀样就算跨域。(路径信息随意)


**跨域这个⾏为，发⽣在哪⾥？**

1. 即使跨域了（协议，域名，端⼝号有不⼀样的），请求也可以发出。
   也就是说, 跨域这个行为, 不是发生在请求发出的时候
2. 服务器端也是可以接收的。
3. 服务器端也是可以正常处理的。
4. 服务器端也是可以正常返回数据。
5. 浏览器也能接收到这些数据。
6. 接收到之后，发现当前⻚⾯的域和请求的域不同（协议，域名，端⼝号有不⼀样的），所以判定为跨域。
7. 我们的代码在这等着结果呢，但是因为浏览器判定跨域了，不会把结果传递给我们的代码。

答: 跨域是发生在浏览器接收到服务器传递过来的数据之后的;

**解决跨域问题**

虽然跨域了，但是我们依然需要这个数据，怎么办？

需要分两种情况来考虑:

1. 后端（别⼈家的）配合我们进⾏跨域。
   `pan.baidu.com` 访问 `zhidao.baidu.com` 虽然它们的一级域名都是 `baidu.com` 但是它们的二级域名不同(`pan.baidu.com`和`zhidao.baidu.com`是二级域名), 所以这也算是跨域请求资源;
   对于这样的情况, 我们有两种解决方式:
      1. JSONP（正常的情况，返回的数据都是JSON格式。JSONP是⼀种特殊的格式。最后节课讲）
      2. 后端设置Access-Control-Allow-Origin属性以⽀持跨域。（聊天机器⼈课讲，因为需要nodejs）
2. 后端不配合我们进⾏跨域。
   1. iframe（只能显示，不能控制）如：`<iframe src="http://www.baidu.com"></iframe>`；
   2. 通过后端代理（⾃⼰的后端）（后⾯聊天机器⼈讲，因为需要nodejs）

---

- [ ] 方式1 JSONP

![20210212131050](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212131050.png)

- [ ] 方式2 后端设置Access-Control-Allow-Origin属性以⽀持跨域

```js
var xhr = null;
if (window.XMLHttpRequest) {
    xhr = new XMLHttpRequest(); // IE6不支持
} else {
     xhr = new ActiveXObject("Microsoft.XMLHttp"); // IE6支持
}
xhr.open("get", "http://developer.duyiedu.com/edu/testAjaxCrossOrigin");
// http://developer.duyiedu.com/edu/testAjaxCrossOrigin 这是经过允许跨域处理的接口
// 处理方式: 后端设置Access-Control-Allow-Origin属性
xhr.send();
```

![20210212130531](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212130531.png)

---

**小结**

遇到跨域的情况：协议、域名、端口，只要有一个不一样，就会发生跨域；

我们处理跨域问题, 得分情况考虑;

# 13. 实战应用_原生JS发送Ajax

**reference:**

1. [XMLHttpRequest 对象(w3school)](https://www.w3school.com.cn/xml/xml_http.asp)
2. [XMLHttpRequest 对象(mdn)](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest)
3. [HTTP状态码 (菜鸟教程)](https://www.runoob.com/http/http-status-codes.html)

- [ ] demo 1 3.1

```js
var xhr = null;
if (window.XMLHttpRequest) {
    xhr = new XMLHttpRequest();
} else {
    xhr = new ActiveXObject("Microsoft.XMLHttp");
}
console.log(xhr.readyState); // 0
xhr.open("get", "http://developer.duyiedu.com/edu/testAjaxCrossOrigin", false); // 初始化服务连接
console.log(xhr.readyState); // 1
xhr.onreadystatechange = function () {
    console.log(xhr.readyState); // 2 3 4
    // readyState == 4表示请求完成，已经接收到数据。
    // status == 200  网络请求，结果都会有一个状态码。来表示这个请求是否正常
    // 200表示请求成功
    // http状态码
    // 2**表示成功
    // 3**表示重定向
    // 4**表示客户端错误,404页面没找到。
    // 5**表示服务端错误
    if (xhr.readyState == 4 && xhr.status == 200) {
        document.getElementById("test").innerText = xhr.responseText;
        var data = JSON.parse(xhr.responseText);
        console.log(data);
    }
}
xhr.send();//如果open第三个参数传true，或者不传，为异步模式。如果传false，为同步模式。
// 异步: 请求数据的后续代码的执行 同时进行;
// 同步: 请求数据时, 会阻塞, 后续代码无法执行, 知道数据请求到了之后, 后续代码才会继续执行;
// 通常, 代码的执行速度 比 网络中数据请求的速度 快
console.log("111"); // open传true或者不传 ==> 先打印111、222，再打印data
console.log("222"); // open传false ==> 先打印data，再打印111、222
// 在计算机的世界里，异步与同步和现实世界中是相反的。
// 在计算机的世界里，同步表示串行。异步表示同时进行。
// 同步和异步 就好比操作系统中的 同线程和异线程。
```

**notes:**

1. `xhr.send();` 要写在 `xhr.onreadystatechange` 的后面, 这是为了防止, 服务器都已经把数据返回给我们了, 我们的事件处理函数都还没绑定好;
   简单点说: 就是我们还没准备好用来处理接收到的数据的函数, 数据就已经到了;

| XMLHttpRequest实例方法  | 描述                                           | link                                                                                              |
| ----------------------- | ---------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `XMLHttpRequest.open()` | XMLHttpRequest.open() 方法初始化一个请求。     | [XMLHttpRequest.open() mdn](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/open) |
| `XMLHttpRequest.send()` | XMLHttpRequest.send() 方法用于发送 HTTP 请求。 | [XMLHttpRequest.send() mdn](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/send) |

---

| XMLHttpRequest实例属性 | 描述                                                   | link                                                                                                                         |
| ---------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| `readyState`           | 它是ajax的一个属性，它会随着ajax发送进度的变化而变化； | [XMLHttpRequest.readyState(mdn)](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/readyState)                 |
| `onreadystatechange`   | 一旦readyState 的值发生变化，就执行事件处理函数；      | [XMLHttpRequest.onreadystatechange(mdn)](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/onreadystatechange) |
| `responseText`         | 返回的结果存放在 responseText 属性里；                 | [XMLHttpRequest.responseText(mdn)](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/responseText)             |
| `status`               | 它是http状态码, 200 表示请求成功, 404 表示页面未找到   | [XMLHttpRequest.status(mdn)](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/status)                         |





- [ ] demo 13.2

封装 ajax

```js
/**
 * 原生js封装ajax
 * @param {String} url 请求的链接
 * @param {Function} success 请求成功后的回调函数
 */
function ajax(url, success) {
    var xhr = null;
    if (window.XMLHttpRequest) {
        xhr = new XMLHttpRequest(); // code for all new browsers
    } else {
        xhr = new ActiveXObject("Microsoft.XMLHttp"); // code for IE5 and IE6
    }
    xhr.open("get", url, false); // 同步
    xhr.onreadystatechange = function () {
        if (xhr.readyState == 4 && xhr.status == 200) {
            var data = JSON.parse(xhr.responseText);
            success && success(data);
        }
    }
    xhr.send();
}
```


# 14. 实战应用_JSONP的使用与特性

- [ ] 正常情况下返回的数据

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>注意正常情况下返回的数据</title>

</head>

<body>
    <div id="test"></div>

    <script>
        var xhr = null;
        if (window.XMLHttpRequest) {
            xhr = new XMLHttpRequest();
        } else {
            xhr = new ActiveXObject("Microsoft.XMLHttp");
        }
        xhr.open("get", "http://developer.duyiedu.com/edu/testAjaxCrossOrigin", false);
        xhr.onreadystatechange = function () {
            //readyState == 4表示请求完成，已经接收到数据。
            //status == 200  网络请求，结果都会有一个状态码。来表示这个请求是否正常
            //200表示请求成功
            // http状态码
            //2**表示成功
            //3**表示重定向
            //4**表示客户端错误,404页面没找到。
            //5**表示服务端错误
            if (xhr.readyState == 4 && xhr.status == 200) {
                document.getElementById("test").innerText = xhr.responseText;
                var data = JSON.parse(xhr.responseText);
                console.log(data);
            }
        }
        xhr.send(); //如果open第三个参数传true，或者不传，为异步模式。如果传false，为同步模式。
        console.log("====");
        console.log("+++");

        //在计算机的世界里，异步与同步和现实世界中是相反的。
        // 在计算机的世界里，同步表示串行。异步表示同时进行。可以理解为同线程和异线程。
    </script>
</body>

</html>
```


![14-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212144823.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!-- 需要引入 jQuery -->
    <script src="jquery.js"></script>
    <script>
        //jsonp格式哪里特殊？
        //发送的时候，会带上一个参数callback
        //返回的结果不是json
        //callback的名 + ( + json + );
        $.ajax({
            url: "http://developer.duyiedu.com/edu/testJsonp",
            type: "post",
            dataType: "jsonp",
            success: function (data) {
                console.log(data);
            }
        });

        //jsonp跨域，只能使用get方法，如果我们设置的是post方法，jquery会自动转为get方法。
        //是不是在jsonp里面我只能使用get方法？是不是我设置的post方法都会转为get方法？
        //不是。
        //jquery会先判断是否同源，如果同源(它就假装自己使用的不是jsonp的方式)，那么设置的是get就是get，设置的post就是post
        //如果不是同源，无论设置的什么，都改为get.

    </script>
</head>
<body>

</body>
</html>
```

![14-2](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212144912.png)

![14-3](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212144932.png)

![14-4](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212144945.png)

jsonp的原理, 下节课会讲;

# 15. 实战应用_JSONP原理

我想从一个接口获取一个数据, 但是这个接口和当前页面不是同源的。（也就是跨域了）但是这个接口是支持JSONP的。

`Q:` 那么我们用什么方法, 可以骗过浏览器, 并把想要的数据获取到呢?
`A:` 可以利用script标签上的src属性来实现;

- [x] demo 15.1

jQuery cdn

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js" integrity="sha512-bLT0Qm9VnAYZDflyKcBaQ2gg0hSYNQrJ8RilYldYQ1FxQYoCLtUjuuRuZo+fjqhx/qtq/1itJ0C2ejDxltZVFg==" crossorigin="anonymous"></script>
    <title>引入一个 jQuery的CDN</title>
</head>
<body>

</body>
</html>
```

![jQuery cdn](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212151421.png)

虽然该jQuery的文件是一个跨域的资源, 但是 src属性依旧可以请求过来, 浏览器不会限制, 因为跨域发生在数据请求过来之后;

并且, 这些数据在被判定为跨域资源之前, 浏览器还会执行请求过来的数据作为js代码执行;

![20210212152046](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212152046.png)

---

- [x] demo 15.2

比如我们之前使用的一个使用jsonp处理过的接口: `http://developer.duyiedu.com/edu/testJsonp`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <script src="http://developer.duyiedu.com/edu/testJsonp?callback=hahaha"></script>
    <title>jsonp</title>
</head>
<body>

</body>
</html>
```

**notes:**

1. `<script src="http://developer.duyiedu.com/edu/testJsonp?callback=hahaha"></script>`
   1. 这么写就相当于调用了咋们本地的一个函数, 函数名为`hahaha`
   2. 传递给该函数的参数, 就是被认为是跨域的数据

![15.2-1](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212152551.png)

![15.2-2](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212152852.png)

- [x] demo 15.3

尝试定义一个函数来处理接收到的数据

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <script>
        /**
         * data 就是后端给我们传递的数据 (json对象)
         *
         */
        function hahaha(data) {
            console.log(data);
            console.log(`这是从后端传递过来的数据
            该data是一个对象. 该对象具有以下两个属性:
            1. status: ${data.status}
            2. msg: ${data.msg}`);
            console.log(`哈哈哈哈哈哈哈`);
        }
    </script>
    <script src="http://developer.duyiedu.com/edu/testJsonp?callback=hahaha"></script>
    <title>jsonp</title>
</head>

<body>

</body>

</html>
```

![20210212153421](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212153421.png)

---

**JQuery 的 JSONP原理**

1. 判断请求与当前页面的域，是否同源，如果同源则发送正常的ajax，就没有跨域的事情了。
2. 如果不同源，生成一个script标签
3. 生成一个随机的callback名字，还得创建一个名为这个的方法。
4. 设置script标签的src，设置为要请求的接口。
5. 将callback作为参数拼接在后面。
> 1-5 是前端部分
6. 后端接收到请求后，开始准备要返回的数据
7. 后端拼接数据，将要返回的数据用callback的值和括号包裹起来
     例如：callback=asd123456，要返回的数据为{"a":1, "b":2},
     就要拼接为：asd123456({"a":1, "b":2});
8. 将内容返回。
> 6-8 是后端部分
9. 浏览器接收到内容，会当做js代码来执行。
10. 从而执行名为asd123456的方法。这样我们就接收到了后端返回给我们的对象。

**小结:**

1. 前端生成 script 标签
2. 后端拼接字符串

- [x] **模拟jQuery里的jsonp实现原理**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>jQuery jsonp</title>
</head>

<body>
    <script>
        var $ = {
            ajax: function (options) {
                var url = options.url;
                var type = options.type;
                var dataType = options.dataType;

                //判断是否同源（协议，域名，端口号）
                //获取目标url的域
                var targetProtocol = ""; //目标接口的协议
                var targetHost = ""; //目标接口的host，host是包涵域名和端口的
                //如果url不带http，那么访问的一定是相对路径，相对路径一定是同源的。
                if (url.indexOf("http://") == 0 || url.indexOf("https://") == 0) {
                    var targetUrl = new URL(url);
                    targetProtocol = targetUrl.protocol;
                    targetHost = targetUrl.host;
                } else {
                    targetProtocol = location.protocol;
                    targetHost = location.host;
                }

                //首先判断是否为jsonp，因为不是jsonp不用做其他的判断，直接发送ajax
                if (dataType == "jsonp") { // 主要模拟jsonp 其他情况这里就不模拟了
                    //要看是否同源
                    if (location.protocol == targetProtocol && location.host == targetHost) { //表示同源
                        //此处省略。因为同源，jsonp会当做普通的ajax做请求
                    } else { //不同源，跨域
                        //随机生成一个callback
                        var callback = "cb" + Math.floor(Math.random() * 1000000);
                        //给window上添加一个方法
                        window[callback] = options.success;
                        //生成script标签。
                        var script = document.createElement("script");
                        if (url.indexOf("?") > 0) { //表示已经有参数了
                            script.src = url + "&callback=" + callback;
                        } else { //表示没有参数
                            script.src = url + "?callback=" + callback;
                        }
                        script.id = callback;
                        document.head.appendChild(script);
                    }
                }
            }
        }
        // 测试用例
        $.ajax({
            url: "http://developer.duyiedu.com/edu/testJsonp",
            type: "get",
            dataType: "jsonp",
            success: function (data) {
                console.log(data);
            }
        });
    </script>
</body>

</html>
```

![jQuery jsonp](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210212161313.png)

jsonp原理的本质就是生成 `script标签` 又因为 `src属性` 是允许跨域的, 然后我们使用src属性去请求后端的东西, 而且script标签还有一个特点: 就是它要求通过src属性请求回来的东西, 必须是js代码, 而且它还会执行该js代码;