# 1. jQuery简介

**jQuery如何下载**

1. 进入jQuery官网: https://jquery.com/
2. 点击Download jQuery

![20210228132335](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210228132335.png)

![20210228132641](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210228132641.png)

![20210228132705](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210228132705.png)

**先将下载好的 jQuery文件引入页面**

```js
<script src="jquery-3.5.1.min.js"></script>
```

```
引入的 jquery-3.5.1.min.js 文件给我们提供了一个 jQuery 对象
实际上我们调用的 也就是这个对象里面的一些东西
```

```js
console.log(jQuery === $); // true
```

**ready、onload和DOMContentLoaded**

- [x] demo1

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>ready</title>
    <script src="./jquery-3.5.1.min.js"></script>
    <script>
        $(document).ready(function () {
            var box = document.getElementById('box');
            console.log(box);
        });

        $().ready(function () {
            var box = document.getElementById('box');
            console.log(box);
        });

        $(function () {
            var box = document.getElementById('box');
            console.log(box);
        });
    </script>
</head>

<body>
    <div id="box"></div>
</body>

</html>
```

```
虽然此时 script 标签 内部的 JavaScript 代码写在了 head 里面, 但是依旧可以获取到想要的元素 div#box
这是因为 ready 是等到页面中的所有元素加载完后触发的
以上是 jQuery 中 ready 的 3 种不同写法
    1. $(document).ready(function() {
        // 函数体
    });
    2. $().ready(funtion() {
        // 函数体
    });
    3. $(function() {
        // 函数体
    });
    这 3 种写法实现的都是相同的功能
```

![20210228200701](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210228200701.png)

- [x] demo2

ready onload addEventListener 3者之间的异同

```
为了测试, 我们先丢一个无效的图片链接 https://www.baidu.com/1.jpg
```

![20210228201712](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210228201712.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>demo2</title>
    <script src="./jquery-3.5.1.min.js"></script>
    <script>
        $(document).ready(function () {
            console.log('ready完成了');
        });
        window.onload = function () {
            console.log('load完成了');
        };
        document.addEventListener('DOMContentLoaded', function () {
            console.log('dom内容加载完毕');
        });
    </script>
</head>

<body>
    <div id="box"></div>
    <img src="https://www.baidu.com/1.jpg" alt="">
</body>

</html>
```

![20210228201905](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210228201905.png)

```
打印结果分析:
1. 为什么 onload 事件最后触发
   先打印的是 DOMContentLoaded 事件中的打印语句 和 ready 事件中的打印语句
   实际上 DOMContentLoaded 的功能和 ready 是相同的, 都是等到页面中的节点加载完毕就触发
   而 onload 是等到页面中所有的资源都请求到了以后才触发
2. 为什么 DOMContentLoaded 绑定在后面 反而 先触发
   这里其实不用过多纠结, 实际上 jQuery 中的 onload 事件 也是通过 DOMContentLoaded 来实现的, 只不过, 在 jQuery 实现这部分功能之前, 还处理了其他方面的一些内容, 所以导致了一定的延时
```

- [x] demo3

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>demo3</title>
</head>

<body>
    <button class="btn">显示一个绿色的小块</button>
	<div></div>
    <script>
        /* 利用原生js实现 */
        let btn = document.querySelector(".btn");
        btn.onclick = function () {
            let div = document.querySelector("div");
            div.style.width = '100px';
            div.style.height = '100px';
            div.style.border = '1px solid #ddd';
            div.style.background = 'green';
            document.body.appendChild(div);
        }
    </script>
</body>

</html>
```

```html
<!DOCTYPE html>
<html>

<head>
	<meta charset="UTF-8">
	<title>demo3</title>
	<script src="./jquery-3.4.1.js"></script>
</head>

<body>
	<button id="btn">显示一个绿色的小块</button>
	<div></div>
	<script>
		/* jQuery的写法 */
		$('#btn').click(function(){
			$('div').css({
				width:'100px',
				height:'100px',
				background:'green'
			}).appendTo('body');
		});
	</script>
</body>

</html>
```

![20210301162837](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301162837.png)

```
都是一样的效果 点击 "显示一个绿色的小块" 按钮后, 会显示如图所示的一个方块
```

- [x] demo4

```
jQuery 强大的选择器
```

```html
<!DOCTYPE html>
<html>

<head>
	<meta charset="UTF-8">
	<title>demo4</title>
	<script src="./jquery-3.4.1.js"></script>
</head>

<body>
	<ul class="new-list">
		<li class="item1">new1</li>
		<li class="item2">new2</li>
		<li class="item3">new3</li>
	</ul>
	<script>
		let ul = $('.new-list'), // 此时选择的是单个 ul
			list = $('.new-list li'); // 此时选择的是所有 li
		console.log(ul, list);
	</script>
</body>

</html>
```

![20210301164247](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301164247.png)

```
注意: 此时是使用 jQuery 来选中页面元素的, 它和原生的 js 选中的元素会有所不同; - 见 demo6
```

- [x] demo5

```
jQuery 强大的链式操作
```

```html
<!DOCTYPE html>
<html>

<head>
	<meta charset="UTF-8">
	<title>demo5</title>
	<script src="./jquery-3.4.1.js"></script>
</head>

<body>
	<p class="text"></p>
	<script>
		$('.text').html('大忽悠').css({
			border: '1px solid #ddd',
			opacity: '0.5',
			color: '#fff',
			lineHeight: '100px', // 注意 要转化为小驼峰的形式
			textAlign: 'center',
			margin: '0 auto'
		}).width(100).height(100).css('background', '#008c8c');
	</script>
</body>

</html>
```

![20210301164905](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301164905.png)

- [x] demo6

```html
<!DOCTYPE html>
<html>

<head>
	<meta charset="UTF-8">
	<title>demo6</title>
	<script src="./jquery-3.4.1.js"></script>
</head>

<body>
	<div class="box"></div>
	<script>
		let $div = $('.box'), // 这是使用 jQuery 选中的 div 元素
			div = document.querySelector('.box'); // 这是使用原生 js 选中的 div 元素

		console.log($div === div); // false

		// 注意点1: 用 jQuery 所选中的页面元素 无法使用 原生 js 中操作 DOM 节点的方法
		div.style.height = '100px';
		div.style.width = '100px';
		div.style.border = '1px solid #ddd'
		div.style.margin = '0 auto';
		/* $div.style.height = '100px'; // Uncaught TypeError: Cannot set property 'height' of undefined
		$div.style.width = '100px';
		$div.style.border = '1px solid #ddd'
		$div.style.margin = '0 auto'; */

		// 注意点2: 用 js 所选中的页面元素 无法使用 jQuery 中封装的操作 DOM 节点的方法
		$div.html('dahuyou').css({
			lineHeight: '100px',
			textAlign: 'center',
			color: '#666'
		})
		/* div.html('dahuyou').css({ // Uncaught TypeError: div.html is not a function
			lineHeight: '100px',
			textAlign: 'center',
			color: '#666'
		}) */

		// 注意点3: 原生获取到的元素 与 jQuery 获取到的元素 之间的相互转换
		$(div).css({ // 原生 转 jQuery
			fontWeight: 'bold'
		});
		$div[0].style.background = '#008c8c'; // jQuery 转 原生
		$div[0].style.opacity = '0.5';
	</script>
</body>

</html>
```

```
notes
  1. 两种方式选中的页面元素 返回的结果是不同的
     利用 jQuery 方式所选中的 div 元素在后续依旧可以调用 jQuery 中封装的些操作DOM节点的方法 但是不能调用原生的一些方法
     但是利用原生的 js 所选中的页面元素则无法使用 jQuery 中封装的一些操DOM节点的方法
  2. 这两种方式所选中的页面元素 它们之间是可以相互转化的 转化后 就可以正常使用本不可以用的一些操作 DOM 节点的方法 (具体内容 见code)
```

![20210301171632](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301171632.png)

![20210301171333](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301171333.png)

# 2. jquery选择器

```
这一部分的内容, 并没有包含 jQuery 中所有的 选择器, 只是其中的一部分
更多相关的 jQuery 选择器 可以直接上 下面提供的 jQuery 中文文档 里面查...
```

[jQuery中文文档 (选择器)](https://www.jquery123.com/category/selectors/)

```
下面要介绍的 jQuery 选择器 按照类型进行分类 分为以下 类
    1. 基础选择器
    2. 层级选择器
    3. 属性选择器
    4. 基础过滤选择器
    5. 子元素过滤选择器
    6. 内容过滤选择器
    7. 表单过滤选择器
notes: 多写一些 demo, 不然的话, 不清楚以下这些选择器的应用场景...
```

**1. 基础选择器**

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>基础选择器</title>
	<style>
		ul{
			width: 500px;
			margin: 0;
			padding: 0;
			list-style: none;
		}
		li{
			padding: 20px;
			margin-top: 10px;
			border: 1px solid #ddd;
		}
	</style>
</head>
<body>
	<ul class="list1">
		<li class="item1 list">Lorem ipsum dolor sit amet.</li>
		<li class="item2 list">Lorem ipsum dolor sit amet.</li>
	</ul>
	<ul class="list2">
		<li class="item3 list">Lorem ipsum dolor sit amet.</li>
		<li class="item4 list">Lorem ipsum dolor sit amet.</li>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>
</html>
```

![20210301200447](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301200447.png)

```js
$('.list1').css('color', '#f40');
```

![20210301200510](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301200510.png)

```js
$('.list').css('color', '#f40');
```

![20210301200616](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301200616.png)

```js
$('li.item1, li.item3').css('color', '#f40');
```

![20210301200717](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301200717.png)

**2. 层级选择器**

```html
<div>
	<a href="#" class="link">链接</a>
	<a href="#">链接</a>
	<a href="#">链接</a>
	<a href="#">链接</a>
	<p>
		<a href="#"></a>
	</p>
</div>
```

![20210301201653](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301201653.png)

```js
$('div a').css('color', '#f40');
```

![20210301201721](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301201721.png)

```js
$('div>a').css('color', '#f40');
```

![20210301201751](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301201751.png)

```js
$('div a.link + a').css('color', '#f40');
```

![20210301201851](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301201851.png)

```js
$('div a.link ~ a').css('color', '#f40');
```

![20210301201925](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301201925.png)

**3. 属性选择器**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>属性选择器</title>
	<style>
		ul {
			margin: 0;
			padding: 0;
			list-style: none;
		}

		ul li {
			float: left;
			width: 100px;
			height: 50px;
			line-height: 50px;
			text-align: center;
			font-weight: bold;
			border: 1px solid #ddd;
		}
	</style>
</head>

<body>
	<ul id="ulColor">
		<li class="red">item1</li>
		<li title="blue">item2</li>
		<li title="css-1">item3</li>
		<li id="color1-green">item4</li>
		<li id="red-1color">item5</li>
		<li lang="encnhk">item6</li>
		<li lang="en cn">item7</li>
		<li class="cl" name="kaivon">item8</li>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210301202756](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301202756.png)

```js
$('#ulColor li[class]').css('background', '#008c8c');
```

![20210301203159](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301203159.png)

```js
$('#ulColor li[title=blue]').css('background', '#008c8c');
```

![20210301215808](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301215808.png)

```js
$('#ulColor li[title!=blue]').css('background', '#008c8c');
```

![20210301215839](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301215839.png)

```js
$('#ulColor li[title|=css]').css('background', '#008c8c'); //前缀是用-隔开的 css-
```

![20210301215914](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301215914.png)

```js
$('#ulColor li[id^=color]').css('background', '#008c8c'); //以属性值为开始（不需要-隔开）
```

![20210301215955](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301215955.png)

```js
$('#ulColor li[id$=color]').css('background', '#008c8c'); //以属性值为结尾（不需要-隔开）
```

![20210301220027](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301220027.png)

```js
$('#ulColor li[lang*=cn]').css('background', '#008c8c'); //属性中包含cn字符串
```

![20210301235141](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301235141.png)

```js
$('#ulColor li[lang~=cn]').css('background', '#008c8c'); //属性中包含cn单词 (用空格隔开)
```

![20210301235245](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301235245.png)

```js
$('#ulColor li[class=cl][name=kaivon]').css('background', '#008c8c');
```

![20210301235303](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210301235303.png)

**4. 基础过滤选择器**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>基础过滤选择器</title>
	<style>
		ul {
			margin: 0;
			padding: 0;
			list-style: none;
			overflow: hidden;
			width: 600px;
			margin: 0 auto;
		}

		ul li {
			float: left;
			width: 100px;
			height: 50px;
			box-sizing: border-box;
			line-height: 50px;
			text-align: center;
			font-weight: bold;
			border: 1px solid #ddd;
		}
	</style>
</head>

<body>
	<ul class="olColor">
		<li>item0</li>
		<li>item1</li>
		<li lang="en">item2</li>
		<li>item3</li>
		<li id="tar">item4</li>
		<li>item5</li>
	</ul>

	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

```js
$('ul li:eq(1)').css('background', '#008c8c'); // 选中指定索引的元素
```

![20210302132952](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302132952.png)

```js
$('ul li:gt(1)').css('background', '#008c8c'); // 选中 大于 指定索引的元素
```

![20210302133105](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133105.png)

```js
$('ul li:lt(3)').css('background', '#008c8c'); // 选中 小于 指定索引的元素
```

![20210302133128](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133128.png)

```js
$('ul li:not(ul li:eq(2))').css('background', '#008c8c'); // 排除
```

![20210302133212](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133212.png)

```js
$('ul li:even').css('background', '#008c8c'); // 偶数
```

![20210302133247](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133247.png)

```js
$('ul li:odd').css('background', '#008c8c'); // 奇数
```

![20210302133442](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133442.png)

```js
$('ul li:first').css('background', '#008c8c'); // 第一个
```

![20210302133521](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133521.png)

```js
$('ul li:last').css('background', '#008c8c'); // 最后一个
```

![20210302133551](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133551.png)

```js
$('ul li:lang(en-us)').css('background', '#008c8c'); // 选择指定语言的所有元素
```

![20210302133607](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133607.png)

```js
$('ul li:target()').css('background', '#008c8c'); // tatget属性
```

![20210302133824](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133824.png)

```js
$(':root').css('background', '#008c8c'); //根节点
```

![20210302133848](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133848.png)

```html
<h1>h1</h1>
<h2>h2</h2>
<h3>h3</h3>
<h4>h4</h4>
```

```js
$(':header').css('background', '#008c8c'); //所有的h标签
```

![20210302133946](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302133946.png)

**5. 子元素过滤选择器**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>子元素过滤选择器</title>
	<style>
		* {
			margin: 0;
			padding: 0;
		}

		.paragraph {
			overflow: hidden;
			width: 700px;
			margin: 10px auto;
		}

		p,
		span {
			float: left;
			width: 100px;
			height: 50px;
			box-sizing: border-box;
			line-height: 50px;
			text-align: center;
			font-weight: bold;
			border: 1px solid #ddd;
		}
	</style>
</head>

<body>
	<!-- 子元素过滤器 -->
	<div class="paragraph">
		<p>p1</p>
		<p>p2</p>
		<span>span1</span>
		<p>p3</p>
		<span>span2</span>
		<p>p4</p>
		<span>span3</span>
	</div>
	<!-- <div id="only">
		<p>唯一的一个子元素</p>
	</div>
	<div id="only-two">
		<span>span</span>
		<p>p</p>
	</div> -->

	<script src="./jquery-3.4.1.js"></script>

	<script>
		// $('.only p:only-child').css('background', '#008c8c'); //选择到只有一个子元素的元素
		// $('.only-two span:only-of-type').css('background', '#008c8c'); //选择到只有一个span子元素的元素
	</script>
</body>

</html>
```

```js
$('.paragraph p:first-child').css('background', '#008c8c'); // 选中第一个子元素 并且该子元素必须是 p元素
```

![20210302141508](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302141508.png)

```js
$('.paragraph span:first-child').css('background', '#008c8c'); // 选中第一个子元素 并且该子元素必须是 span元素 (因为第一个子元素不是 span 元素 所以啥也没选中)
```

![啥也没选中](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302140927.png)

```js
$('.paragraph span:first-of-type').css('background', '#008c8c'); // 选择到第1个 span元素 并不要求该 span元素 是第一个子元素
```

![20210302141403](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302141403.png)

```js
$('.paragraph span:last-child').css('background', '#008c8c'); // 选中最后一个子元素 并且盖子元素必须是 span元素
```

![20210302141319](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302141319.png)

```js
$('.paragraph p:last-child').css('background', '#008c8c'); // 选中最后一个子元素 并且盖子元素必须是 p元素 (因为最后一个子元素 不是 p元素 所以啥也没选中)
```

![啥也没选中](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302140927.png)

```js
$('.paragraph p:last-of-type').css('background', '#008c8c'); // 选中最后一个p元素 并不要求该子元素 p 是最后一个子元素
```

![20210302141216](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302141216.png)

```js
$('.paragraph span:nth-of-type(2)').css('background', '#008c8c'); // 选中第二个 span元素 并不要求该子元素 span 是第二个子元素
```

![20210302140759](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302140759.png)

```js
$('.paragraph span:nth-child(2)').css('background', '#008c8c'); // 选中第二个子元素 并且该子元素必需是 span元素 (因为第二个子元素 不是 span元素 所以啥也没选中)
```

![啥也没选中](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302140927.png)

```js
$('.paragraph p:nth-child(2)').css('background', '#008c8c'); // 选中第二个子元素 并且该子元素必需是 p元素
```

![20210302140951](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302140951.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>子元素过滤选择器</title>
	<style>
		* {
			margin: 0;
			padding: 0;
		}

		.wrapper{
			width: 600px;
			margin: 10px auto;
		}

		p,
		span {
			float: left;
			width: 100px;
			height: 50px;
			box-sizing: border-box;
			line-height: 50px;
			text-align: center;
			font-weight: bold;
			border: 1px solid #ddd;
		}
	</style>
</head>

<body>
	<!-- 子元素过滤器 -->
	<div class="wrapper">
		<div class="one-child">
			<p>p1</p>
		</div>
		<div class="two-child">
			<span>span1</span>
			<p>p2</p>
		</div>
		<div class="three-child">
			<span>span2</span>
			<p>p3</p>
			<span>span3</span>
		</div>
	</div>


	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210302142232](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302142232.png)

```js
$('.two-child span:only-of-type').css('background', '#008c8c'); // 要求选中一个子元素 span 并且该类型的元素只有一个 (span2 和 span3不会被选中 因为它们的父级 three-child下 不只有一个 span元素)
```

![20210302142308](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302142308.png)

```js
$('.one-child p:only-child').css('background', '#008c8c'); // 要求仅有一个子元素 并且该子元素是p元素 选中该 p元素
```

![20210302142327](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302142327.png)

**6. 内容过滤选择器**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>内容过滤选择器</title>
	<style>
		* {
			margin: 0;
			padding: 0;
		}

		div {
			width: 100px;
			border: 1px solid #ddd;
			margin: 0 auto;
		}
	</style>
</head>

<body>
	<!-- 内容过滤选择器 -->
	<div id="content">dahuyou</div>
	<div></div>
	<div id="has">
		<p>p</p>
	</div>
	<div>
		<h1 id="title">h1</h1>
	</div>

	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210302191427](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302191427.png)

```js
$('#content:contains(dahuyou)').css('background', '#008c8c'); // 选中页面的一个 div 要求该 div 内部的内容包含 dahuyou
```

![20210302191212](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302191212.png)

```js
$('div:empty').css({ // 选中页面的的一个 div 要求该 div 内部的内容为空 (不可见字符 如: 括号 也算是内容)
	height: '100px',
	background: 'red'
});
```

![20210302191657](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302191657.png)

```js
$('#has:has(p)').css('background', '#008c8c'); // 选中页面中包含 p元素 的 #has 元素
```

![20210302191721](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302191721.png)

```js
$('#title:parent').css('background', '#008c8c'); // 选中页面中 #title元素 的父级元素
```

![20210302191749](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302191749.png)

**7. 表单过滤选择器**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>内容过滤选择器</title>
</head>

<body>
	<!-- 表单过滤选择器 -->
	<input type="button" value="按钮1">
	<button>按钮2</button>
	<div id="sex">
		<input type="checkbox">男
		<input type="checkbox">女
	</div>
	<div>
		<input type="checkbox" checked>男
		<input type="checkbox">女
	</div>

	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210302193503](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302193503.png)

```js
//表单过滤选择器
$(':button').css('color','#f0f');	// 选中页面中 所有的按钮 它不会区分是 input 标签 还是 button 标签
```

![20210302193648](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302193648.png)

```js
$('#sex input:checkbox').wrap('<span></span>').parent().css('border','1px solid #008c8c');
// $('#sex input:checkbox') 用于选中 #sex 下面的 type 为 checkbox 的 input元素
// .wrap('<span></span>') 为选中的 input元素 添加上一个父级 span
// .parent().css('border','1px solid #008c8c') 因为链式操作的那个对象依旧是开始时被选中的那个 input元素
// 而我们的css样式 是要添加到 span 身上的 所以得先取 input 的父级 span 然后再添加 css
```

![20210302193654](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302193654.png)

```js
$(':checked').wrap('<span></span>').parent().css('border','1px solid #008c8c');
```

![20210302193659](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210302193659.png)

# 3. DOM操作

## 1. 操作css

```
1. addClass('类名')
   添加指定类名
2. removeClass('类名')
   移除指定类名
3. hasClass('类名')
   判断是否含有某个类名
   返回值为 Boolean类型
4. toggleClass()
   切换class

notes
   若 removeClass() 传入的参数为空, 不传入指定的类名, 表示的是移除所有类名
```

- [x] toggleClass()

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>toggleClass()</title>
	<style>
		button {
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			border: none;
			outline: none;
			cursor: pointer;
		}

		.active {
			background-color: #cb4a61;
		}
	</style>
</head>

<body>
	<button class="active">加入购物车</button>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$('button').click(function () {
			$(this).toggleClass();
		});
	</script>
</body>

</html>
```

```
单击 button 其样式会在 有无 active 之间切换
```

![20210303093958](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303093958.png)

![20210303094003](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303094003.png)

## 2. 插入元素 (内部)

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>插入元素 (内部)</title>
	<style>
		p {
			border: 1px solid #ddd;
			text-align: center;
		}
	</style>
</head>

<body>
	<div class="insideAdd">
		<p>p1</p>
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303095158](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303095158.png)

```js
$('.insideAdd').append('<p>p2</p>');
// $(父元素).append(子元素) -> 用于将子元素 append 到父元素中 类似于原生的 appendChild 方法
```

```js
$('<p>p2</p>').appendTo($('.insideAdd'));
// $(子元素).appendTo(父元素)
```

![20210303095536](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303095536.png)

```js
$('.insideAdd').prepend('<p>p2</p>');
```

```js
$('<p>p2</p>').prependTo($('.insideAdd'));
```

![20210303100416](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303100416.png)

```js
$('.insideAdd').append('<h1>h1</h1>');
$('.insideAdd').append($('.insideAdd p')); // 插入是剪切操作
// 将p剪切出来 再 append 到 insideAdd 内部
```

![20210303095845](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303095845.png)

## 3. 插入元素 (外部)

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>插入元素 (外部)</title>
	<style>
		p {
			border: 1px solid #ddd;
			text-align: center;
		}
	</style>
</head>

<body>
	<div class="outsideAdd">
		<p>p1</p>
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303104332](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303104332.png)

```js
$('.outsideAdd p').after('<p>p2</p>');
```

```js
$('<p>p2</p>').insertAfter($('.outsideAdd p'));
```

![20210303104356](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303104356.png)

```js
$('.outsideAdd p').before('<p>p2</p>');
```

```js
$('<p>p2</p>').insertBefore($('.outsideAdd p'));
```

![20210303104733](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303104733.png)

```
notes
  以兄弟节点的方式插入
```

## 4. html 和 text

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>html 和 text</title>
	<style>
		p{
			border: 1px solid #ddd;
			text-align: center;
		}
	</style>
</head>

<body>
	<div class="html-text">
		<p>p1</p>
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303104332](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303104332.png)

```js
$('.html-text').html('<p>p2</p>');
```

![20210303105501](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303105501.png)

```js
console.log($('.html-text').html()); // <p>p1</p>
```

---

```js
$('.html-text').text('<p>p2</p>');
```

![20210303105554](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303105554.png)

```js
console.log($('.html-text').text()); // p1
```

```
notes
	相当于原生的 innerHTML 和 innerText
	可读 可写
	html 操作的是页面结构
	text 操作的是纯文本内容
```

## 5. 包裹元素

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>html 和 text</title>
	<style>
		.wrap {
			border: 1px solid #ddd;
			text-align: center;
		}
	</style>
</head>

<body>
	<div class="wrap">
		<span>1</span>
		<span>2</span>
		<span>3</span>
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303111144](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303111144.png)

```js
$('.wrap span').wrap('<li>'); // 给每个span标签添加上一个父级 li
```

![20210303111149](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303111149.png)

```js
$('.wrap span').wrap('<li>'); // 给每个span标签添加上一个父级 li
$('.wrap li').wrapAll('<ul>'); // 给选中的所有 li 标签 添加上一个父级 ul
```

![20210303111155](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303111155.png)

```js
$('.wrap span').wrapInner('<em>'); // 给选中元素的内容添加上包裹层
```

![20210303112003](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303112003.png)

```js
$('.wrap span').wrapInner('<em>'); // 给选中元素的内容添加上包裹层
$('.wrap em').unwrap(); // 将匹配到的元素的父级(包裹层)删除
```

![20210303112026](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303112026.png)

```
notes
	1. wrap 和 wrapAll
	wrap 是给每一个选中的元素添加上指定的父级 (选中多少个元素就添加多少个父级)
	wrapAll 是给所有选中的元素 添加上一个指定的父级 (选中所有符合条件的元素 仅添加一个父级)
	2. wrap 和 wrapInner
	wrap 是给指定的元素添加上包裹层
	wrapInner 是给指定的元素的内容添加上包裹层
```

## 6. 删除元素

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>删除元素</title>
</head>

<body>
	<div class="del">
		<div class="start">start</div>
		<ul>
			<li>li1</li>
			<li>li2</li>
			<li>li3</li>
		</ul>
		<div class="end">end</div>
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303114612](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303114612.png)

```js
$('.del .start').remove(); // 方式1: 直接找到指定元素 并删除它
/* 等价写法:
$('div').remove('.start'); // 方式2: 先找到所有div元素 然后再删除指定的 div元素 */
```

![20210303114634](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303114634.png)

```js
$('.del ul').empty(); // empty() 清空所有的子元素
```

![20210303114620](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303114620.png)

```js
$('.del .end').click(function () {
	alert(1);
});
let end = $('.del .end').detach(); // 再次 apeend 到页面中后 click 事件依旧存在 当我们点击 end 时 会弹出 1
// let end = $('.del .end').remove(); // 再次 apeend 到页面中后 click 事件依旧存在 当我们点击 end 时 不会弹出 1
setTimeout(() => { // 1s 之后, 将删除的 .end 重新出入到页面中
	$('.del').append(end);
}, 1000);
```

```
notes
	1. remove() 和 detach() -> 自杀
	2. empty() -> 谋杀
	3. remove() 和 detach() 之间的异同:
      	相同点: 它们都会返回被删除的 dom元素
      	不同点: remove() 会把绑定在元素身上的事件处理函数一起删除, detach() 会保留元素身上所绑定的事件处理函数
```

## 7. 克隆与替换元素

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>克隆 与 替换元素</title>
</head>

<body>
	<div class="clone">
		<p>p1</p>
		<h1 class="replaceAll">h1</h1>
		<div class="name1">taojiale</div>
		<div class="name2">dahuyou</div>
		<h2 class="replaceWidth">h2</h2>
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303150225](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303150225.png)

```js
$('.clone p').click(function () {
	alert(2);
});
$('.clone p').clone().appendTo('.clone');
```

![20210303150413](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303150413.png)

```js
$('.clone p').click(function () {
	alert(2);
});
$('.clone p').clone(true).appendTo('.clone'); // clone的参数为true时表示，会把事件也克隆了
```

```
此时若点击被克隆的 p1 会发现也会弹出一个 2
说明事件也一起被克隆了
```

```js
$('<h3>h3</h3>').replaceAll('.clone .replaceAll'); // A.replaceAll(B) -> 用A来覆盖B
```

![20210303150750](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303150750.png)

```js
$('.clone .name2').replaceAll('.clone .name1'); // 剪切操作
```

![20210303150835](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303150835.png)

```js
$('.clone .replaceWidth').replaceWith('<h3>h3</h3>'); // A.replaceWith(B) -> 用B来覆盖A
```

![20210303150900](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303150900.png)

## 8. 属性操作-通用属性操作

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>属性操作-通用属性操作</title>
</head>

<body>
	<div class="attr">
		<img src="images/img_01.jpg" width="200" alt="" dahuyou="niu">
		<img src="images/img_02.jpg" width="200" alt="" dahuyou="niu">
		<input type="text" value="这是一个正经的输入框">
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303154419](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303154419.png)

```js
console.log($('.attr img').attr('src')); // images/img_01.jpg
// 1. 若仅传入了一个参数 那么表示的是获取该属性的值
// 2. 若有多个img的 那么它获取到的是第一个
// 3. 对于 img元素 的 src属性 而言, attr 它返回的是一个 相对路径
```

![20210303155455](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303155455.png)

```js
$('.attr img').attr('title', '这是一张图片');
$('.attr img').attr({
	class: 'delicious',
	alt: '美食'
});
// 1. 若有多个img的话 设置的是所有的img
// 2. 可以同时设置多个属性
```

![20210303155538](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303155538.png)

```js
/* attr 和 prop 之间的异同 */
console.log($('.attr img').prop('src'));
console.log(
	$('.attr img').attr('dahuyou'), // niu
	$('.attr img').prop('dahuyou'), // undefined
);
// 1. 对于 img元素 的 src属性 而言, prop 它返回的是一个 绝对路径
// 2. attr 可以获取到 自定义的属性值 prop 不能获取到 自定义的属性值
```

![20210303155829](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303155829.png)

```js
$('.attr img').prop({
	id: 'food', // 非自定义属性
	dahuyou: 'niuniu', // 自定义属性
});
let food_img = document.querySelector("#food"); // 利用原生的方式 获取到对应的 DOM对象
console.log(food_img.getAttribute('dahuyou')); // niu
console.log(food_img.getAttribute('id')); // food
console.log(food_img.dahuyou); // niuniu
console.log(food_img.id); // food
// 注意: 自定义的属性 prop 并没有添加到 DOM 元素身上, 但是它会添加到 DOM 对象身上
// 可以理解为 若利用 prop 设置 属性值 是设置在 DOM 对象身上的
// 若设置的这个属性是自定义的属性 那么它将不会同步到 DOM元素 上
```

![20210303155906](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303155906.png)

```js
$('.attr img').attr('dahuyou', 'niuniuniu');
let food_img = document.querySelector("img");
console.log(food_img.dahuyou); // undefined (DOM对象上并没有该属性)
console.log(food_img.getAttribute('dahuyou')); // niuniuniu
// 若使用 attr 来设置 属性值 它相当于操作的就是 DOM元素
// 所以我们无法从指定的 DOM 对象上获取到我们先前设置好的属性的属性值
```

![20210303160040](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303160040.png)

```js
$('.attr img').removeAttr('dahuyou'); // 移除属性 dahuyou
$('.attr img').removeAttr('id'); // 移除属性 dahuyou
// 操作的是 DOM 元素
```

![20210303160125](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303160125.png)

```js
$('.attr img').removeProp('id');
// 操作的是 DOM 对象 但是 因为 id 并不是一个自定义的属性 所以会同步至 DOM 元素中
```

![20210303160157](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303160157.png)

```js
$('.attr img').prop('index', 5);
console.log($('.attr img').prop('index')); // 5 这条属性是添加在 DOM 对象身上
$('.attr img').removeProp('index');
console.log($('.attr img').prop('index')); // undefined -> removeProp 是删除 DOM 对象身上的属性
```

```js
console.log($('.attr input').val()); // 这是一个正经的输入框 (在 set 之前获取)
// 不传入参数 表示 get
$('.attr input').val('这不是一个输入框');
// 传入参数 表示 set
```

![20210303160438](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303160438.png)

```
小结
	attr -> 操作的是 DOM 元素
	prop -> 操作的是 DOM 对象 (若 prop 操作的那个属性 不是自定义属性 那么会同步到 DOM 元素身上)
```

## 9. 属性操作-css类属性操作

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>属性操作-css类属性操作</title>
	<style>
		.css {
			border: 2px solid #999;
		}
	</style>
</head>

<body>
	<div class="css">
		<h2>h2</h2>
		<p>p1</p>
		<div>div1</div>
	</div>
	<!-- img1 -->
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303170417](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303170417.png)

```js
/* get操作 */
console.log(
	$('.css').css('border'), // 2px solid rgb(153, 153, 153)
	$('.css').css('height'), // 129.828px
);
// 获取到的都是最终的计算结果
```

```js
/* set操作 */
$('.css h2').css('width', '200px').css('height', '100px').css('background', '#ccc').text('dahuyou');
$('.css h2').css({
	color: 'green',
	fontSize: '30px', /* 转小驼峰 */
	'line-height': '100px' /* JSON格式 */
});
// 1. 利用链式操作来实现 css 样式的添加
// 2. 利用对象的形式实现 一次性添加多条 css 样式
// 3. 对于那些 属性 -> 单词-单词 中间用 - 来拼接的属性, 既可以使用 小驼峰 的形式来写, 也可以使用 JSON 格式 的形式来写
```

![20210303170523](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303170523.png)

```js
/* 以下程序的公共code */
$('.css p').css({
	width: '50px',
	height: '50px',
	padding: '20px',
	margin: '20px auto',
	border: '5px solid #f00',
});
```

```js
/* set操作 和 get操作 */
console.log(
	$('.css p').width(), // 50
	$('.css p').height(), // 50
	$('.css p').innerWidth(), // 90	获取包含padding的宽度 (clientWidth 可视区的宽度值)
	$('.css p').innerHeight(), // 90
	$('.css p').outerWidth(), // 100 获取包含border的宽度 (offsetWidth 包含 border 区域的尺寸值)
	$('.css p').outerHeight(), // 100
);
```

![20210303170621](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303170621.png)

```js
/* inner 和 outer 的 set操作 */
$('.css p').width(100); // 把实际的宽度设置为 100
console.log($('.css p').width()); // 100
```

![20210303170713](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303170713.png)

```js
$('.css p').innerWidth(100); // 实际的 width === 100 - paddingLeft - paddingRight
console.log($('.css p').width()); // 60
```

![20210303170748](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303170748.png)

```js
$('.css p').outerWidth(200); // 实际的 width === 200 - paddingLeft - paddingRight - marginLeft - marginRight
console.log($('.css p').width()); // 150
```

![20210303170959](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303170959.png)

---

```js
/* 以下程序的公共code */
$('.css').css('position', 'relative'); // 先把父级设置成相对定位
$('.css div').css({
	width: '100px',
	height: '100px',
	background: 'green',
	position: 'absolute',
	left: '50px',
	top: '100px'
});
```

```js
console.log(
	$('.css div').offset().left, // 60
	$('.css div').offset().top, // 110
);
```

![20210303171107](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303171107.png)

```js
$('.css div').offset({
	left: 100,
	top: 100
});
console.log(
	$('.css div').offset().left, // 100
	$('.css div').offset().top, // 100
);
// 1. offset() 方法获取和设置的 left 和 top 是相对于 document 而言的
// 2. offset() 方法没有 .right 和 .bottom
```

![20210303171211](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303171211.png)

```js
console.log(
	$('.css div').position().left, // 50
	$('.css div').position().top, // 100
);

$('.css div').position({
	left: 200,
	top: 200
});

console.log(
	$('.css div').position().left, // 50
	$('.css div').position().top, // 100
);

// 1. position 获取的 left 和 top 是相对于有定位的父级的位置信息
// 2. position (貌似)无法写入 (在测试的时候 set操作无效 (没有报错 但是 div 的位置没有发生改变))
```

```js
console.log(
	$(document).scrollTop(), // 33.5
	$(document).scrollLeft(), // 0
);
setTimeout(function () {
	$(document).scrollTop(10); // set 滚动条距离顶部的距离为 10
	console.log(
		$(document).scrollTop(), // 10
		$(document).scrollLeft(), // 0
	);
}, 2000);
```

![20210303171316](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303171316.png)![20210303171325](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303171325.png)


# 4. 遍历

## 1. 获取后代元素

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>获取后代元素</title>
	<style>
		* {
			padding: 0;
			margin: 0;
		}

		ul {
			margin: 10px;
			list-style: none;
		}

		li {
			padding: 10px 20px;
			border: 1px solid #ccc;
		}

		li+li {
			margin-top: 10px;
		}
	</style>
</head>

<body>
	<ul class="child">
		<li>1</li>
		<li>
			<ul>
				<li>2</li>
				<li><span>3</span></li>
			</ul>
		</li>
		<li><span>4</span></li>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303192349](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303192349.png)

```js
$('.child').children().css('color', 'green');
$('.child').children(':eq(1)').css('border-color', 'red'); // 可以接收一个选择器的参数 这个选择器用来过滤子元素
// 1. children() 只能用于获取子元素 (也就是获取直接子代 li 下面的 span 它是获取不到的)
// 2. 参数可以传入 第 2 节讲的 jQuery选择器 对选中的子元素加以过滤
```

![20210303192428](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303192428.png)

```js
$('.child').find('span:eq(0)').css({
    'font-size': '2em',
    color: 'red'
});
// find() 获取匹配到的后代元素 (不仅仅是子元素)
```

![20210303192502](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303192502.png)


## 2. 获取祖先元素

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>获取祖先元素</title>
	<style>
		* {
			padding: 0;
			margin: 0;
		}

		ul {
			margin: 10px;
			list-style: none;
		}

		li {
			padding: 10px 20px;
			border: 1px solid #ccc;
		}

		li+li {
			margin-top: 10px;
		}
	</style>
</head>

<body>
	<ul class="parent" style="position: relative;">
		<li>1</li>
		<li>
			<ul>
				<li>2</li>
				<li>3</li>
				<li>4</li>
			</ul>
		</li>
		<li>5</li>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303194728](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303194728.png)

```js
$('.parent li ul li:first').parent('ul').css('border', '1px solid red');
// 1. parent() 获取到的是父元素 (包裹该元素的第一层父级)
// 2. parent() 也可以传入参数 jquery选择器 用于对选中的父级进行过滤
```

![20210303194834](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303194834.png)

```js
$('.parent li ul li:first').parents().css('border','1px solid red');
// 1. parents() 和 parent() 之间的区别在与 parent() 获取的是第一层父级 parents() 获取的是所有父级
// 2. 现象: 所有父级都加上了 指定的 border 样式
```

![20210303194919](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303194919.png)

```js
console.log($('.parent li ul li:first').parents());
// 会一直找到 html
```

![20210303195010](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303195010.png)

```js
$('.parent li ul li:first').parents('ul').css('border', '1px solid red');
// parents() 也可以传入一个 jquery 选择器 来过滤掉不匹配的父级
```

![20210303195051](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303195051.png)

```js
$('.parent li ul li:first').parentsUntil('li').css('border', '1px solid red');
// parentUntil() 以传入的参数作为查找的终点 (不包括该终点)
```

![20210303195102](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303195102.png)

```js
$('.parent li ul li:first').offsetParent().css('border', '1px solid red');
// 1. offsetParent() 用于获取最近的有定位的祖先元素
// 2. 若祖先元素都不是定位元素 则 获取到的是 html 元素
```

![20210303195231](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303195231.png)

## 3. 获取祖先元素 .closest()

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>获取祖先元素.closest()</title>
	<style>
		* {
			padding: 0;
			margin: 0;
		}

		ul {
			margin: 10px;
			list-style: none;
		}

		li {
			padding: 10px 20px;
			border: 1px solid #ccc;
		}

		li+li {
			margin-top: 10px;
		}
	</style>
</head>

<body>
	<ul class="closest">
		<li>
			<ul class="closest">
				<li>1</li>
				<li>2</li>
			</ul>
		</li>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303201735](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303201735.png)

```js
$('.closest li ul li').closest('ul').css('border', '1px solid red');
// closest 需要接收一个 jQuery选择器 作为参数 用于获取到指定的一个父级
```

![20210303201820](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303201820.png)

```js
$('.closest li ul li').parents('ul.closest').css('border','1px solid red');
// parents 获取到的是所有满足条件的父级
```

![20210303201827](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303201827.png)

```js
$('.closest li ul li').closest('ul.closest').css('border', '1px solid red');
// closest 获取到的是最近的满足条件的父级
```

![20210303201839](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303201839.png)

```js
$('.closest li ul li').parents('li').css('border','1px solid red');
// parents 获取到的是父级
```

![20210303201940](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303201940.png)

```js
$('.closest li ul li').closest('li').css('border', '1px solid red');
// closest 获取到的可以是自身及兄弟元素
```

![20210303202011](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303202011.png)


## 4. 获取后面的兄弟元素

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>获取后面的兄弟元素</title>
	<style>
		* {
			padding: 0;
			margin: 0;
		}

		ul {
			margin: 10px;
			list-style: none;
		}

		li,	p, div {
			padding: 10px 20px;
			border: 1px solid #ccc;
		}

		li+li, p, div {
			margin-top: 10px;
		}
	</style>
</head>

<body>
	<ul class="next">
		<li>1</li>
		<li>2</li>
		<li>
			<ul>
				<li>3</li>
			</ul>
		</li>
		<p>4</p>
		<div>5</div>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303212456](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303212456.png)

```js
$('.next li:first').next('li').css('borderColor', 'red');
// 1. next() 用于获取后面紧临的兄弟元素
// 2. 若传入一个 jQuery 选择器 作为参数 那么可以过滤掉不满足条件的兄弟元素
```

![20210303212536](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303212536.png)

```js
$('.next li:first').nextAll('li').css('borderColor', 'red');
// 1. nextAll() 获取后面所有的兄弟元素
// 注意: 3 不是 .next li:first 的兄弟元素 它的父级 ul 的 父级 li 才是
```

![20210303212626](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303212626.png)

```js
$('.next li:first').nextUntil('div').css('borderColor', 'red');
// 1. 获取后面所有的同辈兄弟元素 但是有个范围
// 2. 传入的参数 用于 限定终点 (不包括终点)
```

![20210303212647](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303212647.png)

## 5. 获取前面的兄弟元素

```
同前一个知识点 4. 获取后面的兄弟元素 一样
    1. prev() -> next()
    2. prevAll() -> nextAll()
    3. prevUntil() -> nextUntil()
```

## 6. 获取所有的兄弟元素

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>获取所有的兄弟节点</title>
	<style>
		* {
			padding: 0;
			margin: 0;
		}

		ul {
			margin: 10px;
			list-style: none;
		}

		li {
			padding: 10px 20px;
			border: 1px solid #ccc;
		}

		li+li {
			margin-top: 10px;
		}
	</style>
</head>

<body>
	<ul class="siblings">
		<li>0</li>
		<li class="select">1</li>
		<li>2</li>
		<li class="select">3</li>
		<li>
			<ul>
				<li>4</li>
			</ul>
		</li>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210303214056](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303214056.png)

```js
$('.siblings li:eq(2)').siblings().css('borderColor', 'red');
// 获取到所有兄弟元素 不包括自身
```

![20210303214116](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303214116.png)

```js
$('.siblings li:eq(2)').siblings('.select').css('borderColor', 'red');
// 过滤掉不满足条件的兄弟元素
```

![20210303214147](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210303214147.png)

# 5. 事件

## 1. 绑定事件的 3 种方式

### 1. 通过事件名称来绑定事件

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>绑定事件</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<button class="btn">加入购物车</button>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$('.btn').mouseover(function () { // 通过事件名 mouseover 来给按钮 .btn 绑定鼠标移入事件
			$(this).css('background', '#008c8c');
		}).mouseleave(function () { // 通过事件名 mouseleave 来给按钮 .btn 绑定鼠标移出事件
			$(this).css('background', '#f40');
		})
	</script>
</body>

</html>
```

![20210304121529](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304121529.png)

![20210304121523](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304121523.png)

### 2. 通过 on 来绑定事件

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>绑定事件</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<button class="btn">加入购物车</button>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

```js
$('.btn').on({ // 通过 on 的方式来绑定事件 可以为一个元素 一次性绑定多个事件
    mousemove: function () {
        $(this).css('background', '#008c8c'); // this 指向 .btn
    },
    mouseleave: function () {
        $(this).css('background', '#f40'); // this 指向 .btn
    }
});
```

![20210304121529](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304121529.png)

![20210304121523](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304121523.png)

```js
$('.btn').on('click', function () {
    $(this).css('background', '#008c8c');
});
$('.btn').on('click', {
    name: '移出购物车'
}, function (e) {
    $(this).text(e.data.name);
});
```

```
notes -> 通过 on 的方式来为一个元素绑定事件
    1. 若多次绑定同一个事件 那么效果会叠加 而不是覆盖
    2. 也可以传入 3 个参数, 其中一个参数是一个对象, 它可以用来存放一些数据, 这些数据我们可以在事件对象的 data 属性下获取
```

![20210304152511](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304152511.png)

![20210304152517](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304152517.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>绑定事件</title>
	<style>
		button {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<div class="wrapper">
		<button class="btn1">add</button>
		<button class="btn2">remove</button>
	</div>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$('.wrapper').on('click', '.btn2', {
			msg: 'change'
		}, function (e) {
			$(this).text(e.data.msg); // 注意 这里的 this 指向 .btn2
		});
	</script>
</body>

</html>
```

```
notes: 通过 on 的方式来绑定事件 传入 4 个参数的情况 (事件委托 + 过滤)
    在这里, 我们为父级 .wrapper 绑定 click 事件
    当我们点击 wrapper 区域时, click 事件就会触发, 但是这里做了过滤处理
    表示 当我我们点击的是 .btn2 时 事件才会被触发 否则 不会触发
```

![20210304124034](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304124034.png)

![20210304124058](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304124058.png)


### 3. 通过 one 来绑定事件

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>绑定事件</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<div class="wrapper">
		<button class="btn">加入购物车</button>
	</div>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$('.wrapper').one('click', '.btn', {
			backgroundColor: '#008c8c',
			text: '移出购物车'
		}, function (e) {
			$(this).css('background-color', e.data.backgroundColor);
			$(this).text(e.data.text);
			console.log('1'); // 只会打印一次
		});
	</script>
</body>

</html>
```

```
notes
    通过 one 来绑定事件 和 on 类似
    区别在于 通过 one 来绑定的话, 事件仅会触发一次
```

![20210304153715](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304153715.png)

![20210304153721](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304153721.png)



## 2. 解除事件

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>解除事件</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<div class="wrapper">
		<button class="btn">加入购物车</button>
	</div>
	<p>
		<button class="btn removeEvent">off</button>
	</p>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$('.wrapper').on('click', '.btn', {
			backgroundColor: '#008c8c',
			text: '移出购物车'
		}, function (e) {
			$(this).css('background-color', e.data.backgroundColor);
			$(this).text(e.data.text);
			console.log('1'); // 只会打印一次
		});

		$('.removeEvent').click(function () {
			console.log(1);
			$('.wrapper').off(); // 解除所有绑定在 .wrapper 上的事件
			// $('.wrapper').off('click'); // 解除绑定在 .wrapper 上的 click 事件
		});
	</script>
</body>

</html>
```

![20210304154817](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304154817.png)

```
notes
    1. off() 用于解除绑定的事件
    2. 若 off() 不传入参数, 那么表示的是解除指定元素身上的所有事件
    3. 若 off() 传入指定的事件名(字符串形式), 那么表示解除指定的事件
```

## 3. 主动触发绑定事件

### 1. trigger

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>主动触发绑定事件</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<div class="wrapper">
		<button class="btn">加入购物车</button>
	</div>
	<p>
		<button class="btn trigger">trigger</button>
	</p>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$('.wrapper .btn').on({
			click: function (e, backgroundColor, text) {
				console.log('click');
				$(this).css('background-color', backgroundColor);
				$(this).text(text);
			},
			mouseover: function () {
				console.log('mouseover');
			},
			diy: function () { // 自定义事件
				console.log('diy 自定义事件');
			}
		});

		$('.trigger').click(function () {
			$('.wrapper .btn').trigger('click', ['#008c8c', '移出购物车']);
			$('.wrapper .btn').trigger('mouseover');
			$('.wrapper .btn').trigger('diy');
		});
	</script>
</body>

</html>
```

```
notes
    1. trigger() 可以主动触发指定事件 比如 元素.trigger('mouseover') 就相当于我们把鼠标移入到了元素身上 就会触发 mouseover 事件
    2. trigger() 也可以触发我们绑定的自定义事件 如 diy
    3. trigger() 主动触发事件时 参数以数组的形式传入
```

![20210304161315](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304161315.png)

![20210304161323](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304161323.png)

### 2. triggerHandler 与 trigger 之间的区别

**区别1: 是否触发事件的默认行为**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>主动触发绑定事件</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<div class="wrapper">
		<button class="btn trigger">trigger</button>
		<button class="btn triggerHandler">triggerHandler</button>
	</div>
	<p>
		<input type="text" placeholder="please input some text!!!!">
	</p>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$('input').focus(function () {
			console.log('log focus');
		});
		$('.trigger').click(function () {
			$('input').trigger('focus');
		});
		$('.triggerHandler').click(function () {
			$('input').triggerHandler('focus');
		});
	</script>
</body>

</html>
```

![20210304211617](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304211617.png)

![20210304212255](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304212255.png)

![20210304212330](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304212330.png)

```
notes
    由于 trigger 会触发事件的默认行为 所以 当点击 trigger按钮 后, input 框会聚焦
    而 triggerHandler 不会触发事件的默认行为 所以 若点击的是 triggerHandler 按钮, input 框不会聚焦
    但是都会触发 focus 事件 控制台都会打印 log focus
```

**区别2: 执行事件的元素个数**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>主动触发绑定事件</title>
</head>

<body>
	<ul id="color">
		<li>li</li>
		<li>li</li>
		<li>li</li>
		<li>li</li>
	</ul>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

```js
$('#color li').click(function () {
    $(this).html($(this).html() + ' -> ' + $(this).index());
});
```

![20210304213958](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304213958.png)

```js
setTimeout(function () {
    $('#color li').trigger('click'); // jquery 选择器选中的所有 li 都会触发 click 事件
}, 1000);
```

![20210304214024](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304214024.png)

```js
setTimeout(function () {
    $('#color li').triggerHandler('click'); // jquery 选择器选中的所有 li 中的第一个 li 会触发 click 事件
}, 1000);
```

![20210304214102](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304214102.png)

**区别3: 是否冒泡**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>主动触发绑定事件</title>
</head>

<body>
	<div id="bubble">
		<h2>
			<span>span</span>
		</h2>
	</div>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

```js
$('#bubble h2').click(function () {
    console.log('h2被点击了');
});
$('#bubble span').click(function () {
    console.log('span被点击了');
});
```

```js
setTimeout(function () {
    // trigger()会冒泡
    $('#bubble span').trigger('click'); // 1s 后 控制台会先打印  span被点击了 再打印 h2被点击了
}, 2500);
```

![20210304214533](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304214533.png)

```js
setTimeout(function () {
    // triggerHandler()不会冒泡
    $('#bubble span').triggerHandler('click'); // 1s 后 控制台会打印 span被点击了
}, 2500);
```

![20210304214614](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304214614.png)

**区别4: 是否支持链式操作**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>主动触发绑定事件</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<button class="btn">链式操作</button>
	<!-- img1 -->
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

![20210304215830](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304215830.png)

```js
$('.btn').on({
    mouseover: function () {
        $(this).css('font-size', '2em');
    },
    mouseout: function () {
        $(this).css('height', '100px');
    }
});
setTimeout(function () {
    $('.btn').trigger('mouseover').trigger('mouseout'); // trigger()可以使用链式操作
}, 1000);
```

![20210304215946](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304215946.png)

```js
$('.btn').on({
    mouseover: function () {
        $(this).css('font-size', '2em');
    },
    mouseout: function () {
        $(this).css('height', '100px');
    }
});
setTimeout(function () {
    $('.btn').triggerHandler('mouseover').triggerHandler('mouseout'); // triggerHandler()不可以使用链式操作
    // 因为默认情况下 triggerHandler 返回的是 undefined
}, 1000);
```

![20210304220025](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304220025.png)

```js
$('.btn').on({
    mouseover: function () {
        $(this).css('font-size', '2em');
        return $(this); // 我们手动的把当前操作的这个对象给返回 即可让 triggerHandler 实现链式操作
    },
    mouseout: function () {
        $(this).css('height', '100px');
    }
});
setTimeout(function () {
    $('.btn').triggerHandler('mouseover').triggerHandler('mouseout'); // triggerHandler()不可以使用链式操作
    // 因为默认情况下 triggerHandler() 方法返回的是一个 undefined
}, 1000);
```

![20210304215946](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304215946.png)
## 4. 事件对象

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>主动触发绑定事件</title>
	<style>
		.btn1, .btn2 {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}
	</style>
</head>

<body>
	<p>
		<button class="btn1">事件对象1</button>
	</p>
	<p>
		<button class="btn2">事件对象2</button>
	</p>
	<script src="./jquery-3.4.1.js"></script>
</body>

</html>
```

```js
$('.btn1').click(function (event) {
    console.log(event);
});
$('.btn2')[0].onclick = function (ev) {
    console.log(ev);
};
```

![20210304224208](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304224208.png)

![20210304224239](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304224239.png)

![20210304224249](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210304224249.png)

```
notes
    原生 js 的事件对象中的一些属性
    在 jQuery 中 一般都被封装成了相应的方法
    (若实际开发中接触到了相关的 事件对象的一些 用法, 重点记录一下即可...)
```
# 6. 内置特效

## 1. 基本特效

[jQuery 中文文档 -> 基本特效](https://www.jquery123.com/category/effects/basics/)

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>基本特效</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}

		img {
			padding: 20px;
			margin: 20px;
			background: #999;
			border: 10px solid #008c8c;
			width: 300px;
		}
	</style>
</head>

<body>
	<!-- 基本特效 -->
	<div class="btnbox">
		<button class="btn" id="hide">隐藏</button>
		<button class="btn" id="show">显示</button>
		<button class="btn" id="toggle">隐藏/显示切换</button>
	</div>

	<div class="imgbox">
		<img src="https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/%E5%85%B5%E9%95%BF.jpg" alt="兵长">
	</div>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./demo.js"></script>
</body>

</html>
```

```js
// hide 隐藏效果
$('#hide').click(function () {
    //$('img').hide('fast'); // 快
    //$('img').hide('nomal'); // 中
    //$('img').hide('slow'); // 慢
    $('img').hide(1000, function () { // 隐藏过程持续 1000ms
        console.log('隐藏动画完成了'); // 隐藏动画完成后会打印
    });
});


// show 显示效果
$('#show').click(function () {
    $('img').show('slow', function () {
        console.log('显示动画完成了');
    });
});


// toggle 切换效果
var n = 0; // 用于实现切换效果
$('#toggle').click(function () {
    $('img').toggle('fast', function () {
        n++;
        if (n % 2 === 1) {
            console.log('隐藏动画结束了');
        } else {
            console.log('显示动画结束了');
        }
    });
});
```

![20210305103234](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305103234.png)

```
notes
3 个基本动画函数
    hide 隐藏
    show 显示
    toggle 切换
参数
    一共可以接受两个参数
    第一个参数表示的是动画的持续时长 (可以是 String 类型 或 Number 类型)
    第二个参数表示的是动画完成后的回调函数 在动画完成后 就会触发 (通常可以用它来实现动画的联动效果)
```

## 2. 滑动特效

```
notes
3 个滑动动画函数
    slideDown   滑动显示
    slideUp     滑动隐藏
    slideToggle 滑动切换
参数
    (同上)
```


## 3. 渐变特效

```
notes
3 个滑动动画函数
    fadeOut    渐变显示
    fadeIn     渐变隐藏
    fadeToggle 渐变切换
参数
    (同上)
```

**透明度渐变**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>渐变特效</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}

		img {
			padding: 20px;
			margin: 20px;
			background: #999;
			border: 10px solid #008c8c;
			width: 300px;
		}
	</style>
</head>

<body>
	<!-- 基本特效 -->
	<div class="btnbox">
		<button class="btn" id="fadeTo">opacity</button>
	</div>

	<div class="imgbox">
		<img src="https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/%E5%85%B5%E9%95%BF.jpg" alt="兵长">
	</div>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./demo.js"></script>
</body>

</html>
```

```js
$('#fadeTo').click(function () {
    $('.imgbox').fadeTo('nomal', 0.5, function () {
        console.log('透明度变化完成了');
    });
});
```

```
notes
fadeTo 用于实现透明度渐变效果
参数
    不同点:
    第 2 个参数表示的是 透明度渐变的终点
    第 3 个参数表示的才是 动画完成后的回调函数
```

![20210305105055](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305105055.png)

## 4. 自定义特效

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>自定义特效</title>
	<style>
		.btn {
			border: none;
			outline: none;
			height: 50px;
			padding: 0 20px;
			border-radius: 5%;
			color: #fff;
			background-color: #f40;
		}

		img {
			padding: 20px;
			margin: 20px;
			background: #999;
			border: 10px solid #008c8c;
			width: 300px;
		}
	</style>
</head>

<body>
	<!-- 基本特效 -->
	<div class="btnbox">
		<button class="btn" id="animate">animate</button>
	</div>

	<div class="imgbox" style="position: absolute;">
		<img src="https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/%E5%85%B5%E9%95%BF.jpg" alt="兵长">
	</div>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./demo.js"></script>
</body>

</html>
```

```js
$('#animate').click(function () {
    $('.imgbox').animate({
        width: 'toggle',
        height: 'toggle',
        left: '+=50', // 每次变化 都会向右边移动 50px
    }, 500, function () { // 动画持续 500ms
        console.log('运动结束了'); // 动画结束时的回调函数
    });
});
```

```
notes
但凡是 数字类的属性 都可以写到第一个参数里面
key 为该属性的名字
value 有多种写法
    1. 具体的数字
    2. 'toggle' -> 表示在当前状态值 和 0 之间切换
    3. '+=数字' 或 '-=数字' -> 表示每次切换时的变化值
```

```js
$('#animate').click(function () {
    $('.imgbox').animate({
            width: 'toggle'
        }, 'fast') // 'fast' 作为 animate 的第 2 个参数 表示该动画的执行时长
        .delay(1000) // 让后面的动画延迟 1000ms 执行
        .animate({
            height: 'toggle'
        }, 'slow')
        .delay(500)
        .animate({
            opacity: 0.5
        }, 1000);
});
```

```
notes
    自定义动画
    支持链式操作 .animate({}, 'normal').animate()
    支持延时执行 .animate({}, 'normal').delay(1000)
```

## 5. 控制动画

```
notes
控制动画有 3 个方法
    stop    让正在执行的动画停止
    finish  立即完成正在执行的动画
    delay   延时执行下一个动画 (传入的参数可以是 Number 类型 表示的是延时执行的毫秒数)
```
# 7. Ajax

https://developer.duyiedu.com/previewAPI/%E5%AD%A6%E7%94%9F%E4%BF%A1%E6%81%AF%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F

## 1. GET请求

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>get请求</title>
</head>

<body>
	<button id="get">$.get()</button>
	<button id="ajaxGet">$.ajax() get</button>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./demo.js"></script>
</body>

</html>
```

```js
$('#get').click(function () {
    $.get('http://api.duyiedu.com/api/student/findAll', {
        appkey: '_abc123_1606358542486'
    }, function (data) {
        console.log(data);
        console.log(typeof data);
        console.log(JSON.parse(data));
        console.log(typeof JSON.parse(data));
    });
});
//
$('#ajaxGet').click(function () {
    $.ajax({
        url: 'http://api.duyiedu.com/api/student/findAll',
        type: 'get',
        data:{
            appkey:'_abc123_1606358542486',
        },
        // data: 'appkey=_abc123_1606358542486',
        dataType: 'json',
        success: function (data) {
            console.log(data);
        }
    });
});
```

![20210305122621](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305122621.png)

## 2. POST请求

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>post请求</title>
	<style>
		#register {
			width: 400px;
			margin: 50px auto;
			border: 1px solid #ddd;
			background-color: #ddd;
		}

		#register h2 {
			text-align: center;
		}

		#register p {
			text-align: center;
		}

		#register p label {
			display: inline-block;
			width: 100px;
			text-align: right;
		}

		#register p input {
			width: 50%;
			margin-left: 10px;
		}
	</style>
</head>

<body>
	<div id="register">
		<h2>注册用户信息</h2>
		<p>
			<label for="account">account: </label>
			<input type="text" name="account" id="account" placeholder="用来登录学生管理系统的帐号">
		</p>
		<p>
			<label for="username">username: </label>
			<input type="text" name="username" id="username" placeholder="用户名">
		</p>
		<p>
			<label for="password">password: </label>
			<input type="text" name="password" id="password" placeholder="用来登录学生管理系统的密码">
		</p>
		<p>
			<label for="re-password">rePassword: </label>
			<input type="text" name="re-password" id="re-password" placeholder="确认密码">
		</p>
		<p>
			<button>register</button>
		</p>
	</div>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./demo.js"></script>
</body>

</html>
```

![20210305130256](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305130256.png)

**先注册两个用户**

```js
// post请求 -> 注册功能
$('#register button').on({
    click: function () {
        // 获取先到用户输入的 用户名 和 密码
        let account = $('#register input[name=account]').val(),
            username = $('#register input[name=username]').val(),
            password = $('#register input[name=password]').val(),
            rePassword = $('#register input[name=re-password]').val();
        $.ajax({
            url: 'http://api.duyiedu.com/api/student/stuRegister', // 请求接口的 url
            type: 'post', // 请求方式为 post
            data: { // 请求参数
                appkey: '_abc123_1606358542486', // 用户访问该接口时所必须携带的身份凭据
                account, // 用来登录学生管理系统的帐号
                username, // 用户名
                password, // 用来登录学生管理系统的密码
                rePassword // 确认密码
            },
            dataType: 'json', // 将返回的数据转换为 json 格式
            success: function (res) {
                console.log(res);
            },
            error: function (res) {
                console.log('错误原因: ' + res);
            }
        })
    }
})
```

![20210305125556](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305125556.png)

![20210305125603](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305125603.png)

**再登录刚注册好的两个用户**

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>post请求</title>
	<style>
		#login {
			width: 400px;
			margin: 50px auto;
			border: 1px solid #ddd;
			background-color: #ddd;
		}

		#login h2 {
			text-align: center;
		}

		#login p {
			text-align: center;
		}

		#login p label {
			display: inline-block;
			width: 100px;
			text-align: right;
		}

		#login p input {
			width: 50%;
			margin-left: 10px;
		}
	</style>
</head>

<body>
	<div id="login">
		<h2>登录界面</h2>
		<p>
			<label for="account">account: </label>
			<input type="text" name="account" id="account" placeholder="用来登录学生管理系统的帐号">
		</p>
		<p>
			<label for="password">password: </label>
			<input type="text" name="password" id="password" placeholder="用来登录学生管理系统的密码">
		</p>
		<p>
			<button>login</button>
		</p>
	</div>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./demo.js"></script>
</body>

</html>
```

![20210305130210](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305130210.png)

```js
// post请求 -> 实现登录功能
$('#login button').click(function () {
    // 先获取到用户输入的 用户名 和 密码
    let username = $('#login input[name=account]').val(),
        password = $('#login input[name=password]').val();
    //console.log(username,password);
    $.post('http://api.duyiedu.com/api/student/stuLogin', {
        appkey: '_abc123_1606358542486',
        account: username,
        password: password
    }, function (data) {
        console.log(data);
    }, 'json');
});
```

![20210305130307](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305130307.png)

![20210305130316](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305130316.png)

![20210305130325](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305130325.png)

```
notes
    post 请求的语法格式 和 get 请求的语法格式 类似 对照这 get 请求的相关内容来学习即可
```

## 3. JSON请求

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>JSON请求</title>
</head>

<body>

	<button id="json">JSON请求</button>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./demo.js"></script>
</body>

</html>
```

```js
$('#json').click(function () {
    $.getJSON('http://api.duyiedu.com/api/student/findAll', {
        appkey: '_abc123_1606358542486'
    }, function (data) {
        console.log(data);
    });
});
```

![20210305192402](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210305192402.png)

# 8. jquery插件

**之前网络部分有关 jsonp 的相关笔记**

> 在 EV 播放器中 有两个名为 08-jquery插件 的视频
> 其中第一个视频内容讲解的是有关 jquery的jsonp原理
> 直接查看网络课的相关笔记即可 (更加全面)

之前网络部分有关jsonp原理讲解的笔记: [前端网络](https://github.com/123taojiale/front_end_notes/tree/main/%E5%89%8D%E7%AB%AF%E7%BD%91%E7%BB%9C)

**两个常用的 jQuery插件库**

https://plugins.jquery.com/

http://www.jq22.com/

**fullPage 插件**

[fullPage](https://alvarotrigo.com/fullPage/zh/) 是本节课介绍的一个 jQuery 插件, 主要功能就是实现全屏滚动...

[github上有关该插件的使用说明](https://github.com/alvarotrigo/fullPage.js/tree/master/lang/chinese#fullpagejs)

![20210306115510](https://cdn.jsdelivr.net/gh/123taojiale/dahuyou_picture@main/blogs/20210306115510.png)

插件下载下来之后, 将压缩包解压, 打开其中的 dist 文件夹, 直接把相应的 js 文件 和 css 文件引入即可...

```html
<!DOCTYPE html>
<html>

<head>
	<meta charset="UTF-8">
	<title></title>
	<link rel="stylesheet" href="./fullpage.css">
	<style>
		ul {
			margin: 0;
			padding: 0;
			list-style: none;
		}

		h2 {
			margin: 0;
		}

		#fullpage .section {
			text-align: center;
		}

		#fullpage h2 {
			color: #fff;
			font-size: 80px;
		}

		#fp-nav ul li a span {
			background: #fff;
		}

		.fp-controlArrow.fp-prev {
			left: 50px;
		}

		.fp-controlArrow.fp-next {
			right: 50px;
		}

		#menu {
			position: fixed;
			z-index: 1024;
			width: 100%;
			top: 0;
		}

		#menu ul {
			overflow: hidden;
		}

		#menu li {
			float: left;
			margin: 0 15px;
		}

		#menu a {
			color: #fff;
			font-size: 18px;
			line-height: 40px;
			text-decoration: none;
		}

		#menu li.active a {
			font-weight: bold;
			text-decoration: underline;
		}
	</style>
</head>

<body>
	<ul id="menu">
		<li data-menuanchor="fist" class="active"><a href="#fist">第一屏</a></li>
		<li data-menuanchor="second"><a href="#second">第二屏</a></li>
		<li data-menuanchor="third"><a href="#third">第三屏</a></li>
		<li data-menuanchor="fourth"><a href="#fourth">第四屏</a></li>
	</ul>
	<div id="fullpage">
		<div class="section">
			<h2>第一屏</h2>
		</div>
		<div class="section">
			<h2>第二屏</h2>
		</div>
		<div class="section">
			<h2>第三屏</h2>
			<div class="slide">
				<h2>第三屏，第一页</h2>
			</div>
			<div class="slide">
				<h2>第三屏，第二页</h2>
			</div>
			<div class="slide">
				<h2>第三屏，第三页</h2>
			</div>
			<div class="slide">
				<h2>第三屏，第四页</h2>
			</div>
		</div>
		<div class="section">
			<h2>第四屏</h2>
		</div>
	</div>

	<script src="./jquery-3.4.1.js"></script>
	<script src="./fullpage.js"></script>
	<script>
		$('#fullpage').fullpage({
			sectionsColor: ['#693AB8', '#a74a2a', '#48B7DB', '#b32e37'], // （默认 none ）为每个 section 定义 CSS background-color 属性。
			navigation: true, // （默认 false ）如果设置为 true ，则会显示一个由小圆圈组成的导航栏。
			navigationTooltips: ['one', 'two', 'three', 'four'], // 默认为[]）定义要使用导航圈(侧边)的提示。
			anchors: ['fist', 'second', 'third', 'fourth'], // （默认[]）定义要在每个 section 的 URL 上显示的锚链接（#example）。
			menu: '#menu' // （默认 false ）选择器可以用来指定菜单链接到锚。 (实现点击上面的菜单 也能切换页面)
		});
	</script>
</body>
<html>
```

```
直接使用他人的插件, 有一些需要注意的地方
比如页面结构应该怎么写
id名 class名 ... 怎么取
jQuery初始化 Vue初始化 ... 咋写
总之, 遇到不理解的点, 直接上 github 上看看使用说明即可

ps: 懂原理还是很重要的, 对于一些需要付费才能使用的插件功能, 如果懂原理的话, 我们可以直接 加点 css 或 js 来实现
因为人家都已经把 js 和 css 源文件提供给我们了, 我们想怎么改就怎么改
```

# 9. 自定义插件

## 1. $.extend

```
写法1
    $.extend({
        key: value,
        key: value
    });

写法2
    $.key = value;

表示的是给 jQuery 对象本身拓展方法
参数
    key     表示函数名
    value   表示函数体
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>$.extend</title>
</head>

<body>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		// 写法1
		$.extend({
			log: function (value) {
				console.log(value);
			}
		});

		// 写法2
		$.maxOfArr = function (arr) {
			return Math.max.apply(null, arr);
		}

		$.log('dahuyou'); // dahuyou
		let arr = [1, 4, 7, 2];
		console.log($.maxOfArr(arr)); // 7
	</script>
</body>

</html>
```

## 2. $.fn.extend

```
写法1
$.fn.extend({
    key: value,
    key: value
});

写法2
    $.fn.key = value;

表示给 jQuery 的 DOM 对象拓展方法
```

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>$.extend</title>
</head>

<body>
	<p>dahuyou</p>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		$.fn.extend({
			changeColor: function () {
				$(this).css('color', 'red'); // $(this) 指向使用的DOM对象
				return $(this); // 实现链式操作
			}
		});
		$.fn.changeSize = function () {
			$(this).css('fontSize', 30);
			return $(this);
		}
		$('p').changeColor().changeSize();
	</script>
</body>

</html>
```

## 3. 拖拽插件

自定义一个实现拖拽功能的 jQuery 插件

```html
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<title>$.extend</title>
	<style>
		#box {
			width: 50px;
			height: 50px;
			background-color: #008c8c;
			border-radius: 50%;
		}
	</style>
</head>

<body>
	<div id="box"></div>
	<script src="./jquery-3.4.1.js"></script>
	<script>
		// 封装拖拽的插件
		$.fn.draggable = function (options) {
			let defaultOption = {
				limit: false, // 默认拖拽限定范围 (不允许拖出浏览器窗口边界)
			};
			options = Object.assign({}, defaultOption, options); // 对象混合 options 中设置的属性优先使用
			// console.log(options);

			var This = $(this);

			// 修改DOM元素的样式
			$(this).css({
				position: 'absolute',
				left: 0,
				top: 0,
				cursor: 'move'
			});

			$(this).mousedown(function (e) {
				// console.log(e.pageX === e.clientX); // true
				var disX = e.pageX - $(this).offset().left;
				var disY = e.pageY - $(this).offset().top;

				$(document).mousemove(function (e) {
					var l = e.pageX - disX;
					var t = e.pageY - disY;

					if (options.limit) { // 边界处理
						if (l < 0) {
							l = 0;
						} else if (l > $(document).innerWidth() - This.outerWidth()) {
							l = $(document).innerWidth() - This.outerWidth();
						}

						if (t < 0) {
							t = 0;
						} else if (t > $(document).innerHeight() - This.outerHeight()) {
							t = $(document).innerHeight() - This.outerHeight();
						}
					}

					This.css({
						left: l,
						top: t
					});
				});

				$(document).mouseup(function () {
					$(this).off(); // 解除绑定在 被拖拽元素身上的所有事件处理函数
				});

				return false;
			});
		};


		$('#box').draggable({
			limit: true,
		});
	</script>
</body>

</html>
```

```
notes
    1. e.pageX 和 e.clientX 之间的区别
    前者相对于的是 document 的左上角
    后者相对于的是 浏览器可视窗口 的左上角
```