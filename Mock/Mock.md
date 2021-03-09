# 1. mock语法

**加载 Mock**

```html
<script src="http://mockjs.com/dist/mock.js"></script>
```

---

[Mock.js](http://mockjs.com/)

[Mock.js 示例](http://mockjs.com/examples.html)

[YApi 可视化接口管理平台](https://github.com/YMFE/yapi)

```
在后端没有给我们提供数据时, 我们可以使用 mock.js 来模拟生成后端传递过来的数据

因为在大多数情况下, 我们前端的工作一般都是在后端做好接口后, 才开始做的

这样就会显得十分的被动

mock.js 在某些层面 也许可以缓解一下这样的问题

在 mock 之前, 如果业务并不算复杂, 通常, 一些前端工程师会自己手动的写一些数据到 JSON 文件中, 用来模拟后端传递过来的数据

这样的做法虽然也行的通, 但是很多时候就显得过于低效了, 所以还得学习学习 mock.js 这门课程...

如果会后端的话, mock.js 好像就没那么有必要学习了...
```

## 1. 语法规范

```js
// 1. 属性值是字符串 String
console.log(
    Mock.mock({
        'data1|1-4': '陈学辉', // 随机重复1-4次
        // 'name|min-max': string
        // 通过重复 string 生成一个字符串，重复次数大于等于 min，小于等于 max。
        'data2|3': '好帅', // 固定重置3次
        // 'name|count': string
        // 通过重复 string 生成一个字符串，重复次数等于 count。
    })
);

// 2. 属性值是数字 Number
console.log(
    Mock.mock({
        'number1|+1': 100, // 整数，自动加1并且初始值为100
        /* 'name|+1': number
            属性值自动加 1，初始值为 number。 */
        'number2|1-100': 12, // 整数，1-100之间的随机数，包括1和100（1=<数字<=100）	12用来确定是数据为数字类型
        /* 'name|min-max': number
            生成一个大于等于 min、小于等于 max 的整数，属性值 number 只是用来确定类型。 */
        'number3|1-100.5': 12, // 小数，整数部分为为1-100间随机数，包括1和100；小数部分为固定5位随机数
        'number4|1-100.1-10': 12, // 小数，整数部分为为1-100间随机数，包括1和100；小数部分为1-10个随机数（位数随机，数字也随机）
        'number5|123.1-10': 12, // 数字123后面随机添加1-10位小数
        'number6|123.10': 12, // 数字123后面固定添加10位小数，但小数的值是随机的
        /* 'name|min-max.dmin-dmax': number
            生成一个浮点数，整数部分大于等于 min、小于等于 max，小数部分保留 dmin 到 dmax 位。 */
    })
);

// 3. 属性值是布尔型 Boolean
console.log(
    Mock.mock({
        'b1|1': false, // 随机生成一个布尔值，true与false的概率各为一半
        /* 'name|1': boolean
            随机生成一个布尔值，值为 true 的概率是 1/2，值为 false 的概率同样是 1/2。 */
        'b2|1-5': true,
        /* 'name|min-max': value
            随机生成一个布尔值，值为 value 的概率是 min / (min + max)，值为 !value 的概率是 max / (min + max)。 */
    })
);

// 4. 属性值是对象 Object
console.log(
    Mock.mock({
        'num1|1-3': { a: 10, b: 20, c: 30, d: 40 }, // 随机选取对象里1-3个属性
        /* 'name|min-max': object
            从属性值 object 中随机选取 min 到 max 个属性。 */
            'num2|2': { a: 10, b: 20, c: 30, d: 40 }, // 随机选取对象里2个属性
        /* 'name|count': object
            从属性值 object 中随机选取 count 个属性。 */
    })
);

// 5. 属性值是数组 Array
console.log(
    Mock.mock({
        'arr1|1': ['a', 'b', 'c', 'd', 'e'], // 随机选取数组里1个数据
        /* 'name|1': array
            从属性值 array 中随机选取 1 个元素，作为最终值。 */
        'arr2|1-3': ['a', 'b', 'c', 'd', 'e'], // 通过重复属性值生成一个新数组，min<=重复次数<=max
        /* 'name|min-max': array
            通过重复属性值 array 生成一个新数组，重复次数大于等于 min，小于等于 max。 */
    })
);

// 6. 属性值是函数 Function
console.log(
    Mock.mock({
        'result': function () { return 1 + 2 } // 把函数的返回值当作属性的结果
        /* 'name': function
            执行函数 function，取其返回值作为最终的属性值，函数的上下文为属性 'name' 所在的对象。 */
    })
)

// 7. 属性值是正则表达式 RegExp
console.log(
    Mock.mock({
        'reg1': /[a-z][A-Z][0-9]/,
        'reg2': /\w\W\s\S\d\D/,
        'reg3': /\d{5,10}/
        /* 'name': regexp
            根据正则表达式 regexp 反向生成可以匹配它的字符串。用于生成自定义格式的字符串。 */
    })
)
```

## 2. Random对象 Basic

[Basic](https://github.com/nuysoft/Mock/wiki/Basic)

![20210307121937](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210307121937.png)

```
Basics	基础类里的方法，共7个 以下内容主要介绍 这 7 个方法
```

```js
// Mock.Random
var Random = Mock.Random;
// console.log(Random);

// Random.boolean() 随机一个布尔值
console.log(
    Random.boolean(), // true 和 false 出现的概率 各占一半
    Random.boolean(1, 9, true), // 有 1 / 10 的概率出现 true 有 9 / 10 的概率出现 false
    Random.boolean(1, 2, false), // 有 1 / 3 的概率出现 false 有 2 / 3 的概率出现 true
);

// Random.natural() 随机一个自然数（大于等于 0 的整数）
console.log(
    Random.natural(), // 随机一个自然数 (0, 9007199254740992)
    Random.natural(100), // 随机一个自然数 (100, 9007199254740992)
    Random.natural(0, 50), // 随机一个自然数 (0, 50)
);

// Random.integer() 随机一个整数（包含负数）
console.log(
    Random.integer(), // 随意一个整数 (-9007199254740992, 9007199254740992)
    Random.integer(-100), // (-100, 9007199254740992)
    Random.integer(-50, 50), // (-50, 50)
);

// Random.float() 随机一个小数
console.log(
    Random.float(), // 随机一个浮点数
    Random.float(0),
    Random.float(-10, 10),
    Random.float(-10, 10, 3),
    Random.float(-10, 10, 2, 5),
    // Random.float(
    // 可选 整数部分的最小值 默认值为 -9007199254740992,
    // 可选 整数部分的最大值 默认值为 9007199254740992,
    // 可选 小数部分位数的最小值 默认值为 0,
    // 可选 小数部分位数的最大值 默认值为 17)
);

// Random.character() 随机一个字符
console.log(
    /* 语法: Random.character( pool? )
    Random.character()
    Random.character( 'lower/upper/number/symbol' )
    Random.character( pool ) */
    Random.character(), // Random.character( 'lower/upper/number/symbol' )
    Random.character('abc123'), // 在自定义的字符池 'abc123' 中随机返回一个字符
    Random.character('lower'), // 在指定的字符池 lower 中随机返回一个字符
    Random.character('symbol'), // 在指定的字符池 symbol 中随机返回一个字符
    /* {
    lower: "abcdefghijklmnopqrstuvwxyz",
    upper: "ABCDEFGHIJKLMNOPQRSTUVWXYZ",
    number: "0123456789",
    symbol: "!@#$%^&*()[]"
    } */
);



// Random.string() 随机一个字符串
console.log(
    /* 语法: Random.string( pool?, min?, max? )
    Random.string()
    Random.string( length )
    Random.string( pool, length )
    Random.string( min, max )
    Random.string( pool, min, max ) */
    Random.string(), // 随机生成不定长的字符串
    Random.string(5), // 随机生成长度为 5 的字符串
    Random.string(7, 10), // 随机生成长度为 5 - 7 的字符串
    Random.string('symbol', 5), // 随机生成长度为 5 的字符串 (字符串中的字符 由 symbol 字符池 中的字符构成)
    Random.string('abc123', 1, 3), // 随机生成长度为 1 - 3 的字符串 (字符串中的字符 由 'abc123' 字符池 中的字符构成)
);

// Random.range() 随机一个整数数据的数组
console.log(
    /* Random.range( start?, stop, step? )
    Random.range( stop )
    Random.range( start, stop )
    Random.range( start, stop, step ) */
    Random.range(7), // (7) [0, 1, 2, 3, 4, 5, 6]
    Random.range(3, 7), // (4) [3, 4, 5, 6]
    Random.range(1, 10, 2), // (5) [1, 3, 5, 7, 9]
    // start 指定数组中整数的起始值
    // stop  指定数组中整数的结束值
    // step  指定数组中整数之间的步长
);
```

# 2. Random对象

## 1. Random对象 Date

[Data](https://github.com/nuysoft/Mock/wiki/Date)

- [x] Random.date()

```js
Random.date(), // 默认值为 yyyy-MM-dd
// => "2002-10-23"
Random.date('yyyy-MM-dd'),
// => "1983-01-29"
Random.date('yy-MM-dd'),
// => "79-02-14"
Random.date('y-MM-dd'),
// => "81-05-17"
Random.date('y-M-d'),
// => "84-6-5"
```

```js
// Random.date() 随机一个日期
console.log(
    /* Random.date( format? )
    format 指示生成的日期字符串的格式。默认值为 yyyy-MM-dd。 */
    Random.date(), // 随机生成一个日期 eg: 1984-07-30
    Random.date('yyyy-MM--dd : HH-m-ss'),
);
```

- [x] Random.time()

```js
Random.time() // 默认值为 HH:mm:ss
// => "00:14:47"
Random.time('A HH:mm:ss')
// => "PM 20:47:37"
Random.time('a HH:mm:ss')
// => "pm 17:40:00"
Random.time('HH:mm:ss')
// => "03:57:53"
Random.time('H:m:s')
// => "3:5:13"
```

```js
// Random.time() 随机一个时间
console.log(
    Random.time(),
    Random.time('A HH:mm:ss:SS'), // 大写的 SS 表示 毫秒
);
```

- [x] Random.datetime()

```js
Random.datetime() // 默认值为 yyyy-MM-dd HH:mm:ss
// => "1977-11-17 03:50:15"
Random.datetime('yyyy-MM-dd A HH:mm:ss')
// => "1976-04-24 AM 03:48:25"
Random.datetime('yy-MM-dd a HH:mm:ss')
// => "73-01-18 pm 22:12:32"
Random.datetime('y-MM-dd HH:mm:ss')
// => "79-06-24 04:45:16"
Random.datetime('y-M-d H:m:s')
// => "02-4-23 2:49:40"
```

```js
// Random.datetime() 随机一个日期 + 时间
console.log(
    Random.datetime(), // 1993-02-17 15:38:45
);
```

- [x] Random.now()

```js
Random.now()
// => "2014-04-29 20:08:38 "
Random.now('day', 'yyyy-MM-dd HH:mm:ss SS')
// => "2014-04-29 00:00:00 000"
Random.now('day')
// => "2014-04-29 00:00:00 "
Random.now('yyyy-MM-dd HH:mm:ss SS')
// => "2014-04-29 20:08:38 157"

Random.now('year')
// => "2014-01-01 00:00:00"
Random.now('month')
// => "2014-04-01 00:00:00"
Random.now('week') // week 表示跳转到这一周的第一天 (周日)
// => "2014-04-27 00:00:00"
Random.now('day')
// => "2014-04-29 00:00:00"
Random.now('hour')
// => "2014-04-29 20:00:00"
Random.now('minute')
// => "2014-04-29 20:08:00"
Random.now('second')
// => "2014-04-29 20:08:38"
```

```js
// Random.now() 返回当前的日期和时间字符串
// week 定到这个周的第一天
console.log(
    Random.now(), // 2021-03-07 12:42:58
    Random.now('minute'), // 2021-03-07 12:42:00
    // 'minute' 表示时间精确到 分钟
);
```

## 2. Random对象 Image

[Image](https://github.com/nuysoft/Mock/wiki/Image)

- [x] Random.image()

生成一个随机的图片地址。

> Random.image() 用于生成高度自定义的图片地址，一般情况下，应该使用更简单的 [Random.dataImage()](https://github.com/nuysoft/Mock/wiki/Image#randomdataimage-size-text-)。

```js
Random.image()
// => "http://dummyimage.com/125x125"
Random.image('200x100')
// => "http://dummyimage.com/200x100"
Random.image('200x100', '#fb0a2a')
// => "http://dummyimage.com/200x100/fb0a2a"
Random.image('200x100', '#02adea', 'Hello')
// => "http://dummyimage.com/200x100/02adea&text=Hello"
Random.image('200x100', '#00405d', '#FFF', 'Mock.js')
// => "http://dummyimage.com/200x100/00405d/FFF&text=Mock.js"
Random.image('200x100', '#ffcc33', '#FFF', 'png', '!')
// => "http://dummyimage.com/200x100/ffcc33/FFF.png&text=!"
```


```js
// Random.image() 生成一个随机的图片地址
console.log(
    Random.image(),
    // http://dummyimage.com/120x60
    Random.image('200x100'),
    // http://dummyimage.com/200x100
    Random.image('200x100', '#ffcc33', '#FFF', 'png', 'dahuyou'),
    // http://dummyimage.com/200x100/ffcc33/FFF.png&text=dahuyou

    // http://dummyimage.com 请求这网站的资源速度可能会有点慢 可以尝试将域名改为 placehold.it
    // 它们都是生成图片占位符的在线工具
    // http://placehold.it/200x100/ffcc33/FFF.png&text=dahuyou
);
```

![20210307140617](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210307140617.png)

![20210307140632](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210307140632.png)

![20210307140639](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210307140639.png)

- [x] Random.dataImage()

生成一段随机的 Base64 图片编码。

```js
// Random.dataImage() 生成一段随机的 Base64 图片编码
console.log(
    // Random.dataImage(),
    Random.dataImage('200x100'), // 太长了...
)
```

![20210307141223](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210307141223.png)

![20210307141248](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210307141248.png)

![20210307141314](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210307141314.png)

```
背景色是随机生成的
```

## 3. Random对象 Color

```js
// Random.color() 随机一个16进制的颜色
console.log(
    Random.color(),
);
```

```js
// Random.hex()
console.log(
    Random.hex(),
);
```

```js
// Random.rgb()
console.log(
    Random.rgb(), // 随机生成一个rgb格式的颜色
);
```

```js
// Random.rgba()
console.log(
    Random.rgba(), // 随机生成一个rgba格式的颜色
);
```

```js
// Random.hsl()
console.log(
    Random.hsl(), // 随机生成一个hsl格式(色相、饱和度、亮度)的颜色
);
```

## 4. Random对象 Text

```js
// Random.paragraph() 随机生成一段文本
console.log(Random.paragraph()); // 默认 1-7 句话 (英文)
console.log(Random.paragraph(2)); // 生成随机的 2 句话 (英文)
console.log(Random.paragraph(1, 3)); // 生成随机的 1 - 3 句话 (英文)

// Random.cparagraph() 随机生成一段中文文本。
console.log(Random.cparagraph()); // 默认 1 - 7 句话 (中文)
console.log(Random.cparagraph(2)); // 生成随机的 2 句话 (中文)
console.log(Random.cparagraph(1, 3)); // 生成随机的 1 - 3 句话 (中文)

// Random.sentence() 随机生成一个句子，句子首字母大写
console.log(Random.sentence()); // 默认生成一个句子 由 12 - 18 个英文单词构成
console.log(Random.sentence(5)); // 随机生成一个 由 5 个英文单词构成的句子
console.log(Random.sentence(1, 5)); // 随机生成一个 由 1 - 5 个英文单词构成的句子

// Random.csentence() 随机生成一段中文文本
console.log(Random.csentence()); // 默认生成一个句子 由 12 - 18 个汉字构成
console.log(Random.csentence(5)); // 随机生成一个 由 5 个汉字构成的句子
console.log(Random.csentence(1, 5)); // 随机生成一个 由 1 - 5 个汉字构成的句子

// Random.word() 随机生成一个单词
console.log(Random.word()); // 由 3 - 7 个字母组成
console.log(Random.word(5)); // 由  5 个字母组成
console.log(Random.word(1, 5)); // 由 1 - 5 个字母组成

// Random.cword() 随机生成一个汉字
console.log(Random.cword()); // 随机生成一个汉字
console.log(Random.cword(5)); // 随机生成 5 个汉字
console.log(Random.cword(1, 5)); // 随机生成 1 - 5 个汉字
console.log(Random.cword('零一二三四五六七八九十', 3)); // 从指定的汉字字符池中随机生成 3 个汉字
console.log(Random.cword('零一二三四五六七八九十', 5, 7)); // 从指定的汉字字符池中随机生成 5 - 7 个汉字

// Random.title() 随机生成一个标题，其中每个单词的首字母大写。
console.log(Random.title()); // 指示单词中字符的个数。默认值为 3 到 7 之间的随机数。
console.log(Random.title(3));
console.log(Random.title(1, 5));

// Random.ctitle() 随机生成一句中文标题
console.log(Random.ctitle()); // 指示单词中字符的个数。默认值为 3 到 7 之间的随机数。
console.log(Random.ctitle(3));
console.log(Random.ctitle(1, 5));
```

## 5. Random对象 Name

```js
// Random.first() 随机生成一个常见的英文名
console.log(Random.first())

// Random.last() 随机生成一个常见的英文姓
console.log(Random.last());

// Random.name() 随机生成一个常见的英文姓名
console.log(Random.name(true)); // 是否添加一个中间值

// Random.cfirst() 随机生成一个常见的中文名 (这个 应该是 姓)
console.log(Random.cfirst());

// Random.clast() 随机生成一个常见的中文姓 (这个 应该是 名)
console.log(Random.clast());

// Random.cname() 随机生成一个常见的中文姓名
console.log(Random.cname());
```

## 6. Random对象 Web

```js
// Random.url()	随机生成一个 URL
console.log(Random.url());
console.log(Random.url('http')); // 指定协议
console.log(Random.url('http', 'dahuyou.top')); // 指定域名

// Random.protocol() 随机生成一个 URL 协议
console.log(Random.protocol());

// Random.domain()	随机生成一个域名
console.log(Random.domain());

//Random.tld() 随机生成一个顶级域名
console.log(Random.tld());

// Random.email() 随机生成一个邮件地址
console.log(Random.email());
console.log(Random.email('dahuyou.top')); // 指定@后的域名

// Random.ip() 随机生成一个 IP 地址
console.log(Random.ip());
```

## 7. Random对象 Address

```js
// Random.region() 随机生成一个（中国）大区
console.log(Random.region());

// Random.province() 随机生成一个（中国）省（或直辖市、自治区、特别行政区）
console.log(Random.province());

// Random.city() 随机生成一个（中国）市
console.log(Random.city());
console.log(Random.city(true)); // 是否生成所属的省

// Random.county() 随机生成一个（中国）县
console.log(Random.county());
console.log(Random.county(true)); // 指示是否生成所属的省、市

// Random.zip() 随机生成一个邮政编码
console.log(Random.zip());
```

## 8. Random对象 Helper

```js
// Random.capitalize() 把字符串的第一个字母转换为大写
console.log(Random.capitalize('dahuyou'));

// Random.upper() 把字符串转换为大写
console.log(Random.upper('Dahuyou'));

// Random.lower() 把字符串转换为小写
console.log(Random.lower('DA'));

// Random.pick() 从数组中随机选取一个元素
console.log(Random.pick(['a', 'b', 'c', 'd', 'e']));

// Random.shuffle() 打乱数组中元素的顺序
console.log(Random.shuffle(['a', 'b', 'c', 'd', 'e']));
```

## 9. Random对象 Miscellaneous

```js
// Random.guid() 随机生成一个 GUID -> Globally Unique Identifier (全局唯一标识符)
console.log(Random.guid());

// Random.id() 随机生成一个 18 位身份证
console.log(Random.id());
```

## 10. DPD

[数据占位符定义规范（Data Placeholder Definition，DPD）](https://github.com/nuysoft/Mock/wiki/Syntax-Specification#%E6%95%B0%E6%8D%AE%E5%8D%A0%E4%BD%8D%E7%AC%A6%E5%AE%9A%E4%B9%89%E8%A7%84%E8%8C%83-dpd)

占位符 只是在属性值字符串中占个位置，并不出现在最终的属性值中。

```
@占位符
@占位符(参数 [, 参数])
```

```
注意：
  1. 用 @ 来标识其后的字符串是 占位符。
  2. 占位符 引用的是 Mock.Random 中的方法。
  3. 通过 Mock.Random.extend() 来扩展自定义占位符。 ***
  4. 占位符 也可以引用 数据模板 中的属性。
  5. 占位符 会优先引用 数据模板 中的属性。
  6. 占位符 支持 相对路径 和 绝对路径。
```

```js
Mock.mock({
    name: {
        first: '@FIRST', // 推荐大写 (并不强制)
        middle: '@FIRST',
        last: '@LAST',
        full: '@first @middle @last'
    }
})
// =>
{
    "name": {
        "first": "Charles",
        "middle": "Brenda",
        "last": "Lopez",
        "full": "Charles Brenda Lopez"
    }
}
```

**通过 Mock.Random.extend() 来扩展自定义占位符**

Mock.Random 中的方法与数据模板的 @占位符 一一对应，在需要时还可以为 Mock.Random 扩展方法，然后在数据模板中通过 @扩展方法 引用。

```js
Random.extend({
    constellation: function(date) {
        var constellations = ['白羊座', '金牛座', '双子座', '巨蟹座', '狮子座', '处女座', '天秤座', '天蝎座', '射手座', '摩羯座', '水瓶座', '双鱼座'];
        return this.pick(constellations);
    }
})
Random.constellation();
// => "水瓶座"
Mock.mock('@CONSTELLATION');
// => "天蝎座"
Mock.mock({
    constellation: '@CONSTELLATION',
})
// => { constellation: "射手座" }
```

# 3. mock方法

## 1. Mock.mock()

[Mock.mock()](https://github.com/nuysoft/Mock/wiki/Mock.mock())

根据数据模板生成模拟数据。

```json
// 使用 学生信息管理系统中的 查询所有学生的接口
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
<html>

<head>
	<meta charset="UTF-8">
	<title></title>
	<style>
		table {
			border-collapse: collapse;
			width: 90%;
			margin: 0 auto;
			font-size: 20px;
			line-height: 60px;
		}

		th,
		td {
			padding: 0;
			border: 1px solid #99b0da;
			text-align: center;
		}

		th {
			background: #dbe3fa;
		}
	</style>
</head>

<body>
	<script src="js/mock.js"></script>
	<script src="js/jquery-3.4.1.min.js"></script>

	<button id="btn">请求数据</button>
	<table>
		<thead>
			<tr>
				<th>学号</th>
				<th>姓名</th>
				<th>性别</th>
				<th>邮箱</th>
				<th>生日</th>
				<th>手机号</th>
				<th>住址</th>
				<th>操作</th>
			</tr>
		</thead>
		<tbody id="table-body"></tbody>
	</table>

	<script>
		$('#btn').click(function () {
			$.ajax({
				url: 'js/data.json',
				type: 'get',
				dataType: 'json',
				success: function (data) {
					console.log(data);
					createDom(data.data);
				}
			});
		});

		function createDom(data) {
			var str = '';
			data.forEach(function (item, index) {
				str += `
					<tr>
						<td>${item.sNo}</td>
						<td>${item.name}</td>
						<td>${item.sex}</td>
						<td>${item.email}</td>
						<td>${item.birth}</td>
						<td>${item.phone}</td>
						<td>${item.address}</td>
						<td>
							<button>编辑</button>
							<button>删除</button>
						</td>
					</tr>
				`;
			});
			$('#table-body').html(str);
		};


        // 拦截 ajax 请求 , 并生成模板数据, 模拟后端返回的数据
		Mock.mock('js/data.json', {
			"status": "success",
			"msg": "查询成功",
			"data|10": [{
				"id|+1": 1,
				"name": "@cname",
				"birth": "@date",
				"sex|1": ['男', '女'],
				"sNo|+1": 11000,
				"email": "@email",
				// "phone": "@natural(13000000000,19900000000)",
				"phone": /^(13[0-9]|14[5|7]|15[0|1|2|3|4|5|6|7|8|9]|18[0|1|2|3|5|6|7|8|9])\d{8}$/, // ^(13[0-9]|14[5|7]|15[0|1|2|3|4|5|6|7|8|9]|18[0|1|2|3|5|6|7|8|9])\d{8}$
				"address": "@county(true) @ctitle(5,10)",
				"appkey": "@string(4,7)_@date(T)",
				"ctime": "@date(T)",
           		"utime": "@date(T)"
			}],
		});

		Mock.setup({
			timeout:5000,
		});



		// https://github.com/YMFE/yapi
	</script>
</body>
<html>
```

## 2. Mock.setup()

配置拦截 Ajax 请求时的行为。支持的配置项有：timeout。

[Mock.setup()](https://github.com/nuysoft/Mock/wiki/Mock.setup())

指定被拦截的 Ajax 请求的响应时间，单位是毫秒。值可以是正整数，例如 400，表示 400 毫秒 后才会返回响应内容；也可以是横杠 '-' 风格的字符串，例如 '200-600'，表示响应时间介于 200 和 600 毫秒之间。默认值是'10-100'。

```js
Mock.setup({
    timeout: 400
})
Mock.setup({
    timeout: '200-600'
})
```

> 目前，接口 Mock.setup( settings ) 仅用于配置 Ajax 请求，将来可能用于配置 Mock 的其他行为。
