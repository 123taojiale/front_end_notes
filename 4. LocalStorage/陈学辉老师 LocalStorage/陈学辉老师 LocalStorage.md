# 1. cookie

```
为什么有 cookie?
    我们会使用 cookie 来长期存储数据

为什么要用 cookie 来长期存储数据?
    我们学习的 http 它是上下文无关, 无状态协议, 所以我们得使用 cookie 来解决
    cookie 其实就是用来关联多次不同请求之间的联系
```

![cookie原理](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/cookie原理.png)

```
1. cookie不可跨域
2. cookie存储在浏览器里面
3. cookie有数量与大小的限制
    1. 数量在50个左右
    2. 大小在4kb左右
4. cookie的存储时间非常灵活
5. cookie不光可以服务器(后端)设置，客户端(前端)也可以设置
```

**document.cookie**

```
1. name		cookie的名字，唯一性
2. value	cookie的值
3. domain	设置cookie在哪个域下是有效的
4. path		cookie的路径
5. expires	cookie的过期时间点
6. max-age	cookie的有效时间段
7. HttpOnly	有这个标记的cookie，前端是无法获取的
8. Secure	设置cookie只能通过https协议传输
9. SameSite	设置cookie在跨域请求的时候不能被发送

notes:
   1. domain 和 path 主要限制 cookie 限定其在指定的域名和指定的路径下才有效
   2. express 若不设置, 那么它的值默认是 Session, 表示浏览器一关闭, 该 cookie 就消失 (也称为会话期的cookie)
      若要给 express 赋值, 那么需要赋 GMT 格式的时间 (new Date() 所返回的时间格式 就是 GMT 格式)
   3. max-age 设置的是 cookie 的有效时间段
      3种值 -1、0、正数
         -1 -> 临时的 cookie 它不会生成
         0 -> 该 cookie 的生命周期已经到了 马上就要失效了
         正数 -> 该 cookie 还能存活的秒数
   4. 最后介绍的3个属性 HttpOnly、Secure、SameSite 我们前端只能看 不能操作
```

- [x] demo1

![20210226130528](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226130528.png)

```js
// 一次若设置多组 Name-Value 那么只有第一组有效
document.cookie = 'name=kaivon';
document.cookie = 'age=18; sex=1;';
```

- [x] demo2

使用 domain 和 path 来限定 cookie 的有效区域

```js
document.cookie = 'color=red; domain=127.0.0.1; path=/docs';
```

![20210226131449](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226131449.png)

![20210226131358](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226131358.png)

- [x] demo3

```js
// GMT 格式的时间
new Date(); // Fri Feb 26 2021 13:15:55 GMT+0800 (中国标准时间)
```

- [x] demo4

使用 expires 设置 cookie 的有效时间点

```js
document.cookie = 'hahaha=20; expires=' + new Date(2008, 1, 1); // 失效时间点 2008年 2月 1号 早就过了 浏览器中不会保存
document.cookie = 'hehehe=20; expires=' + new Date(2108, 1, 1); // 失效时间点 2108年 2月 1号 还没到 浏览器中会保存
```

![20210226131941](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226131941.png)

- [x] demo5

使用 max-age 设置 cookie 的剩余生命周期

```js
document.cookie = "abc=123; max-age=3;"
setTimeout(() => {
    console.log(`document.cookie -> ${document.cookie}`);
}, 2000);
setTimeout(() => {
    console.log(`document.cookie -> ${document.cookie}`);
}, 4000);
```

![20210226133303](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226133303.png)

- [ ] demo6

请求会携带 cookie

chrome 控制台没看懂...

```js
// 网络课上简单封装的 ajax
function ajax(url, success) {
    var xhr = null;
    if (window.XMLHttpRequest) {
        xhr = new XMLHttpRequest();
    } else {
        xhr = new ActiveXObject("Microsoft.XMLHttp");
    }
    xhr.open("get", url, false);
    xhr.onreadystatechange = function () {
        if (xhr.readyState == 4 && xhr.status == 200) {
            var data = JSON.parse(xhr.responseText);
            success && success(data);
        }
    }
    xhr.send();
}
```

```json
// 学生信息管理系统中的部分数据
{
    "status": "success",
    "msg": "查询成功",
    "data": [
        {
            "id": 6,
            "name": "张某某2",
            "birth": 1997,
            "sex": 1,
            "sNo": "11009",
            "email": "382246268@qq.com",
            "phone": "18846411586",
            "address": "黑龙江省哈尔滨市XXXX",
            "appkey": "demo13_1545210570249",
            "ctime": 1547190636,
            "utime": 1547190636
        },
        {
            "id": 7,
            "name": "张某某2",
            "birth": 1997,
            "sex": 1,
            "sNo": "11010",
            "email": "382246268@qq.com",
            "phone": "18846411586",
            "address": "黑龙江省哈尔滨市XXXX",
            "appkey": "demo13_1545210570249",
            "ctime": 1547190666,
            "utime": 1547190666
        }
    ]
}
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>cookie</title>
</head>

<body>
    <button id="btn">发送请求</button>
    <script src="./ajax.js"></script>
    <script>
        document.cookie = "duyi=2021;"; // 设置一个 cookie
        btn.onclick = function () {
            console.log(document.cookie);
            ajax('./data.json', function (data) {
                console.log(data);
            });
        }
    </script>
</body>

</html>
```

![20210226134554](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226134554.png)

![20210226134729](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226134729.png)

# 2. cookie封装及应用

```
经过上节课对 cookie 的了解, 我们发现 我们 读写 cookie 只有一个原生的接口 document.cookie
而且我们读取的话, 是读取全部的 cookie, 而不能读取指定的 cookie, 所以本课程将封装一个 manageCookie 对象, 实现对 cookie 的基本操作, 并完成一个 拖拽实例;
```

- [x] manageCookie

```js
let manageCookie = {
    /* 添加 */
    set: function (name, value, date) {
        // 方式1: 使用 expires 来设置 cookie 的生命周期 (此时传进来的 date 表示该 cookie 的生命周期的剩余天数)
        /* let endDate = new Date(); // 过期时间点
        endDate.setDate(endDate.getDate() + date);
        document.cookie = `${name}=${value}; expires=${endDate};` */
        // 方式2: 使用 max-age 来设置 cookie 的生命周期 (此时传进来的 date 表示该 cookie 的生命周期的剩余秒数)
        document.cookie = `${name}=${value}; max-age=${date};`;
    },
    /* 删除 */
    remove: function (name) {
        this.set(name, "", 0); // 只要把 剩余的生命周期设置为 0 即可删除指定的 cookie
    },
    /* 读取 */
    get: function (name) {
        let cookies = document.cookie.split(';'),
            len = cookies.length;
        for (let i = 0; i < len; i++) {
            let item = cookies[i].split('=');
            if (item[0].trim() == name) {
                return item[1];
            }
        }
    }
}

// 测试一下 (注意: 要以 live server 的方式打开)
/* manageCookie.set('left', 100, 10000);
manageCookie.set('duyi', 'good', 10000);
console.log(document.cookie);
manageCookie.remove('duyi');
console.log(document.cookie);
console.log(manageCookie.get('left')); */
```

- [x] drag

```
该拖拽实例, 要求页面刷新时, 其当前位置不会改变
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>封装cookie操作及拖拽应用</title>
    <style>
        #box {
            position: absolute;
            left: 0;
            top: 0;
            height: 100px;
            width: 100px;
            border-radius: 50%;
            background-color: #008c8c;
            opacity: 0.5;
            cursor: pointer;
        }
    </style>
</head>

<body>
    <div id="box"></div>
    <script src="./manageCookie.js"></script>
    <script>
        let drag = {
            init: function (dom) {
                this.dom = dom;
                this.bindEvent();

                let newLeft = manageCookie.get('newLeft');
                let newTop = manageCookie.get('newTop');

                this.dom.style.left = newLeft ? newLeft + 'px' : '0';
                this.dom.style.top = newTop ? newTop + 'px' : '0';
            },
            bindEvent: function () {
                this.dom.onmousedown = this.mouseDown.bind(this);
            },
            mouseDown: function (e) {
                document.onmousemove = this.mouseMove.bind(this);
                document.onmouseup = this.mouseUp.bind(this);

                this.disX = e.clientX - this.dom.offsetLeft;
                this.disY = e.clientY - this.dom.offsetTop;
            },
            mouseMove: function (e) {
                this.newLeft = e.clientX - this.disX;
                this.newTop = e.clientY - this.disY;

                this.dom.style.left = this.newLeft + 'px';
                this.dom.style.top = this.newTop + 'px';
            },
            mouseUp: function () {
                document.onmousemove = null;
                document.onmouseup = null;

                // 鼠标抬起的时候, 使用 cookie 记录下当前元素所在的位置
                manageCookie.set('newLeft', this.newLeft, 3600); // 1小时后失效
                manageCookie.set('newTop', this.newTop, 3600); // 1小时后失效
            }
        }

        drag.init(box);
    </script>
</body>

</html>
```

# 3. localstorage

```
之前我们学习过了 cookie, 虽然它可以用来存储数据, 但是, 它的大小还是只有 4kb(因浏览器而异) 左右的
由于其容量还是偏小, 所以我们一般不会用 cookie 来实现本地数据的存储
在 localstorage 之前, 我们可能还是会首选 cookie 来实现本地数据的存储, 那也是没办法, 因为只有 cookie 能用
```

参考文章: [详说 Cookie, LocalStorage 与 SessionStorage](https://jerryzou.com/posts/cookie-and-web-storage/)

```
Web Storage
    1. localStorage 它的大小在 5MB 左右 (因浏览器而异 在 chrome 上 其大小是 10MB)
    2. sessionStorage (不常用 不细讲)
Web Storage 和 cookie 之间的区别
    Web Storage 不依赖于 http协议
    cookie 依赖于 http协议
```

- [x] demo1

localStorage 和 sessionStorage 都继承自 Storage 对象

![20210226205631](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226205631.png)

```
1、length       获取本地存储数据的数量
2、key()        通过索引找到存储的数据
3、getItem()    获取一个本地存储的数据
4、setItem()    设置一个本地存储的数据
5、removeItem() 删除一个本地存储的数据
6、clear()      清空本地存储的数据

notes:
  key() 方法比较鸡肋, 就是我们在存储数据的时候, 它不是按照索引来存储的
  比如说我们在本地存储了一条数据 age = 18
  随后, 我们又存储了一条数据 sex = 0
  按理来说 若 第一条数据的索引是 n 那么接下来存储的那条数据的索引就是 n + 1
  但实际上, 第二个数据的索引不一定是 n + 1, 这和数组不一样, 所以说, key() 这个方法很鸡肋...
```

- [x] demo2

![20210226211305](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226211305.png)

```js
console.log(localStorage.length); // 0
```

- [x] demo3

```js
// 现在我们添加几条原始类型的数据 (注意顺序)
localStorage.setItem('name', 'kaivon');
localStorage.setItem('age', '18');
localStorage.setItem('sex', 'male');
localStorage.setItem('insterest', 'drink');
```

![20210226211656](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226211656.png)

- [x] demo4

```js
// 添加原始类型的数据 会先调用自身的 toString 方法 再将结果添加至 value 中
var color1 = ["red", "green"];
var color2 = { "c1": "red", "c2": "green" };
localStorage.setItem('color1', color1);
localStorage.setItem('color2', color2);
```

![20210226212133](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226212133.png)

![20210226212240](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226212240.png)

- [x] demo5

```js
// 添加引用类型的数据需要转化为 JSON 格式
// 不需要删除之前的错误数据 因为新的 value 会覆盖之前的值
// localStorage.removeItem('color1');
// localStorage.removeItem('color2');
var color1 = ["red", "green"];
var color2 = { "c1": "red", "c2": "green" };
localStorage.setItem('color1', JSON.stringify(color1));
localStorage.setItem('color2', JSON.stringify(color2));
```

- [x] demo6

```
注意:
  我们读取过来的数据 实际上也是 JSON 格式的字符串
  所以对于引用类型来说, 我们需要先使用 JSON.parse(数据) 将其转化后再使用
```

```js
var color1 = ["red", "green"];
var color2 = { "c1": "red", "c2": "green" };

localStorage.setItem('color1', JSON.stringify(color1));
localStorage.setItem('color2', JSON.stringify(color2));

// 直接读取 得到的是 JSON格式的字符串
let c1 = localStorage.getItem('color1'),
    c2 = localStorage.getItem('color2');
console.log(c1, typeof c1);
console.log(c2, typeof c2);
// 需要使用 JSON.parse() 将其转化 才能获得我们想要的数据
let parse_c1 = JSON.parse(localStorage.getItem('color1')),
    parse_c2 = JSON.parse(localStorage.getItem('color2'));
console.log(parse_c1, typeof parse_c1);
console.log(parse_c2, typeof parse_c2);
```

![20210226213409](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226213409.png)

- [x] demo7

```js
// 使用 removeItem 来删除数据
localStorage.removeItem('color1');
```

![20210226213644](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226213644.png)

- [x] demo8

```js
// 使用 clear 来清空数据
localStorage.clear();
```

![20210226213927](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226213927.png)

- [x] demo9

```
除了使用原生API removeItem来删除数据, 我们还可以在控制台选中指定数据进行删除 或 清空
```

![20210226214139](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210226214139.png)

```
补充:
  在浏览器的无痕模式下, 我们使用的 localStorage 是临时的, 当我们关闭浏览器, 它就会自动被清除;
```

# 4. localStorage应用1

```
购物车案例 - 前半部分
```

# 5. localStorage应用2

```
购物车案例 - 后半部分
补充功能:
    1. 一键清空购物车效果
    2. 不同页面之间的联动效果
```

- [x] demo1

`storage事件`

```js
window.addEventListener('storage', function (e) {
    console.log('当 localStorage 发生改变时 就会在其他同样绑定了 storage事件 的页面中触发');
    /* 认识该事件的几个关键属性 */
    console.log(e.key); // 被修改的那个 localStorage 的名字
    console.log(e.newValue); // 修改后的新数据
    console.log(e.oldValue); // 修改前的旧数据
    console.log(e.storageArea); // 返回 storage 对象
    console.log(e.url); // 返回当前正在操作的页面的 url
})
```

# 6. Resultful API

参考文章: [RESTful API 设计指南 (阮一峰)](http://www.ruanyifeng.com/blog/2014/05/restful_api.html)

```
Resultful API 是什么?
    是一种互联网软件架构的设计规范、设计指南、设计风格、设计原则
下面分为两个部分来理解:
    1. API
    2. Result
```

**1. API**

```
API (Application Programming Interface)
    中文: 应用程序接口（接口）
    在之前没有 API 的时候, 会采用下面这种模板字符串来实现数据的展示 (老程序员也许知道 dede cms)
```

```html
<ul>
    {dede:arclist typeid="1" row="6"}
    <li>[field:title function="cn_substr(@me, 63)" /]</li>
    {/dede:arclist}
</ul>
```

**2. Rest**

```
Rest (Resource Representational State Transfer)
    中文: 资源表述性状态传递
1. Resource (资源)
    URI:统一资源标识符。是一个字符串。用来标识互联网资源的名称
    URL:统一资源定位符。它是一种具体的URI
2. Representational (表现层)
3. State Transfer (状态转化)

notes:
    1. URI 和 URL 之间的关系
       URI 可以理解为一个 构造函数
       URL 可以理解为该构造函数所创建的一个实例对象
    2. Representational -> 资源的表现形式
       比如:
          文本资源就有多种表现形式, 如: text\html\xml\json\二进制 等等
```

---

**Restful API具体设计规范**

```
1. 协议
   HTTPS
2. 域名
   若我们的网站域名是: https://www.dahuyou.top 那么我们所提供的API的域名有以下两种推荐写法
   1. https://api.dahuyou.top
   2. https://wwww.dahuyou.top/api/
3. 版本
    https://api.dahuyou.top/v1
4. 路径
    注意: 路径中不允许出现 动词, 并且路径名要求和数据库中的文件名儿 对应
       正确写法: https://api.dahuyou.top/v1/blogs (数据库中的技术文章放在表 blog 内, 路径名为 blogs 表示获取所有技术文章)
       错误写法: https://api.dahuyou.top/v1/getblogs
5. 方法 (资源可以发生状态变化 也就是说 我们是可以操作这些资源的, 而操作资源的方式, 我们得通过HTTP所提供的一些方法来操作它们)
   1. GET       获取资源
      GET https://api.dahuyou.top/v1/blogs          获取所有的文章
      GET https://api.dahuyou.top/v1/blogs/id       获取到某一篇文章 (每一个资源一般都会带有一个id 通过该资源的id 我们可以直接获取到指定的资源)
   2. POST      添加资源
      POST https://api.dahuyou.top/v1/blogs         增加一篇文章
   3. PUT       修改资源 (客户端需要提供改变后的 完整资源)
      POST https://api.dahuyou.top/v1/blogs/id      修改某一篇文章
   4. PATCH	    更新资源 (客户端需要提供改变的属性)
      PATCH https://api.dahuyou.top/v1/blogs/id     更新某一篇文章
   5. DELETE    删除资源
      DELETE https://api.dahuyou.top/v1/blogs/id    删除某一篇文章
6. 数据过滤
   1. ?limit=10                 指定返回数据的数量
      GET https://api.dahuyou.top/v1/blogs?limit=10
   2. ?offset=10                指定一个偏移量 (表示从第10条数据开始获取)
      GET https://api.dahuyou.top/v1/blogs?offset=10
   3. ?page=2&per_page=10       指定第几页，以及每页的数量 (表示每页展示10条数据, 展示第2页的10条数据, 也就是展示 10-19条数据)
      GET https://api.dahuyou.top/v1/blogs?offset=10
   4. ?sortby=time&order=arc    指定返回结果按照哪个属性排序，以及排序的方式 (sortby=time ==> 按照时间排序 order=arc ==> 升序)
      GET https://api.dahuyou.top/v1/blogs?sortby=time&order=arc
   PS: limit offset 这些名儿 是由后端来取的 通常会取上述名来表示这些的含义
       数据过来还远不止上面提到的这些, 这里仅仅是举几个例子来认识认识
7. 状态码
8. 返回结果
   1. GET       资源对象列表（数组），如果取的是一条数据，那返回一个对象
   2. POST      返回添加后的资源对象，以及有可能会加上是否成功
   3. PUT       返回修改后的资源对象，以及有可能会加上是否成功
   4. PATCH     返回更新后的资源对象，以及有可能会加上是否成功
   5. DELETE    返回空，以及有可能会加上是否成功
9. 返回的数据格式
   尽量使用JSON，避免使用XML
```

---

**状态码 (HTTP stuts code)**

服务器向用户返回的状态码和提示信息，常见的有以下一些（方括号中是该状态码对应的HTTP动词）。

![20210227182822](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210227182822.png)

```
200 OK                          [GET]               服务器成功返回用户请求的数据，该操作是幂等的（Idempotent）。
201 CREATED                     [POST/PUT/PATCH]    用户新建或修改数据成功。
202 Accepted                    [*]                 表示一个请求已经进入后台排队（异步任务）
204 NO CONTENT                  [DELETE]            用户删除数据成功。
400 INVALID REQUEST             [POST/PUT/PATCH]    用户发出的请求有错误，服务器没有进行新建或修改数据的操作，该操作是幂等的。
401 Unauthorized                [*]                 表示用户没有权限（令牌、用户名、密码错误）。
403 Forbidden                   [*]                 表示用户得到授权（与401错误相对），但是访问是被禁止的。
404 NOT FOUND                   [*]                 用户发出的请求针对的是不存在的记录，服务器没有进行操作，该操作是幂等的。
406 Not Acceptable              [GET]               用户请求的格式不可得（比如用户请求JSON格式，但是只有XML格式）。
410 Gone                        [GET]               用户请求的资源被永久删除，且不会再得到的。
422 Unprocesable entity         [POST/PUT/PATCH]    当创建一个对象时，发生一个验证错误。
500 INTERNAL SERVER ERROR       [*]                 服务器发生错误，用户将无法判断发出的请求是否成功。
```

**小结**

```
1. 看 URL 就知道要什么
2. 看 HTTP method 就知道干什么
3. 看 HTTP stuts code 就知道结果如何
```
