# JavaScript概述

## JavaScript定义

JavaScript  是一种脚本，一门编程语言，它可以在网页上实现复杂的功能，网页展现给你的不再是简单的静态信息，而是实时的内容更新，交互式的地图，2D/3D  动画，滚动播放的视频等等。JavaScript 怎能缺席。它是标准 Web 技术蛋糕的第三层，其中 [HTML ](https://developer.mozilla.org/en-US/docs/Learn/HTML)和 [CSS ](https://developer.mozilla.org/en-US/docs/Learn/CSS)我们已经在学习中心的其他部分进行了详细的讲解

![img](https://mdn.mozillademos.org/files/13502/cake.png)

- [HTML](https://developer.mozilla.org/zh-CN/docs/Glossary/HTML)是一种标记语言，用来结构化我们的网页内容并赋予内容含义，例如定义段落、标题和数据表，或在页面中嵌入图片和视频。
- [CSS](https://developer.mozilla.org/zh-CN/docs/Glossary/CSS) 是一种样式规则语言，可将样式应用于 HTML 内容， 例如设置背景颜色和字体，在多个列中布局内容。
- [JavaScript](https://developer.mozilla.org/zh-CN/docs/Glossary/JavaScript) 是一种脚本语言，可以用来创建动态更新的内容，控制多媒体，制作图像动画，还有很多。（好吧，虽然它不是万能的，但可以通过简短的代码来实现神奇的功能。）

## JavaScript可以做什么

客户端（client-side）JavaScript 语言的核心包含一些普遍的编程特性，以让你可以做到如下的事情：

- 在变量中储存有用的值。比如上文的示例中，我们请求客户输入一个新名字，然后将其储存到 `name` 变量中。
- 操作一段文本（在编程中称为“字符串”（string））。上文的示例中，我们取字符串 "玩家1："，然后把它和 `name` 变量连结起来，创造出完整的文本标签，比如："玩家1：小明"。
- 运行代码以响应网页中发生的特定事件。上文的示例中，我们用一个 `click (en-US)` 事件来检测按钮什么时候被点击，然后运行代码更新文本标签。
- 以及更多！

JavaScript 语言核心之上所构建的功能更令人兴奋。**应用程序接口（Application Programming Interfaces**（**API**））将为你的代码提供额外的超能力。

API 是已经建立好的一套代码组件，可以让开发者实现原本很难甚至无法实现的程序。就像现成的家具套件之于家居建设，用一些已经切好的木板组装一个书柜，显然比自己设计，寻找合适的木材，裁切至合适的尺寸和形状，找到正确尺寸的螺钉，再组装成书柜要简单得多。

API 通常分为两类。![img](https://mdn.mozillademos.org/files/13508/browser.png)

**浏览器 API** 内建于 web 浏览器中，它们可以将数据从周边计算机环境中筛选出来，还可以做实用的复杂工作。例如：

- [`文档对象模型 API（DOM（Document Object Model）API）`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model) 能通过创建、移除和修改 HTML，为页面动态应用新样式等手段来操作 HTML 和 CSS。比如当某个页面出现了一个弹窗，或者显示了一些新内容（像上文小 demo 中看到那样），这就是 DOM 在运行。
- [`地理位置 API（Geolocation API）`](https://developer.mozilla.org/zh-CN/docs/Web/API/Geolocation) 获取地理信息。这就是为什么 [谷歌地图](https://www.google.cn/maps) 可以找到你的位置，而且标示在地图上。
- [`画布（Canvas）`](https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas_API) 和 [`WebGL`](https://developer.mozilla.org/zh-CN/docs/Web/API/WebGL_API) API 可以创建生动的 2D 和 3D 图像。人们正运用这些 web 技术制作令人惊叹的作品。参见 [Chrome Experiments](https://www.chromeexperiments.com/webgl) 以及 [webglsamples](https://webglsamples.org/)。
- 诸如 [`HTMLMediaElement`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLMediaElement) 和 [`WebRTC`](https://developer.mozilla.org/zh-CN/docs/Web/API/WebRTC_API) 等 [影音类 API](https://developer.mozilla.org/en-US/Apps/Fundamentals/Audio_and_video_delivery) 让你可以利用多媒体做一些非常有趣的事，比如在网页中直接播放音乐和影片，或用自己的网络摄像头获取录像，然后在其他人的电脑上展示（试用简易版 [截图 demo](http://chrisdavidmills.github.io/snapshot/) 以理解这个概念）。

**注**: 上述很多演示都不能在旧浏览器中运行。推荐你在测试代码时使用诸如 Firefox, Chrome, Edge 或者 Opera 等现代浏览器。当代码即将交付生产环境时（也就是真实的客户即将使用真实的代码时），你还需要深入考虑 [跨平台测试](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing)

**第三方 API** 并没有默认嵌入浏览器中，一般要从网上取得它们的代码和信息。比如：

- [Twitter API](https://dev.twitter.com/overview/documentation)、[新浪微博 API](https://open.weibo.com/) 可以在网站上展示最新推文之类。
- [谷歌地图 API](https://developers.google.com/maps/)、[高德地图 API](https://lbs.amap.com/) 可以在网站嵌入定制的地图等等。

**注**：这些 API 较为高级，我们的课程中不会涉及，更多信息请参考：[客户端 web API 模块](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs).

## JavaScript在页面上做了什么

现在我们实实在在的学习一些代码，与此同时，探索 JavaScript 运行时背后发生的事情。

让我们简单回顾一下，浏览器在读取一个网页时都发生什么（[CSS 如何工作](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_works#how_does_css_actually_work) 一文中首次谈及）。浏览器在读取一个网页时，代码（HTML, CSS 和 JavaScript）将在一个运行环境（浏览器标签页）中得到执行。就像一间工厂，将原材料（代码）加工为一件产品（网页）。

![img](https://mdn.mozillademos.org/files/13504/execution.png)

在 HTML 和 CSS 集合组装成一个网页后，浏览器的 JavaScript 引擎将执行 JavaScript 代码。这保证了当 JavaScript 开始运行之前，网页的结构和样式已经就位。

这样很好，因为JavaScript 最普遍的用处是通过 DOM API（见上文）动态修改 HTML 和 CSS 来更新用户界面 （user interface）。如果 JavaScript 在 HTML 和 CSS 就位之前加载运行，就会引发错误。

### 浏览器安全

每个浏览器标签页就是其自身用来运行代码的独立容器（这些容器用专业术语称为“运行环境”）。大多数情况下，每个标签页中的代码完全独立运行，而且一个标签页中的代码不能直接影响另一个标签页（或者另一个网站）中的代码。这是一个好的安全措施，如果不这样，黑客就可以从其他网站盗取信息，等等。

### JavaScript运行次序

当浏览器执行到一段 JavaScript 代码时，通常会按从上往下的顺序执行这段代码。这意味着你需要注意代码书写的顺序。比如，我们回到第一个例子中的 JavaScript 代码：

```javascript
const para = document.querySelector('p');

para.addEventListener('click', updateName);

function updateName() {
  let name = prompt('输入一个新的名字：');
  para.textContent = '玩家1：' + name;
}
```

这里我们选定一个文本段落（第 1 行)，然后给它附上一个事件监听器（第 3 行），使得在它被点击时，`updateName()` 代码块（code block） （5 – 8 行）便会运行。`updateName()` （这类可以重复使用的代码块称为“函数”）向用户请求一个新名字，然后把这个名字插入到段落中以更新显示。

如果你互换了代码里最初两行的顺序，会导致问题。浏览器[开发者控制台](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/zh-CN/docs/Learn/Discover_browser_developer_tools)将返回一个错误： `TypeError: para is undefined`。这意味着 `para` 对象还不存在，所以我们不能为它增添一个事件监听器。

**注**：*这是一个很常见的错误*，在引用对象之前必须确保该对象已经存在。

## 三种添加JavaScript的方式

### 内部JavaScript

1. 首先，下载示例文件 [apply-javascript.html](https://github.com/roy-tian/learning-area/blob/master/javascript/introduction-to-js-1/what-is-js/apply-javascript.html)。放在一个好记的文件夹里。

2. 分别在浏览器和文本编辑器中打开这个文件。你会看到这个 HTML 文件创建了一个简单的网页，其中有一个可点击按钮。

3. 然后转到文本编辑器，在 `</head>` 标签结束前插入以下代码：  

```
<script>

  // 在此编写 JavaScript 代码

</script>
```

4. 下面，在 \<script>元素中添加一些 JavaScript 代码，这个页面就能做一些更有趣的事。在“/ /在此编写 JavaScript 代码”一行下方添加以下代码：  

```
document.addEventListener("DOMContentLoaded", function() {
  function createParagraph() {
    let para = document.createElement('p');
    para.textContent = '你点击了这个按钮！';
    document.body.appendChild(para);
  }

  const buttons = document.querySelectorAll('button');

  for(let i = 0; i < buttons.length ; i++) {
    buttons[i].addEventListener('click', createParagraph);
  }
});
```

5. 保存文件并刷新浏览器，然后你会发现，点击按钮文档下方将会添加一个新段落

### 外部JavaScript

1. 首先，在刚才的 HTML 文件所在的目录下创建一个名为 `script.js` 的新文件。请确保扩展名为 `.js`，只有这样才能被识别为 JavaScript 代码。

2. 将\<script>元素替换为：  

```
<script src="script.js" async></script>
```

3. 在 `script.js` 文件中，添加下面的脚本：  

```
function createParagraph() {
  let para = document.createElement('p');
  para.textContent = '你点击了这个按钮！';
  document.body.appendChild(para);
}

const buttons = document.querySelectorAll('button');

for(let i = 0; i < buttons.length ; i++) {
  buttons[i].addEventListener('click', createParagraph);
} 
```

4. 保存并刷新浏览器，你会发现二者完全一样。但是现在我们把 JavaScript 写进了一个外部文件。这样做一般会使代码更加有序，更易于复用，且没有了脚本的混合，HTML 也会更加易读，因此这是个好的习惯。

### 内联JavaScript

注意，有时候你会遇到在 HTML 中存在着一丝真实的 JavaScript 代码。它或许看上去像这样：

```js
function createParagraph() {
  const para = document.createElement('p');
  para.textContent = '你点击了这个按钮！';
  document.body.appendChild(para);
}
<button onclick="createParagraph()">点我呀</button>
```

**然而请不要这样做。** 这将使 JavaScript 污染到 HTML，而且效率低下。对于每个需要应用 JavaScript 的按钮，你都得手动添加 `onclick="createParagraph()"` 属性。

### 脚本调用策略

要让脚本调用的时机符合预期，需要解决一系列的问题。这里看似简单，实际大有文章。最常见的问题就是：HTML 元素是按其在页面中出现的次序调用的，如果用 JavaScript 来管理页面上的元素（更精确的说法是使用 [文档对象模型](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model) DOM），若 JavaScript 加载于欲操作的 HTML 元素之前，则代码将出错。

在上文的“内部”、“外部”示例中，JavaScript 调用于文档头处，解析 HTML 文档体之前。这样做是有隐患的，需要使用一些结构来避免错误发生。

“内部”示例使用了以下结构：

```
document.addEventListener("DOMContentLoaded", function() {
  . . .
});
```

这是一个事件监听器，它监听浏览器的 "`DOMContentLoaded`" 事件，即 HTML 文档体加载、解释完毕事件。事件触发时将调用 " `. . .`" 处的代码，从而避免了错误发生（[事件](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Building_blocks/Events) 的概念稍后学习）。

“外部”示例中使用了 JavaScript 的一项现代技术（`async` “异步”属性）来解决这一问题，它告知浏览器在遇到 `<script>` 元素时不要中断后续 HTML 内容的加载。

```
<script src="script.js" async></script>
```

上述情况下，脚本和 HTML 将一并加载，代码将顺利运行。

***注**：“外部”示例中 `async` 属性可以解决调用顺序问题，因此无需使用 `DOMContentLoaded` 事件。而 `async` 只能用于外部脚本，因此不适用于“内部”示例。*

解决此问题的旧方法是：把脚本元素放在文档体的底端（`</body>` 标签之前，与之相邻），这样脚本就可以在 HTML 解析完毕后加载了。此方案（以及上述的 `DOMContentLoaded` 方案）的问题是：只有在所有 HTML DOM 加载完成后才开始脚本的加载/解析过程。对于有大量 JavaScript 代码的大型网站，可能会带来显著的性能损耗。这也是 `async` 属性诞生的初衷。

#### `async` 和 `defer`

上述的脚本阻塞问题实际有两种解决方案 —— `async` 和 `defer`。我们来依次讲解。

浏览器遇到 `async` 脚本时不会阻塞页面渲染，而是直接下载然后运行。这样脚本的运行次序就无法控制，只是脚本不会阻止剩余页面的显示。当页面的脚本之间彼此独立，且不依赖于本页面的其它任何脚本时，`async` 是最理想的选择。

比如，如果你的页面要加载以下三个脚本：

```
<script async src="js/vendor/jquery.js"></script>

<script async src="js/script2.js"></script>

<script async src="js/script3.js"></script>
```

三者的调用顺序是不确定的。`jquery.js` 可能在 `script2` 和 `script3` 之前或之后调用，如果这样，后两个脚本中依赖 `jquery` 的函数将产生错误，因为脚本运行时 `jquery` 尚未加载。

解决这一问题可使用 `defer` 属性，脚本将按照在页面中出现的顺序加载和运行：

```
<script defer src="js/vendor/jquery.js"></script>

<script defer src="js/script2.js"></script>

<script defer src="js/script3.js"></script>
```

添加 `defer` 属性的脚本将按照在页面中出现的顺序加载，因此第二个示例可确保 `jquery.js` 必定加载于 `script2.js` 和 `script3.js` 之前，同时 `script2.js` 必定加载于 `script3.js` 之前。

脚本调用策略小结：

- 如果脚本无需等待页面解析，且无依赖独立运行，那么应使用 `async`。
- 如果脚本需要等待页面解析，且依赖于其它脚本，调用这些脚本时应使用 `defer`，将关联的脚本按所需顺序置于 HTML 中。

## 注释

### 行注释

```
// 我是一条注释
```

### 块注释

```
/*
  我也是
  一条注释
*/
```

# 变量

## 概念

变量是用来存储数值的，变量不等于数值本身，而是存储数值的容器，是计算机中的内存。

![img](https://mdn.mozillademos.org/files/13506/boxes.png)

## 声明变量

要想使用变量，你需要做的第一步就是创建它 -- 更准确的说，是声明一个变量。声明一个变量的语法是在 `var` 或 `let` 关键字之后加上这个变量的名字：

```
let myName;
let myAge
```

## 初始化变量

一旦你定义了一个变量，你就能够初始化它. 方法如下，在变量名之后跟上一个“=”，然后是数值:

```
myName = 'Chris';
myAge = 37;
```

可以声明变量的同时初始化变量

```
let myName = 'Chris';
```

## var与let的区别

为什么有 `var` 和 `let` 呢？。

原因是有些历史性的。 回到最初创建 JavaScript 时，是只有 `var` 的。 在大多数情况下，这种方法可以接受， 但有时在工作方式上会有一些问题——它的设计会令人困惑或令人讨厌 。 因此，`let` 是在现代版本中的 JavaScript 创建的一个新的关键字，用于创建与 `var` 工作方式有些不同的变量，解决了过程中的问题。

下面解释几个简单的差异。 我们现在不会讨论所有的差异，但是当您了解有关 JavaScript 的更多信息时，您将开始发现它们（如果您现在真的想要阅读它们，请随时查看我们的[参考页面](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)）。

首先，如果你编写一个声明并初始化变量的多行 JavaScript 程序，你可以在初始化一个变量之后用 `var` 声明它，它仍然可以工作。 例如：

```js
myName = 'Chris';

function logName() {
  console.log(myName);
}

logName();

var myName;
```

Note: 只有在 web 文档中运行多行 JavaScript 时才会有这种效果，当在 JavaScript 控制台中键入单独的行，这将不起作用。

这是由于变量的**提升**，更多细节请阅读[变量提升](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/var#变量提升)。

但提升操作不再适用于 `let` 。如果将上面例子中的 `var` 替换成 `let` 将不起作用并引起一个错误。 这是一件好事——因为初始化后再声明一个变量会使代码变得混乱和难以理解。

其次，当你使用 `var` 时，可以根据需要多次声明相同名称的变量，但是 `let` 不能。 以下将有效：

```js
var myName = 'Chris';
var myName = 'Bob';
```

但是以下内容会在第二行引发错误：

```
let myName = 'Chris';
let myName = 'Bob';
```

你必须这样做：

```js
let myName = 'Chris';
myName = 'Bob';
```

同样，这是一个明智的语言决定。没有理由重新声明变量——这只会让事情变得更加混乱。

出于这些以及其他原因，我们建议您在代码中尽可能多地使用 `let`，而不是 `var`。因为没有理由使用 `var`，除非您需要用代码支持旧版本的 Internet Explorer (它直到第 11 版才支持 `let` ，现代的 Windows Edge 浏览器支持的很好)。

## 变量类型

- Number（整数，浮点数，双精度，二进制，八进制，十六进制都是该类型）
- String（'tom',"tom")
- BOOlean（true or false）
- Array
- Object

# 运算符

## 算术运算符

| 运算符 | 名称                 | 作用                                                         | 示例                                                |
| ------ | -------------------- | ------------------------------------------------------------ | --------------------------------------------------- |
| `+`    | 加法                 | 两个数相加。                                                 | `6 + 9`                                             |
| `-`    | 减法                 | 从左边减去右边的数。                                         | `20 - 15`                                           |
| `*`    | 乘法                 | 两个数相乘。                                                 | `3 * 7`                                             |
| `/`    | 除法                 | 用右边的数除左边的数                                         | `10 / 5`                                            |
| `%`    | 求余(有时候也叫取模) | 在你将左边的数分成同右边数字相同的若干整数部分后，返回剩下的余数 | `8 % 3` (返回 2，8除以3的倍数，余下2 。)            |
| `**`   | 幂                   | 取底数的指数次方，即指数所指定的底数相乘。它在EcmaScript 2016 中首次引入。 | `5 ** 5` (返回 3125，相当于 `5 * 5 * 5 * 5 * 5` 。) |

## 赋值运算符

| 运算符 | 名称     | 作用                                           | 示例                 | 等价于                  |
| ------ | -------- | ---------------------------------------------- | -------------------- | ----------------------- |
| `+=`   | 加法赋值 | 右边的数值加上左边的变量，然后再返回新的变量。 | `x = 3;    x += 4;`  | `x = 3;    x = x + 4;`  |
| `-=`   | 减法赋值 | 左边的变量减去右边的数值，然后再返回新的变量。 | `x = 6;    x -= 3;`  | `x = 6;    x = x - 3;`  |
| `*=`   | 乘法赋值 | 左边的变量乘以右边的数值，然后再返回新的变量。 | `x = 2;    x *= 3;`  | `x = 2;    x = x * 3;`  |
| `/=`   | 除法赋值 | 左边的变量除以右边的数值，然后再返回新的变量。 | `x = 10;    x /= 5;` | `x = 10;    x = x / 5;` |

## 比较运算符

| 运算符 | 名称       | 作用                           | 示例          |
| ------ | ---------- | ------------------------------ | ------------- |
| `===`  | 严格等于   | 测试左右值是否相同             | `5 === 2 + 4` |
| `!==`  | 严格不等于 | 测试左右值是否**不**相同       | `5 !== 2 + 3` |
| `<`    | 小于       | 测试左值是否小于右值。         | `10 < 6`      |
| `>`    | 大于       | 测试左值是否大于右值           | `10 > 20`     |
| <=     | 小于或等于 | 测试左值是否小于或等于右值。   | `3 <= 2`      |
| >=     | 大于或等于 | 测试左值是否大于或等于正确值。 | `5 >= 4`      |

*特别提到测试布尔值（true / false），和一个通用模式，你会频繁遇到它，任何不是 `false`, `undefined`, `null`, `0`, `NaN` 的值，或一个空字符串（''）在作为条件语句进行测试时实际返回true，因此您可以简单地使用变量名称来测试它是否为真，甚至是否存在（即它不是未定义的）。例如:*

```
var cheese = 'Cheddar';

if (cheese) {
  console.log('Yay! Cheese available for making cheese on toast.');
} else {
  console.log('No cheese on toast for you today.');
}
```

## 逻辑运算符

| 运算符 |  名称  | 作用                                                         |
| ------ | :----: | ------------------------------------------------------------ |
| `&&`   | 逻辑与 | 使得并列两个或者更多的表达式成为可能，只有当这些表达式每一个都返回`true`时，整个表达式才会返回`true.` |
| `||`   | 逻辑或 | 测试左右值是否相同                                           |
| `！`   | 逻辑非 | 测试左右值是否**不**相同                                     |

## 三元运算符

**返回值或者表达**

```
var greeting = ( isBirthday ) ? 'Happy birthday Mrs. Smith — we hope you have a great day!' : 'Good morning Mrs. Smith.';
```

# **正则表达式**

https://www.zhihu.com/question/48219401/answer/742444326



# 字符串

JavaScript万物皆对象，字符串也是，字符串有很多对象的方法。

## 创建字符串

```
let sgl = 'Single quotes.';
let dbl = "Double quotes";
sgl;
dbl;
```

## 转义字符

在字符前面加一个斜杠\表示转义字符

```
let bigmouth = 'I\'ve got no right to take my place...';
bigmouth;
```

## 连接字符串

```
let one = 'Hello, ';
let two = 'how are you?';
let joined = one + two;
joined;
```

字符串加数字，会自动将数字转换成字符串，因为字符串不一定能转数字

```
'Front ' + 242;
```

## 字符串与数字互换

### 字符串转数字

```
let myString = '123';
let myNum = Number(myString);
typeof myNum;
```

### 数字转字符串

```
let myNum = 123;
let myString = myNum.toString();
typeof myString;
```

## 字符串对象的方法

### 获取字符串长度

```
let browserType = 'mozilla';
browserType.length;
```

### 检索特定字符串字符

```
browserType[0];
browserType[browserType.length-1];
```

### 查找子串

找到返回下标，否则返回-1。

```
browserType.indexOf('zilla');
```

可以使用它来查找不包含子串“mozilla”的所有字符串实例，或者如果使用否定运算符，请执行以下操作。 你可以这样做：  

```
if(browserType.indexOf('mozilla') !== -1) {
  // do stuff with the string
}
```

### 提取子串

```
browserType.slice(0,3);
browserType.slice(2);
```

### 转换大小写

```
let radData = 'My NaMe Is MuD';
radData.toLowerCase();
radData.toUpperCase();
```

### 替换子串

```
browserType.replace('moz','van');
```

# 数组

## 创建数组

可以将任何类型的元素存储在数组中 - 字符串，数字，对象，另一个变量，甚至另一个数组。 您也可以混合和匹配项目类型 - 它们并不都是数字，字符串等。尝试下面这些：  

```
let sequence = [1, 1, 2, 3, 5, 8, 13];
let random = ['tree', 795, [0, 1, 2]];
```

## 获取数组长度

```
sequence.length;
```

## 字符串和数组互换

### 字符串.split为数组

将字符串根据符号自动划分为数组，数组内容不包括符号。

```
let myData = 'Manchester,London,Liverpool,Birmingham,Leeds,Carlisle';
let myArray = myData.split(',');
myArray;
```

### 数组.join为字符串

```
let myNewString = myArray.join(',');
myNewString;
```

### .toString转换为字符串

```
let dogNames = ["Rocket","Flash","Bella","Slugger"];
dogNames.toString(); //Rocket,Flash,Bella,Slugger
```

## push和pop数组项

### push到数组最后

```
myArray.push('Bradford', 'Brighton');
myArray;
```

### pop出数组最后

```
let removedItem = myArray.pop();
myArray;
removedItem;
```

***unshift()**和**shift()**功能上与push()和pop()完全相同，只是方向改为开头。*

# 条件语句(Conditional)

```
var shoppingDone = false;

if (shoppingDone === true) {
  var childsAllowance = 10;
} else {
  var childsAllowance = 5;
}
```

# switch语句

```
switch (expression) {
  case choice1:
    run this code
    break;

  case choice2:
    run this code instead
    break;

  // include as many cases as you like

  default:
    actually, just run this code
    }
```

**break 不能与执行代码同行，否则会出错**。

这里我们得到:

1. 关键字 `switch`, 后跟一组括号.
2. 括号内的表达式或值.
3. 关键字 `case`, 后跟一个选项的表达式/值，后面跟一个冒号.
4. 如果选择与表达式匹配，则运行一些代码.
5. 一个 `break` 语句, 分号结尾. 如果先前的选择与表达式/值匹配，则浏览器在此停止执行代码块，并执行switch语句之后的代码.
6. 你可以添加任意的 case 选项（选项3-5）.
7. 关键字 `default`, 后面跟随和 `case` 完全相同的代码模式 (选项 3–5), except that `default` 之后不需要再有选项, 并且您不需要 `break` 语句, 因为之后没有任何运行代码. 如果之前没有选项匹配，则运行`default`选项.

**Note**: `default` 部分不是必须的 - 如果表达式不可能存在未知值，则可以安全地省略它。 如果有机会，您需要包括它来处理未知的情况

# 循环（Loop)

## for循环

```
for (initializer; exit-condition; final-expression) {
  // code to run
}
```

```
var cats = ['Bill', 'Jeff', 'Pete', 'Biggles', 'Jasmin'];
var info = 'My cats are called ';
var para = document.querySelector('p');

for (var i = 0; i < cats.length; i++) {
  info += cats[i] + ', ';
}

para.textContent = info;
```

### 用break提前退出循环

```
for(let i = 0; i < contacts.length; i++) {
        let splitContact = contacts[i].split(':');
        if(splitContact[0].toLowerCase() === searchName) {
          para.textContent = splitContact[0] + '\'s number is ' + splitContact[1] + '.';
          break;
        } else if(i === contacts.length - 1) {
          para.textContent = 'Contact not found.';
        }
      }
```

### 用continue跳过迭代

continue语句以类似的方式工作，而不是完全跳出循环，而是跳过当前循环而执行下一个循环。 我们来看另外一个例子，它把一个数字作为一个输入，并且只返回开平方之后为整数的数字（整数）。

## while循环

```
initializer
while (exit-condition) {
  // code to run

  final-expression
}
```

```
var i = 0;

while (i < cats.length) {
  if (i === cats.length - 1) {
    info += 'and ' + cats[i] + '.';
  } else {
    info += cats[i] + ', ';
  }

  i++;
}
```

## do...while循环

[do...while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)循环非常类似但在while后提供了终止条件，do while 语句至少执行一次，while语句可能一次都不执行。

# 函数（切记带括号）

## 函数与方法

**函数（fuction）**是可执行的JavaScript代码块，函数可以带有实际参数或者形式参数。

**方法（method）**是通过对象调用的函数，也就是说，方法也是函数，只是比较特殊的函数。

## 匿名函数

```
function() {
  alert('hello');
}
```

匿名函数常与事件处理程序一起使用，或者用于返回计算值

```
btn.onclick = function() {
  displayMessage('Woo, this is a different message!');
};
```

  如果我们要在点击事件里面绑定这个新函数，我们不能直接使用（`btn.onclick = displayMessage('Woo, this is a different message!');`）前面已经讲过— 我们要把它放在一个匿名函数里面，不然函数会直接调用，而不是按钮点击之后才会调用。

## 函数内部的函数

函数内部调用函数得传参才能把值传过去

```
function myBigFunction() {
  var myValue;

  subFunction1();
  subFunction2();
  subFunction3();
}

function subFunction1() {
  console.log(myValue);
}

function subFunction2() {
  console.log(myValue);
}

function subFunction3() {
  console.log(myValue);
}
```

```
function myBigFunction() {
  var myValue = 1;

  subFunction1(myValue);
  subFunction2(myValue);
  subFunction3(myValue);
}

function subFunction1(value) {
  console.log(value);
}

function subFunction2(value) {
  console.log(value);
}

function subFunction3(value) {
  console.log(value);
}
```

## 构造函数

### 构造函数与普通函数的区别

1、构造函数也是一个普通函数，创建方式和普通函数一样，但构造函数习惯上首字母大写

2、构造函数和普通函数的区别在于：调用方式不一样。作用也不一样（构造函数用来新建实例对象）

3、调用方式不一样。

 a. 普通函数的调用方式：直接调用 person();

 b.构造函数的调用方式：需要使用new关键字来调用 new Person();

4、构造函数的函数名与类名相同：Person( ) 这个构造函数，Person 既是函数名，也是这个对象的类名

5、内部用this 来构造属性和方法 

```
function Person(name,job,age)
{
     this.name=name;
     this.job=job;
     this.age=age;
     this.sayHi=function()
         {
          alert("Hi")
         }
 } 
```

5、构造函数的执行流程

  A、立刻在堆内存中创建一个新的对象

  B、将新建的对象设置为函数中的this

  C、逐个执行函数中的代码

  D、将新建的对象作为返回值

6、普通函数例子：因为没有返回值，所以为undefined

![img](https://img-blog.csdn.net/20180225172343927)

7、构造函数例子：构造函数会马上创建一个新对象，并将该新对象作为返回值返回

![img](https://img-blog.csdn.net/20180225171616395)

![img](https://img-blog.csdn.net/20180225171625162)

8、用instanceof 可以检查一个对象是否是一个类的实例，是则返回true；

所有对象都是Object对象的后代，所以任何对象和Object做instanceof都会返回true

![img](https://img-blog.csdn.net/2018022517200858)

![img](https://img-blog.csdn.net/20180225172513790)

# 对象（object）

## 定义

**对象是一个包含相关数据和方法的集合（通常由一些变量和函数组成，我们称之为对象里面的属性和方法）。**

## 创建对象（声明对象的方式）

#### 格式

```
var objectName = {
  member1Name : member1Value,
  member2Name : member2Value,
  member3Name : member3Value
}
```

#### 例子

```
var person = {
  name : ['Bob', 'Smith'],
  age : 32,
  gender : 'male',
  interests : ['music', 'skiing'],
  bio : function() {
    alert(this.name[0] + ' ' + this.name[1] + ' is ' + this.age + ' years old. He likes ' + this.interests[0] + ' and ' + this.interests[1] + '.');
  },
  greeting: function() {
    alert('Hi! I\'m ' + this.name[0] + '.');
  }
};
```

### 调用对象的属性和方法

#### 点表示法

```
person.name[0]
person.age
person.interests[1]
person.bio()
person.greeting()
```

#### 子命名空间

用一个对象来做另一个对象成员的值。

将name成员改成

```
name : {
  first : 'Bob',
  last : 'Smith'
},
```

调用时链式地使用点表示法

```
person.name.first
person.name.last
```

#### 括号表示法

使用括号表示法(bracket notation)，替代这样的代码

```
person.age
person.name.first
```

如下

```
person['age']
person['name']['first']
```

*注：这看起来很像访问一个数组的元素，从根本上来说是一回事儿，你使用了关联了值的名字，而不是索引去选择元素。难怪对象有时被称之为关联数组(associative array)了——对象做了字符串到值的映射，而数组做的是数字到值的映射*

## 设置对象成员

目前我们仅仅看到了如何访问对象的成员，而你其实也可以设置对象成员的值，通过声明你要设置的成员，像这样：

```
person.age = 45
person['name']['last'] = 'Cratchit'
```

尝试这些代码，然后再查看这些成员是否已经被改变了

```
person.age
person['name']['last']
```

设置成员并不意味着你只能更新已经存在的属性的值，你完全可以创建新的成员，尝试以下代码：

```
person['eyes'] = 'hazel'
person.farewell = function() { alert("Bye everybody!") }
```

现在你可以测试你新创建的成员

```
person['eyes']
person.farewell()
```

**括号表示法一个有用的地方是它不仅可以动态的去设置对象成员的值，还可以动态的去设置成员的名字**。

比如说，我们想让用户能够在他们的数据里存储自己定义的值类型，通过两个input框来输入成员的名字和值，通过以下代码获取用户输入的值：

```
var myDataName = nameInput.value
var myDataValue = nameValue.value
```

我们可以这样把这个新的成员的名字和值加到person对象里：

```
person[myDataName] = myDataValue
```

为了测试这个功能，尝试在你的代码里添加以下几行，就在person对象的右花括号的下面：

```
var myDataName = 'height'
var myDataValue = '1.75m'
person[myDataName] = myDataValue
```

现在，保存并刷新，在输入框里输入以下代码：

```
person.height
```

**这是使用点表示法无法做到的，点表示法只能接受字面量的成员的名字，不接受变量作为名字**

## 创建对象的其他方法

#### 使用构造函数

1. 让我们看看如何通过一个普通的函数定义一个”人“。在您的文件中添加以下代码:  

```
function createNewPerson(name) {
  var obj = {};
  obj.name = name;
  obj.greeting = function () {
    alert('Hi! I\'m ' + this.name + '.');
  }
  return obj;
}
```

2.您现在可以通过调用这个函数创建一个新的叫 salva 的人，在您浏览器的JavaScript console 试试 ：  

```
var salva = createNewPerson('salva');
salva.name;
salva.greeting();
```

  上述代码运行良好，但是有点冗长；如果我们知道如何创建一个对象，就没有必要创建一个新的空对象并且返回它。幸好 JavaScript 通过构建函数提供了一个便捷的方法，方法如下：

3.将之前的代码用如下代码代替：  

```
function Person(name) {
  this.name = name;
  this.greeting = function() {
    alert('Hi! I\'m ' + this.name + '.');
  };
}
```

这个构建函数是 JavaScript 版本的类。您会发现，它只定义了对象的属性和方法，除了没有明确创建一个对象和返回任何值和之外，它有了您期待的函数所拥有的全部功能。这里使用了`this`关键词，即无论是该对象的哪个实例被这个构建函数创建，它的 `name` 属性就是传递到构建函数形参`name`的值，它的 `greeting()` 方法中也将使用相同的传递到构建函数形参`name`的值。

***注：** 一个构建函数通常是大写字母开头，这样便于区分构建函数和普通函数。*

**那如何调用构建函数创建新的实例呢？**

1. 将下面的代码加在您之前的代码下面：  

   ```
   var person1 = new Person('Bob');
   var person2 = new Person('Sarah');
   ```

2.保存并刷新浏览器，在 console 里输入如下代码：  

```
person1.name
person1.greeting()
person2.name
person2.greeting()
```

酷！您现在看到页面上有两个对象，每一个保存在不同的命名空间里，当您访问它们的属性和方法时，您需要使用`person1`或者`person2`来调用它们。尽管它们有着相同的`name`属性和 `greeting()`方法它们是各自独立的，所以相互的功能不会冲突。注意它们使用的是自己的 name 值，这也是使用 this 关键字的原因，它们使用的从实参传入形参的自己的值，而不是其它的什么值。

再看看这个构造对象的语法：

```
var person1 = new Person('Bob');
var person2 = new Person('Sarah');
```

上述代码中，关键字 `new` 跟着一个含参函数，用于告知浏览器我们想要创建一个对象，非常类似函数调用，并把结果保存到变量中。每个示例类都是根据下面的方式定义的。

```
function Person(name) {
  this.name = name;
  this.greeting = function() {
    alert('Hi! I\'m ' + this.name + '.');
  };
}
```

当新的对象被创立, 变量`person1`与`person2`有效地包含了以下值：

```
{
  name : 'Bob',
  greeting : function() {
    alert('Hi! I\'m ' + this.name + '.');
  }
}

{
  name : 'Sarah',
  greeting : function() {
    alert('Hi! I\'m ' + this.name + '.');
  }
}
```

值得注意的是每次当我们调用构造函数时，我们都会重新定义一遍 greeting()，这不是个理想的方法。为了避免这样，我们可以在原型里定义函数，接下来我们会讲到。

**创建我们最终的构造函数**

上面的例子仅仅是简单地介绍如何开始。让我们现在开始创建`Person()`构造函数。

1. 移除掉您之前写的所有代码， 用如下构造函数替代 —— 实现原理上，这与我们之前的例子并无二致， 只是变得稍稍复杂了些：  

   ```
   function Person(first, last, age, gender, interests) {
     this.name = {
       'first': first,
       'last': last
     };
     this.age = age;
     this.gender = gender;
     this.interests = interests;
     this.bio = function() {
       alert(this.name.first + ' ' + this.name.last + ' is ' + this.age + ' years old. He likes ' + this.interests[0] + ' and ' + this.interests[1] + '.');
     };
     this.greeting = function() {
       alert('Hi! I\'m ' + this.name.first + '.');
     };
   };
   ```

接下来加上这样一行代码， 用来创建它的一个对象：  

```
var person1 = new Person('Bob', 'Smith', 32, 'male', ['music', 'skiing']);
```

这样，您就可以像我们定义第一个对象一样访问它的属性和方法了：

```
person1['age']
person1.interests[1]
person1.bio()
// etc.
```

#### Object()构造函数

首先, 您能使用`Object()`构造函数来创建一个新对象。 是的， 一般对象都有构造函数，它创建了一个空的对象。

1. 尝试在您浏览器中的Javascript控制台中输入以下代码：  

   ```
   var person1 = new Object();
   ```

这样就在`person1`变量中存储了一个空对象。然后, 可以根据需要, 使用点或括号表示法向此对象添加属性和方法；试试这个例子：  

```
person1.name = 'Chris';
person1['age'] = 38;
person1.greeting = function() {
  alert('Hi! I\'m ' + this.name + '.');
}
```

还可以将对象文本传递给Object() 构造函数作为参数， 以便用属性/方法填充它。请尝试以下操作：  

```
var person1 = new Object({
  name : 'Chris',
  age : 38,
  greeting : function() {
    alert('Hi! I\'m ' + this.name + '.');
  }
});
```

#### 使用create()方法

JavaScript有个内嵌的方法`create()`, 它允许您基于现有对象创建新的对象。

1. 在 JavaScript 控制台中尝试此操作：  

   ```
   var person2 = Object.create(person1);
   ```

现在尝试这个：  

```
person2.name
person2.greeting()
```

您可以看到，`person2`是基于`person1`创建的，  它们具有相同的属性和方法。这非常有用， 因为它允许您创建新的对象而无需定义构造函数。缺点是比起构造函数，浏览器在更晚的时候才支持create()方法。

## 对象原型（Object prototypes）

- 任何对象都有一个\__proto__属性，该属性指向其继承的对象。
- prototype是函数才有的属性，用于存放继承给子代的属性和方法。

### prototype和\__proto__的区别



![img](https://images2015.cnblogs.com/blog/787416/201603/787416-20160323103557261-114570044.png)



```
var a = {};
console.log(a.prototype);  //undefined
console.log(a.__proto__);  //Object {}

var b = function(){}
console.log(b.prototype);  //b {}
console.log(b.__proto__);  //function() {}
```

![img](https://images2015.cnblogs.com/blog/787416/201603/787416-20160323103622089-1134417169.png)

```
/*1、字面量方式*/
var a = {};
console.log(a.__proto__);  //Object {}

console.log(a.__proto__ === a.constructor.prototype); //true

/*2、构造器方式*/
var A = function(){};
var a = new A();
console.log(a.__proto__); //A {}

console.log(a.__proto__ === a.constructor.prototype); //true

/*3、Object.create()方式*/
var a1 = {a:1}
var a2 = Object.create(a1);
console.log(a2.__proto__); //Object {a: 1}

console.log(a2.__proto__ === a2.constructor.prototype); //false（此处即为图1中的例外情况）
```



![什么是原型链？](https://images2015.cnblogs.com/blog/787416/201603/787416-20160322110905589-2039017350.png)



```
var A = function(){};
var a = new A();
console.log(a.__proto__); //A {}（即构造器function A 的原型对象）
console.log(a.__proto__.__proto__); //Object {}（即构造器function Object 的原型对象）
console.log(a.__proto__.__proto__.__proto__); //null
```

### 对象原型的具体细节和特性

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Objects/Object_prototypes

#### create() 方法创建新的对象实例

1. 例如，在上个例子的 JavaScript 控制台中输入：  

```
var person2 = Object.create(person1);
```

2. `create()` 实际做的是从指定原型对象创建一个新的对象。这里以 `person1` 为原型对象创建了 `person2` 对象。在控制台输入：  

```
person2.__proto__
```

结果返回对象`person1`

#### constructor 属性

每个实例对象都从原型中继承了一个constructor属性，该属性指向了用于构造此实例对象的构造函数。

1. 例如，在控制台中尝试下面的指令：  

   ```
   person1.constructor
   person2.constructor
   ```

都将返回 `Person()` 构造器，因为该构造器包含这些实例的原始定义。

一个小技巧是，你可以在 `constructor` 属性的末尾添加一对圆括号（括号中包含所需的参数），从而用这个构造器创建另一个对象实例。毕竟构造器是一个函数，故可以通过圆括号调用；只需在前面添加 `new` 关键字，便能将此函数作为构造器使用。

在控制台中输入：  

```
var person3 = new person1.constructor('Karen', 'Stephenson', 26, 'female', ['playing drums', 'mountain climbing']);
```

现在尝试访问新建对象的属性，例如：  

```
person3.name.first
person3.age
person3.bio()
```

正常工作。通常你不会去用这种方法创建新的实例；但如果你刚好因为某些原因没有原始构造器的引用，那么这种方法就很有用了。

此外，`constructor` 属性还有其他用途。比如，想要获得某个对象实例的构造器的名字，可以这么用：

```
instanceName.constructor.name
```

具体地，像这样：

```
person1.constructor.name
```

#### 修改原型

从我们从下面这个例子来看一下如何修改构造器的 `prototype` 属性。

1. 回到 

   oojs-class-further-exercises.html

    的例子，在本地为

   源代码

   创建一个副本。在已有的 JavaScript 的末尾添加如下代码，这段代码将为构造器的 

   ```
   prototype
   ```

    属性添加一个新的方法：   

   ```
   Person.prototype.farewell = function() {
     alert(this.name.first + ' has left the building. Bye for now!');
   }
   ```

保存代码，在浏览器中加载页面，然后在控制台输入：  

```
person1.farewell();
```

你会看到一条警告信息，其中还显示了构造器中定义的人名；这很有用。但更关键的是，整条继承链动态地更新了，任何由此构造器创建的对象实例都自动获得了这个方法。

再想一想这个过程。我们的代码中定义了构造器，然后用这个构造器创建了一个对象实例，*此后*向构造器的 `prototype` 添加了一个新的方法：

```
function Person(first, last, age, gender, interests) {

  // 属性与方法定义

};

var person1 = new Person('Tammi', 'Smith', 32, 'neutral', ['music', 'skiing', 'kickboxing']);

Person.prototype.farewell = function() {
  alert(this.name.first + ' has left the building. Bye for now!');
}
```

但是 `farewell()` 方法*仍然*可用于 `person1`  对象实例——旧有对象实例的可用功能被自动更新了。这证明了先前描述的原型链模型。这种继承模型下，上游对象的方法不会复制到下游的对象实例中；下游对象本身虽然没有定义这些方法，但浏览器会通过上溯原型链、从上游对象中找到它们。这种继承模型提供了一个强大而可扩展的功能系统。

**注意**：如果运行样例时遇到问题，请参阅 [oojs-class-prototype.html](https://github.com/mdn/learning-area/blob/master/javascript/oojs/advanced/oojs-class-prototype.html) 样例（也可查看[即时运行](https://mdn.github.io/learning-area/javascript/oojs/advanced/oojs-class-prototype.html)）。

你很少看到属性定义在 prototype 属性中，因为如此定义不够灵活。比如，你可以添加一个属性：

```
Person.prototype.fullName = 'Bob Smith';
```

但这不够灵活，因为人们可能不叫这个名字。用 `name.first` 和 `name.last` 组成 `fullName` 会好很多：

```
Person.prototype.fullName = this.name.first + ' ' + this.name.last;
```

然而，这么做是无效的，因为本例中 `this` 引用全局范围，而非函数范围。访问这个属性只会得到 `undefined undefined`。但这个语句若放在 先前定义在 `prototype` 上的方法中则有效，因为此时语句位于函数范围内，从而能够成功地转换为对象实例范围。你可能会在 `prototype` 上定义常属性 (constant property) （指那些你永远无需改变的属性），但一般来说，在构造器内定义属性更好。



事实上，一种极其常见的对象定义模式是，在构造器（函数体）中定义属性、在 `prototype` 属性上定义方法。如此，构造器只包含属性定义，而方法则分装在不同的代码块，代码更具可读性。例如：

```
// 构造器及其属性定义

function Test(a,b,c,d) {
  // 属性定义
};

// 定义第一个方法

Test.prototype.x = function () { ... }

// 定义第二个方法

Test.prototype.y = function () { ... }

// 等等……
```

## getElementById和querySelector方法的区别           

   习惯了用jQ查找元素，有时候我们不妨试试js原生的DOM选择符，getElementById()、getElementsByTagName()、querySelector()、querySelectorAll()。说不定一不小心就发现彩蛋了。

那么我们来说说上面那几个方法。

"querySelector 属于 W3C 中的 Selectors API 规范 。而 getElementsBy 系列则属于 W3C 的 DOM 规范"

---------------请忽略上面那句话----------------

还不如来点实际的。

**1、区别**

getXXXByXXX 获取的是动态集合，querySelector获取的是静态集合。

简单的说就是，动态就是选出的元素会随文档改变，静态的不会，取出来之后就和文档的改变无关了。

先看看一个例子：

```
<ul>
    <li>aaa</li>
    <li>ddd</li>
    <li>ccc</li>
</ul>

//demo1
var ul = document.getElementsByTagName('ul')[0],
      lis = ul.getElementsByTagName("li");
for(var i = 0; i < lis.length ; i++){
     ul.appendChild(document.createElement("li"));
}
console.log( lis.length);  //6
 
//demo2
var ul = document.querySelectorAll('ul'),
      lis = ul.querySelectorAll("li");
for(var i = 0; i < lis.length ; i++){
     ul.appendChild(document.createElement("li"));
}
console.log( lis.length);  //3
```

Demo1 中的 lis 是一个动态的 Node List， 每一次调用 lis 都会重新对文档进行查询，导致无限循环的问题。

# 类（class）

## 用类来描述对象原型

```
class Person {
  constructor(first, last, age, gender, interests) {
    this.name = {
      first,
      last
    };
    this.age = age;
    this.gender = gender;
    this.interests = interests;
  }

  greeting() {
    console.log(`Hi! I'm ${this.name.first}`);
  };

  farewell() {
    console.log(`${this.name.first} has left the building. Bye for now!`);
  };
}
```

声明一个类包括如下几点

- constructor方法定义了表示Person类的构造器函数
- greeting()和farerwell()都是类的方法，任何与类相关的方法都定义在类中，构造器之后。

***Note:*** *在浏览器中，类会被转换成原型继承模型。这只是一种语法上的便捷，实际底层和前文的对象原型一样。*

## 类的继承

```
class Teacher extends Person {
  constructor(first, last, age, gender, interests, subject, grade) {
    super(first, last, age, gender, interests);

    // subject and grade are specific to Teacher
    this.subject = subject;
    this.grade = grade;
  }
}

```

**super()操作符用于调用父类的构造器，括号内如果不传参则表示不继承父类的属性，否则要传入继承属性的参数。**

```
let snape = new Teacher('Severus', 'Snape', 58, 'male', ['Potions'], 'Dark arts', 5);
snape.greeting(); // Hi! I'm Severus.
snape.farewell(); // Severus has left the building. Bye for now.
snape.age // 58
snape.subject; // Dark arts
```

现在可以实例化Teacher类，可以调用定义在Teacher和Person类上的属性和方法了。

```
let snape = new Teacher('Severus', 'Snape', 58, 'male', ['Potions'], 'Dark arts', 5);
snape.greeting(); // Hi! I'm Severus.
snape.farewell(); // Severus has left the building. Bye for now.
snape.age // 58
snape.subject; // Dark arts
```

## getters和setters

**使用getters和setters函数便于我们调用和改变某些属性**

```
class Teacher extends Person {
  constructor(first, last, age, gender, interests, subject, grade) {
    super(first, last, age, gender, interests);
    // subject and grade are specific to Teacher
    this._subject = subject;
    this.grade = grade;
  }

  get subject() {
    return this._subject;
  }

  set subject(newSubject) {
    this._subject = newSubject;
  }
}
```

在上述代码中，使用了下划线_命名我们自己定义的属性（区分同名的方法和属性），使用

- 用getter方法展示snape对象当前的_subject属性的值
- 用setter方法给snape对象当前饿_subject属性重新赋值。

```
// Check the default value
console.log(snape.subject) // Returns "Dark arts"

// Change the value
snape.subject = "Balloon animals" // Sets _subject to "Balloon animals"

// Check it again and see if it matches the new value
console.log(snape.subject) // Returns "Balloon animals"
```

*注: 考虑到JavaScript的工作方式，由于原型链等特性的存在，在不同对象之间功能的共享通常被叫做 **委托** - 特殊的对象将功能委托给通用的对象类型完成。这也许比将其称之为继承更为贴切，因为“被继承”了的功能并没有被拷贝到正在“进行继承”的对象中，相反它仍存在于通用的对象中*

# 事件

## 旧事件处理器

每个可用的事件都会有一个**事件处理器**，也就是事件触发时会运行的代码块。当我们定义了一个用来回应事件被激发的代码块的时候，我们说我们**注册了一个事件处理器**。注意事件处理器有时候被叫做**事件监听器**——从我们的用意来看这两个名字是相同的，尽管严格地来说这块代码既监听也处理事件。监听器留意事件是否发生，然后处理器就是对事件发生做出的回应。

```
const btn = document.querySelector('button');

function bgChange() {
  const rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
  document.body.style.backgroundColor = rndCol;
}

btn.onclick = bgChange;
```

## 行内事件处理器

<button onclick="bgChange()">Press me</button>

```
function bgChange() {
  const rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
  document.body.style.backgroundColor = rndCol;
}
```

尽量避免使用行内处理器，吧JavaScript嵌入HTML效率低下。

## 新的事件触发机制

### addEventListener() 和removeEventListener()

```
const btn = document.querySelector('button');

function bgChange() {
  const rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
  document.body.style.backgroundColor = rndCol;
}

btn.addEventListener('click', bgChange);
```

`在addEventListener()` 函数中, 我们具体化了两个参数——我们想要将处理器应用上去的事件名称，和包含我们用来回应事件的函数的代码。注意将这些代码全部放到一个匿名函数中是可行的:

```
btn.addEventListener('click', function() {
  var rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
  document.body.style.backgroundColor = rndCol;
});
```

这个机制带来了一些相较于旧方式的优点。有一个相对应的方法，`removeEventListener()，`这个方法移除事件监听器。例如，下面的代码将会移除上个代码块中的事件监听器：

```
btn.removeEventListener('click', bgChange);
```

在这个简单的、小型的项目中可能不是很有用，但是在大型的、复杂的项目中就非常有用了，可以非常高效地清除不用的事件处理器，另外在其他的一些场景中也非常有效——比如您需要在不同环境下运行不同的事件处理器，您只需要恰当地删除或者添加事件处理器即可。

您也可以给同一个监听器注册多个处理器，下面这种方式不能实现这一点：

```
myElement.onclick = functionA;
myElement.onclick = functionB;
```

第二行会覆盖第一行，但是下面这种方式就会正常工作了：

```
myElement.addEventListener('click', functionA);
myElement.addEventListener('click', functionB);
```

当元素被点击时两个函数都会工作：

此外，该事件机制还提供了许多其他强大的特性和选项。这对于本文来说有点超出范围，但是如果您想要阅读它们，请查看`addEventListener()`和`removeEventListener()`参考页面。

## 我该使用哪种机制？

在三种机制中,您绝对不应该使用HTML事件处理程序属性 - 这些属性已经过时了，而且也是不好的做法，如上所述.

另外两种是相对可互换的，至少对于简单的用途:

    事件处理程序属性功能和选项会更少，但是具有更好的跨浏览器兼容性(在Internet Explorer 8的支持下)，您应该从这些开始学起。
    DOM Level 2 Events (addEventListener(), etc.) 更强大，但也可以变得更加复杂，并且支持不足（只支持到Internet Explorer 9）。 但是您也应该尝试这个方法，并尽可能地使用它们。

第三种机制（DOM Level 2 Events (addEventListener(), etc.)）的主要优点是，如果需要的话，可以使用removeEventListener()删除事件处理程序代码，而且如果有需要，您可以向同一类型的元素添加多个监听器。例如，您可以在一个元素上多次调用addEventListener('click', function() { ... })，并可在第二个参数中指定不同的函数。对于事件处理程序属性来说，这是不可能的，因为后面任何设置的属性都会尝试覆盖较早的属性，例如：

在三种机制中,您绝对不应该使用HTML事件处理程序属性 - 这些属性已经过时了，而且也是不好的做法，如上所述.

另外两种是相对可互换的，至少对于简单的用途:

- 事件处理程序属性功能和选项会更少，但是具有更好的跨浏览器兼容性(在Internet Explorer 8的支持下)，您应该从这些开始学起。
- DOM Level 2 Events (`addEventListener()`, etc.) 更强大，但也可以变得更加复杂，并且支持不足（只支持到Internet Explorer 9）。 但是您也应该尝试这个方法，并尽可能地使用它们。

第三种机制（DOM Level 2 Events (`addEventListener()`, etc.)）的主要优点是，如果需要的话，可以使用`removeEventListener()`删除事件处理程序代码，而且如果有需要，您可以向同一类型的元素添加多个监听器。例如，您可以在一个元素上多次调用`addEventListener('click', function() { ... })`，并可在第二个参数中指定不同的函数。对于事件处理程序属性来说，这是不可能的，因为后面任何设置的属性都会尝试覆盖较早的属性，例如：

```
element.onclick = function1;
element.onclick = function2;
etc.
```

## 事件冒泡和捕获

最后即将介绍的这个主题你常常不会深究，但如果你不理解这个主题，就会十分痛苦。事件冒泡和捕捉是两种机制，主要描述当在一个元素上有两个相同类型的事件处理器被激活会发生什么。为了容易理解，我们来看一个例子——在新标签页打开这个[show-video-box.html](https://mdn.github.io/learning-area/javascript/building-blocks/events/show-video-box.html) 例子（在这里可以查看源码 [source code](https://github.com/mdn/learning-area/blob/master/javascript/building-blocks/events/show-video-box.html)）。也可以在下面查看：

**这是一个非常简单的例子，它显示和隐藏一个包含`<video>`元素的`<div>`元素：**

```
<button>Display video</button>

<div class="hidden">
  <video>
    <source src="rabbit320.mp4" type="video/mp4">
    <source src="rabbit320.webm" type="video/webm">
    <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
  </video>
</div>
```

当‘’button‘’元素按钮被单击时，将显示视频，它是通过将改变`<div>的`class属性值从`hidden`变为`showing`(这个例子的CSS包含两个`class`，它们分别控制这个`<div>`盒子在屏幕上显示还是隐藏。)：

```
btn.onclick = function() {
  videoBox.setAttribute('class', 'showing');
}
```

然后我们再添加几个`onclick`事件处理器，第一个添加在`<div>`元素上，第二个添加在`<video>`元素上。这个想法是当视频(`<video>`）外 `<div>`元素内这块区域被单击时，这个视频盒子应该再次隐藏；当单击视频(`<video>`）本身，这个视频将开始播放。

```
videoBox.onclick = function() {
  videoBox.setAttribute('class', 'hidden');
};

video.onclick = function() {
  video.play();
};
```

但是有一个问题 - 当您点击`video`开始播放的视频时，它会在同一时间导致`<div>`也被隐藏。 这是因为`video`在`<div>`之内 - `video`是`<div>`的一个子元素 - 所以点击`video`实际上是同时也运行`<div>`上的事件处理程序。

#### 对事件冒泡和捕捉的解释

当一个事件发生在具有父元素的元素上(例如，在我们的例子中是`<video>`元素)时，现代浏览器运行两个不同的阶段 - 捕获阶段和冒泡阶段。 在捕获阶段：

- 浏览器检查元素的最外层祖先`<html>`，是否在捕获阶段中注册了一个`onclick`事件处理程序，如果是，则运行它。
- 然后，它移动到`<html>`中单击元素的下一个祖先元素，并执行相同的操作，然后是单击元素再下一个祖先元素，依此类推，直到到达实际点击的元素。

在冒泡阶段，恰恰相反:

- 浏览器检查实际点击的元素是否在冒泡阶段中注册了一个`onclick`事件处理程序，如果是，则运行它
- 然后它移动到下一个直接的祖先元素，并做同样的事情，然后是下一个，等等，直到它到达`<html>`元素。

[![img](https://mdn.mozillademos.org/files/14075/bubbling-capturing.png)](https://mdn.mozillademos.org/files/14075/bubbling-capturing.png)

(单击图片可以放大这个图表)

在现代浏览器中，默认情况下，所有事件处理程序都在冒泡阶段进行注册。因此，在我们当前的示例中，当您单击视频时，这个单击事件从 `<video>`元素向外冒泡直到`<html>`元素。沿着这个事件冒泡线路：

- 它发现了`video.onclick...`事件处理器并且运行它，因此这个视频`<video>`第一次开始播放。
- 接着它发现了（往外冒泡找到的） `videoBox.onclick...`事件处理器并且运行它，因此这个视频`<video>`也隐藏起来了。

#### 用 stopPropagation() 修复问题

这是令人讨厌的行为，但有一种方法来解决它！标准事件对象具有可用的名为 `stopPropagation()`的函数, 当在事件对象上调用该函数时，它只会让当前事件处理程序运行，但事件不会在**冒泡**链上进一步扩大，因此将不会有更多事件处理器被运行(不会向上冒泡)。所以，我们可以通过改变前面代码块中的第二个处理函数来解决当前的问题:

```
video.onclick = function(e) {
  e.stopPropagation();
  video.play();
};
```

***注解**:  为什么我们要弄清楚捕捉和冒泡呢？那是因为，在过去糟糕的日子里，浏览器的兼容性比现在要小得多，Netscape（网景）只使用事件捕获，而Internet  Explorer只使用事件冒泡。当W3C决定尝试规范这些行为并达成共识时，他们最终得到了包括这两种情况（捕捉和冒泡）的系统，最终被应用在现在浏览器里。*

***注解**: 如上所述，默认情况下，所有事件处理程序都是在冒泡阶段注册的，这在大多数情况下更有意义。如果您真的想在捕获阶段注册一个事件，那么您可以通过使用`addEventListener()`注册您的处理程序，并将可选的第三个属性设置为true。*

#### 事件委托

冒泡还允许我们利用事件委托——这个概念依赖于这样一个事实,如果你想要在大量子元素中单击任何一个都可以运行一段代码，您可以将事件监听器设置在其父节点上，并让子节点上发生的事件冒泡到父节点上，而不是每个子节点单独设置事件监听器。

一个很好的例子是一系列列表项，如果你想让每个列表项被点击时弹出一条信息，您可以将`click`单击事件监听器设置在父元素`<ul>`上，这样事件就会从列表项冒泡到其父元素`<ul>`上。

这个的概念在David Walsh的博客上有更多的解释，并有多个例子——看看[How JavaScript Event Delegation Works](https://davidwalsh.name/event-delegate).

# JSON

## 定义

**JSON(JavaScript Object Notation, JS 对象简谱) 是一种轻量级的数据交换格式。**

可以把 JavaScript 对象原原本本的写入 JSON 数据——字符串，数字，数组，布尔还有其它的字面值对象。这允许您构造出一个对象树，如下：

```javascript
{
  "squadName" : "Super hero squad",
  "homeTown" : "Metro City",
  "formed" : 2016,
  "secretBase" : "Super tower",
  "active" : true,
  "members" : [
    {
      "name" : "Molecule Man",
      "age" : 29,
      "secretIdentity" : "Dan Jukes",
      "powers" : [
        "Radiation resistance",
        "Turning tiny",
        "Radiation blast"
      ]
    },
    {
      "name" : "Madame Uppercut",
      "age" : 39,
      "secretIdentity" : "Jane Wilson",
      "powers" : [
        "Million tonne punch",
        "Damage resistance",
        "Superhuman reflexes"
      ]
    },
    {
      "name" : "Eternal Flame",
      "age" : 1000000,
      "secretIdentity" : "Unknown",
      "powers" : [
        "Immortality",
        "Heat Immunity",
        "Inferno",
        "Teleportation",
        "Interdimensional travel"
      ]
    }
  ]
}
```

使用链式法（.或者[]）则访问JSON中的对象或者属性

```
superHeroes.hometown
superHeroes["active"]
```

## JSON数组

```
[
  {
    "name" : "Molecule Man",
    "age" : 29,
    "secretIdentity" : "Dan Jukes",
    "powers" : [
      "Radiation resistance",
      "Turning tiny",
      "Radiation blast"
    ]
  },
  {
    "name" : "Madame Uppercut",
    "age" : 39,
    "secretIdentity" : "Jane Wilson",
    "powers" : [
      "Million tonne punch",
      "Damage resistance",
      "Superhuman reflexes"
    ]
  }
]
```

上面是完全合法的 JSON。您只需要通过数组索引就可以访问数组元素，如`[0]["powers"][0]。`

**注意事项**

- JSON 是一种纯数据格式，它**只包含属性，没有方法。**
- JSON要求在字符串和属性名称周围使用双引号。 单引号无效。
- 甚至一个错位的逗号或分号就可以导致  JSON 文件出错。您应该小心的检查您想使用的数据(虽然计算机生成的 JSON 很少出错，只要生成程序正常工作)。您可以通过像 [JSONLint](http://jsonlint.com/) 的应用程序来检验 JSON。
- JSON 可以将任何标准合法的 JSON 数据格式化保存，不只是数组和对象。比如，一个单一的字符串或者数字可以是合法的 JSON 对象。虽然不是特别有用处……
- 与 JavaScript 代码中对象属性可以不加引号不同，JSON 中只有带引号的字符串可以用作属性。

# Asynchronous JavaScript

## 线程

一个线程是一个基本的处理过程，程序利用线程来完成任务，每个线程只能执行一个任务；

*注：JavaScript是**单线程**的*

## 异步JavaScript

### callbacks

异步callbacks 其实就是函数，只不过是作为参数传递给那些在后台执行的其他函数.  当那些后台运行的代码结束，就调用callbacks函数，通知你工作已经完成，或者其他有趣的事情发生了。使用callbacks  有一点老套，在一些老派但经常使用的API里面，你会经常看到这种风格。

举个例子，异步callback 就是[`addEventListener()`](https://developer.mozilla.org/zh-CN/docs/Web/API/EventTarget/addEventListener)第二个参数（前面的例子）：

```
btn.addEventListener('click', () => {
  alert('You clicked me!');

  let pElem = document.createElement('p');
  pElem.textContent = 'This is a newly-added paragraph.';
  document.body.appendChild(pElem);
});
```

第一个参数是侦听的事件类型，第二个就是事件发生时调用的回调函数。.

当我们把回调函数作为一个参数传递给另一个函数时，仅仅是把回调函数定义作为参数传递过去 — 回调函数并没有立刻执行，回调函数会在包含它的函数的某个地方异步执行，包含函数负责在合适的时候执行回调函数。



你可以自己写一个容易的，包含回调函数的函数。来看另外一个例子，用 [`XMLHttpRequest` API](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) ([运行它](https://mdn.github.io/learning-area/javascript/asynchronous/introducing/xhr-async-callback.html), [源代码](https://github.com/mdn/learning-area/blob/master/javascript/asynchronous/introducing/xhr-async-callback.html)) 加载资源：

```
function loadAsset(url, type, callback) {
  let xhr = new XMLHttpRequest();
  xhr.open('GET', url);
  xhr.responseType = type;

  xhr.onload = function() {
    callback(xhr.response);
  };

  xhr.send();
}

function displayImage(blob) {
  let objectURL = URL.createObjectURL(blob);

  let image = document.createElement('img');
  image.src = objectURL;
  document.body.appendChild(image);
}

loadAsset('coffee.jpg', 'blob', displayImage);
```

创建 `displayImage()` 函数，简单的把blob传递给它，生成objectURL，然后再生成一个image元素，把objectURL作为image的源地址，最后显示这张图片。 然后，我们创建 `loadAsset()` 函数，把URL，type，和回调函数同时都作为参数。函数用 `XMLHttpRequest` (通常缩写 "XHR") 获取给定URL的资源，在获得资源响应后再把响应作为参数传递给回调函数去处理。 (使用 `onload` 事件处理) ，有点烧脑，是不是？！

回调函数用途广泛 — 他们不仅仅可以用来控制函数的执行顺序和函数之间的数据传递，还可以根据环境的不同，将数据传递给不同的函数，所以对下载好的资源，你可以采用不同的操作来处理，譬如 `processJSON()`, `displayText()`, 等等。

请注意，不是所有的回调函数都是异步的 — 有一些是同步的。一个例子就是使用 [`Array.prototype.forEach()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) 来遍历数组 ([运行](https://mdn.github.io/learning-area/javascript/asynchronous/introducing/foreach.html), [源代码](https://github.com/mdn/learning-area/blob/master/javascript/asynchronous/introducing/foreach.html)):

```javascript
const gods = ['Apollo', 'Artemis', 'Ares', 'Zeus'];

gods.forEach(function (eachName, index){
  console.log(index + '. ' + eachName);
});
```

在这个例子中，我们遍历一个希腊神的数组，并在控制台中打印索引和值。`forEach()` 需要的参数是一个回调函数，回调函数本身带有两个参数，数组元素和索引值。它无需等待任何事情，立即运行。

#### **什么是回调函数？**

我们绕点远路来回答这个问题。

编程分为两类：[系统编程](https://www.zhihu.com/search?q=系统编程&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A27459821})（system programming）和应用编程（application programming）。所谓系统编程，简单来说，就是编写**库**；而应用编程就是利用写好的各种库来编写具某种功用的程序，也就是**应用**。系统程序员会给自己写的库留下一些接口，即API（application programming interface，[应用编程接口](https://www.zhihu.com/search?q=应用编程接口&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A27459821})），以供应用程序员使用。所以在抽象层的图示里，库位于应用的底下。

当程序跑起来时，一般情况下，[应用程序](https://www.zhihu.com/search?q=应用程序&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A27459821})（application program）会时常通过API调用库里所预先备好的函数。但是有些库函数（library function）却要求应用先传给它一个函数，好在合适的时候调用，以完成目标任务。这个被传入的、后又被调用的函数就称为**回调函数**（[callback function](https://www.zhihu.com/search?q=callback+function&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A27459821})）。

打个比方，有一家旅馆提供叫醒服务，但是要求旅客自己决定叫醒的方法。可以是打客房电话，也可以是派服务员去敲门，睡得死怕耽误事的，还可以要求往自己头上浇盆水。这里，“叫醒”这个行为是旅馆提供的，相当于库函数，但是叫醒的方式是由旅客决定并告诉旅馆的，也就是回调函数。而旅客告诉旅馆怎么叫醒自己的动作，也就是把回调函数传入库函数的动作，称为**登记回调函数**（to register a callback function）。如下图所示（图片来源：[维基百科](https://www.zhihu.com/search?q=维基百科&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A27459821})）：![img](https://pic1.zhimg.com/80/0ef3106510e2e1630eb49744362999f8_720w.jpg?source=1940ef5c)
可以看到，回调函数通常和应用处于同一抽象层（因为传入什么样的回调函数是在应用级别决定的）。而回调就成了一个高层调用底层，底层再**回**过头来**调**用高层的过程。（我认为）这应该是回调最早的应用之处，也是其得名如此的原因。

**[回调机制](https://www.zhihu.com/search?q=回调机制&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A27459821})**的优势

**从上面的例子可以看出，回调机制提供了非常大的灵活性。请注意，从现在开始，我们把图中的库函数改称为**中间函数**了，这是因为回调并不仅仅用在应用和库之间。任何时候，只要想获得类似于上面情况的灵活性，都可以利用回调。**

**这种灵活性是怎么实现的呢？乍看起来，回调似乎只是函数间的调用，但仔细一琢磨，可以发现两者之间的一个关键的不同：在回调中，我们利用某种方式，把回调函数像参数一样传入中间函数。可以这么理解，在传入一个回调函数之前，中间函数是不完整的。换句话说，程序可以在运行时，通过登记不同的回调函数，来决定、改变中间函数的行为。这就比简单的函数调用要灵活太多了。请看下面这段Python写成的回调的简单示例：

![image-20211225114111257](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20211225114111257.png)

上面的代码里，给`getOddNumber`传入不同的回调函数，它的表现也不同，这就是回调机制的优势所在。值得一提的是，上面的第三个回调函数是一个匿名函数。

**易被忽略的第三方**

通过上面的论述可知，中间函数和回调函数是回调的两个必要部分，不过人们往往忽略了回调里的第三位要角，就是中间函数的调用者。绝大多数情况下，这个调用者可以和程序的主函数等同起来，但为了表示区别，我这里把它称为**起始函数**（如上面的代码中注释所示）。

之所以特意强调这个第三方，是因为我在网上读相关文章时得到一种印象，很多人把它简单地理解为两个个体之间的来回调用。譬如，很多中文网页在解释“回调”（callback）时，都会提到这么一句话：“If you call me, I will call you  back.”我没有查到这句英文的出处。我个人揣测，很多人把起始函数和回调函数看作为一体，大概有两个原因：第一，可能是“回调”这一名字的误导；第二，给中间函数传入什么样的回调函数，是在起始函数里决定的。实际上，回调并不是“你我”两方的互动，而是ABC的三方联动。有了这个清楚的概念，在自己的代码里实现回调时才不容易混淆出错。

另外，回调实际上有两种：阻塞式回调和延迟式回调。两者的区别在于：阻塞式回调里，回调函数的调用一定发生在起始函数返回之前；而延迟式回调里，回调函数的调用有可能是在起始函数返回之后。这里不打算对这两个概率做更深入的讨论，之所以把它们提出来，也是为了说明强调起始函数的重要性。网上的很多文章，提到这两个概念时，只是笼统地说阻塞式回调发生在[主调函数](https://www.zhihu.com/search?q=主调函数&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A27459821})返回之前，却没有明确这个主调函数到底是起始函数还是中间函数，不免让人糊涂，所以这里特意说明一下。另外还请注意，本文中所举的示例均为阻塞式回调。延迟式回调通常牵扯到多线程，我自己还没有完全搞明白，所以这里就不多说了。

### Promises

Promises 是新派的异步代码，现代的web APIs经常用到。 `fetch()` API就是一个很好的例子, 它基本上就是一个现代版的，更高效的 [`XMLHttpRequest`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest)。看个例子，来自于文章 [Fetching data from the server](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data) ：

```JavaScript
fetch('products.json').then(function(response) {
  return response.json();
}).then(function(json) {
  products = json;
  initialize();
}).catch(function(err) {
  console.log('Fetch problem: ' + err.message);
});
```

**Note**: 在GitHub上有完整的代码 ([see the source here](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/can-store-xhr/can-script.js), and also [see it running live](https://mdn.github.io/learning-area/javascript/apis/fetching-data/can-store-xhr/))。

这里`fetch``()` 只需要一个参数— 资源的网络 URL — 返回一个 [promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). promise 是表示异步操作完成或失败的对象。可以说，它代表了一种中间状态。 本质上，这是浏览器说“我保证尽快给您答复”的方式，因此得名“promise”。

这个概念需要练习来适应;它感觉有点像运行中的[薛定谔猫](https://zh.wikipedia.org/wiki/薛定谔猫)。这两种可能的结果都还没有发生，因此fetch操作目前正在等待浏览器试图在将来某个时候完成该操作的结果。然后我们有三个代码块链接到fetch()的末尾：

- 两个 `then()` 块。两者都包含一个回调函数，如果前一个操作成功，该函数将运行，并且每个回调都接收前一个成功操作的结果作为输入，因此您可以继续对它执行其他操作。每个 `.then()`块返回另一个promise，这意味着可以将多个`.then()`块链接到另一个块上，这样就可以依次执行多个异步操作。
- 如果其中任何一个`then()`块失败，则在末尾运行`catch()`块——与同步`try...catch`类似，`catch()`提供了一个错误对象，可用来报告发生的错误类型。但是请注意，同步`try...catch`不能与promise一起工作，尽管它可以与[async/await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)一起工作，稍后您将了解到这一点。

### 事件队列

像promise这样的异步操作被放入事件队列中，事件队列在主线程完成处理后运行，这样它们就不会阻止后续JavaScript代码的运行。排队操作将尽快完成，然后将结果返回到JavaScript环境。

### Promises 对比 callbacks

promises与旧式callbacks有一些相似之处。它们本质上是一个返回的对象，您可以将回调函数附加到该对象上，而不必将回调作为参数传递给另一个函数。

然而，`Promise`是专门为异步操作而设计的，与旧式回调相比具有许多优点:

- 您可以使用多个then()操作将多个异步操作链接在一起，并将其中一个操作的结果作为输入传递给下一个操作。这种链接方式对回调来说要难得多，会使回调以混乱的“末日金字塔”告终。 (也称为[回调地狱](http://callbackhell.com/))。
- `Promise`总是严格按照它们放置在事件队列中的顺序调用。
- 错误处理要好得多——所有的错误都由块末尾的一个.catch()块处理，而不是在“金字塔”的每一层单独处理。

### 异步代码的本质

让我们研究一个示例，它进一步说明了异步代码的本质，展示了当我们不完全了解代码执行顺序以及将异步代码视为同步代码时可能发生的问题。下面的示例与我们之前看到的非常相似( [运行它](https://mdn.github.io/learning-area/javascript/asynchronous/introducing/async-sync.html) 和 [源代码](https://github.com/mdn/learning-area/blob/master/javascript/asynchronous/introducing/async-sync.html))。一个不同之处在于，我们包含了许多[`console.log()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Console/log)语句，以展示代码将在其中执行的顺序。

```JavaScript
console.log ('Starting');
let image;

fetch('coffee.jpg').then((response) => {
  console.log('It worked :)')
  return response.blob();
}).then((myBlob) => {
  let objectURL = URL.createObjectURL(myBlob);
  image = document.createElement('img');
  image.src = objectURL;
  document.body.appendChild(image);
}).catch((error) => {
  console.log('There has been a problem with your fetch operation: ' + error.message);
});

console.log ('All done!');
```

浏览器将会执行代码，看见第一个`console.log()` 输出(`Starting`) ，然后创建`image` 变量。

然后，它将移动到下一行并开始执行`fetch()`块，但是，因为`fetch()`是异步执行的，没有阻塞，所以在`promise`相关代码之后程序继续执行，从而到达最后的`console.log()`语句(`All done`!)并将其输出到控制台。

只有当`fetch()` 块完成运行返回结果给`.then()` ，我们才最后看到第二个`console.log()` 消息 (`It worked ;)`) . 所以 这些消息 可能以 和你预期不同的顺序出现：

- Starting
- All done!
- It worked :)

如果你感到疑惑，考虑下面这个小例子：

```java
console.log("registering click handler");

button.addEventListener('click', () => {
  console.log("get click");
});

console.log("all done");
```

这在行为上非常相似——第一个和第三个`console.log()`消息将立即显示，但是第二个消息将被阻塞，直到有人单击鼠标按钮。前面的示例以相同的方式工作，只是在这种情况下，第二个消息在`promise`链上被阻塞，直到获取资源后再显示在屏幕上，而不是单击。

要查看实际情况，请尝试获取[示例](https://github.com/mdn/learning-area/blob/master/javascript/asynchronous/introducing/async-sync.html)的本地副本，并将第三个`console.log()`调用更改为以下命令：

```
console.log ('All done! ' + image.src + 'displayed.');
```

此时控制台将会报错，而不会显示第三个 `console.log` 的信息：

```
TypeError: image is undefined; can't access its "src" property
```

这是因为：浏览器运行第三个`console.log()`的时候，`fetch()` 语句块还没有完成，因此`image`还没有赋值。

## 合作异步JavaScript：延时(timeout)和间隔(interval)

很长一段时间以来，web平台为JavaScript程序员提供了许多函数，这些函数允许您在一段时间间隔过后异步执行代码，或者重复异步执行代码块，直到您告诉它停止为止。这些都是:

- `setTimeout()`

  在指定的时间后执行一段代码.

- `setInterval()`

  以固定的时间间隔，重复运行一段代码.

- `requestAnimationFrame()`

  setInterval()的现代版本;在浏览器下一次重新绘制显示之前执行指定的代码块，从而允许动画在适当的帧率下运行，而不管它在什么环境中运行.

这些函数设置的异步代码实际上在主线程上运行（在其指定的计时器过去之后）。

在 `setTimeout()` 调用执行之前或 `setInterval()` 迭代之间可以（并且经常会）运行其他代码。根据这些操作的处理器密集程度，它们可以进一步延迟异步代码，因为任何异步代码仅在主线程可用后才执行（换句话说，当调用栈为空时）。在阅读本文时，您将学到更多关于此问题的信息。

### setTimeout()

正如前述， `setTimeout()` 在指定的时间后执行一段特定代码. 它需要如下参数:

- 要运行的函数，或者函数引用。
- 表示在执行代码之前等待的时间间隔(以毫秒为单位，所以1000等于1秒)的数字。如果指定值为0(或完全省略该值)，函数将尽快运行（参阅下面的注释，了解为什么它“尽快”而不是“立即”运行）。稍后详述这样做的原因。
- 更多的参数：在指定函数运行时，希望传递给函数的值。

**Note:** 指定的时间（或延迟）不能保证在指定的确切时间之后执行，而是最短的延迟执行时间。在主线程上的堆栈为空之前，传递给这些函数的回调将无法运行。

结果，像 `setTimeout(fn, 0)` 这样的代码将在堆栈为空时立即执行，而不是立即执行。如果执行类似 `setTimeout(fn, 0)` 之类的代码，之后立即运行从 1 到 100亿 的循环之后，回调将在几秒后执行。 

在下面的示例中，浏览器将在执行匿名函数之前等待两秒钟，然后显示alert消息 ([see it running live](https://mdn.github.io/learning-area/javascript/asynchronous/loops-and-intervals/simple-settimeout.html), and [see the source code](https://github.com/mdn/learning-area/blob/master/javascript/asynchronous/loops-and-intervals/simple-settimeout.html)):

```
let myGreeting = setTimeout(function() {
  alert('Hello, Mr. Universe!');
}, 2000)
```

#### 传递参数给setTimeout()

我们希望传递给`setTimeout()`中运行的函数的任何参数，都必须作为列表末尾的附加参数传递给它。

例如，我们可以重构之前的函数，这样无论传递给它的人的名字是什么，它都会向它打招呼：

```
function sayHi(who) {
  alert('Hello ' + who + '!');
}
```

人名可以通过第三个参数传进 `setTimeout()` ：

```
let myGreeting = setTimeout(sayHi, 2000, 'Mr. Universe');
```

### clearTimeout

如果创建了 timeout，您可以通过调用`clearTimeout()`，将`setTimeout()`调用的标识符作为参数传递给它，从而在超时运行之前取消。要取消上面的超时，你需要这样做：

```
clearTimeout(myGreeting);
```

### setInterval()

当我们需要在一段时间之后运行一次代码时，`setTimeout()`可以很好地工作。但是当我们需要反复运行代码时会发生什么，例如在动画的情况下?

这就是`setInterval()`的作用所在。这与`setTimeout()`的工作方式非常相似，只是作为第一个参数传递给它的函数，**重复**执行的时间不少于第二个参数给出的毫秒数，**而不是一次执行**。您还可以将正在执行的函数所需的任何参数作为 `setInterval()` 调用的后续参数传递。

让我们看一个例子。下面的函数创建一个新的`Date()`对象，使用`toLocaleTimeString()`从中提取一个时间字符串，然后在UI中显示它。然后，我们使用`setInterval()`每秒运行该函数一次，创建一个每秒更新一次的数字时钟的效果。

([see this live](https://mdn.github.io/learning-area/javascript/asynchronous/loops-and-intervals/setinterval-clock.html), and also [see the source](https://github.com/mdn/learning-area/blob/master/javascript/asynchronous/loops-and-intervals/setinterval-clock.html)):

```
function displayTime() {
   let date = new Date();
   let time = date.toLocaleTimeString();
   document.getElementById('demo').textContent = time;
}

const createClock = setInterval(displayTime, 1000);
```

`像setTimeout()一样`, `setInterval()` 返回一个确定的值，稍后你可以用它来取消间隔任务。

### clearInterval()

`setInterval`()永远保持运行任务,除非我们做点什么——我们可能会想阻止这样的任务,否则当浏览器无法完成任何进一步的任务时我们可能得到错误, 或者动画处理已经完成了。我们可以用与停止超时相同的方法来实现这一点——通过将`setInterval`()调用返回的标识符传递给`clearInterval`()函数:

```JavaScript
const myInterval = setInterval(myFunction, 2000);

clearInterval(myInterval);
```

### setTimeout()与setInterval()几个注意点

当使用 `setTimeout()` 和 `setInterval()`的时候，有几点需要额外注意。 现在让我们回顾一下：

#### 递归的timeouts

还有另一种方法可以使用`setTimeout()`：我们可以递归调用它来重复运行相同的代码，而不是使用`setInterval()`。

下面的示例使用递归`setTimeout()`每100毫秒运行传递来的函数：

```
let i = 1;

setTimeout(function run() {
  console.log(i);
  i++;
  setTimeout(run, 100);
}, 100);
```

将上面的示例与下面的示例进行比较 ––这使用 `setInterval()` 来实现相同的效果：

```
let i = 1;

setInterval(function run() {
  console.log(i);
  i++
}, 100);
```

#### 递归setTimeout()和setInterval()有何不同？

上述代码的两个版本之间的差异是微妙的。

- 递归 `setTimeout()` 保证执行之间的延迟相同，例如在上述情况下为100ms。 代码将运行，然后在它再次运行之前等待100ms，因此无论代码运行多长时间，间隔都是相同的。
- 使用 `setInterval()` 的示例有些不同。 我们选择的间隔包括执行我们想要运行的代码所花费的时间。假设代码需要40毫秒才能运行 - 然后间隔最终只有60毫秒。
- 当递归使用 `setTimeout()` 时，每次迭代都可以在运行下一次迭代之前计算不同的延迟。 换句话说，第二个参数的值可以指定在再次运行代码之前等待的不同时间（以毫秒为单位）。

当你的代码有可能比你分配的时间间隔，花费更长时间运行时，最好使用递归的 `setTimeout()` - 这将使执行之间的时间间隔保持不变，无论代码执行多长时间，你不会得到错误。

#### 立即超时

使用0用作setTimeout()的回调函数会立刻执行，但是在主线程代码运行之后执行。

举个例子，下面的代码([see it live](https://mdn.github.io/learning-area/javascript/asynchronous/loops-and-intervals/zero-settimeout.html)) 输出一个包含警报的"Hello"，然后在您点击第一个警报的OK之后立即弹出“world”。

```
setTimeout(function() {
  alert('World');
}, 0);

alert('Hello');
```

如果您希望设置一个代码块以便在所有主线程完成运行后立即运行，这将很有用。将其放在异步事件循环中，这样它将随后直接运行。

#### 使用 clearTimeout() or clearInterval()清除

```
clearTimeout()` 和`clearInterval()` 都使用相同的条目列表进行清除。有趣的是，这意味着你可以使用任一一种方法来清除 `setTimeout()` 和 `setInterval()。
```

但为了保持一致性，你应该使用 `clearTimeout()` 来清除 `setTimeout()` 条目，使用 `clearInterval()` 来清除 `setInterval()` 条目。 这样有助于避免混乱。

### requestAnimationFranme()

`requestAnimationFrame()` 是一个专门的循环函数，旨在浏览器中高效运行动画。它基本上是现代版本的`setInterval()` —— 它在浏览器重新加载显示内容之前执行指定的代码块，从而允许动画以适当的帧速率运行，不管其运行的环境如何。

它是针对`setInterval()` 遇到的问题创建的，比如 `setInterval()`并不是针对设备优化的帧率运行，有时会丢帧。还有即使该选项卡不是活动的选项卡或动画滚出页面等问题 。

（在[CreativeJS](http://creativejs.com/resources/requestanimationframe/index.html)上了解有关此内容的更多信息）.

**注意：** 你可以在课程中其他地方找到`requestAnimationFrame()` 的使用范例—参见 [Drawing graphics](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Drawing_graphics), 和 [Object building practice](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_building_practice)。

该方法将重新加载页面之前要调用的回调函数作为参数。这是您将看到的常见表达：

```
function draw() {
   // Drawing code goes here
   requestAnimationFrame(draw);
}

draw();
```

这个想法是要定义一个函数，在其中更新动画 (例如，移动精灵，更新乐谱，刷新数据等)，然后调用它来开始这个过程。在函数的末尾，以 `requestAnimationFrame()` 传递的函数作为参数进行调用，这指示浏览器在下一次显示重新绘制时再次调用该函数。然后这个操作连续运行， 因为`requestAnimationFrame()` 是递归调用的。

**注意**: 如果要执行某种简单的常规DOM动画, [CSS 动画](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) 可能更快，因为它们是由浏览器的内部代码计算而不是JavaScript直接计算的。但是，如果您正在做一些更复杂的事情，并且涉及到在DOM中不能直接访问的对象(such as [2D Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) or [WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API) objects), `requestAnimationFrame()` 在大多数情况下是更好的选择。

#### [你的动画跑得有多快？](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals#你的动画跑得有多快？)

动画的平滑度直接取决于动画的帧速率，并以每秒帧数（fps）为单位进行测量。这个数字越高，动画看起来就越平滑。

由于大多数屏幕的刷新率为60Hz，因此在使用web浏览器时，可以达到的最快帧速率是每秒60帧（FPS）。然而，更多的帧意味着更多的处理，这通常会导致卡顿和跳跃-也称为丢帧或跳帧。

如果您有一个刷新率为60Hz的显示器，并且希望达到60fps，则大约有16.7毫秒（1000/60）来执行动画代码来渲染每个帧。这提醒我们，我们需要注意每次通过动画循环时要运行的代码量。

`requestAnimationFrame()` 总是试图尽可能接近60帧/秒的值，当然有时这是不可能的如果你有一个非常复杂的动画，你是在一个缓慢的计算机上运行它，你的帧速率将更少。`requestAnimationFrame()` 会尽其所能利用现有资源提升帧速率。

#### [ requestAnimationFrame() 与 setInterval() 和 setTimeout()有什么不同?](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals#requestanimationframe_与_setinterval_和_settimeout有什么不同)

让我们进一步讨论一下 `requestAnimationFrame()` 方法与前面介绍的其他方法的区别. 下面让我们看一下代码:

```
function draw() {
   // Drawing code goes here
   requestAnimationFrame(draw);
}

draw();
```

现在让我们看看如何使用`setInterval()`:

```
function draw() {
   // Drawing code goes here
}

setInterval(draw, 17);
```

如前所述，我们没有为`requestAnimationFrame()`;指定时间间隔；它只是在当前条件下尽可能快速平稳地运行它。如果动画由于某些原因而处于屏幕外浏览器也不会浪费时间运行它。

 另一方面`setInterval()`需要指定间隔。我们通过公式1000毫秒/60Hz得出17的最终值，然后将其四舍五入。四舍五入是一个好主意，浏览器可能会尝试运行动画的速度超过60fps，它不会对动画的平滑度有任何影响。如前所述，60Hz是标准刷新率。

#### [包括时间戳](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals#包括时间戳)

传递给 `requestAnimationFrame()` 函数的实际回调也可以被赋予一个参数（一个时间戳值），表示自 `requestAnimationFrame()` 开始运行以来的时间。这是很有用的，因为它允许您在特定的时间以恒定的速度运行，而不管您的设备有多快或多慢。您将使用的一般模式如下所示：

```
let startTime = null;

function draw(timestamp) {
    if(!startTime) {
      startTime = timestamp;
    }

   currentTime = timestamp - startTime;

   // Do something based on current time

   requestAnimationFrame(draw);
}

draw();
```

#### [浏览器支持](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals#浏览器支持)

 与`setInterval()或``setTimeout()` 相比最近的浏览器支持`requestAnimationFrame()`

— `requestAnimationFrame()`.在Internet Explorer 10及更高版本中可用。因此，除非您的代码需要支持旧版本的IE，否则没有什么理由不使用`requestAnimationFrame()` 。

#### [撤销requestAnimationFrame()](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Timeouts_and_intervals#撤销requestanimationframe)

`requestAnimationFrame()`可用与之对应的`cancelAnimationFrame()`方法“撤销”（不同于“set…”类方法的“清除”，此处更接近“撤销”之意）。

该方法以`requestAnimationFrame()`的返回值为参数，此处我们将该返回值存在变量 `rAF` 中：

```
cancelAnimationFrame(rAF);
```

## 异步处理promises

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Promises#promise%E6%9C%AF%E8%AF%AD%E5%9B%9E%E9%A1%BE

## async和await:让异步编程更简单

[async functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) 和 `await` 关键字是最近添加到JavaScript语言里面的。它们是ECMAScript 2017 JavaScript版的一部分（参见[ECMAScript Next support in Mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_Next_support_in_Mozilla)）。简单来说，它们是基于promises的语法糖，使异步代码更易于编写和阅读。通过使用它们，异步代码看起来更像是老式同步代码，因此它们非常值得学习。

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Async_await

## 选择正确的方法

- callback()
- setTimeout()
- setInterval()
- requestAnimationFrame()
- Promises
- Promise.all()
- Async/await

根据需要选择相应的方法，能够提升代码的效率。

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Asynchronous/Choosing_the_right_approach

# 客户端API

## Web API简介

客户端JavaScript中的API分为两类

- 浏览器API
- 第三方API

JavaScript，API和其它JavaScript工具之间的关系

- JavaScript — 一种内置于浏览器的高级脚本语言，您可以用来实现Web页面/应用中的功能。注意JavaScript也可用于其他象[Node](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)这样的的编程环境。但现在您不必考虑这些。
- 客户端API — 内置于浏览器的结构程序，位于JavaScript语言顶部，使您可以更容易的实现功能。
- 第三方API — 置于第三方普通的结构程序（例如Twitter，Facebook），使您可以在自己的Web页面中使用那些平台的某些功能（例如在您的Web页面显示最新的Tweets）。
- JavaScript库 — 通常是包含具有[特定功能](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions#custom_functions)的一个或多个JavaScript文件，把这些文件关联到您的Web页以快速或授权编写常见的功能。例如包含jQuery和Mootools
- JavaScript框架 — 从库开始的下一步，JavaScript框架视图把HTML、CSS、JavaScript和其他安装的技术打包在一起，然后用来从头编写一个完整的Web应用。

## API的作用

各种API的作用https://developer.mozilla.org/en-US/docs/Web/API

### 常见的浏览器API

- **操作文档的API**内置于浏览器中。最明显的例子是[DOM（文档对象模型）](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model)API，它允许您操作HTML和CSS — 创建、移除以及修改HTML，动态地将新样式应用到您的页面，等等。每当您看到一个弹出窗口出现在一个页面上，或者显示一些新的内容时，这都是DOM的行为。 您可以在在[Manipulating documents](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents)中找到关于这些类型的API的更多信息。
- **从服务器获取数据的API** 用于更新网页的一小部分是相当好用的。这个看似很小的细节能对网站的性能和行为产生巨大的影响 — 如果您只是更新一个股票列表或者一些可用的新故事而不需要从服务器重新加载整个页面将使网站或应用程序感觉更加敏感和“活泼”。使这成为可能的API包括[`XMLHttpRequest`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest)和[Fetch API](https://developer.mozilla.org/zh-CN/docs/Web/API/Fetch_API)。您也可能会遇到描述这种技术的术语**Ajax**。您可以在[Fetching data from the server](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data)找到关于类似的API的更多信息。
- **用于绘制和操作图形的API**目前已被浏览器广泛支持 — 最流行的是允许您以编程方式更新包含在HTML [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/canvas) 元素中的像素数据以创建2D和3D场景的[Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)和[WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)。例如，您可以绘制矩形或圆形等形状，将图像导入到画布上，然后使用Canvas API对其应用滤镜（如棕褐色滤镜或灰度滤镜），或使用WebGL创建具有光照和纹理的复杂3D场景。这些API经常与用于创建动画循环的API（例如[`window.requestAnimationFrame()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/requestAnimationFrame)）和其他API一起不断更新诸如动画和游戏之类的场景。
- **音频和视频API**例如[`HTMLMediaElement`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLMediaElement)，[Web Audio API](https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Audio_API)和[WebRTC](https://developer.mozilla.org/zh-CN/docs/MDN/Doc_status/API/WebRTC)允许您使用多媒体来做一些非常有趣的事情，比如创建用于播放音频和视频的自定义UI控件，显示字幕字幕和您的视频，从网络摄像机抓取视频，通过画布操纵（见上），或在网络会议中显示在别人的电脑上，或者添加效果到音轨（如增益，失真，平移等） 。
- **设备API**基本上是以对网络应用程序有用的方式操作和检索现代设备硬件中的数据的API。我们已经讨论过访问设备位置数据的地理定位API，因此您可以在地图上标注您的位置。其他示例还包括通过系统通知（参见[Notifications API](https://developer.mozilla.org/zh-CN/docs/Web/API/Notifications_API)）或振动硬件（参见[Vibration API](https://developer.mozilla.org/zh-CN/docs/Web/API/Vibration_API)）告诉用户Web应用程序有用的更新可用。
- **客户端存储API**在Web浏览器中的使用变得越来越普遍 - 如果您想创建一个应用程序来保存页面加载之间的状态，甚至让设备在处于脱机状态时可用，那么在客户端存储数据将会是非常有用的。例如使用[Web Storage API](https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Storage_API)的简单的键 - 值存储以及使用[IndexedDB API](https://developer.mozilla.org/zh-CN/docs/Web/API/IndexedDB_API)的更复杂的表格数据存储。

### 常见的第三方API

- The [Twitter API](https://dev.twitter.com/overview/documentation), 允许您在您的网站上展示您最近的推文等。
- The [Google Maps API](https://developers.google.com/maps/) 允许你在网页上对地图进行很多操作（这很有趣，它也是Google地图的驱动器）。现在它是一整套完整的，能够胜任广泛任务的API。其能力已经被[Google Maps API Picker](https://developers.google.com/maps/documentation/api-picker)见证。
- The [Facebook suite of API](https://developers.facebook.com/docs/) 允许你将很多Facebook生态系统中的功能应用到你的app，使之受益，比如说它提供了通过Facebook账户登录、接受应用内支付、推送有针对性的广告活动等功能。
- The [YouTube API](https://developers.google.com/youtube/), 允许你将Youtube上的视频嵌入到网站中去，同时提供搜索Youtube，创建播放列表等众多功能。
- The [Twilio API](https://www.twilio.com/), 其为您的app提供了针对语音通话和视频聊天的框架，以及从您的app发送短信息或多媒体信息等诸多功能。

### API的工作原理

- **API是基于对象的， API使用一个或多个 [JavaScript objects](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects) 在您的代码中进行交互，这些对象用作API使用的数据（包含在对象属性中）的容器以及API提供的功能（包含在对象方法中）。**
- **API有可识别的入口点（例如DOM的入口点是document，通过document.来调用各种对象）**。
- **API使用事件来处理状态的变化**
- **API再适当的地方有额外的安全机制**

## 操作文档

### web浏览器的重要部分

![img](https://mdn.mozillademos.org/files/14557/document-window-navigator.png)

- window是载入浏览器的标签，在JavaScript中用[`Window`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window)对象来表示，使用这个对象的可用方法，你可以返回窗口的大小（参见[`Window.innerWidth`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/innerWidth)和[`Window.innerHeight`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/innerHeight)），操作载入窗口的文档，存储客户端上文档的特殊数据（例如使用本地数据库或其他存储设备），为当前窗口绑定[event handler](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#a_series_of_fortunate_events)，等等。
- navigator表示浏览器存在于web上的状态和标识（即用户代理）。在JavaScript中，用[`Navigator`](https://developer.mozilla.org/zh-CN/docs/Web/API/Navigator)来表示。你可以用这个对象获取一些信息，比如来自用户摄像头的地理信息、用户偏爱的语言、多媒体流等等。
- document（在浏览器中用DOM表示）是载入窗口的实际页面，在JavaScript中用[`Document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document) 对象表示，你可以用这个对象来返回和操作文档中HTML和CSS上的信息。例如获取DOM中一个元素的引用，修改其文本内容，并应用新的样式，创建新的元素并添加为当前元素的子元素，甚至把他们一起删除。

## 文档对象模型

在浏览器标签中当前载入的文档用文档对象模型来表示。这是一个由浏览器生成的“树结构”，使编程语言可以很容易的访问HTML结构 —  例如浏览器自己在呈现页面时，使用它将样式和其他信息应用于正确的元素，而页面呈现完成以后，开发人员可以用JavaScript操作DOM。

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Simple DOM example</title>
  </head>
  <body>
      <section>
        <img src="dinosaur.png" alt="A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.">
        <p>Here we will add a link to the <a href="https://www.mozilla.org/">Mozilla homepage</a></p>
      </section>
  </body>
</html>

DOM树如下所示：

![img](https://mdn.mozillademos.org/files/14559/dom-screenshot.png)

这里你可以看到，文档中每个元素和文本在树中都有它们自己的入口 — 称之为**节点**。你将用不同的术语来描述节点的类型和它们相对于其他节点的位置：

- **元素节点**: 一个元素，存在于DOM中。
- **根节点**: 树中顶层节点，在HTML的情况下，总是一个`HTML`节点（其他标记词汇，如SVG和定制XML将有不同的根元素）。
- **子节点**: *直接*位于另一个节点内的节点。例如上面例子中，`IMG`是`SECTION`的子节点。
- **后代节点**: 位于另一个节点内*任意位置*的节点。例如 上面例子中，`IMG`是`SECTION`的子节点，也是一个后代节点。`IMG`不是`BODY`的子节点，因为它在树中低了`BODY`两级，但它是`BODY`的后代之一。
- **父节点**: 里面有另一个节点的节点。例如上面的例子中`BODY`是`SECTION`的父节点。
- **兄弟节点**: DOM树中位于同一等级的节点。例如上面例子中，`IMG`和`P`是兄弟。
- **文本节点**: 包含文字串的节点

在用DOM工作之前，熟悉这些术语是很有用的，因为你将会遇到大量代码术语的使用。你在研究CSS时也会遇到这些术语（例如后代选择器、子选择器）

#### 三种获取元素的方法

- [`Document.querySelector()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelector)是推荐的主流方法，它允许你使用CSS选择器选择元素，使用很方便。上面的`querySelector()`调用会匹配它在文档中遇到的第一个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a)元素。如果想对多个元素进行匹配和操作，你可以使用[`Document.querySelectorAll()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll)元素。如果想对多个元素进行匹配和操作，你可以使用[`Document.querySelectorAll()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll)元素。如果想对多个元素进行匹配和操作，你可以使用[`Document.querySelectorAll()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll)元素。如果想对多个元素进行匹配和操作，你可以使用[`Document.querySelectorAll()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll)，这个方法匹配文档中每个匹配选择器的元素，并把它们的引用存储在一个[array](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays)中。

- [`Document.getElementById()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementById)，选择一个`id`属性值已知的元素，例如`<p id="myId">My paragraph</p>`。ID作为参数传递给函数，即 `var elementRef = document.getElementById('myId')`。

- [`Document.getElementsByTagName()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementsByTagName)，返回页面中包含的所有已知类型元素的数组。如`<p>`s, `<a>`。元素类型作为参数传递给函数，即`var elementRefArray = document.getElementsByTagName('p')`.

**在较老的浏览器中使用这两种方法而不是流行的`querySelector()`方法，但这样并不方便。**

#### 两种通过javascript动态修改元素样式的方法

**1.利用对象的style属性添加内联样式**

```
para.style.color = 'white';
para.style.backgroundColor = 'black';
para.style.padding = '10px';
para.style.width = '250px';
para.style.textAlign = 'center';
```

**2.在样式表中设置调用的样式，通过改变元素的类来选中元素，修改样式**

先设置样式表

```
<style>
.highlight {
  color: white;
  background-color: black;
  padding: 10px;
  width: 250px;
  text-align: center;
}
</style>
```

现在我们改为使用HTML操作的常用方法 — [`Element.setAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/setAttribute) — 这里有两个参数，你想在元素上设置的属性，你要为它设置的值。在这种情况下，我们在段落中设置类名为highlight：  

```
para.setAttribute('class', 'highlight');
```

两种方式各有优缺点，选择哪种取决于你自己。第一种方式无需安装，适合简单应用，第二种方式更加正统（没有CSS和JavaScript的混合，没有内联样式，而这些被认为是不好的体验）。当你开始构建更大更具吸引力的应用时，你可能会更多地使用第二种方法，但这完全取决于你自己。

## 从服务器获取数据

### Browser-Server模型

最初加载页面很简单 -- 你为网站发送一个请求到服务器， 只要没有出错你将会获取资源并显示网页到你的电脑上。

![A basic representation of a web site architecture](https://mdn.mozillademos.org/files/6475/web-site-architechture@2x.png)

这个模型的问题是当你想更新网页的任何部分，例如显示一套新的产品或者加载一个新的页面，你需要再一次加载整个页面。这是非常浪费的并且导致了差的用户体验尤其是现在的页面越来越大且越来越复杂。

### [Ajax开始](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data#ajax开始)

这导致了创建允许网页请求小块数据（例如 [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), [XML](https://developer.mozilla.org/zh-CN/docs/Glossary/XML), [JSON](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON), 或纯文本) 和 仅在需要时显示它们的技术，从而帮助解决上述问题。

这是通过使用诸如 [`XMLHttpRequest`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest) 之类的API或者 — 最近以来的 [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) 来实现. 这些技术允许网页直接处理对服务器上可用的特定资源的 [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) 请求，并在显示之前根据需要对结果数据进行格式化。

**注意：在早期，这种通用技术被称为**Asynchronous JavaScript and XML**（Ajax），** 因为它倾向于使用[`XMLHttpRequest`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest) 来请求XML数据。 但通常不是这种情况 (你更有可能使用 `XMLHttpRequest` 或 Fetch 来请求JSON), 但结果仍然是一样的，术语“Ajax”仍然常用于描述这种技术。

![A simple modern architecture for web sites](https://mdn.mozillademos.org/files/6477/moderne-web-site-architechture@2x.png)

Ajax模型包括使用Web API作为代理来更智能地请求数据，而不仅仅是让浏览器重新加载整个页面。让我们来思考这个意义：

1. 去你最喜欢的信息丰富的网站之一，如亚马逊，油管，CNN等，并加载它。
2. 现在搜索一些东西，比如一个新产品。 主要内容将会改变，但大部分周围的信息，如页眉，页脚，导航菜单等都将保持不变。

这是一件非常好的事情，因为：

- 页面更新速度更快，您不必等待页面刷新，这意味着该网站体验感觉更快，响应更快。
- 每次更新都会下载更少的数据，这意味着更少地浪费带宽。在宽带连接的桌面上这可能不是一个大问题，但是在移动设备和发展中国家没有无处不在的快速互联网服务是一个大问题。

为了进一步提高速度，有些网站还会在首次请求时将资产和数据存储在用户的计算机上，这意味着在后续访问中，他们将使用本地版本，而不是在首次加载页面时下载新副本。 内容仅在更新后从服务器重新加载。

![A basic web app data flow architecture](https://mdn.mozillademos.org/files/6479/web-app-architecture@2x.png)

### [基本的Ajax请求](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data#基本的ajax请求)

让我们看看使用[`XMLHttpRequest`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest) 和 [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)如何处理这样的请求. 对于这些例子，我们将从几个不同的文本文件中请求数据，并使用它们来填充内容区域。

这一系列文件将作为我们的假数据库; 在真正的应用程序中，我们更可能使用服务器端语言（如PHP，Python或Node）从数据库请求我们的数据。 不过，我们要保持简单，并专注于客户端部分。

### [XMLHttpRequest](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data#xmlhttprequest)

`XMLHttpRequest` （通常缩写为XHR）现在是一个相当古老的技术 - 它是在20世纪90年代后期由微软发明的，并且已经在相当长的时间内跨浏览器进行了标准化。

1. 为例子做些准备, 将 [ajax-start.html](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/ajax-start.html) 和四个文本文件 — [verse1.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse1.txt), [verse2.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse2.txt), [verse3.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse3.txt), [verse4.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse4.txt) — 复制到你计算机上的一个新目录. 在这个例子中，我们将通过XHR在下拉菜单中选择一首诗（您可能会认识 — "如果谷歌翻译可以翻译的话"）加载另一首诗。

2. 在 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/script) 的内部, 添加下面的代码. 将 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select) 和 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/pre) 元素的引用存储到变量中, 并定义一个 [`onchange`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onchange) 事件处理函数，可以在select的值改变时， 将其值传递给 `updateDisplay()` 函数作为参数。 

   ```
   const verseChoose = document.querySelector('select');
   const poemDisplay = document.querySelector('pre');
   
   verseChoose.onchange = function() {
     const verse = verseChoose.value;
     updateDisplay(verse);
   };
   ```

定义 `updateDisplay()` 函数. 首先，将下面的代码块放在之前代码块的下面 - 这是函数的空壳：

```
function updateDisplay(verse) {

}
```

我们将通过构造一个 指向我们要加载的文本文件的相对URL 来启动我们的函数, 因为我们稍后需要它. 任何时候 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select) 元素的值都与所选的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option) 内的文本相同 (除非在值属性中指定了不同的值) — 例如 "Verse 1". 相应的诗歌文本文件是 "verse1.txt", 并与HTML文件位于同一目录中, 因此只需要文件名即可。

但是，Web服务器往往是区分大小写的，文件名没有空格。 要将“Verse 1”转换为“verse1.txt”，我们需要将V转换为小写，删除空格，并在末尾添加.txt。  这可以通过 [`replace()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace), [`toLowerCase()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase), 和 简单的 [string concatenation](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Strings#concatenating_strings) 来完成. 在 `updateDisplay()` 函数中添加以下代码:

```
verse = verse.replace(" ", "");
verse = verse.toLowerCase();
let url = verse + '.txt';
```

要开始创建XHR请求，您需要使用 [`XMLHttpRequest()`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/XMLHttpRequest) 的构造函数创建一个新的请求对象。 你可以把这个对象叫做你喜欢的任何东西, 但是我们会把它叫做 `request` 来保持简单. 在之前的代码中添加以下内容:

```
let request = new XMLHttpRequest();
```

接下来，您需要使用 [`open()`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/open) 方法来指定用于从网络请求资源的 [HTTP request method](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods) , 以及它的URL是什么。我们将在这里使用 `GET` 方法, 并将URL设置为我们的 `url` 变量. 在你上面的代码中添加以下代码:

```
request.open('GET', url);
```

接下来，我们将设置我们期待的响应类型 — 这是由请求的 [`responseType`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/responseType) 属性定义的 — 作为 `text`.  这并不是绝对必要的 — XHR默认返回文本 —但如果你想在以后获取其他类型的数据，养成这样的习惯是一个好习惯. 接下来添加:

```
request.responseType = 'text';
```

从网络获取资源是一个 [asynchronous](https://developer.mozilla.org/zh-CN/docs/Glossary/Asynchronous) "异步" 操作, 这意味着您必须等待该操作完成（例如，资源从网络返回），然后才能对该响应执行任何操作，否则会出错,将被抛出错误。 XHR允许你使用它的 `onload` 事件处理器来处理这个事件 — 当`onload` 事件触发时（当响应已经返回时）这个事件会被运行。 发生这种情况时， `response` 数据将在XHR请求对象的响应属性中可用。

在后面添加以下内容.  你会看到，在 `onload` 事件处理程序中，我们将 `poemDisplay` ( [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/pre) 元素 ) 的 `textContent` 设置为 [`request.response`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/response) 属性的值。

```
request.onload = function() {
  poemDisplay.textContent = request.response;
};
```

以上都是XHR请求的设置 — 在我们告诉它之前，它不会真正运行，这是通过 [`send()`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/send) 完成的. 在你之前的代码下添加以下内容完成该函数:

```
request.send();
```

这个例子中的一个问题就是它首次加载时不会显示任何诗。 为了解决这个问题，在代码的底部添加以下两行 (正好在关闭的 `</script>` 标签之上) 默认加载第1节，并确保 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select) 元素始终显示正确的值：

```
updateDisplay('Verse 1');
verseChoose.value = 'Verse 1';
```

### [xmlhttprequest的readystate属性的五个状态](https://www.cnblogs.com/jerry01/archive/2009/09/03/1559624.html)             

  **昨天做了一个利用ajax实现页面无刷新的从服务器端获得时间的例子，当时对于xmlhttprequest对象的readystate的后三个状态不是很清楚，想了半天，也不明白！后面在程序的不同地方中用alert(xmlhttp.readystate)查看readystate值的变化，并且请教朋友之后，才弄明白其中的几个问题：创建xmlhttprequest对象之后没有调用open之前readystate值为0，调用open()之后就变为1了，并且此时onreadystatechange函数与open()几乎是同时执行的。在之后调用send方法之后，在startHttpRequest函数中readystate值仍为1，而调用send方法之后应该有2，3，4三个状态，而只有在startHttpRequest函数用alert语句才可以观察到3个值！这是为什么呢?这是因为在startHttpRequest函数中当解析到send这一句时，并没有真正开始执行send执行。只有send执行，才可以在onreadystatechange函数观察到状态值的变化。readystate不是发送的状态，它是准备发送的状态，要把它想像成“人间大炮一级准备、二级准备、放”这样的口号，不是请求发送本身。同时xmlhttp也不是监听服务器信息，它是在send的时候获取服务器返回的状态信息而已，只有一次，监听则是一直在观察状态。至此，心中的疑惑全部解开！**

 **关于readystate五个状态总结如下：**  

**readyState 状态  状态说明
(0)未初始化
此阶段确认XMLHttpRequest对象是否创建，并为调用open()方法进行未初始化作好准备。值为0表示对象已经存在，否则浏览器会报错－－对象不存在。
(1)载入
此阶段对XMLHttpRequest对象进行初始化，即调用open()方法，根据参数(method,url,true)完成对象状态的设置。并调用send()方法开始向服务端发送请求。值为1表示正在向服务端发送请求。
(2)载入完成
此阶段接收服务器端的响应数据。但获得的还只是服务端响应的原始数据，并不能直接在客户端使用。值为2表示已经接收完全部响应数据。并为下一阶段对数据解析作好准备。
(3)交互
此阶段解析接收到的服务器端响应数据。即根据服务器端响应头部返回的MIME类型把数据转换成能通过responseBody、responseText或responseXML属性存取的格式，为在客户端调用作好准备。状态3表示正在解析数据。
(4)完成
此阶段确认全部数据都已经解析为客户端可用的格式，解析已经完成。值为4表示数据解析完毕，可以通过XMLHttpRequest对象的相应属性取得数据。
概而括之，整个XMLHttpRequest对象的生命周期应该包含如下阶段：
创建－初始化请求－发送请求－接收数据－解析数据－完成**

### xmlhttprequest的status值与状态

status状态值 
 长整形标准http状态码，定义如下： Number Description  
 100 Continue 
 101 Switching protocols 
 200 OK 
 201 Created 
 202 Accepted 
 203 Non-Authoritative Information 
 204 No Content 
 205 Reset Content 
 206 Partial Content 
 300 Multiple Choices 
 301 Moved Permanently 
 302 Found 
 303 See Other 
 304 Not Modified 
 305 Use Proxy 
 307 Temporary Redirect 
 400 Bad Request 
 401 Unauthorized 
 402 Payment Required 
 403 Forbidden 
 404 Not Found 
 405 Method Not Allowed 
 406 Not Acceptable 
 407 Proxy Authentication Required 
 408 Request Timeout 
 409 Conflict 
 410 Gone 
 411 Length Required 
 412 Precondition Failed 
 413 Request Entity Too Large 
 414 Request-URI Too Long 
 415 Unsupported Media Type 
 416 Requested Range Not Suitable 
 417 Expectation Failed 
 500 Internal Server Error 
 501 Not Implemented 
 502 Bad Gateway 
 503 Service Unavailable 
 504 Gateway Timeout 
 505 HTTP Version Not Supported 

 readyState的状态值 
 0 (未初始化) 对象已建立，但是尚未初始化（尚未调用open方法） 
 1 (初始化) 对象已建立，尚未调用send方法 
 2 (发送数据) send方法已调用，但是当前的状态及http头未知 
 3 (数据传送中) 已接收部分数据，因为响应及http头不全，这时通过responseBody和responseText获取部分数据会出现错误， 
 4 (完成) 数据接收完毕,此时可以通过通过responseBody和responseText获取完整的回应数据

https://baitianli2007.iteye.com/blog/774786

### [在server端运行例子](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data#在server端运行例子)

如果只是从本地文件运行示例，一些浏览器(包括Chrome)将不会运行XHR请求。这是因为安全限制(更多关于web安全性的限制，请参阅[Website security](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security))。

为了解决这个问题，我们需要通过在本地web服务器上运行它来测试这个示例。要了解如何实现这一点，请阅读[How do you set up a local testing server?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/set_up_a_local_testing_server)

### [Fetch](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data#fetch)

Fetch API基本上是XHR的一个现代替代品——它是最近在浏览器中引入的，它使异步HTTP请求在JavaScript中更容易实现，对于开发人员和在Fetch之上构建的其他API来说都是如此。

让我们将最后一个示例转换为使用Fetch !

1. 复制您之前完成的示例目录. (如果您没有通过以前的练习，创建一个新的目录。, 然后复制 [xhr-basic.html](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/xhr-basic.html)和这四个文件 — [verse1.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse1.txt), [verse2.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse2.txt), [verse3.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse3.txt), and [verse4.txt](https://github.com/mdn/learning-area/blob/master/javascript/apis/fetching-data/verse4.txt).)

2. 在 `updateDisplay()` 里找到 XHR 那段代码:

   ```
   let request = new XMLHttpRequest();
   request.open('GET', url);
   request.responseType = 'text';
   
   request.onload = function() {
     poemDisplay.textContent = request.response;
   };
   
   request.send();
   ```

像这样替换掉所有关于XHR的代码:

```
fetch(url).then(function(response) {
  response.text().then(function(text) {
    poemDisplay.textContent = text;
  });
});
```

1. 在浏览器中加载示例(通过web服务器运行)，它应该与XHR版本相同，前提是您运行的是一个现代浏览器。

### 那么Fetch代码中发生了什么呢?

首先，我们调用了`fetch()`方法，将我们要获取的资源的URL传递给它。这相当于现代版的XHR中的`request.open()`,另外，您不需要任何等效的`send()`方法。

然后，你可以看到`.then()`方法连接到了`fetch()`末尾-这个方法是[`Promises`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)的一部分，是一个用于执行异步操作的现代JavaScript特性。`fetch()`返回一个promise，它将解析从服务器发回的响应。我们使用`then()`来运行一些后续代码，这是我们在其内部定义的函数。这相当于XHR版本中的`onload`事件处理程序。

当`fetch()` promise 解析时，这个函数会自动将响应从服务器传递给参数。在函数内部，我们获取响应并运行其`text()`方法。这基本上将响应作为原始文本返回，这相当于在XHR版本中的`responseType = 'text'`。

你会看到 `text()` 也返回了一个 promise, 所以我们连接另外一个 `.then()` 到它上面, 在其中我们定义了一个函数来接收 `text()` promise解析的生文本。

在promise的函数内部，我们做的和在XHR版本中差不多— 设置 [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre) 元素的文本内容为text的值。

### [关于promises ](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data#关于promises)

当你第一次见到它们的时候，promises会让你有点困惑，但现在不要太担心这个。在一段时间之后，您将会习惯它们，特别是当您了解更多关于现代JavaScript api的时候——大多数现代的JavaScript api都是基于promises的。

让我们再看看上面的promises结构，看看我们是否能更清楚地理解它:

```
fetch(url).then(function(response) {
  response.text().then(function(text) {
    poemDisplay.textContent = text;
  });
});
```

第一行是说‘’获取位于url里的资源(`fetch(url)`)‘’和“然后当promise解析后运行指定的函数(`.then(function() { ... })`)”。"解析"的意思是"在将来某一时刻完成指定的操作"。在本例中，指定的操作是从指定的URL(使用HTTP请求)获取资源，并返回对我们执行某些操作的响应。

实际上，传递给 `then()` 是一段不会立即执行的代码 — 而是当返回响应时代码会被运行。注意，你还可以选择把你的 promise 保存到一个变量里, 链接 [`.then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) 在相同的位置。下面的代码会做相同的事情。

```
let myFetch = fetch(url);

myFetch.then(function(response) {
  response.text().then(function(text) {
    poemDisplay.textContent = text;
  });
});
```

因为方法 fetch() 返回一个解析HTTP响应的promise, 你在 .then()  中定义的任何函数会被自动给与一个响应作为一个参数。你可以给这个参数取任何名字，以下的例子依然可以实现：（例子里把response参数叫做狗饼干---'dogBiscuits'=狗饼干）

```
fetch(url).then(function(dogBiscuits) {
  dogBiscuits.text().then(function(text) {
    poemDisplay.textContent = text;
  });
});
```

但是把参数叫做描述其内容的名字更有意义。

现在让我们来单独看一下函数：

```
function(response) {
  response.text().then(function(text) {
    poemDisplay.textContent = text;
  });
}
```

response 对象有个 [`text()`](https://developer.mozilla.org/en-US/docs/Web/API/Body/text)方法, 获取响应主体中的原始数据a并把它转换成纯文本, 那是我们想要的格式。它也返回一个promise (解析结果文本字符串), 所以这里我们再使用 [`.then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then), 在里面我们再定义一个操作文本字符串的函数。我们设置诗歌的 [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre) 元素的 `textContent` 属性和这个文本字符串相同, 这样就非常简单地解决了。

值得注意的是你可以直接将promise块 (`.then()`块, 但也有其他类型) 链接到另一个的尾部, 顺着链条将每个块的结果传到下一个块。 这使得promises非常强大。

下面的代码块和我们原始的例子做的是相同的事, 但它是不同的写法:

```
fetch(url).then(function(response) {
  return response.text()
}).then(function(text) {
  poemDisplay.textContent = text;
});
```

很多开发者更喜欢这种样式, 因为它更扁平并且按理说对于更长的promise链它更容易读 — 每一个promise(承诺）接续上一个promise，而不是在上一个promise的里面(会使得整个代码笨重起来，难以理解）。以上两种写法还有一个不同的地方是我们在`response.text()` 语句之前得包含一个 `return` 语句, 用来把这一部分的结果传向promise链的下一段。

### [你应该用哪种方法呢?](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Fetching_data#你应该用哪种方法呢)

   这完全取决于你正在干的项目是啥样。XHR已经面世非常之久，现在已经有了相当棒的跨浏览器支持。然而对于网页平台来说，Fetch和Promise是新近的产物，除了IE和Safari浏览器不支持，别的浏览器大多提供了支持。（现在Safari也即将为fetch和promise提供支持）。

 如果你的项目需要支持年代久远的浏览器，那么使用XHR可能会更爽一些。如果你的项目比较激进而且你根本不管老版的浏览器吃不吃这套，那就选择Fetch吧老铁。

 话说回来，咱倒真应该两者都学学——因为使用IE浏览器的人们在变少，Fetch会变得越来越流行（事实上IE已经没人管了，因为微软Edge浏览器的受宠），但在所有浏览器彻底支持Fetch之前，你可能还得和XHR纠缠一阵子。

## 第三方API

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Third_party_APIs

## 绘图

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Drawing_graphics

## 视频和音频API

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs

## 客户端存储

其他的MDN学习中我们已经讨论过 静态网站（[static sites](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Client-Server_overview#static_sites)） 和动态网站（ [dynamic sites](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Client-Server_overview#dynamic_sites)）的区别。 大多数现代的web站点是动态的— 它们在服务端使用各种类型的数据库来存储数据(服务端存储), 之后通过运行服务端（ [server-side](https://developer.mozilla.org/en-US/docs/Learn/Server-side)） 代码来重新获取需要的数据，把其数据插入到静态页面的模板中，并且生成出HTML渲染到用户浏览上。

客户端存储以相同的原理工作，但是在使用上有一些不同。它是由 JavaScript APIs 组成的因此允许你在客户端存储数据 (比如在用户的机器上)，而且可以在需要的时候重新取得需要的数据。这有很多明显的用处，比如：

- 个性化网站偏好（比如显示一个用户选择的窗口小部件，颜色主题，或者字体）。
- 保存之前的站点行为 (比如从先前的session中获取购物车中的内容， 记住用户是否之前已经登陆过)。
- 本地化保存数据和静态资源可以使一个站点更快（至少让资源变少）的下载， 甚至可以在网络失去链接的时候变得暂时可用。
- 保存web已经生产的文档可以在离线状态下访问。

通常客户端和服务端存储是结合在一起使用的。例如，你可以从数据库中下载一个由网络游戏或音乐播放器应用程序使用的音乐文件，将它们存储在客户端数据库中，并按需要播放它们。用户只需下载音乐文件一次——在随后的访问中，它们将从数据库中检索。

**注意：**使用客户端存储 API 可以存储的数据量是有限的（可能是每个API单独的和累积的总量）;具体的数量限制取决于浏览器，也可能基于用户设置。有关更多信息，获取更多信息，请参考[浏览器存储限制和清理标准](https://developer.mozilla.org/zh-CN/docs/Web/API/IndexedDB_API/Browser_storage_limits_and_eviction_criteria)。

### 传统方法cookie

使用简单，不作过多分析。

### 新方法Web Storage、IndexedDB

- [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) 提供了一种非常简单的语法，用于存储和检索较小的、由名称和相应值组成的数据项。当您只需要存储一些简单的数据时，比如用户的名字，用户是否登录，屏幕背景使用了什么颜色等等，这是非常有用的。
- [IndexedDB API](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) 为浏览器提供了一个完整的数据库系统来存储复杂的数据。这可以用于存储从完整的用户记录到甚至是复杂的数据类型，如音频或视频文件。

### 未来Cache API

一些现代浏览器支持新的 [`Cache`](https://developer.mozilla.org/zh-CN/docs/Web/API/Cache) API。这个API是为存储特定HTTP请求的响应文件而设计的，它对于像存储离线网站文件这样的事情非常有用，这样网站就可以在没有网络连接的情况下使用。缓存通常与 [Service Worker API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API) 组合使用，尽管不一定非要这么做。
 Cache 和 Service Workers 的使用是一个高级主题，我们不会在本文中详细讨论它，尽管我们将在下面的 [离线文件存储](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Client-side_storage#离线文件存储) 一节中展示一个简单的例子。

https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/Client-side_web_APIs/Client-side_storage

# Web表单核心

## [HTML表单](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Your_first_form#html表单是什么？)概览

HTML表单是用户和web站点或应用程序之间交互的主要内容之一。它们允许用户将数据发送到web站点。大多数情况下，数据被发送到web服务器，但是web页面也可以自己拦截它并使用它。

HTML表单是由一个或多个小部件组成的。这些小部件可以是文本字段(单行或多行)、选择框、按钮、复选框或单选按钮。大多数情况下，这些小部件与描述其目的的标签配对——正确实现的标签能够清楚地指示视力正常的用户和盲人用户输入表单所需的内容。

HTML表单和常规HTML文档的主要区别在于，大多数情况下，表单收集的数据被发送到web服务器。在这种情况下，您需要设置一个web服务器来接收和处理数据。如何设置这样的服务器超出了本文的范围，但是如果您想了解更多，请参阅模块后面的[发送表单数据](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data)。

### [设计表单](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Your_first_form#设计表单)

在开始编写代码之前，最好先退一步，花点时间考虑一下您的表单。设计一个快速的模型将帮助您定义您想要询问用户的正确的数据集。从用户体验(UX)的角度来看，要记住：表单越大，失去用户的风险就越大。保持简单，保持专注:只要求必要的数据。在构建站点或应用程序时，设计表单是非常重要的一步。这超出了本文的范围，涵盖了表单的用户体验，但是如果您想深入了解这个主题，您应该阅读下面的文章:

- 杂志<Smashing Magazine>中有[很好的关于表单用户体验的文章](http://uxdesign.smashingmagazine.com/tag/forms/)，或许其中最重要的应该是他们的[Extensive Guide To Web Form Usability](http://uxdesign.smashingmagazine.com/2011/11/08/extensive-guide-web-form-usability/).
- UXMatters 也是一个非常有思想的资源，从基本的[最佳实践](http://www.uxmatters.com/mt/archives/2012/05/7-basic-best-practices-for-buttons.php)到复杂的问题如[多页表单](https://www.uxmatters.com/mt/archives/2010/03/pagination-in-web-forms-evaluating-the-effectiveness-of-web-forms.php)，都有很好的建议。

在本文中，我们将构建一个简单的联系人表单。让我们做一个粗略的草图。

我们的表单将包含三个文本字段和一个按钮。我们向用户询问他们的姓名、电子邮件和他们想要发送的信息。点击这个按钮将把他们的数据发送到一个web服务器。

### [主动学习:使用HTML实现我们的表单](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Your_first_form#主动学习使用html实现我们的表单)

好了，现在我们准备进入HTML代码并对表单进行编码。为了构建我们的联系人表单，我们将使用以下HTML元素:<form>,<label>,<input>,<textare>,and <button>.

在进一步讨论之前，先创建一个[简单HTML模板](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/getting-started/index.html)的本地副本—您将在这里输入您的表单HTML。

### form 元素

所有HTML表单都以一个<form>元素开始：

```
<form action="/my-handling-form-page" method="post">

</form>
```

这个元素正式定义了一个表单。就像div or p元素，它是一个容器元素，但它也支持一些特定的属性来配置表单的行为方式。它的所有属性都是可选的，但实践中最好至少要设置`action`属性和`method`属性。

- `action` 属性定义了在提交表单时,应该把所收集的数据送给谁(/那个模块)(URL)去处理。.
-  `method` 属性定义了发送数据的HTTP方法(它可以是“get”或“post”).

**注意:**如果您想深入了解这些属性是如何工作的，那么将在[发送表单数据](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Forms/Sending_and_retrieving_form_data)文章中详细说明。

现在，将上面的from元素添加到您的HTML主体中

### \<label>,\<input>和\<textarea>元素

我们的联系人表单非常简单，包含三个文本字段，每个字段都有一个标签。该名称的输入字段将是一个基本的单行文本字段，电子邮件的输入字段将是一个只接受电子邮件地址的单行文本字段，而消息的输入字段将是一个基本的多行文本字段。

就HTML代码而言，我们需要如下的东西来实现这些表单小部件：

```
<form action="/my-handling-form-page" method="post">
  <div>
    <label for="name">Name:</label>
    <input type="text" id="name">
  </div>
  <div>
    <label for="mail">E-mail:</label>
    <input type="email" id="mail">
  </div>
  <div>
    <label for="msg">Message:</label>
    <textarea id="msg"></textarea>
  </div>
</form>
```

更新您的表单代码，使其看起来像上面的代码。

使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/div) 元素可以使我们更加方便地构造我们自己的代码，并且更容易样式化(参见本文后面的文章)。注意在所有[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label) 元素可以使我们更加方便地构造我们自己的代码，并且更容易样式化(参见本文后面的文章)。注意在所有[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label) 元素可以使我们更加方便地构造我们自己的代码，并且更容易样式化(参见本文后面的文章)。注意在所有[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label) 元素可以使我们更加方便地构造我们自己的代码，并且更容易样式化(参见本文后面的文章)。注意在所有[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label) 元素可以使我们更加方便地构造我们自己的代码，并且更容易样式化(参见本文后面的文章)。注意在所有[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)元素上使用`for`属性；它是将标签链接到表单小部件的一种正规方式。这个属性引用对应的小部件的`id`。这样做有一些好处。最明显的一个好处是允许用户单击标签以激活相应的小部件。如果您想更好地理解这个属性的其他好处，您可以找到[如何构造HTML表单的详细信息](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/How_to_structure_an_HTML_form)。

在 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素中，最重要的属性是`type` 属性。这个属性非常重要，因为它定义了[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)属性的行为方式。它可以从根本上改变元素，所以要注意它。稍后您将在[原生表单控件](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Forms/The_native_form_widgets)文章中找到更多关于此的内容。

- 在我们的简单示例中，我们使用值 `text` 作为第一个输入——这个属性的默认值。它表示一个基本的单行文本字段，接受任何类型的文本输入。
- 对于第二个输入，我们使用值`email`，它定义了一个只接受格式正确的电子邮件地址的单行文本字段。这会将一个基本的文本字段转换为一种“智能”字段，该字段将对用户输入的数据进行一些检查。在稍后的表单数据验证文章中，您将了解到更多关于[表单验证](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Forms/Data_form_validation)的信息。

最后但同样重要的是，要注意`<input>` 和 `<textarea></textarea>`的语法。这是HTML的一个奇怪之处。 `<input>` 标签是一个空元素，这意味着它不需要关闭标签。相反， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)不是一个空元素，因此必须使用适当的结束标记来关闭它。这对HTML表单的特定特性有影响:定义默认值的方式。要定义[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)的默认值，你必须使用`value` 属性，如下所示：

```
<input type="text" value="by default this element is filled with this text" />
```

相反，如果您想定义[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)的默认值，您只需在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)元素的开始和结束标记之间放置默认值，就像这样:

```
<textarea>by default this element is filled with this text</textarea>
```

### button 元素

我们的表格已经快准备好了，我们只需要再添加一个按钮，让用户在填写完表单后发送他们的数据。这是通过使用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button) 元素完成的。在 `</form>这个结束`标签上方添加以下内容：

```
<div class="button">
  <button type="submit">Send your message</button>
</div>
```

您会看到[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素也接受一个 `type`属性，它接受`submit`, `reset`或者 `button` 三个值中的任一个。

- 单击 `type` 属性定义为 `submit` 值(也是默认值)的按钮会发送表单的数据到[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)元素的`action` 属性所定义的网页。
- 单击 `type` 属性定义为 `reset` 值的按钮 将所有表单小部件重新设置为它们的默认值。从用户体验的角度来看，这被认为是一种糟糕的做法。
- 单击 `type` 属性定义为 `button` 值的按钮……不会发生任何事！这听起来很傻，但是用JavaScript构建定制按钮非常有用。 

**注意：**您还可以使用相应类型的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素来生成一个按钮，如 `<input type="submit">`。[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素的主要优点是， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素只允许纯文本作为其标签，而[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素允许完整的HTML内容，允许更复杂、更有创意的按钮文本。

### [基本表单样式](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Your_first_form#基本表单样式)

现在您已经完成了表单的HTML代码，尝试保存它并在浏览器中查看它。
 现在，你会看到它看起来很丑。

![img](https://developer.mozilla.org/files/4049/form-no-style.png)

**注意：** 如果你怀疑你的HTML代码不对，试着把它和我们完成的例子进行比较 —— [first-form.html](https://github.com/mdn/learning-area/blob/master/html/forms/your-first-HTML-form/first-form.html) (你也可以观看[预览版](https://mdn.github.io/learning-area/html/forms/your-first-HTML-form/first-form.html))。

如何排布好表单是公认的难点。这超出了本文的讨论范围，所以现在我们只需要让您添加一些CSS来让它看起来很好。

首先，在您的HTML头部中添加一个 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/style)元素。应该是这样的：

```
<style>

</style>
```

在样式标签中，添加如下的CSS，如下所示:

```
form {
  /* 居中表单 */
  margin: 0 auto;
  width: 400px;
  /* 显示表单的轮廓 */
  padding: 1em;
  border: 1px solid #CCC;
  border-radius: 1em;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

form li + li {
  margin-top: 1em;
}

label {
  /* 确保所有label大小相同并正确对齐 */
  display: inline-block;
  width: 90px;
  text-align: right;
}

input, textarea {
  /* 确保所有文本输入框字体相同
     textarea默认是等宽字体 */
  font: 1em sans-serif;

  /* 使所有文本输入框大小相同 */
  width: 300px;
  box-sizing: border-box;

  /* 调整文本输入框的边框样式 */
  border: 1px solid #999;
}

input:focus, textarea:focus {
  /* 给激活的元素一点高亮效果 */
  border-color: #000;
}

textarea {
  /* 使多行文本输入框和它们的label正确对齐 */
  vertical-align: top;

  /* 给文本留下足够的空间 */
  height: 5em;
}

.button {
  /* 把按钮放到和文本输入框一样的位置 */
  padding-left: 90px; /* 和label的大小一样 */
}

button {
  /* 这个外边距的大小与label和文本输入框之间的间距差不多 */
  margin-left: .5em;
}
```

现在，它看起来没那么丑了。

![img](https://developer.mozilla.org/files/4051/form-style.png)

**注意**: 你可以在GitHub上的这里找到它 [first-form-styled.html](https://github.com/mdn/learning-area/blob/master/html/forms/your-first-HTML-form/first-form-styled.html) ([也可以在这儿看运行结果](https://mdn.github.io/learning-area/html/forms/your-first-HTML-form/first-form-styled.html)).

### [向您的web服务器发送表单数据](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Your_first_form#向您的web服务器发送表单数据)

最后一部分，也许是最棘手的部分，是在服务器端处理表单数据。如前所述，大多数时候HTML表单是向用户请求数据并将其发送到web服务器的一种方便的方式。

[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form) 元素将定义如何通过`action` 属性和 `method`属性来发送数据的位置和方式。

但这还不够。我们还需要为我们的数据提供一个名称。这些名字对双方都很重要：在浏览器端，它告诉浏览器给数据各自哪个名称，在服务器端，它允许服务器按名称处理每个数据块。

要将数据命名为表单，您需要在每个表单小部件上使用 `name` 属性来收集特定的数据块。让我们再来看看我们的表单代码:

```
<form action="/my-handling-form-page" method="post">
  <div>
    <label for="name">Name:</label>
    <input type="text" id="name" name="user_name">
  </div>
  <div>
    <label for="mail">E-mail:</label>
    <input type="email" id="mail" name="user_email">
  </div>
  <div>
    <label for="msg">Message:</label>
    <textarea id="msg" name="user_message"></textarea>
  </div>

  ...
```

在我们的例子中，表单会发送三个已命名的数据块 "`user_name`", "`user_email`", 和 "`user_message`"。这些数据将用使用[HTTP `POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) 方法,把信息发送到URL为 "`/my-handling-form-page`"目录下。

在服务器端，位于URL"`/my-handling-form-page`"  上的脚本将接收的数据作为HTTP请求中包含的3个键/值项的列表。这个脚本处理这些数据的方式取决于您。每个服务器端语言(PHP、Python、Ruby、Java、c等等)都有自己的机制。深入到这个主题已经超出了本指南的范围，但是如果您想了解更多，我们已经在[发送表单数据](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data)文章中提供了一些示例。 

## 如何构造HTML表单

HTML表单的灵活性使它们成为HTML中最复杂的结构之一;您可以使用专用的表单元素和属性构建任何类型的基本表单。在构建HTML表单时使用正确的结构将有助于确保表单可用性和可访问性。

###  \<form>元素

 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form) 元素按照一定的格式定义了表单和确定表单行为的属性。当您想要创建一个HTML表单时，都必须从这个元素开始，然后把所有内容都放在里面。许多辅助技术或浏览器插件可以发现[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)元素并实现特殊的钩子，使它们更易于使用。 

我们早在之前的文章中就遇见过它了。

**注意:** 严格禁止在一个表单内嵌套另一个表单。嵌套会使表单的行为不可预知，而这取决于正在使用的浏览器。

请注意，在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)元素之外使用表单小部件是可以的，但是如果您这样做了，那么表单小部件与任何表单都没有任何关系。这样的小部件可以在表单之外使用，但是您应该对于这些小部件有特别的计划，因为它们自己什么也不做。您将不得不使用JavaScript定制他们的行为。

**注意**: HTML5在HTML表单元素中引入`form`属性。它让您显式地将元素与表单绑定在一起，即使元素不在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)中。不幸的是，就目前而言，跨浏览器对这个特性的实现还不足以使用。

###  \<fieldset>元素和 \<legend>元素

[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)元素是一种方便的用于创建具有相同目的的小部件组的方式，出于样式和语义目的。 你可以在`<fieldset>`开口标签后加上一个 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)元素来给[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset) 标上标签。 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)的文本内容正式地描述了[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)里所含有部件的用途。

许多辅助技术将使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend) 元素，就好像它是相应的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset) 元素里每个部件的标签的一部分。例如，在说出每个小部件的标签之前，像[Jaws](http://www.freedomscientific.com/products/fs/jaws-product-page.asp)或[NVDA](http://www.nvda-project.org/)这样的屏幕阅读器会朗读出legend的内容。

这里有一个小例子:

```
<form>
  <fieldset>
    <legend>Fruit juice size</legend>
    <p>
      <input type="radio" name="size" id="size_1" value="small">
      <label for="size_1">Small</label>
    </p>
    <p>
      <input type="radio" name="size" id="size_2" value="medium">
      <label for="size_2">Medium</label>
    </p>
    <p>
      <input type="radio" name="size" id="size_3" value="large">
      <label for="size_3">Large</label>
    </p>
  </fieldset>
</form>
```

**注意**: 你可以在 [fieldset-legend.html](https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/fieldset-legend.html) (你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/html-form-structure/fieldset-legend.html)) 看到该例。

当阅读上述表格时，屏幕阅读器将会读第一个小部件“Fruit juice size small”，“Fruit juice size medium”为第二个，“Fruit juice size large”为第三个。

本例中的用例是最重要的。每当您有一组单选按钮时，您应该将它们嵌套在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)元素中。还有其他用例，一般来说，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)元素也可以用来对表单进行分段。理想情况下，长表单应该在拆分为多个页面，但是如果表单很长，却必须在单个页面上，那么将以不同的关联关系划分的分段，分别放在不同的fieldset里，可以提高可用性。

因为它对辅助技术的影响， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset) 元素是构建可访问表单的关键元素之一。无论如何，你有责任不去滥用它。如果可能，每次构建表单时，尝试侦听[屏幕阅读器](https://www.nvaccess.org/download/)如何解释它。如果听起来很奇怪，试着改进表单结构。

### \<label>元素

正如我们在前一篇文章中看到的， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label) 元素是为HTML表单小部件定义标签的正式方法。如果你想构建可访问的表单，这是最重要的元素——当实现的恰当时，屏幕阅读器会连同有关的说明和表单元素的标签一起朗读。以我们在上一篇文章中看到的例子为例:

```
<label for="name">Name:</label> <input type="text" id="name" name="user_name">
```

`<label>` 标签与 `<input>` 通过他们各自的`for` 属性和 `id` 属性正确相关联（label的for属性和它对应的小部件的id属性），这样，屏幕阅读器会读出诸如“Name, edit text”之类的东西。

如果标签没有正确设置，屏幕阅读器只会读出“Edit text blank”之类的东西，这样会没什么帮助。

注意，一个小部件可以嵌套在它的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)元素中，就像这样：

```
<label for="name">
  Name: <input type="text" id="name" name="user_name">
</label>
```

尽管可以这样做，但人们认为设置`for`属性才是最好的做法，因为一些辅助技术不理解标签和小部件之间的隐式关系。

### [标签也可点击!](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/How_to_structure_a_web_form#标签也可点击!)

正确设置标签的另一个好处是可以在所有浏览器中单击标签来激活相应的小部件。这对于像文本输入这样的例子很有用，这样你可以通过点击标签，和点击输入区效果一样，来聚焦于它，这对于单选按钮和复选框尤其有用——这种控件的可点击区域可能非常小，设置标签来使它们可点击区域变大是非常有用的。

举个例子：

```
<form>
  <p>
    <label for="taste_1">I like cherry</label>
    <input type="checkbox" id="taste_1" name="taste_cherry" value="1">
  </p>
  <p>
    <label for="taste_2">I like banana</label>
    <input type="checkbox" id="taste_2" name="taste_banana" value="2">
  </p>
</form>
```

**注意**: 你可以在 [checkbox-label.html](https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/checkbox-label.html) (你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/html-form-structure/checkbox-label.html)) 看到该例。

### [多个标签](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/How_to_structure_a_web_form#多个标签)

严格地说，您可以在一个小部件上放置多个标签，但是这不是一个好主意，因为一些辅助技术可能难以处理它们。在多个标签的情况下，您应该将一个小部件和它的标签嵌套在一个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)元素中。

让我们考虑下面这个例子：

```
<p>Required fields are followed by <abbr title="required">*</abbr>.</p>

<!--这样写：-->
<div>
  <label for="username">Name:</label>
  <input type="text" name="username">
  <label for="username"><abbr title="required">*</abbr></label>
</div>

<!--但是这样写会更好：-->
<div>
  <label for="username">
    <span>Name:</span>
    <input id="username" type="text" name="username">
    <abbr title="required">*</abbr>
  </label>
</div>

<!--但最好的可能是这样：-->
<div>
  <label for="username">Name: <abbr title="required">*</abbr></label>
  <input id="username" type="text" name="username">
</div>
```

顶部的段落定义了所需元素的规则。它必须在开始时确保像屏幕阅读器这样的辅助技术在用户找到必需的元素之前显示或念出它们。这样，他们就知道星号表达的是什么意思了。根据屏幕阅读器的设置，屏幕阅读器会把星号读为“star”或“required”，取决于屏幕阅读器的设置——不管怎样，要念出来的都会在第一段清楚的呈现出来。

- 在第一个例子中，标签根本没有和`input`一起被念出来——读出来的只是“edit the blank”，和单独被念出的标签。多个`<label>`元素会使屏幕阅读器迷惑。
- 在第二个例子中，事情变得清晰一点了——标签和输入一起，读出的是“name star name edit text”，但标签仍然是单独读出的。这还是有点令人困惑，但这次还是稍微好一点了，因为`input`和`label`联系起来了。
- 第三个例子是最好的——标签是一起读出的，标签和输入读出的是“name star edit text”。

**注意**：你可能会得到一些不同的结果，这取决于你的屏幕阅读器。这是在VoiceOver上测试的（NVDA的行为也类似）。我们也乐于听听你的试验结果。

**注意**: 你可以在 GitHub 上看到 [required-labels.html](https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/required-labels.html) (你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/html-form-structure/required-labels.html))。不要运行2个或3个未注释版本的示例—— 如果您有多个标签和多个输入相同的ID，那么屏幕阅读器肯定会感到困惑！

## [用于表单的通用HTML结构](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/How_to_structure_a_web_form#用于表单的通用html结构)

除了特定于HTML表单的结构之外，还应该记住表单同样是HTML。这意味着您可以使用HTML的所有强大功能来构造一个HTML表单。

正如您在示例中可以看到的，用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/div)元素包装标签和它的小部件是很常见的做法。[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p)元素也经常被使用，HTML列表也是如此（后者在构造多个复选框或单选按钮时最为常见）。

除了[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)元素之外，使用HTML标题（例如，[ (en-US)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)、[ (en-US)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)）和分段（如[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/section)）来构造一个复杂的表单也是一种常见的做法。

最重要的是，你要找到一种你觉得很舒服的风格去码代码，而且它也能带来可访问的、可用的形式。

它包含了从功能上划分开并分别包含在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/section)元素中的部分，以及一个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)来包含单选按钮。

### [自主学习:构建一个表单结构](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/How_to_structure_a_web_form#自主学习构建一个表单结构)

让我们把这些想法付诸实践，建立一个稍微复杂一点的表单结构——一个支付表单。这个表单将包含许多您可能还不了解的小部件类型—现在不要担心这个；在下一篇文章（[原生表单小部件](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/The_native_form_widgets)）中，您将了解它们是如何工作的。现在，当您遵循下面的指令时，请仔细阅读这些描述，并开始理解我们使用的包装器元素是如何构造表单的，以及为什么这么做。

1. 在开始之前，在计算机上的一个新目录中，创建一个[空白模板文件](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/getting-started/index.html)和[我们的支付表单的CSS样式](https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/payment-form.css)的本地副本。

2. 首先，通过添加下面这行代码到你的HTML

   `<head>`

   使你的HTML应用CSS。  

   ```
   <link href="payment-form.css" rel="stylesheet">
   ```

接下来，通过添加外部[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)元素来开始一张表单：  

```
<form>

</form>
```

在 `<form>` 标签内，以添加一个标题和段落开始，告诉用户必需的字段是如何标记的:  

```
<h1>Payment form</h1>
<p>Required fields are followed by <strong><abbr title="required">*</abbr></strong>.</p>
```

接下来，我们将在表单中添加一个更大的代码段，在我们之前的代码下面。在这里，您将看到，我们正在将联系人信息字段包装在一个单独的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/section)元素中。此外，我们有一组两个单选按钮，每个单选按钮都放在自己的列表中([``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/li)))元素。最后，我们有两个标准文本[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)和它们相关的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)元素，每个元素包含在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p)中，加上输入密码的密码输入。现在将这些代码添加到您的表单中:  

```
<section>
    <h2>Contact information</h2>
    <fieldset>
      <legend>Title</legend>
      <ul>
          <li>
            <label for="title_1">
              <input type="radio" id="title_1" name="title" value="K" >
              King
            </label>
          </li>
          <li>
            <label for="title_2">
              <input type="radio" id="title_2" name="title" value="Q">
              Queen
            </label>
          </li>
          <li>
            <label for="title_3">
              <input type="radio" id="title_3" name="title" value="J">
              Joker
            </label>
          </li>
      </ul>
    </fieldset>
    <p>
      <label for="name">
        <span>Name: </span>
        <strong><abbr title="required">*</abbr></strong>
      </label>
      <input type="text" id="name" name="username">
    </p>
    <p>
      <label for="mail">
        <span>E-mail: </span>
        <strong><abbr title="required">*</abbr></strong>
      </label>
      <input type="email" id="mail" name="usermail">
    </p>
    <p>
      <label for="pwd">
        <span>Password: </span>
        <strong><abbr title="required">*</abbr></strong>
      </label>
      <input type="password" id="pwd" name="password">
    </p>
</section>
```

现在，我们将转到表单的第二个`<section>`——支付信息。在这里，我们有三个不同的小部件以及它们的标签，每个都包含在一个`<p>`中。第一个是选择信用卡类型的下拉菜单([``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select))。第二个是输入一个信用卡号的类型编号的 `<input>` 元素。最后一个是输入`date`类型的`<input>` 元素，用来输入卡片的过期日期（这将在支持的浏览器中出现一个日期选择器小部件，并在非支持的浏览器中回退到普通的文本输入）。同样，在之前的代码后面输入以下内容：  

```
<section>
    <h2>Payment information</h2>
    <p>
      <label for="card">
        <span>Card type:</span>
      </label>
      <select id="card" name="usercard">
        <option value="visa">Visa</option>
        <option value="mc">Mastercard</option>
        <option value="amex">American Express</option>
      </select>
    </p>
    <p>
      <label for="number">
        <span>Card number:</span>
        <strong><abbr title="required">*</abbr></strong>
      </label>
        <input type="number" id="number" name="cardnumber">
    </p>
    <p>
      <label for="date">
        <span>Expiration date:</span>
        <strong><abbr title="required">*</abbr></strong>
        <em>formatted as mm/yy</em>
      </label>
      <input type="date" id="date" name="expiration">
    </p>
</section>
```

我们要添加的最后一个部分要简单得多，它只包含了一个`submit`类型的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button) ，用于提交表单数据。现在把这个添加到你的表单的底部:  

```
<p> <button type="submit">Validate the payment</button> </p>
```

![image-20211129144658614](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20211129144658614.png)

## 原生表单部件

### [通用属性](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#通用属性)

大部分用来定义表单小部件的元素都有一些他们自己的属性。然而，在所有表单元素中都有一组通用属性，它们可以对这些小部件进行控制。下面是这些通用属性的列表:

| 属性名称    | 默认值    | 描述                                                         |
| ----------- | --------- | ------------------------------------------------------------ |
| `autofocus` | (*false*) | 这个布尔属性允许您指定当页面加载时元素应该自动具有输入焦点，除非用户覆盖它，例如通过键入不同的控件。文档中只有一个与表单相关的元素可以指定这个属性。 |
| `disabled`  | (*false*) | 这个布尔属性表示用户不能与元素交互。如果没有指定这个属性，元素将从包含它的元素继承设置，例如[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset);如果没有包含在设定了`disabled`属性的元素里，那么这个元素就是可用的。 |
| `form`      |           | 小部件与之相关联的表单元素。属性值必需是同个文档中的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form) 元素的 `id`属性。理论上，它允许您在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)元素之外设置一个表单小部件。然而，在实践中，没有任何支持该特性的浏览器。 |
| `name`      |           | 元素的名称;这是跟表单数据一起提交的。                        |
| `value`     |           | 元素的初始值。                                               |

### [文本输入框](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#文本输入框)

文本输入框**\<input>** 是最基本的表单小部件。 这是一种非常方便的方式，可以让用户输入任何类型的数据。但是，一些文本字段可以专门用于满足特定的需求。我们已经看到了几个简单的例子。

**注意**: HTML表单文本字段是简单的纯文本输入控件。 这意味着您不能使用它们执行[富文本编辑](https://developer.mozilla.org/en-US/docs/Rich-Text_Editing_in_Mozilla)(粗体、斜体等)。你遇到的所有富文本编辑器（rich text editors）都是使用HTML、CSS和JavaScript所创建的自定义小部件。

所有文本框都有一些通用规范：

- 它们可以被标记为 [`readonly`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-readonly) (用户不能修改输入值)甚至是 [`disabled`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-disabled) (输入值永远不会与表单数据的其余部分一起发送)。
- 它们可以有一个 [`placeholder`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-placeholder); 这是文本输入框中出现的文本，用来简略描述输入框的目的。
- 它们可以被限制在[`size`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-size) (框的物理尺寸) 和 [`maxlength`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-maxlength) (可以输入的最大字符数)。
- 如果浏览器支持的话，他们可以从[拼写检查](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Input#attr-spellcheck)中获益。

**注意：** [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素是如此特别因为它几乎可以是任何东西。通过简单设置 `type` 属性，它可以彻底的改变，它用于创建大多数类型的表单小部件，包括单行文本字段、没有文本输入的控件、时间和日期控件和按钮。 然而，也有一些例外，比如用来多行输入的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)。阅读这篇文章时，要注意这些。

### [单行文本框](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#单行文本框)

使用[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性值被设置为`text` 的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素创建一个单行文本框（同样的，如果你不提供[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性，`text` 是默认值）。在你指定的[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性的值在浏览器中是未知的情况下（比如你指定 `type="date"`，但是浏览器不支持原生日期选择器），属性值`text`也是备用值。

**注意：** 你可以在Github上的 [single-line-text-fields.html](https://github.com/mdn/learning-area/blob/master/html/forms/native-form-widgets/single-line-text-fields.html)找到所有单行文本框类型。(你也可以直接看[预览版](https://mdn.github.io/learning-area/html/forms/native-form-widgets/single-line-text-fields.html))。

这是一个基本的单行文本框示例：

```
<input type="text" id="comment" name="comment" value="I'm a text field">
```

单行文本框只有一个真正的约束：如果您输入带有换行符的文本，浏览器会在发送数据之前删除这些换行符。

![Screenshots of single line text fields on several platforms.](https://developer.mozilla.org/files/4273/all-single-line-text-field.png)

HTML5通过为[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性增加特殊值增强了基本单行文本框。这些值仍然将[\<input>](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素转换为单行文本框，但它们为字段添加了一些额外的约束和特性。

#### E-mail 地址框

该类型的框将 [`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性设置为 `email` 值：

```
<input type="email" id="email" name="email" multiple>
```

当使用 `type`时， 用户需要在框中输入有效的电子邮件地址；任何其他内容都会导致浏览器在提交表单时显示错误。注意，这是客户端错误验证，由浏览器执行：

![An invalid email input showing the message Please enter an email address.](https://mdn.mozillademos.org/files/14781/email-invalid.png)

通过包括[`multiple`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-multiple)属性，它还可以让用户将多个电子邮件地址输入相同的输入(以逗号分隔)。

在一些设备上(特别是在移动设备上)，可能会出现一个不同的虚拟键盘，更适合输入电子邮件地址。

**注意**: 您可以在[表单数据验证](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Form_validation)文中找到关于表单验证的更多信息。

#### 密码框

通过设置[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type) 属性值为`password`来设置该类型框：

```
<input type="password" id="pwd" name="pwd">
```

它不会为输入的文本添加任何特殊的约束，但是它会模糊输入到字段中的值(例如，用点或小行星)，这样它就不能被其他人读取。

请记住，这只是一个用户界面特性;除非你安全地提交你的表单，否则它会以明文发送，这不利于安全——恶意的一方可能会截获你的数据，窃取你的密码、信用卡信息，或者你提交的其他任何东西。保护用户不受此影响的最佳方式是在安全连接上托管任何涉及表单的页面(例如:https://……地址)，使得数据在发送之前就已加密。

现代浏览器认识到在不安全的连接上发送表单数据所带来的安全影响，并且已经实现了警告，以阻止用户使用不安全的表单。有关Firefox实现的更多信息，请参见[不安全的密码](https://developer.mozilla.org/en-US/docs/Web/Security/Insecure_passwords)。

#### 搜索框

通过设置 [`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性值为 `search` 来设置该类型框：

```
<input type="search" id="search" name="search">
```

文本框和搜索框之间的主要区别是浏览器的样式——通常，搜索框是渲染成圆角的，并且/可能给定一个“x”来清除输入的值。然而，还有另外一个值得注意的特性:它们的值可以被自动保存用来在同一站点上的多个页面上自动补全。

![Screenshots of search fields on several platforms.](https://developer.mozilla.org/files/4269/all-search-field.png)

#### 电话号码栏：

通过 [`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性的 `tel` 值设置该类型框：

```
<input type="tel" id="tel" name="tel">
```

由于世界范围内各种各样的电话号码格式，这种类型的字段不会对用户输入的值执行任何限制(包括字母，等等)。这主要是在语义上的区分，尽管在一些设备上(特别是在移动设备上)，可能会出现一个不同的虚拟键盘，更适合输入电话号码。

#### URL 栏

通过[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性的`url` 值设置该类型框：

```
<input type="url" id="url" name="url">
```

它为字段添加了特殊的验证约束，如果输入无效的url，浏览器就会报告错误。

**注意：**URL格式良好并不一定意味着它引用了一个实际存在的位置。

**注意：**有特殊约束并出错了的输入框可以防止表单被发送；此外，还可以将它们设置为使错误更清晰。我们将在[数据表单验证](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)中详细讨论这个问题。

### [多行文本框](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#多行文本框)

多行文本框专指使用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)元素，而不是使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input) 元素。

```
<textarea cols="30" rows="10"></textarea>
```

textarea和常规的单行文本字段之间的主要区别是，允许用户输入包含硬换行符(即按回车)的文本。

![image-20211130102721116](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20211130102721116.png)

**注意：**你可以在Github上的[multi-line-text-field.html](https://github.com/mdn/learning-area/blob/master/html/forms/native-form-widgets/multi-line-text-field.html)看到本例（你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/native-form-widgets/multi-line-text-field.html)）。注意到在大多数浏览器中，文本区域在右下角有一个拖放操作，允许用户调整它的大小。这种调整能力可以通过使用[CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)设置文本区域的[`resize`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/resize)性质为 `none` 来关闭。

textarea 还接受了一些额外的属性，以控制它在几行代码中呈现的效果 (除此以外还有其他几个)：

textarea 元素属性**

| 属性名                                                       | 默认值 | 描述                                                 |
| ------------------------------------------------------------ | ------ | ---------------------------------------------------- |
| [`cols`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea#attr-cols) | `20`   | 文本控件的可见宽度，平均字符宽度。                   |
| [`rows`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea#attr-rows) |        | 控制的可见文本行数。                                 |
| [`wrap`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea#attr-wrap) | `soft` | 表示控件是如何包装文本的。可能的值：`hard` 或 `soft` |

注意，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)元素与[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素与[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素的编写略有不同。[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素是一个空元素，这意味着它不能包含任何子元素。另一方面，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)元素是一个空元素，这意味着它不能包含任何子元素。另一方面，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)元素是一个常规元素，可以包含文本内容的子元素。 

这里有两个关键点需要注意：

- 如果您想为[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素定义一个默认值，那么您必须使用`value`属性;另一方面，对于[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)元素，只需要将默认的文本放在起始标记和[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)的结束标记之间。
- 因为它的本质， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)元素只接受文本内容；这意味着将任何HTML内容放入[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)中都呈现为纯文本内容。

### [下拉内容](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#下拉内容)

下拉窗口小部件是一种简单的方法，可以让用户选择众多选项中的一个，而不需要占用用户界面的太多空间。HTML有两种类型的下拉内容:**select box**和**autocomplete box**。在这两种情况下，交互都是相同的——一旦控件被激活，浏览器就会显示用户可以选择的值列表。

**注意：**你可以在Github上的[drop-down-content.html](https://github.com/mdn/learning-area/blob/master/html/forms/native-form-widgets/drop-down-content.html)看到本例（你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/native-form-widgets/drop-down-content.html)）。

### [选择框](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#选择框)

一个选择框是用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select)元素创建的，其中有一个或多个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)元素作为子元素，每个元素都指定了其中一个可能的值。

```
<select id="simple" name="simple">
  <option>Banana</option>
  <option>Cherry</option>
  <option>Lemon</option>
</select>
```

如果需要，可以使用[`selected`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option#attr-selected)属性在所需的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)元素上设置选择框的默认值---在页面加载时会默认选择该选项。[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)元素也可以嵌套在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/optgroup)元素中，以创建视觉关联的组值：

```
<select id="groups" name="groups">
  <optgroup label="fruits">
    <option>Banana</option>
    <option selected>Cherry</option>
    <option>Lemon</option>
  </optgroup>
  <optgroup label="vegetables">
    <option>Carrot</option>
    <option>Eggplant</option>
    <option>Potato</option>
  </optgroup>
</select>
```

![Screenshots of single line select box on several platforms.](https://developer.mozilla.org/files/4517/all-select.png)

如果一个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)元素设置了`value`属性，那么当提交表单时该属性的值就会被发送。如果忽略了`value`属性，则使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)元素的内容作为选择框的值。

在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/optgroup)元素中，`label`属性显示在值之前，但即使它看起来有点像一个选项，它也不是可选的。

### [多选选择框](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#多选选择框)

默认情况下，选择框只允许用户选择一个值。通过将[`multiple`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select#attr-multiple)属性添加到[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select)元素，您可以允许用户通过操作系统提供的默认机制来选择几个值。 (如， 同时按下 Cmd/Ctrl 并点击多个值).

注意：在多个选项选择框的情况下，选择框不再显示值为下拉内容——相反，它们都显示在一个列表中。

```
<select multiple id="multi" name="multi">
  <option>Banana</option>
  <option>Cherry</option>
  <option>Lemon</option>
</select>
```

![Screenshots of multi-lines select box on several platforms.](https://developer.mozilla.org/files/4559/all-multi-lines-select.png)

**注意：**所有支持 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select) 元素的浏览器也支持 [`multiple`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select#attr-multiple) 。

### [自动补全输入框](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#自动补全输入框)

您可以使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist)元素来为表单小部件提供建议的、自动完成的值，并使用一些[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)子元素来指定要显示的值。

然后使用[`list`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-list)属性将数据列表绑定到一个文本框(通常是一个 `<input>` 元素)。

一旦数据列表与表单小部件相关联，它的选项用于自动完成用户输入的文本;通常，这是作为一个下拉框提供给用户的，匹配在输入框中输入了的内容。

```
<label for="myFruit">What's your favorite fruit?</label>
<input type="text" name="myFruit" id="myFruit" list="mySuggestion">
<datalist id="mySuggestion">
  <option>Apple</option>
  <option>Banana</option>
  <option>Blackberry</option>
  <option>Blueberry</option>
  <option>Lemon</option>
  <option>Lychee</option>
  <option>Peach</option>
  <option>Pear</option>
</datalist>
```

**注意：** 根据[HTML规范](https://www.w3.org/TR/html5/common-input-element-attributes.html#attr-input-list)，[`list`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-list) 属性和[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist)元素元素可以用于任何需要用户输入的小部件。但是，除了文本控件外(例如颜色或日期)，还不清楚它会如何工作，不同的浏览器在不同的情况下会有不同的表现。正因为如此，除了文本字段以外，要小心使用这个特性。

![Screenshots of datalist on several platforms.](https://developer.mozilla.org/files/4593/all-datalist.png)

#### 数据列表支持和后备

[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist)元素是HTML表单的最新补充，因此浏览器的支持比我们之前看到的要少一些。最值得注意的是，它在版本小于10的IE中不受支持，同时在版本小于12的Safari中不受支持。

为了处理这个问题，这里有一个小技巧，可以为这些浏览器提供一个不错的备用：

```
<label for="myFruit">What is your favorite fruit? (With fallback)</label>
<input type="text" id="myFruit" name="fruit" list="fruitList">

<datalist id="fruitList">
  <label for="suggestion">or pick a fruit</label>
  <select id="suggestion" name="altFruit">
    <option>Apple</option>
    <option>Banana</option>
    <option>Blackberry</option>
    <option>Blueberry</option>
    <option>Lemon</option>
    <option>Lychee</option>
    <option>Peach</option>
    <option>Pear</option>
  </select>
</datalist>
```

支持[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist)元素的浏览器将忽略所有不是[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option)元素的元素，并按照预期工作。另一方面，不支持[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist)元素的浏览器将显示标签和选择框。当然，还有其他方法可以处理对[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist)元素支持的不足，但这是最简单的(其他方法往往需要JavaScript)。

| Safari 6   | ![Screenshot of the datalist element fallback with Safari on Mac OS](https://developer.mozilla.org/files/4583/datalist-safari.png) |
| ---------- | ------------------------------------------------------------ |
| Firefox 18 | ![Screenshot of the datalist element with Firefox on Mac OS](https://developer.mozilla.org/files/4581/datalist-firefox-macos.png) |

### [可选中项](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#可选中项)

可选中项是可以通过单击它们来更改状态的小部件。有两种可选中项：复选框和单选按钮。两者都使用[`checked`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-checked)属性，以指示该部件的默认状态: "选中"或"未选中"。

值得注意的是，这些小部件与其他表单小部件不一样。对于大多数表单部件，一旦表单提交，所有具有[`name`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-name)属性的小部件都会被发送，即使没有任何值被填。对于可选中项，只有在勾选时才发送它们的值。如果他们没有被勾选，就不会发送任何东西，甚至连他们的名字也没有。

**注意**: 你可以在Github上看到 [checkable-items.html](https://github.com/mdn/learning-area/blob/master/html/forms/native-form-widgets/checkable-items.html) (你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/native-form-widgets/checkable-items.html))。

为了获得最大的可用性和可访问性，建议您在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset)中包围每个相关项目的列表，并使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)提供对列表的全面描述。每个单独的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)/[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素都应该包含在它自己的列表项中(或者类似的)。正如在示例中显示的。

您还需要为这些类型的输入提供`value`属性，如果您想让它们具有意义——如果没有提供任何值，则复选框和单选按钮被赋予一个 `on`值。

### [复选框](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#复选框)

使用[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性值为`checkbox`的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素来创建一个复选框。

```
<input type="checkbox" checked id="carrots" name="carrots" value="carrots">
```

包含`checked`属性使复选框在页面加载时自动被选中。

![Screenshots of check boxes on several platforms.](https://developer.mozilla.org/files/4595/all-checkbox.png)

### [单选按钮](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#单选按钮)

使用[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性值为`radio`的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素来创建一个单选按钮。

```
<input type="radio" checked id="soup" name="meal">
```

几个单选按钮可以连接在一起。如果它们的[`name`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-name)属性共享相同的值，那么它们将被认为属于同一组的按钮。同一组中只有一个按钮可以同时被选；这意味着当其中一个被选中时，所有其他的都将自动未选中。如果没有选中任何一个，那么整个单选按钮池就被认为处于未知状态，并且没有以表单的形式发送任何值。

```
<fieldset>
  <legend>What is your favorite meal?</legend>
  <ul>
    <li>
      <label for="soup">Soup</label>
      <input type="radio" checked id="soup" name="meal" value="soup">
    </li>
    <li>
      <label for="curry">Curry</label>
      <input type="radio" id="curry" name="meal" value="curry">
    </li>
    <li>
      <label for="pizza">Pizza</label>
      <input type="radio" id="pizza" name="meal" value="pizza">
    </li>
  </ul>
</fieldset>
```

![Screenshots of radio buttons on several platforms.](https://developer.mozilla.org/files/4597/all-radio.png)

### [按钮](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#按钮)

在HTML表单中，有三种按钮：

- Submit

  将表单数据发送到服务器。对于[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button) 元素, 省略 `type` 属性 (或是一个无效的 `type` 值) 的结果就是一个提交按钮.

- Reset

  将所有表单小部件重新设置为它们的默认值。

- Anonymous

  没有自动生效的按钮，但是可以使用JavaScript代码进行定制。

**注意**: 你可以在Github上看到[button-examples.html](https://github.com/mdn/learning-area/blob/master/html/forms/native-form-widgets/button-examples.html) (你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/native-form-widgets/button-examples.html))。

使用 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素或者[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素来创建一个按钮。[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性的值指定显示什么类型的按钮。

### [submit](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#submit)

```
<button type="submit">
    This a <br><strong>submit button</strong>
</button>

<input type="submit" value="This is a submit button">
```

### [reset](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#reset)

```
<button type="reset">
    This a <br><strong>reset button</strong>
</button>

<input type="reset" value="This is a reset button">
```

### [button](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#button)

```
<button type="button">
    This an <br><strong>anonymous button</strong>
</button>

<input type="button" value="This is an anonymous button">
```

不管您使用的是[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素还是[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素，按钮的行为都是一样的。然而，有一些显著的不同之处：

- 从示例中可以看到，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素允许您在它们的标签中使用HTML内容，这些内容被插入到打开和关闭`<button>` 标签中。另一方面，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素是空元素;它们的标签插入在`value`属性中，因此只接受纯文本内容。
- 使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素，可以有一个不同于按钮标签的值(通过设置`value`中的属性值)。这在IE 8之前的版本中是不可靠的。

![Screenshots of buttons on several platforms.](https://developer.mozilla.org/files/4599/all-buttons.png)

从技术上讲，使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素或[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素定义的按钮几乎没有区别。唯一值得注意的区别是按钮本身的标签。在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素中，标签只能是字符数据，而在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)元素中，标签可以是HTML，因此可以相应地进行样式化。

### [高级表单部件](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#高级表单部件)

在本节中，我们将介绍那些让用户输入复杂或不寻常数据的小部件。这包括精确的或近似的数字，日期和时间，或颜色。

**注意**: 你可以在Github上看到[advanced-examples.html](https://github.com/mdn/learning-area/blob/master/html/forms/native-form-widgets/advanced-examples.html) (你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/native-form-widgets/advanced-examples.html))。

### [数字](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#数字)

用于数字的小部件是用[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性设置为`number`[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)的元素创建的。这个控件看起来像一个文本框，但是只允许浮点数，并且通常提供一些按钮来增加或减少小部件的值。

也可以：

- 通过设置[`min`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-min)和[`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-max)属性来约束该值。
- 通过设置[`step`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-step)属性来指定增加和减少按钮更改小部件的步进值大小。

#### 例子

```
<input type="number" name="age" id="age" min="1" max="10" step="2">
```

这将创建一个数字小部件，其值被限制为1到10之间的任何值，而其增加和减少按钮的步进值将更改为2。

在10以下的Internet Explorer版本中不支持`number` 输入。

### [滑块](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#滑块)

另一种选择数字的方法是使用滑块。从视觉上讲，滑块没有文本字段准确，因此它们被用来选择一个确切值并不重要的数字。

滑块是通过把[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素的[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性值设置为`range`来创建的。正确配置滑块是很重要的；为了达到这个目的，我们强烈建议您设置[`min`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-min)、[`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-max)和[`step`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-step)属性。

#### 例子

```
<input type="range" name="beans" id="beans" min="0" max="500" step="10">
```

这个例子创建了一个滑块，它可能的值在0到500之间，而它的递增/递减按钮以+10和-10来改变值。

滑块的一个问题是，它们不提供任何形式的视觉反馈，以了解当前的值是什么。您需要使用JavaScript来添加这一点，但这相对来说比较容易。在本例中，我们添加了一个空的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/span)元素，其中我们将写入滑块的当前值，并随着更改实时更新它。

```
<label for="beans">How many beans can you eat?</label>
<input type="range" name="beans" id="beans" min="0" max="500" step="10">
<span class="beancount"></span>
```

可以使用一些简单的JavaScript实现

```
var beans = document.querySelector('#beans');
var count = document.querySelector('.beancount');

count.textContent = beans.value;

beans.oninput = function() {
  count.textContent = beans.value;
}
```

这里我们将对范围输入值和span的引用存储在两个变量里，然后我们立即将span的`textContent`设置为输入的当前`value`。最后，我们设置了一个`oninput`事件处理程序，以便每次移动范围滑块时，都会将span `textContent`更新为新的输入值。

在10以下的Internet Explorer版本中不支持`range` 。

##### **利用output输出**

Let's look at the code behind the above example, so you can see how its done. First of all, the basic HTML:

```
<label for="price">Choose a maximum house price: </label>
<input type="range" name="price" id="price" min="50000" max="500000" step="100" value="250000">
<output class="price-output" for="price"></output>
```

This example creates a slider whose value may range between `50000` and `500000`, which increments/decrements by 100 at a time. We've given it default value of `250000`, using the `value` attribute.

One problem with sliders is that they don't offer any kind of visual  feedback as to what the current value is. This is why we've included an [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output) element to contain the current value. You could display an input value or the output of a calculation inside any element, but `<output>` is special — like `<label>` — and it can take a `for` attribute that allows you to associate it with the element or elements that the output value came from.

To actually display the current value, and update it as it changed, you must use JavaScript, but this is relatively easy to do:

```
const price = document.querySelector('#price');
const output = document.querySelector('.price-output');

output.textContent = price.value;

price.addEventListener('input', function() {
  output.textContent = price.value;
});
```

Here we store references to the `range` input and the `output` in two variables. Then we immediately set the `output`'s [`textContent`](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent) to the current `value` of the input. Finally, an event listener is set to ensure that whenever the range slider is moved, the `output`'s `textContent` is updated to the new value.

### [日期时间选择器](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#日期时间选择器)

对于web开发人员来说，收集日期和时间值一直是一场噩梦。HTML5通过提供一种特殊的控制来处理这种特殊的数据，从而带来了一些增强。

使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素和一个适当的值的[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性来创建日期和时间控制，这取决于您是否希望收集日期、时间或两者都。

#### `本地时间`

这将创建一个小部件来显示和选择一个日期，但是没有任何特定的时区信息。

```
<input type="datetime-local" name="datetime" id="datetime">
```

#### `月`

这就创建了一个小部件来显示和挑选一个月。

```
<input type="month" name="month" id="month">
```

#### 时间

这将创建一个小部件来显示并选择一个时间值。

```
<input type="time" name="time" id="time">
```

#### `星期`

这将创建一个小部件来显示并挑选一个星期号和它的年份。

```
<input type="week" name="week" id="week">
```

所有日期和时间控制都可以使用[`min`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-min)和[`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-max)属性来约束。

```
<label for="myDate">When are you available this summer?</label>
<input type="date" name="myDate" min="2013-06-01" max="2013-08-31" id="myDate">
```

警告——日期和时间窗口小部件仍然很不受支持。目前，Chrome、Edge和Opera都支持它们，但IE浏览器没有支持，Firefox和Safari对这些都没有太大的支持。

### [拾色器](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#拾色器)

颜色总是有点难处理。有很多方式来表达它们:RGB值(十进制或十六进制)、HSL值、关键字等等。颜色小部件允许用户在文本和可视的方式中选择颜色。

一个颜色小部件是使用[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性设置为值`color`[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)的元素创建的。

```
<input type="color" name="color" id="color">
```

警告——并不是所有浏览器都支持拾色器。IE中没有支持，Safari目前也不支持它。其他主要的浏览器都支持它。

### [其他小部件](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#其他小部件)

还有一些其他的小部件由于它们非常特殊的行为而不能很容易地分类，但是它们仍然非常有用。

**注意**: 你可以在Github上看到[other-examples.html](https://github.com/mdn/learning-area/blob/master/html/forms/native-form-widgets/other-examples.html)(你也可以看[预览版](https://mdn.github.io/learning-area/html/forms/native-form-widgets/other-examples.html))。

### [文件选择器](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#文件选择器)

HTML表单能够将文件发送到服务器；在[发送和检索表单数据](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)的文章中详细描述了这个特定的操作。文件选择器小部件是用户如何选择一个或多个文件来发送的。

要创建一个文件选择器小部件，您可以使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)元素，将它的[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性设置为`file`。被接受的文件类型可以使用[`accept`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-accept)属性来约束。此外，如果您想让用户选择多个文件，那么可以通过添加[`multiple`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-multiple)属性来实现。

#### 例子

在本例中，创建一个文件选择器，请求图形图像文件。在本例中，允许用户选择多个文件。

```
<input type="file" name="file" id="file" accept="image/*" multiple>
```

### [隐藏内容](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#隐藏内容)

有时候，由于为了方便技术原因，有些数据是用表单发送的，但不显示给用户。要做到这一点，您可以在表单中添加一个不可见的元素。要做到这一点，需要使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)将它的[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性设置为`hidden`值。

如果您创建了这样一个元素，就需要设置它的`name`和`value`属性：

```
<input type="hidden" id="timestamp" name="timestamp" value="1286705410">
```

### [图像按钮](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#图像按钮)

图像按钮控件是一个与[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img)元素完全相同的元素，除了当用户点击它时，它的行为就像一个提交按钮(见上面)。

图像按钮是使用[`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-type)属性值设置为`image`[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)的元素创建的。这个元素支持与[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img)元素相同的属性，和其他表单按钮支持的所有属性。

```
<input type="image" alt="Click me!" src="my-img.png" width="80" height="30" />
```

如果使用图像按钮来提交表单，这个小部件不会提交它的值；相反，提交的是在图像上单击处的X和Y坐标(坐标是相对于图像的，这意味着图像的左上角表示坐标0，0)，坐标被发送为两个键/值对：

- X值键是[`name`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-name)属性的值，后面是字符串“.x”。
- Y值键是[`name`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-name)属性的值，后面是字符串“.y”。

例如，当您点击这个小部件的图像时，您将被发送到一个URL，如下所显示的

```
http://foo.com?pos.x=123&pos.y=456
```

这是构建“热图”的一种非常方便的方式。如何发送和检索这些值在[发送和检索表单数据](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)文章中详细说明。

### [仪表和进度条](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Basic_native_form_controls#仪表和进度条)

仪表和进度条是数值的可视化表示。

#### 进度条

一个进度条表示一个值，它会随着时间的变化而变化到最大的值，这个值由[`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/progress#attr-max)属性指定。这样的一个bar是使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/progress)元素创建的。

```
<progress max="100" value="75">75/100</progress>
```

这是为了实现任何需要进度报告的内容，例如下载的总文件的百分比，或者问卷中填写的问题的数量。

progress元素中的内容用于不支持该元素的浏览器的回退，以及辅助技术对其朗读。

#### 仪表

一个仪表表示一个固定值，这个值由一个[`min`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-min)和一个[`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-max)值所界定。这个值是作为一个条形显示的，并且为了知道这个工具条是什么样子的，我们将这个值与其他一些设置值进行比较

- `low`

   和 

  `high`

   值范围划分为三个部分：  

  - 该范围的较低部分是在[`min`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-min)和[`low`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-low)值(包括那些值)之间。
  - 该范围的中间部分是在[`low`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-low)和[`high`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-high)值之间(不包括那些值)。
  - 该范围的较高部分是在[`high`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-high)和[`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-max)值(包括那些值)之间。

- `optimum`

  值定义了

  `<meter>`

  元素的最优值。在与htmlattrxref(“low”、“meter”)和

  `high`

  值的联合中，它定义了该范围的哪个部分是优先的：  

  - 如果[`optimum`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-optimum)值在较低的范围内，则较低的范围被认为是首选项，中等范围被认为是一般的，而较高的范围被认为是最坏的部分。
  - 如果[`optimum`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-optimum)值在该范围的中等部分，则较低的范围被认为是一个一般的，中等范围被认为是优先的部分，而较高的范围也被认为是平均值。
  - 如果[`optimum`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter#attr-optimum)值在较高的范围内，则较低的范围被认为是最坏的部分，中等范围被认为是一般的部分，较高的范围被认为是优先的部分。

所有实现meter元素的浏览器都使用这些值来改变米尺的颜色。

- 如果当前值位于该范围的优先部分，则该条是绿色的。
- 如果当前值位于该范围的平均部分，则该条是黄色的。
- 如果当前值处于最糟糕的范围，则该条是红色的。

这样的一个工具栏是使用[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter)元素创建的。这是用于实现任何类型的仪表，例如一个显示磁盘上使用的总空间的条，当它开始满时，它会变成红色。

```
<meter min="0" max="100" value="75" low="33" high="66" optimum="50">75</meter>
```

meter元素中的内容是不支持该元素的浏览器的回退，以及辅助技术对其发出的声音。

对进度条和仪表的支持是相当不错的，在Internet Explorer中没有支持，但是其他浏览器都可以很好的支持它。

### 详细介绍input类型

https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types

### 详细介绍其他表单部件

https://developer.mozilla.org/en-US/docs/Learn/Forms/Other_form_controls

## 样式化Web表单

### [为什么使用CSS美化表单组件这么困难？](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#为什么使用css美化表单组件这么困难？)

在1995年左右的Web早期，表单组件(或控件)在 [HTML 2规范](https://www.ietf.org/rfc/rfc1866.txt)中被添加到HTML。由于表单组件的复杂性，实现者选择依靠底层操作系统来管理和渲染它们。

若干年后，CSS被创建出来了，那么技术上的必要性，就是使用原生组件来实现表单控制，这是因为风格的要求。在CSS的早期，表单样式控制不是优先事项。

由于用户习惯于各自平台的视觉外观，浏览器厂商不愿意对表单控件样式进行调整;到目前为止，要重建所有控件以使它们可美化仍然是非常困难的。

即使在今天，仍然没有一个浏览器完全实现了CSS 2.1。然而，随着时间的推移，浏览器厂商已经改进了对表单元素的CSS支持，尽管可用性的声誉不好，但现在已经可以使用CSS来设计[HTML表单](https://developer.mozilla.org/en-US/docs/Learn/Forms)。

[涉及到CSS，并非所有组件都是平等的](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#涉及到css，并非所有组件都是平等的)

目前，在使用表单时使用CSS仍然有一些困难。这些问题可以分为三类： 

#### 好的

有些元素在跨平台上时很少出现问题。包括以下结构元素：

1. form
2. fieldset
3. label
4. output

这还包括所有文本字段小部件（单行和多行）和按钮。

#### 不好的

一些元素难以被美化，并且可能需要一些复杂的技巧，偶尔需要高级的CSS3知识。

这些包括[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)元素，但不能在所有平台上正确定位。 Checkbox和radio按钮也不能直接应用样式，但是，感谢CSS3，你可以解决这个问题。[`placeholder`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-placeholder) 的内容不能以任何标准方式应用样式，但是实现它的所有浏览器也都实现了私有的CSS伪元素或伪类，让你可以对其定义样式。

我们会在[如何构建自定义表单挂件](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Forms/How_to_build_custom_form_widgets)一文中讲述如何处理更多特定的问题。

#### 丑陋的

有些元素根本不能用应用CSS样式。 这些包括：所有高级用户界面小部件，如范围，颜色或日期控件; 和所有下拉小部件，包括[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/select), [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/option), [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/optgroup)和[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/datalist) 元素。 文件选择器小部件也被称为不可样式化。 新的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/progress)和[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meter) 元素也属于这个类别。

所有这些小部件的主要问题来自于它们具有非常复杂的结构，而CSS目前还不足以表达这些小部件的所有细微部分。 如果你想定制这些小部件，你必须依靠JavaScript来构建一个你能够应用样式的DOM树。我们会在 [How to build custom form widgets](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls)一文中探索如何实现这一点。

### [基本样式美化](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#基本样式美化)

为了使用CSS美化容易被美化的元素，你并不会碰到任何困难，因为它们的大部分行为同其他HTML元素差不多。但是，每个浏览器的用户代理样式表可能会有点不一致，所以有一些技巧可以帮助您更轻松地设计它们。

[Search字段](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#search字段)

搜索框是唯一一种应用CSS样式有点棘手的文本字段。 在基于WebKit的浏览器（Chrome，Safari等）上，您必须使用`-webkit-appearance`专有属性来调整它。 我们在文章中进一步讨论这个属性：[HTML表单的高级样式](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)。

#### Example

```
<form>
  <input type="search">
</form>
input[type=search] {
  border: 1px dotted #999;
  border-radius: 0;

  -webkit-appearance: none;
}
```

![This is a screenshot of a search filed on Chrome, with and without the use of -webkit-appearance](https://developer.mozilla.org/files/4153/search-chrome-macos.png)

截图中是 Chrome 浏览器中的两个搜索框，在我们的例子中，两个搜索框均被设置为有边框。第一个没有使用`-webkit-appearance`渲染，而第二个使用了 `-webkit-appearance:none`. 两者的不同显而易见。

### [字体和文本](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#字体和文本)

CSS font和text功能能被很容易的应用到任何组件上（当然你可以在form组件上使用[`@font-face`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/@font-face) ）。然而，浏览器的行为经常不一致。默认情况下，一些组件不会从它们的父元素继承 [`font-family`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-family)和 [`font-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size) 。相反，许多浏览器使用系统默认的字体和文本。为了让form表单的外观和其他内容保持一致，你可以在你的样式表中增加以下内容:

```
button, input, select, textarea {
  font-family : inherit;
  font-size   : 100%;
}
```

下面的截图显示了不同之处; 左边是Mac OS X上Firefox中元素的默认渲染，其中使用了平台的默认字体样式。 在右边是相同的元素，应用了我们的字体统一样式规则。

![This is a screenshot of the main form widgets on Firefox on Mac OSX, with and without font harmonization](https://developer.mozilla.org/files/4157/font-firefox-macos.png)

关于使用系统默认样式的表单还是使用设计用于匹配内容的自定义样式表单，有很多争议。 作为网站或Web应用程序的设计者，您可以自己做出决定。

### [盒子模型](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#盒子模型)

所有文本字段都完全支持与CSS盒模型相关的每个属性([`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width), [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height), [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding), [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin), 和 [`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border))。 但是，像以前一样，浏览器在显示这些小部件时依赖于系统默认的样式。  您需要定义如何将其融入到您的内容中。 如果你既想保持小部件的原生外观和感觉，又想给他们一个一致的尺寸，那么你会遇到一些困难(如果你想保持组件的原生观感，又想给它们一致的大小，你会面临一些困难)。

**这是因为每个小部件都有自己的边框，填充和边距的规则。** 所以如果你想给几个不同的小部件相同的大小，你必须使用[`box-sizing`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/box-sizing) 属性：

```
input, textarea, select, button {
  width : 150px;
  margin: 0;

  -webkit-box-sizing: border-box; /* For legacy WebKit based browsers */
     -moz-box-sizing: border-box; /* For legacy (Firefox <29) Gecko based browsers */
          box-sizing: border-box;
}
```

![This is a screenshot of the main form widgets on Chrome on Windows 7, with and without the use of box-sizing.](https://developer.mozilla.org/files/4161/size-chrome-win7.png)

在上面的屏幕截图中，左侧的列没有[`box-sizing`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/box-sizing)，而右侧的列使用了这个属性和`border-box`。 请注意我们是怎样确保所有元素都占用相同的空间量，尽管平台对每种窗口小部件都有默认规则。

### [定位（Positioning）](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#定位（positioning）)

HTML表单部件的定位通常不是问题; 但是，您应该特别注意两点：

#### legend

[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)元素易于应用CSS，除了定位。在所有浏览器中， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)元素易于应用CSS，除了定位。在所有浏览器中， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)元素易于应用CSS，除了定位。在所有浏览器中， [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend) 元素定位是其 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset) 元素定位是其 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/fieldset) 父元素的上边框的最顶端。在HTML流中无法改变它的绝对位置，无法让其远离顶部边框。然而，你可以使用 [`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position) 父元素的上边框的最顶端。在HTML流中无法改变它的绝对位置，无法让其远离顶部边框。然而，你可以使用 [`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position) 属性将其位置设置为绝对或相对。除此之外，它近几年是fieldset边框的一部分。

由于[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/legend)元素对可访问性非常重要，因为它能被无障碍技术作为每个fieldset中的表单元素的标签读出来，它通常与标题配对，并且在无障碍中被隐藏 。例如:

##### HTML

```
<fieldset>
  <legend>Hi!</legend>
  <h1>Hello</h1>
</fieldset>
```

##### CSS

```
legend {
  width: 1px;
  height: 1px;
  overflow: hidden;
}
```

#### textarea

默认情况下，所有浏览器都认为[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea) 元素是inline block，与文本底线对齐。 这很少是我们真正想看到的。 要将内联(`inline-block`)块更改为块(`block`)，使用[`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display)属性非常简单。 但是如果你想以inline方式使用它，通常改变垂直对齐方式：

```
textarea {
  vertical-align: top;
}
```

### [示例](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#示例)

让我们来看一个样式化 HTML 表单的实际的案例。这有助于理清这里面的许多概念。我们将构建下面的"明信片" 联系人表单：

![This is what we want to achieve with HTML and CSS](https://developer.mozilla.org/files/4149/screenshot.png)

如果你想继续关注这个例子，复制我们的 [postcard-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/postcard-example/postcard-start.html) 文件，并遵循接下来的指导操作。

### [The HTML](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#the_html)

HTML 只比我们在 [the first article of this guide](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form) 中涉及到的多一些；它只有一些额外的 id 和 title。

```
<form>
  <h1>to: Mozilla</h1>

  <div id="from">
    <label for="name">from:</label>
    <input type="text" id="name" name="user_name">
  </div>

  <div id="reply">
    <label for="mail">reply:</label>
    <input type="email" id="mail" name="user_email">
  </div>

  <div id="message">
    <label for="msg">Your message:</label>
    <textarea id="msg" name="user_message"></textarea>
  </div>

  <div class="button">
    <button type="submit">Send your message</button>
  </div>
</form>
```

将上面的代码添加到你 HTML 的 body 中。

### [组织你的静态文件](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#组织你的静态文件)

好戏要开始了! 在开始写代码之前，我们需要三个额外的静态文件：

1. 明信片的[背景](https://developer.mozilla.org/files/4151/background.jpg)——下载这幅图片，把它和你的 HTML 文件保存在相同目录下。
2. 打字机字体：[源自 fontsquirrel.com 的 "Secret Typewriter“ 字体](https://www.fontsquirrel.com/fonts/Secret-Typewriter)——将TTF文件下载到和上面相同的文件夹里。
3. 手绘字体：[源自 fontsquirrel.com 的 The "Journal" 字体 ](https://www.fontsquirrel.com/fonts/Journal) —— 将TTF文件下载到和上面相同的文件夹里。

在你开始之前需要对字体做一些处理：

1. 打开 fontsquirrel [网络字体生成器](https://www.fontsquirrel.com/tools/webfont-generator).
2. 使用表单，上传你的字体文件并生成一个网络字体包，将这个包下载到你的电脑上。
3. 解压提供的 zip 文件。
4. 再解压后的文件内容里你会找到两个 `.woff` 文件和两个`.woff2` 文件。将这四个文件拷贝到一个叫 fonts 的文件夹里，而fonts 文件夹位于和上面相同的文件夹里。我们为每种字体使用两个不同的文件以最大限度地保证浏览器兼容性。查看我们的 [Web 字体](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Web_fonts) 一文获取更多信息。

### [CSS](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Styling_web_forms#css_2)

现在我们可以深入探究本例的 CSS 了。将下面所有的代码块一个接一个地加到[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/style) 元素里。

首先，我们要准备一些基础。这需要定义 [`@font-face`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/@font-face) 规则，以及所有的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/body) 元素和 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form) 元素基本规则：

```
@font-face {
    font-family: 'handwriting';
    src: url('fonts/journal-webfont.woff2') format('woff2'),
         url('fonts/journal-webfont.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}

@font-face {
    font-family: 'typewriter';
    src: url('fonts/veteran_typewriter-webfont.woff2') format('woff2'),
         url('fonts/veteran_typewriter-webfont.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}

body {
  font  : 21px sans-serif;

  padding : 2em;
  margin  : 0;

  background : #222;
}

form {
  position: relative;

  width  : 740px;
  height : 498px;
  margin : 0 auto;

  background: #FFF url(background.jpg);
}
```

现在我们可以定位我们的元素，包括标题和其他表单元素：

```
h1 {
  position : absolute;
  left : 415px;
  top  : 185px;

  font : 1em "typewriter", sans-serif;
}

#from {
  position: absolute;
  left : 398px;
  top  : 235px;
}

#reply {
  position: absolute;
  left : 390px;
  top  : 285px;
}

#message {
  position: absolute;
  left : 20px;
  top  : 70px;
}
```

现在我们开始处理表单元素本身。首先，让我们确保 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label) 被赋予了正确的字体：

```
label {
  font : .8em "typewriter", sans-serif;
}
```

文本域需要一些通用的规则，我们只需简单的移除 [`borders`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border) 和 [`backgrounds`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background), 并重新定义其[`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding) 和 [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin)：

```
input, textarea {
  font    : .9em/1.5em "handwriting", sans-serif;

  border  : none;
  padding : 0 10px;
  margin  : 0;
  width   : 240px;

  background: none;
}
```

当其中的一个域获得焦点后，我们用浅灰色、半透明的背景高亮它们，注意添加[`outline`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/outline) 属性非常重要，这样可以移除由某些浏览器添加的默认高亮效果：

```
input:focus, textarea:focus {
  background   : rgba(0,0,0,.1);
  border-radius: 5px;
  outline      : none;
}
```

现在我们的文本域已经完成了，我们需要调整单行和多行文本域的显示，使其能够匹配，因为通常情况下它们不会以默认的设置而具有一样的外观。

单行文本需要一些调整才能在 Internet Explorer 中渲染良好。Internet Explorer 没有基于字体的自然高度来定义文本域的高度（而这是所有其他浏览器都有的行为）。为了修正这个问题，我们需要给域添加一个确定的高度，像下面这样：

```
input {
    height: 2.5em; /* for IE */
    vertical-align: middle; /* This is optional but it makes legacy IEs look better */
}
```

[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea) 元素默认地被渲染成一个块级元素。这里有重要地两点是 [`resize`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/resize) 和 [`overflow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow) 属性。因为我们的设计是一个固定大小的设计，所以我们会使用 `resize` 属性来防止用户调整我们的多行文本域的大小。[`overflow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow) 属性是用来让域在不同的浏览器上渲染得更一致。一些浏览器默认值为 `auto`，而一些将默认值设为 `scroll`。在我们得例子中，最好确定每个浏览器都使用 `auto`：

```
textarea {
  display : block;

  padding : 10px;
  margin  : 10px 0 0 -10px;
  width   : 340px;
  height  : 360px;

  resize  : none;
  overflow: auto;
}
```

[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button) 元素上使用 CSS 非常方便；你可以做你任何想做得事情，甚至包括使用 [伪元素](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)：

```
button {
  position     : absolute;
  left         : 440px;
  top          : 360px;

  padding      : 5px;

  font         : bold .6em sans-serif;
  border       : 2px solid #333;
  border-radius: 5px;
  background   : none;

  cursor       : pointer;

-webkit-transform: rotate(-1.5deg);
   -moz-transform: rotate(-1.5deg);
    -ms-transform: rotate(-1.5deg);
     -o-transform: rotate(-1.5deg);
        transform: rotate(-1.5deg);
}

button:after {
  content: " >>>";
}

button:hover,
button:focus {
  outline   : none;
  background: #000;
  color   : #FFF;
}
```

![image-20211201100559880](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20211201100559880.png)

## 进阶表单样式化

In this article, we will see what can be done with CSS to style  the types of form control that are more difficult to style — the "bad"  and "ugly" categories. As we saw [in the previous article](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms), text fields and buttons are perfectly easy to style; now we will dig into styling the bits that are more problematic.

**The bad**: Some elements are more difficult to style, requiring more complex CSS or some more specific tricks:

- Checkboxes and radio buttons
- \<input type='search'>

**The ugly**: Some elements can't be styled thoroughly using CSS. These include:

- Elements involved in creating dropdown widgets, including \<select>, \<option>, and \<datalist>.
- \<input type='color'>
- Date-related controls such as \<input type='datatime-local'>
- \<input type="range">
- \<input type="file">
- \<progress> and \<meter>

Let's first talk about the [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance) property, which is pretty useful for making all of the above more stylable.

### 控制浏览器默认样式

In the previous article we said that historically, styling of web form  controls was largely taken from the underlying operating system, which  is part of the problem with customizing the look of these controls.

The [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance) property was created as a way to control what OS- or system-level  styling was applied to web form controls. Unfortunately, the behavior of this property's original implementations was very different across  browsers, making it not very usable. Newer implementations are more  consistent in behavior; interestingly enough, both Chromium-based  browsers (Chrome, Opera, Edge), Safari, and Firefox all support the `-webkit-` prefixed version (`-webkit-appearance`). Firefox settled on this because web developers mostly seemed to be using the `-webkit-` prefixed version, so it was better for compatibility.

If you look at the reference page you'll see a lot of different possible values listed for `-webkit-appearance`, however by far the most helpful value, and probably the only one you'll use, is `none`. This stops any control you apply it to from using system-level styling, as much as possible, and lets you build up the styles yourself using  CSS.

For example, let's take the following controls:

```html
<form>
  <p>
    <label for="search">search: </label>
    <input id="search" name="search" type="search">
  </p>
  <p>
    <label for="text">text: </label>
    <input id="text" name="text" type="text">
  </p>
  <p>
    <label for="date">date: </label>
    <input id="date" name="date" type="datetime-local">
  </p>
  <p>
    <label for="radio">radio: </label>
    <input id="radio" name="radio" type="radio">
  </p>
  <p>
    <label for="checkbox">checkbox: </label>
    <input id="checkbox" name="checkbox" type="checkbox">
  </p>
  <p><input type="submit" value="submit"></p>
  <p><input type="button" value="button"></p>
</form>
```

Applying the following CSS to them removes system-level styling.

```css
input {
  -webkit-appearance: none;
  appearance: none;
}
```

**Note:** It is a good idea to always include both  declarations — prefixed and unprefixed — when using a prefixed property. Prefixed usually means "work in progress", so in the future browser  vendors may come to a consensus to drop the prefix. The above code is  good for future-proofing against such an eventuality.

The following live example shows you what they look like in your  system — default on the left, and with the above CSS applied on the  right ([find it here also](https://mdn.github.io/learning-area/html/forms/styling-examples/appearence-tester.html) if you want to test it on other systems).

![image-20211201204110074](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20211201204110074.png)

In most cases, the effect is to remove the stylized border,  which makes CSS styling a bit easier, but isn't really essential. In a  couple of cases — search and radio buttons/checkboxes, it becomes way  more useful. We'll look at those now.

### 样式化搜索框

search element  is basically just a text input, so why is `appearance: none;` useful here? The answer is that in Chromium-based browsers on macOS,  search boxes have some styling restrictions — you can't adjust their `height` or `font-size` freely, for example. This is because non-macOS [Chrome browsers no longer use the WebKit rendering engine](https://www.wired.com/2013/04/blink/), which enabled Aqua appearance by default for certain form controls. With Aqua enabled, some form controls are not [scalable](https://webkit.org/blog/28/buttons/).

This can be fixed using our friend `appearance: none;`, which disables the default Aqua appearance:

```
input[type="search"] {
    -webkit-appearance: none;
    appearance: none;
}
```

In the example below, you can see two identical styled search boxes. The right one has `appearance: none;` applied, and the left one doesn't. If you look at it in macOS Chrome you'll see that the left one isn't sized properly.

<iframe src="https://mdn.github.io/learning-area/html/forms/styling-examples/search-appearence.html" loading="lazy" width="100%" height="200"></iframe>

Interestingly, setting border/background on the search field also fixes this problem, as it [disables](https://webkit.org/blog/28/buttons/) or "breaks" the Aqua appearance too. The following styled search doesn't have `appearance: none;` applied, but it doesn't suffer from the same problem in macOS Chrome as the previous example.

<iframe src="https://mdn.github.io/learning-area/html/forms/styling-examples/styled-search.html" loading="lazy" width="100%" height="200"></iframe>

**Note:** You may have noticed that in the search  field, the "x" delete icon disappears when the input loses focus in Edge and Chrome, but stays put in Safari. To remove via CSS, you can use `input[type="search"]::-webkit-search-cancel-button { display: none; }`. However, this seems to get rid of the icon *with* focus too, with no apparent way to get it back.

### 样式化checkbox和radio

Styling a checkbox or a radio button is tricky by default. The sizes of check  boxes and radio buttons are not meant to be changed with their default  designs, and browsers react very differently when you try.

For example, consider this simple test case:

```
<span><input type="checkbox"></span>
span {
    display: inline-block;
    background: red;
}

input[type="checkbox"] {
    width: 100px;
    height: 100px;
}
```

Different browsers handle this in many different, often ugly ways:

| Browser                             | Rendering                                                    |
| ----------------------------------- | ------------------------------------------------------------ |
| Firefox 71 (macOS)                  | ![img](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling/firefox-mac-checkbox.png) |
| Firefox 57 (Windows 10)             | ![img](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling/firefox-windows-checkbox.png) |
| Chrome 77 (macOS), Safari 13, Opera | ![img](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling/chrome-mac-checkbox.png) |
| Chrome 63 (Windows 10)              | ![img](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling/chrome-windows-checkbox.png) |
| Internet Explorer 11 (Windows 10)   | ![img](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling/ie11-checkbox.png) |
| Edge 16 (Windows 10)                | ![img](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling/edge-checkbox.png) |

#### Using appearance: none on radios/checkboxes

As we showed before, you can remove the default appearance of a checkbox or radio button altogether with [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance)`:none;` Let's take this example HTML:

```
<form>
  <fieldset>
    <legend>Fruit preferences</legend>

    <p>
      <label>
        <input type="checkbox" name="fruit-1" value="cherry">
        I like cherry
      </label>
    </p>
    <p>
      <label>
        <input type="checkbox" name="fruit-2" value="banana" disabled>
        I can't like banana
      </label>
    </p>
    <p>
      <label>
        <input type="checkbox" name="fruit-3" value="strawberry">
        I like strawberry
      </label>
    </p>
  </fieldset>
</form>
```

Now, let's style these with a custom checkbox design. Let's start by unstyling the original check boxes:

```
input[type="checkbox"] {
  -webkit-appearance: none;
  appearance: none;
}
```

We can use the [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked) and [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled) pseudo-classes to change the appearance of our custom checkbox as its state changes:

```
input[type="checkbox"] {
  position: relative;
  width: 1em;
  height: 1em;
  border: 1px solid gray;
  /* Adjusts the position of the checkboxes on the text baseline */
  vertical-align: -2px;
  /* Set here so that Windows' High-Contrast Mode can override */
  color: green;
}

input[type="checkbox"]::before {
  content: "✔";
  position: absolute;
  font-size: 1.2em;
  right: -1px;
  top: -0.3em;
  visibility: hidden;
}

input[type="checkbox"]:checked::before {
  /* Use `visibility` instead of `display` to avoid recalculating layout */
  visibility: visible;
}

input[type="checkbox"]:disabled {
  border-color: black;
  background: #ddd;
  color: gray;
}
```

You'll find more out about such pseudo-classes and more in the [next article](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes); the above ones do the following:

- `:checked` — the checkbox (or radio button) is in a checked state — the user has clicked/activated it.
- `:disabled` — the checkbox (or radio button) is in a disabled state — it cannot be interacted with.

You can see the live result:

<iframe src="https://mdn.github.io/learning-area/html/forms/styling-examples/checkboxes-styled.html" loading="lazy" width="100%" height="200"></iframe>

We've also created a couple of other examples to give you more ideas:

- [Styled radio buttons](https://mdn.github.io/learning-area/html/forms/styling-examples/radios-styled.html): Custom radio button styling.
- [Toggle switch example](https://mdn.github.io/learning-area/html/forms/toggle-switch-example/): A checkbox styled to look like a toggle switch.

If you view these checkboxes in a browser that doesn't support [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance), your custom design will be lost, but they will still look like checkboxes and be usable.

**Note:** While Internet Explorer doesn't support any version of `appearance`, the `input[type=checkbox]::-ms-check` enables the targeting of checkboxes in IE only. This technique works for radio buttons too, despite the name `-ms-check`.

### 对于ugly的元素可以样式化到什么程度

Now let's turn our attention to the "ugly" controls — the ones that are  really hard to thoroughly style. In short, these are drop-down boxes,  complex control types like [`color`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/color) and [`datetime-local`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local), and feedback—oriented controls like [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) and [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter).

The problem is that these elements have very different default looks  across browsers, and while you can style them in some ways, some parts  of their internals are literally impossible to style.

If you are prepared to live with some differences in look and feel,  you can get away with some simple styling to make sizing consistent,  uniform styling of things like background-colors, and usage of  appearance to get rid of some system-level styling.

Take the following example, which shows a number of the "ugly" form features in action:

<iframe src="https://mdn.github.io/learning-area/html/forms/styling-examples/ugly-controls.html" loading="lazy" width="100%" height="750"></iframe>

This example has the following CSS applied to it:

```
body {
  font-family: 'Josefin Sans', sans-serif;
  margin: 20px auto;
  max-width: 400px;
}

form > div {
  margin-bottom: 20px;
}

select {
  -webkit-appearance: none;
  appearance: none;
}

.select-wrapper {
  position: relative;
}

.select-wrapper::after {
  content: "▼";
  font-size: 1rem;
  top: 6px;
  right: 10px;
  position: absolute;
}

button, label, input, select, progress, meter {
  display: block;
  font-family: inherit;
  font-size: 100%;
  margin: 0;
  box-sizing: border-box;
  width: 100%;
  padding: 5px;
  height: 30px;
}

input[type="text"], input[type="datetime-local"], input[type="color"], select {
  box-shadow: inset 1px 1px 3px #ccc;
  border-radius: 5px;
}

label {
  margin-bottom: 5px;
}

button {
  width: 60%;
  margin: 0 auto;
}
```

**Note:** If you want to test these examples across a number of browsers simultaneously, you can [find it live here](https://mdn.github.io/learning-area/html/forms/styling-examples/ugly-controls.html) (also [see here for the source code](https://github.com/mdn/learning-area/blob/master/html/forms/styling-examples/ugly-controls.html)).

Also bear in mind that we've added some JavaScript to the page that lists the files selected by the file picker, below the control itself.  This is a simplified version of the example found on the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file#examples) reference page.

As you can see, we've done fairly well at getting these to look uniform across modern browsers.

We've applied some global normalizing CSS to all the controls and  their labels, to get them to size in the same way, adopt their parent  font, etc., as mentioned in the previous article:

```
button, label, input, select, progress, meter {
  display: block;
  font-family: inherit;
  font-size: 100%;
  margin: 0;
  box-sizing: border-box;
  width: 100%;
  padding: 5px;
  height: 30px;
}
```

We also added some uniform shadow and rounded corners to the controls on which it made sense:

```
input[type="text"], input[type="datetime-local"], input[type="color"], select {
  box-shadow: inset 1px 1px 3px #ccc;
  border-radius: 5px;
}
```

on other controls like range types, progress  bars, and meters they just add an ugly box around the control area, so  it doesn't make sense.

Let's talk about some specifics of each of these types of control, highlighting difficulties along the way.

### [Selects and datalists](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#selects_and_datalists)

In modern browsers, selects and datalists are generally not too bad to  style provided you don't want to vary the look and feel too much from  the defaults.

We've managed to get the basic look of the boxes looking pretty uniform and consistent. The datalist control is `<input type="text">` anyway, so we knew this wouldn't be a problem.

Two things are slightly more problematic. First of all, the select's  "arrow" icon that indicates it is a dropdown differs across browsers. It also tends to change if you increase the size of the select box, or  resize in an ugly fashion. To fix this in our example we first used our  old friend `appearance: none` to get rid of the icon altogether:

```
select {
  -webkit-appearance: none;
  appearance: none;
}
```

We then created our own icon using generated content. We put an extra wrapper around the control, because [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)/[`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) don't work on `<select>` elements (this is because generated content is placed relative to an  element's formatting box, but form inputs work more like replaced  elements — their display is generated by the browser and put in place —  and therefore don't have one):

```
<div class="select-wrapper"><select id="select" name="select">
  <option>Banana</option>
  <option>Cherry</option>
  <option>Lemon</option>
</select></div>
```

We then use generated content to generate a little down arrow, and put it in the right place using positioning:

```
.select-wrapper {
  position: relative;
}

.select-wrapper::after {
  content: "▼";
  font-size: 1rem;
  top: 6px;
  right: 10px;
  position: absolute;
}
```

The second, slightly more major issue is that you  don't have control over the box that appears containing the options when you click on the `<select>` box to open it. You'll  notice that the options don't inherit the font set on the parent. You  also can't consistently set things like spacing and colors. For example, Firefox will apply [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) and [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) when set on the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements, Chrome won't. Neither of them will apply any kind of spacing (e.g. [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)). The same is also true of the autocomplete list that appears for the datalist.

If you really need full control over the option styling, you'll have  to either use some kind of library to generate a custom control, or  build your own custom control, or in the case of select use the `multiple` attribute, which makes all the options appear on the page, sidestepping this particular problem:

```
<select id="select" name="select" multiple>
  ...
</select>
```

Of course, this might also not fit in with the design you are going for, but it's worth noting!

### [Date input types](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#date_input_types)

The date/time input types ([`datetime-local`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local), [`time`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/time), [`week`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/week), [`month`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/month)) all have the same major associated issue. The actual containing box is  as easy to style as any text input, and what we've got in this demo  looks fine.

However, the internal parts of the control (e.g. the popup calendar  that you use pick a date, the spinner that you can use to  increment/decrement values) are not stylable at all, and you can't get  rid of them using `appearance: none;`. If you really need  full control over the styling, you'll have to either use some kind of  library to generate a custom control, or build your own.

**Note:** It is worth mentioning [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/number) here too — this also has a spinner that you can use to  increment/decrement values, so potentially suffers from the same  problem. However, in the case of the `number` type the data being collected is simpler, and it is easy to just use a `text` input type instead if desired (or `tel` if you want mobile browsers to show the numeric keypad).

### [Range input types](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#range_input_types)

[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range) is annoying to style. You can use something like the following to  remove the default slider track completely and replace it with a custom  style (a thin red track, in this case):

```
input[type="range"] {
  appearance: none;
  -webkit-appearance: none;
  background: red;
  height: 2px;
  padding: 0;
  outline: 1px solid transparent;
}
```

However, it is very difficult to  customize the style of the range control's drag handle — to get full  control over range styling you'll need to use a whole bunch of complex  CSS code, including multiple non-standard, browser-specific  pseudo-elements. Check out [Styling Cross-Browser Compatible Range Inputs with CSS](https://css-tricks.com/styling-cross-browser-compatible-range-inputs-css/) on CSS tricks for a detailed write up of what's needed.

### [Color input types](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#color_input_types)

Input controls of type color are not too bad. In supporting browsers, they  tend to just give you a block of solid color with a small border.

You can remove the border, just leaving the block of color, using something like this:

```
input[type="color"] {
  border: 0;
  padding: 0;
}
```

However, a custom solution is the only way to get anything significantly different.

### [File input types](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#file_input_types)

Inputs of type file are generally OK — as you saw in our example, it is fairly easy to create something that fits in OK with the rest of the page —  the output line that is part of the control will inherit the parent font if you tell the input to do so, and you can style the custom list of  file names and sizes in any way you want; we created it after all.

The only problem with file pickers is that the button provided that  you press to open the file picker is completely unstylable — it can't be sized or colored, and it won't even accept a different font.

One way around this is to take advantage of the fact that if you have a label associated with a form control, clicking the label will  activate the control. So you could hide the actual form input using  something like this:

```
input[type="file"] {
  height: 0;
  padding: 0;
  opacity: 0;
}
```

And then style the label to act like a button, which when pressed will open the file picker as expected:

```
label[for="file"] {
  box-shadow: 1px 1px 3px #ccc;
  background: linear-gradient(to bottom, #eee, #ccc);
  border: 1px solid rgb(169, 169, 169);
  border-radius: 5px;
  text-align: center;
  line-height: 1.5;
}

label[for="file"]:hover {
  background: linear-gradient(to bottom, #fff, #ddd);
}

label[for="file"]:active {
  box-shadow: inset 1px 1px 3px #ccc;
}
```

You can see the result of the above CSS styling in the below live example (see also [styled-file-picker.html](https://mdn.github.io/learning-area/html/forms/styling-examples/styled-file-picker.html) live, and the [source code](https://github.com/mdn/learning-area/blob/master/html/forms/styling-examples/styled-file-picker.html)).

<iframe src="https://mdn.github.io/learning-area/html/forms/styling-examples/styled-file-picker.html" loading="lazy" width="100%" height="200"></iframe>

### [Meters and progress bars](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#meters_and_progress_bars)

[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meter) and [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) are possibly the worst of the lot. As you saw in the earlier example,  we can set them to a desired width relatively accurately. But beyond  that, they are really difficult to style in any way. They don't handle  height settings consistently between each other and between browsers,  you can color the background, but not the foreground bar, and setting `appearance: none` on them makes things worse, not better.

It is easier to just create your own custom solution for these  features, if you want to be able to control the styling, or use a  third-party solution such as [progressbar.js](https://kimmobrunfeldt.github.io/progressbar.js/#examples).

### [The road to nicer forms: useful libraries and polyfills](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#the_road_to_nicer_forms_useful_libraries_and_polyfills)

As we've mentioned above a few times, if you want to gain full control  over the "ugly" control types, you have no choice but to rely on  JavaScript. In the article [How to build custom form controls](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls) you will see how to do it on your own, but there are some very useful libraries out there that can help you:

- [Uni-form](https://github.com/draganbabic/uni-form) is a framework that standardizes form markup, styling it with CSS. It  also offers a few additional features when used with jQuery, but that's  optional.
- [Formalize](https://formalize.me/) is an extension to common JavaScript frameworks (such as jQuery, Dojo,  YUI, etc.) that helps to normalize and customize your forms.
- [Niceforms](https://www.emblematiq.com/lab/niceforms/) is a standalone JavaScript method that provides complete customization  of web forms. You can use some of the built in themes, or create your  own.

The following libraries aren't just about forms, but they have very interesting features for dealing with HTML forms:

- [jQuery UI](https://jqueryui.com/) offers customizable widgets such as date pickers (with special attention given to accessibility).
- [Twitter Bootstrap](https://twitter.github.com/bootstrap/base-css.html#forms) can help normalize your forms.
- [WebShim](https://afarkas.github.io/webshim/demos/) is a huge tool that can help you deal with browser HTML5 support. The web forms part can be really helpful.

Remember that CSS and JavaScript can have side effects. So if you  choose to use one of those libraries, you should always have robust  fallback HTML in case the script fails. There are many reasons why  scripts may fail, especially in the mobile world, and you need to design your Web site or app to handle these cases as well as possible.

## UI伪类

In the previous articles, we covered the styling of various form controls, in a general manner. This included some usage of  pseudo-classes, for example using `:checked` to target a  checkbox only when it is selected. In this article, we will explore in  detail the different UI pseudo-classes available to us in modern  browsers for styling forms in different states.

| Prerequisites: | Basic computer literacy, and a basic understanding of        [HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML) and        [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps), including general        knowledge of        [pseudo-classes and pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements). |
| -------------- | ------------------------------------------------------------ |
| Objective:     | To understand what parts of forms are hard to style, and why; to learn        what can be done to customize them. |

### [What pseudo-classes do we have available?](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#what_pseudo-classes_do_we_have_available)

The original pseudo-classes available to us (as of [CSS 2.1](https://www.w3.org/TR/CSS21/selector.html#dynamic-pseudo-classes)) that are relevant to forms are:

- [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover): Selects an element only when it is being hovered over by a mouse pointer.
- [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus): Selects an element only when it is focused (i.e. by being tabbed to via the keyboard).
- ​    [`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active): selects an element only when it is being activated (i.e. while it is being clicked on, or when the    Return    /    Enter    key is being pressed down in the case of a keyboard activation).  

These basic pseudo-classes should be familiar to you now. More recently, the [CSS Selector Level 3](https://www.w3.org/TR/css3-selectors/) and [CSS Basic UI Level 3](https://dev.w3.org/csswg/css3-ui/#pseudo-classes) added more pseudo-classes related to HTML forms that provide several  other useful targeting conditions that you can take advantage of. We'll  discuss these in more detail in the sections below, but briefly, the  main ones we'll be looking at are:

- [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required) and [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional): Targets required or optional form controls.
- [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid), and [`:in-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range): Target form controls that are valid/invalid according to form validation constraints set on them, or in-range/out-of-range.
- [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled) and [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled), and [`:read-only`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only) and [`:read-write`](https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write): Target enabled or disabled form controls (e.g. with the `disabled` HTML attribute set), and read-write or read-only form controls (e.g. with the `readonly` HTML attribute set).
- [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked), [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate), and [`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default): Respectively target checkboxes and radio buttons that are checked, in  an indeterminate state (neither checked or not checked), and the default selected option when the page loads (e.g. an [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox) with the `checked` attribute set, or an [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) element with the `selected` attribute set).

There are many others too, but the ones listed above are the most  obviously useful. Some of the others are aimed at solving very specific  niche problems, or not very well supported in browsers yet. The ones  listed above all have pretty good browser support, but of course, you  should test your form implementations carefully to make sure they work  for your target audience.

**Note:** A number of the pseudo-classes discussed  here are concerned with styling form controls based on their validation  state (is their data valid, or not?) You'll learn much more about  setting and controlling validation constraints in our next article — [Client-side form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) — but for now we'll keep things simple with regards to form validation, so it doesn't confuse things.

### [Styling inputs based on whether they are required or not](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#styling_inputs_based_on_whether_they_are_required_or_not)

One of the most basic concepts with regards to client-side form validation  is whether a form input is required (it has to be filled in before the  form can be submitted) or optional.

[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), and [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements have a `required` attribute available which, when set, means that you have to fill in  that control before the form will successfully submit. For example:

```
<form>
  <fieldset>
    <legend>Feedback form</legend>
    <div>
      <label for="fname">First name: </label>
      <input id="fname" name="fname" type="text" required>
    </div>
    <div>
      <label for="lname">Last name: </label>
      <input id="lname" name="lname" type="text" required>
    </div>
    <div>
      <label for="email">Email address (include if you want a response): </label>
      <input id="email" name="email" type="email">
    </div>
    <div><button>Submit</button></div>
  </fieldset>
</form>
```

Here, the first name and last name are required, but the email address is optional.

You can match these two states using the [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required) and [`:optional`](https://developer.mozilla.org/en-US/docs/Web/CSS/:optional) pseudo-classes. For example, if we apply the following CSS to the above HTML:

```
input:required {
  border: 1px solid black;
}

input:optional {
  border: 1px solid silver;
}
```

The required controls would have a black border, and the optional control will have a silver border, like so:

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/basic-required-optional.html" loading="lazy" width="100%" height="400"></iframe>

You can also try submitting the form without filling it in, to see  the client-side validation error messages browsers give you by default.

The above form isn't bad, but it isn't great either. For a start, we  are signalling required versus optional status using color alone, which  isn't great for colorblind people. Second, the standard convention on  the web for required status is an asterisk (*), or the word "required"  being associated with the controls in question.

In the next section, we'll look at a better example of indicating required fields using `:required`, which also digs into using generated content.

**Note:** You'll probably not find yourself using the `:optional` pseudo-class very often. Form controls are optional by default, so you  could just do your optional styling by default, and add styles on top  for required controls.

**Note:** If one radio button in a same-named group of radio buttons has the `required` attribute, all the radio buttons will be invalid until one is selected, but only the one with the attribute assigned will actually match [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)**.**

### [Using generated content with pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#using_generated_content_with_pseudo-classes)

In previous articles, we've seen the usage of [generated content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Generated_Content), but we thought now would be a good time to talk about it in a bit more detail.

The idea is that we can use the [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) and [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-elements along with the [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property to make a chunk of content appear before or after the affected element. The chunk of content is not added to the DOM, so is invisible  to screenreaders; it is part of the document's styles. Because it is a  pseudo element, it can be targeted with styles in the same way that any  actual DOM node can.

This is really useful when you want to add a visual indicator to an  element, such as a label or icon, but don't want it to be picked up by  assistive technologies. For example, in our [custom radio buttons example](https://mdn.github.io/learning-area/html/forms/styling-examples/radios-styled.html), we use generated content to handle the placement and animation of the inner circle when a radio button is selected:

```
input[type="radio"]::before {
  display: block;
  content: " ";
  width: 10px;
  height: 10px;
  border-radius: 6px;
  background-color: red;
  font-size: 1.2em;
  transform: translate(3px, 3px) scale(0);
  transform-origin: center;
  transition: all 0.3s ease-in;
}

input[type="radio"]:checked::before {
  transform: translate(3px, 3px) scale(1);
  transition: all 0.3s cubic-bezier(0.25, 0.25, 0.56, 2);
}
```

This is really useful — screenreaders  already let their users know when a radio button or checkbox they  encounter is checked/selected, so you don't want them to read out  another DOM element that indicates selection — that could be confusing.  Having a purely visual indicator solves this problem.

**Note:** This also shows how you can combine a pseudo-class and pseudo-element if required.

Back to our required/optional example from before, this time we'll  not alter the appearance of the input itself — we'll use generated  content to add an indicating label ([see it live here](https://mdn.github.io/learning-area/html/forms/pseudo-classes/required-optional-generated.html), and see the [source code here](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/required-optional-generated.html)).

First of all, we'll add a paragraph to the top of the form to say what you are looking for:

```
<p>Required fields are labelled with "required".</p>
```

Screenreader users will get "required" read out as an extra bit of information when they get to each required input, which sighted users will get our label.

Since form inputs don't directly support having generated content put on them (this is because generated content is placed relative to an  element's formatting box, but form inputs work more like replaced  elements and therefore don't have one), we will add an empty [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) to hang the generated content on:

```
<div>
  <label for="fname">First name: </label>
  <input id="fname" name="fname" type="text" required>
  <span></span>
</div>
```

The immediate problem with this was that the span  was dropping onto a new line below the input because the input and label are both set with `width: 100%`. To fix this we style the parent `<div>` to become a flex container, but also tell it to wrap its contents onto new lines if the content becomes too long:

```
fieldset > div {
  margin-bottom: 20px;
  display: flex;
  flex-flow: row wrap;
}
```

The effect this has is that the label and input sit on separate lines because they are both `width: 100%`, but the `<span>` has a width of 0 so can sit on the same line as the input.

Now onto the generated content. We create it using this CSS:

```
input + span {
  position: relative;
}

input:required + span::after {
  font-size: 0.7rem;
  position: absolute;
  content: "required";
  color: white;
  background-color: black;
  padding: 5px 10px;
  top: -26px;
  left: -70px;
}
```

We set the `<span>` to `position: relative` so that we can set the generated content to `position: absolute` and position it relative to the `<span>` rather than the <body> (The generated content acts as though it  is a child node of the element it is generated on, for the purposes of  positioning).

Then we give the generated content the content "required", which is  what we wanted our label to say, and style and position it as we want.  The result is seen below.

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/required-optional-generated.html" loading="lazy" width="100%" height="430"></iframe>

### [Styling controls based on whether their data is valid](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#styling_controls_based_on_whether_their_data_is_valid)

The other really important, fundamental concept in form validation is  whether a form control's data is valid or not (in the case of numerical  data, we can also talk about in-range and out-of-range data). Form  controls with [constraint limitations](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation) can be targeted based on these states.

### [:valid and :invalid](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#valid_and_invalid)

You can target form controls using the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) pseudo-classes. Some points worth bearing in mind:

- Controls with no constraint validation will always be valid, and therefore matched with `:valid`.
- Controls with `required` set on them that have no value are counted as invalid — they will be matched with `:invalid` and `:required`.
- Controls with built-in validation, such as `<input type="email">` or `<input type="url">` are (matched with) `:invalid` when the data entered into them does not match the pattern they are looking for (but they are valid when empty).
- Controls whose current value is outside the range limits specified by the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min) and [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max) attributes are (matched with) `:invalid`, but also matched by [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range), as you'll see later on.
- There are some other ways to make an element matched by `:valid`/`:invalid`, as you'll see in the [Client-side form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation) article. But we'll keep things simple for now.

Let's go in and look at a simple example of `:valid`/`:invalid` (see [valid-invalid.html](https://mdn.github.io/learning-area/html/forms/pseudo-classes/valid-invalid.html) for the live version, and also check out the [source code](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/valid-invalid.html)).

As in the previous example, we've got extra `<span>`s to generate content on, which we'll use to provide indicators of valid/invalid data:

```
<div>
  <label for="fname">First name *: </label>
  <input id="fname" name="fname" type="text" required>
  <span></span>
</div>
```

To provide these indicators, we use the following CSS:

```
input + span {
  position: relative;
}

input + span::before {
  position: absolute;
  right: -20px;
  top: 5px;
}

input:invalid {
  border: 2px solid red;
}

input:invalid + span::before {
  content: '✖';
  color: red;
}

input:valid + span::before {
  content: '✓';
  color: green;
}
```

As before, we set the `<span>`s to `position: relative` so that we can position the generated content relative to them. We then absolutely position different generated content depending on whether  the form's data is valid or invalid — a green check or a red cross,  respectively. To add a bit of extra urgency to the invalid data, we've  also given the inputs a thick red border when invalid.

**Note:** We've used `::before` to add these labels, as we were already using `::after` for the "required" labels.

You can try it below:

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/valid-invalid.html" loading="lazy" width="100%" height="430"></iframe>

Notice how the required text inputs are invalid when empty, but valid when they have something filled in. The email input on the other hand  is valid when empty, as it is not required, but invalid when it contains something that is not a proper email address.

### [In-range and out-of-range data](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#in-range_and_out-of-range_data)

As we hinted at above, there are two other related pseudo-classes to consider — [`:in-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range) and [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range). These match numeric inputs where range limits are specified by the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-min) and [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-max), when their data is inside or outside the specified range, respectvely.

**Note:** Numeric input types are `date`, `month`, `week`, `time`, `datetime-local`, `number`, and `range`.

It is worth noting that inputs whose data is in-range will also be matched by the `:valid` pseudo-class and inputs whose data is out-of-range will also be matched by the `:invalid` pseudo-class. So why have both? The issue is really one of semantics —  out-of-range is a more specific type of invalid communication, so you  might want to provide a different message for out-of-range inputs, which will be more helpful to users than just saying "invalid". You might  even want to provide both.

Let's look at an example that does exactly this. Our [out-of-range.html](https://mdn.github.io/learning-area/html/forms/pseudo-classes/out-of-range.html) demo (see also the [source code](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/out-of-range.html)) builds on top of the previous example to provide out-of-range messages  for the numeric inputs, as well as saying whether they are required.

The numeric input looks like this:

```
<div>
  <label for="age">Age (must be 12+): </label>
  <input id="age" name="age" type="number" min="12" max="120" required>
  <span></span>
</div>
```

And the CSS looks like this:

```
input + span {
  position: relative;
}

input + span::after {
  font-size: 0.7rem;
  position: absolute;
  padding: 5px 10px;
  top: -26px;
}

input:required + span::after {
  color: white;
  background-color: black;
  content: "Required";
  left: -70px;
}

input:out-of-range + span::after {
  color: white;
  background-color: red;
  width: 155px;
  content: "Outside allowable value range";
  left: -182px;
}
```

This is a similar story to what we had before in the `:required` example, except that here we've split out the declarations that apply to any `::after` content into a separate rule, and given the separate `::after` content for `:required` and `:out-of-range` states their own content and styling. You can try it here:

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/out-of-range.html" loading="lazy" width="100%" height="430"></iframe>

It is possible for the number input to be both required and out-of-range at the same time, so what happens then? Because the `:out-of-range` rule appears later in the source code than the `:required` rule, the [cascade rules](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance#understanding_the_cascade) come into play, and the out of range message is shown.

This works quite nicely — when the page first loads, "Required" is  shown, along with a red cross and border. When you've typed in a valid  age (i.e. in the range of 12-120), the input turns valid. If however,  you then change the age entry to one that is out of range, the "Outside  allowable value range" message then pops up in place of "Required".

**Note:** To enter an invalid/out-of-range value,  you'll have to actually focus the form and type it in using the  keyboard. The spinner buttons won't let you increment/decrement the  value outside the allowable range.

### [Styling enabled and disabled inputs, and read-only and read-write](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#styling_enabled_and_disabled_inputs_and_read-only_and_read-write)

An enabled element is an element that can be activated; it can be  selected, clicked on, typed into, etc. A disabled element on the other  hand cannot be interacted with in any way, and its data isn't even sent  to the server

These two states can be targeted using [`:enabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled) and [`:disabled`](https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled). Why are disabled inputs useful? Well, sometimes if some data does not  apply to a certain user, you might not even want to submit that data  when they submit the form. A classic example is a shipping form —  commonly you'll get asked if you want to use the same address for  billing and shipping; if so, you can just send a single address to the  server, and might as well just disable the billing address fields.

Let's have a look at an example that does just this. First of all,  the HTML is a simple form containing text inputs, plus a checkbox to  toggle disabling the billing address on and off. The billing address  fields are disabled by default.

```
<form>
  <fieldset id="shipping">
    <legend>Shipping address</legend>
    <div>
      <label for="name1">Name: </label>
      <input id="name1" name="name1" type="text" required>
    </div>
    <div>
      <label for="address1">Address: </label>
      <input id="address1" name="address1" type="text" required>
    </div>
    <div>
      <label for="pcode1">Zip/postal code: </label>
      <input id="pcode1" name="pcode1" type="text" required>
    </div>
  </fieldset>
  <fieldset id="billing">
    <legend>Billing address</legend>
    <div>
      <label for="billing-checkbox">Same as shipping address:</label>
      <input type="checkbox" id="billing-checkbox" checked>
    </div>
    <div>
      <label for="name" class="billing-label disabled-label">Name: </label>
      <input id="name" name="name" type="text" disabled required>
    </div>
    <div>
      <label for="address2" class="billing-label disabled-label">Address: </label>
      <input id="address2" name="address2" type="text" disabled required>
    </div>
    <div>
      <label for="pcode2" class="billing-label disabled-label">Zip/postal code: </label>
      <input id="pcode2" name="pcode2" type="text" disabled required>
    </div>
  </fieldset>

  <div><button>Submit</button></div>
</form>
```

Now onto the CSS. The most relevant parts of this example are as follows:

```
input[type="text"]:disabled {
    background: #eee;
    border: 1px solid #ccc;
}

.disabled-label {
  color: #aaa;
}
```

We've directly selected the inputs we want to disable using `input[type="text"]:disabled`, but we also wanted to gray out the corresponding text labels. These  weren't quite as easy to select, so we've used a class to provide them  with that styling.

Now finally, we've used some JavaScript to toggle the disabling of the billing address fields:

```
// Wait for the page to finish loading
document.addEventListener('DOMContentLoaded', function () {

  // Attach `change` event listener to checkbox
  document.getElementById('billing-checkbox').addEventListener('change', toggleBilling);
}, false);

function toggleBilling() {
  // Select the billing text fields
  let billingItems = document.querySelectorAll('#billing input[type="text"]');
  // Select the billing text labels
  let billingLabels = document.querySelectorAll('.billing-label');

  // Toggle the billing text fields and labels
  for (let i = 0; i < billingItems.length; i++) {
    billingItems[i].disabled = !billingItems[i].disabled;

    if(billingLabels[i].getAttribute('class') === 'billing-label disabled-label') {
      billingLabels[i].setAttribute('class', 'billing-label');
    } else {
      billingLabels[i].setAttribute('class', 'billing-label disabled-label');
    }
  }
}
```

It uses the [`change` event](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event) to let the user enable/disable the billing fields, and toggle the styling of the associated labels.

You can see the example in action below (also [see it live here](https://mdn.github.io/learning-area/html/forms/pseudo-classes/enabled-disabled-shipping.html), and see the [source code](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/enabled-disabled-shipping.html)):

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/enabled-disabled-shipping.html" loading="lazy" width="100%" height="600"></iframe>

### [Read-only and read-write](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#read-only_and_read-write)

In a similar manner to `:disabled` and `:enabled`, the `:read-only` and `:read-write` pseudo-classes target two states that form inputs toggle between.  Read-only inputs have their values submitted to the server, but the user can't edit them, whereas read-write means they can be edited — their  default state.

An input is set to read-only using the `readonly`  attribute. As an example, imagine a confirmation page where the  developer has sent the details filled in on previous pages over to this  page, with the aim of getting the user to check them all in one place,  add any final data that is needed, and then confirm the order by  submitting. At this point, all the final form data can be sent to the  server in one go.

Let's look at what a form might look like (see [readonly-confirmation.html](https://mdn.github.io/learning-area/html/forms/pseudo-classes/readonly-confirmation.html) for the live example; also [see the source code](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/readonly-confirmation.html)).

A fragment of the HTML is as follows — note the readonly attribute:

```
<div>
  <label for="name">Name: </label>
  <input id="name" name="name" type="text"
         value="Mr Soft" readonly>
</div>
```

If you try the live example, you'll see that the top set of form elements are not focusable, however, the values are submitted when the form is submitted. We've styled the form controls  using the `:read-only` and `:read-write` pseudo-classes, like so:

```
input:-moz-read-only, textarea:-moz-read-only,
input:read-only, textarea:read-only {
  border: 0;
  box-shadow: none;
  background-color: white;
}

textarea:-moz-read-write,
textarea:read-write {
  box-shadow: inset 1px 1px 3px #ccc;
  border-radius: 5px;
}
```

Firefox only supported these pseudo-classes  with a prefix up to version 78; at which point it started to support the unprefixed version. The full example looks like so:

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/readonly-confirmation.html" loading="lazy" width="100%" height="660"></iframe>

**Note:** `:enabled` and `:read-write` are two more pseudo-classes that you'll probably rarely use, given that they describe the default states of input elements.

### [Radio and checkbox states — checked, default, indeterminate](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#radio_and_checkbox_states_—_checked_default_indeterminate)

As we've seen in earlier articles in the module, [radio buttons](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio) and [checkboxes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox) can be checked or unchecked. But there are a couple of other states to consider too:

- [`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default): Matches radios/checkboxes that are checked by default, on page load (i.e. by setting the `checked` attribute on them) These match the [`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default) pseudo-class, even if the user unchecks them.
- [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate): When radios/checkboxes are neither checked nor unchecked, they are considered *indeterminate* and will match the [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate) pseudo-class. More on what this means below.

### [:checked](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#checked)

When checked, they will be matched by the [`:checked`](https://developer.mozilla.org/en-US/docs/Web/CSS/:checked) pseudo-class.

The most common use of this is to add a different style onto the  checkbox/radiobutton when it is checked, in cases where you've removed  the system default styling with `appearance: none;` and want to build the styles back up yourself. We saw examples of this in the previous article when we talked about [Using `appearance: none` on radios/checkboxes](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling#using_appearance_none_on_radioscheckboxes).

As a recap, the `:checked` code from our [Styled radio buttons](https://mdn.github.io/learning-area/html/forms/styling-examples/radios-styled.html) example looks like so:

```
input[type="radio"]::before {
  display: block;
  content: " ";
  width: 10px;
  height: 10px;
  border-radius: 6px;
  background-color: red;
  font-size: 1.2em;
  transform: translate(3px, 3px) scale(0);
  transform-origin: center;
  transition: all 0.3s ease-in;
}

input[type="radio"]:checked::before {
  transform: translate(3px, 3px) scale(1);
  transition: all 0.3s cubic-bezier(0.25, 0.25, 0.56, 2);
}
```

You can try it out here:

<iframe src="https://mdn.github.io/learning-area/html/forms/styling-examples/radios-styled.html" loading="lazy" width="100%" height="200"></iframe>

Basically, we build the styling for the radio button "inner circle" using the `::before` pseudo element, but set a `scale(0)` [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) on it. We then use a [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) to make it nicely animate into view when the radio is selected/checked. The advantage of using a transform rather than transitioning [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)/[`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) is that you can use [`transform-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin) to make it grow from the center of the circle, rather than having it appear to grow from the circle's corner.

### [:default and :indeterminate](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#default_and_indeterminate)

As mentioned above, the [`:default`](https://developer.mozilla.org/en-US/docs/Web/CSS/:default) pseudo-class matches radios/checkboxes that are checked by default, on  page load, even when unchecked. This could be useful for adding an  indicator to a list of options to remind the user what the defaults (or  starting options) were, in case they want to reset their choices.

Also mentioned above radios/checkboxes will be matched by the [`:indeterminate`](https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate) pseudo-class when they are in a state where they are neither checked  nor unchecked. But what does this mean? Elements that are indeterminate  include:

- [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio) inputs, when all radio buttons in a same-named group are unchecked
- [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox) inputs whose `indeterminate` property is set to `true` via JavaScript
- [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) elements that have no value.

This isn't something you'll likely use very often. One use case could be an indicator to tell users that they really need to select a radio  button before they move on.

Let's look at a couple of modified versions of the previous example  that remind the user what the default option was, and style the radio  buttons when indeterminate. Both of these have the following HTML  structure for the inputs:

```
<p>
  <input type="radio" name="fruit" value="cherry" id="cherry">
  <label for="cherry">Cherry</label>
  <span></span>
</p>
```

For the `:default` example, we've added the `checked` attribute to the middle radio button input, so it will be selected by  default when loaded. We then style this with the following CSS:

```
input ~ span {
  position: relative;
}

input:default ~ span::after {
  font-size: 0.7rem;
  position: absolute;
  content: "Default";
  color: white;
  background-color: black;
  padding: 5px 10px;
  right: -65px;
  top: -3px;
}
```

This provides a little "Default" label on the one  the was originally selected when the page loaded. Note here we are using the general sibling combinator (`~`) rather than the adjacent sibling combinator (`+`) — we need to do this because the `<span>` does not come right after the `<input>` in the source order.

See the live result below:

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/radios-checked-default.html" loading="lazy" width="100%" height="200"></iframe>

**Note:** You can also find the example live on GitHub at [radios-checked-default.html](https://mdn.github.io/learning-area/html/forms/pseudo-classes/radios-checked-default.html) (also see the [source code](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/radios-checked-default.html).)

For the `:indeterminate` example, we've got no default  selected radio button — this is important — if there was, then there  would be no indeterminate state to style. We style the indeterminate  radio buttons with the following CSS:

```
input[type="radio"]:indeterminate {
  border: 2px solid red;
  animation: 0.4s linear infinite alternate border-pulse;
}

@keyframes border-pulse {
  from {
    border: 2px solid red;
  }

  to {
    border: 6px solid red;
  }
}
```

This creates a fun little animated border on the radio buttons, which hopefully indicates that you need to select one of them!

See the live result below:

<iframe src="https://mdn.github.io/learning-area/html/forms/pseudo-classes/radios-checked-indeterminate.html" loading="lazy" width="100%" height="200"></iframe>

**Note:** You can also find the example live on GitHub at [radios-checked-indeterminate.html](https://mdn.github.io/learning-area/html/forms/pseudo-classes/radios-checked-indeterminate.html) (also see the [source code](https://github.com/mdn/learning-area/blob/master/html/forms/pseudo-classes/radios-checked-indeterminate.html).)

**Note:** You can find an [interesting example involving `indeterminate` states](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox#indeterminate_state_checkboxes) on the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox) reference page.

### [More pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes#more_pseudo-classes)

There are a number of other pseudo-classes of interest, and we don't have  space to write about them all in detail here. Let's talk about a few  more that you should take the time to investigate.

The following are fairly well-supported in modern browsers:

- The [`:focus-within`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within) pseudo-class matches an element that has received focus or *contains* an element that has received focus. This is useful if you want a whole  form to highlight in some way when an input inside it is focused.
- The [`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible) pseudo-class matches focused elements that received focus via keyboard  interaction (rather than touch or mouse) — useful if you want to show a  different style for keyboard focus compared to mouse (or other) focus.
- The [`:placeholder-shown`](https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown) pseudo-class matches [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) and [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) elements that have their placeholder showing (i.e. the contents of the [`placeholder`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/placeholder) attribute) because the value of the element is empty.

The following are also interesting, but as yet not well-supported in browsers:

- The [`:blank`](https://developer.mozilla.org/en-US/docs/Web/CSS/:blank) pseudo-class selects empty form controls. [`:empty`](https://developer.mozilla.org/en-US/docs/Web/CSS/:empty) also matches elements that have no children, like [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), but it is more general — it also matches other empty elements like [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br) and [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr). `:empty` has reasonable browser support; the `:blank` pseudo-class's specification is not yet finished, so it not yet supported in any browser.
- The [`:user-invalid`](https://drafts.csswg.org/selectors-4/#user-invalid-pseudo) pseudo-class, when supported, will be similar to [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid), but with better user experience. If the value is valid when the input receives focus, the element may match `:invalid` as the user enters data if the value is temporarily invalid, but will only match `:user-invalid` when the element loses focus. If the value was originally invalid, it will match both `:invalid` and `:user-invalid` for the whole duration of the focus. In a similar manner to `:invalid`, it will stop matching `:user-invalid` if the value does become valid.

## 表单数据校验

### [什么是表单数据校验？](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#什么是表单数据校验？)

访问任何一个带注册表单的网站，你都会发现，当你提交了没有输入符合预期格式的信息的表单时，注册页面都会给你一个反馈，这些信息可能看起来像下面这样的：

- “该字段是必填的”（该字段不能留空）
- “请输入你的电话号码，它的格式是：xxx-xxxx”（它要求你输入的数据格式为三个数字接一个横杠，然后再接着是四个数字）
- “请输入一个合法的邮箱地址”（如果你输入的数据不符合“somebody@example.com“的邮箱格式）
- “你的密码长度应该是8至30位的，并且至少应该包含一个大写字母、一个符号以及一个数字”

这就是**表单校验**  —— 当你向 Web 应用输入数据时，应用会验证你输入的数据是否是正确的。如果验证通过，应用允许提交这些数据到服务器并储存到数据库中（通常情况下），如果验证未通过，则 Web 应用会提示你有错误的数据，并且一般都会明确的告诉你错误发生在哪里。表单校验可以通过许多不同的方式实现。

**译者注**：下面一段在英文原文中已经删除

(事实上，没有人愿意填写表单 —— 很多证据表明，用户对填写表单这件事情都感到很烦恼，如果他们在填写表单的过程中遇到一些自己无法理解的问题，通常都会导致他们直接离开你的 Web 应用，简而言之，[表单是一个很烦人的东西](https://www.slideshare.net/jwegesin/forms-suck/)。)

我们希望把填写表单变的越简单越好。那么，为什么我们还坚持进行表单的数据校验呢？这有三个最主要的原因：

- **我们希望以正确的格式获取到正确的数据** —— 如果我们的用户数据以不正确的格式存储，或者他们没有输入正确的信息/完全省略信息，我们的应用程序将无法正常运行。
- **我们希望保护我们的用户** ——强制用户输入安全的密码，有利于保护他们的账户信息。
- **我们希望保护我们自己** —— 恶意用户有很多通过滥用应用中缺乏保护的表单破坏应用的方法（具体请参见[网站安全](https://developer.mozilla.org/zh-CN/docs/learn/Server-side/First_steps/Website_security)）。

警告： 永远不要相信从客户端传递到服务器的数据。 即使您的表单正确验证并防止输入格式错误，恶意用户仍然可以更改网络请求。

### [不同类型的表单数据校验](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#不同类型的表单数据校验)

在 Web 中，你可能会遇见各种不同的表单校验：

- 客户端校验

  发生在浏览器端，表单数据被提交到服务器之前，这种方式相较于服务器端校验来说，用户体验更好，它能实时的反馈用户的输入校验结果，这种类型的校验可以进一步细分成下面这些方式：   

  - **JavaScript** 校验，这是可以完全自定义的实现方式；
  - HTML5 **内置校验**，这不需要 JavaScript ，而且性能更好，但是不能像JavaScript那样可自定义。

- **服务器端校验**则是发生在浏览器提交数据并被服务器端程序接收之后  —— 通常服务器端校验都是发生在将数据写入数据库之前，如果数据没通过校验，则会直接从服务器端返回错误消息，并且告诉浏览器端发生错误的具体位置和原因，服务器端校验不像客户端校验那样有好的用户体验，因为它直到整个表单都提交后才能返回错误信息。但是服务器端校验是你的应用对抗错误/恶意数据的最后防线，在这之后，数据将被持久化至数据库。当今[所有的服务端框架](https://developer.mozilla.org/zh-CN/docs/learn/Server-side/First_steps/Web_frameworks)都提供了数据**校验**与**清洁**功能（让数据更安全）。

在真实的项目开发过程中，开发者一般都倾向于使用客户端校验与服务器端校验的组合校验方式以更好的保证数据的正确性与安全性。

### [使用内置表单数据校验](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#使用内置表单数据校验)

[HTML5](https://developer.mozilla.org/en-US/docs/HTML/HTML5) 一个特别有用的新功能就是，可以在不写一行脚本代码的情况下，即对用户的输入进行数据校验，这都是通过表单元素的[校验属性 (en-US)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation)实现的，这些属性可以让你定义一些规则，用于限定用户的输入，比如某个输入框是否必须输入，或者某个输入框的字符串的最小最大长度限制，或者某个输入框必须输入一个数字、邮箱地址等；还有数据必须匹配的模式。如果表单中输入的数据都符合这些限定规则，那么表示这个表单校验通过，否则则认为校验未通过。

当一个元素校验通过时：

- 该元素将可以通过 CSS 伪类 [`:valid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:valid) 进行特殊的样式化；
- 如果用户尝试提交表单，如果没有其它的控制来阻止该操作（比如JavaScript即可阻止提交），那么该表单的数据会被提交。

如果一个元素未校验通过：

- 该元素将可以通过 CSS 伪类 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) 进行特殊的样式化；
- 如果用户尝试提交表单，浏览器会展示出错误消息，并停止表单的提交。 

### [input 元素的校验约束 — starting simple](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#input_元素的校验约束_—_starting_simple)

在这一节，我们将会看到一些用于\<input>元素校验的HTML5的特性。

让我们用一个简单的例子开始 — 一个可以让你从香蕉或樱桃中选择你最喜欢的水果的input。 这个包含了一个简单的文本[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input) 和一个与之匹配的label，还有一个 submit [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)。你可以在GitHub [fruit-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-start.html)找到源码，在线例子如下:



开始之前，先拷贝一份 `fruit-start.html` 放在你硬盘上的新目录里。

### [required 属性](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#required_属性)

最简单的HTML5校验功能是 [`required`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-required)属性 — 如果要使输入成为必需的，则可以使用此属性标记元素。 当设置此属性时，如果输入为空，该表单将不会提交（并将显示错误消息），输入也将被视为无效。

添加一个 `required` 属性到你的 input 元素, 如下所示:

```html
<form>
  <label for="choose">Would you prefer a banana or cherry?</label>
  <input id="choose" name="i_like" required>
  <button>Submit</button>
</form>
```

同时注意在示例文件中包含的 CSS :

```css
input:invalid {
  border: 2px dashed red;
}

input:valid {
  border: 2px solid black;
}
```

以上样式效果为：在校验失败时 输入框会有一个亮红色的虚线边框, 在校验通过时会有一个更微妙的黑色边框。在以下示例中尝试新的行为：



### [使用正则表达式校验](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#使用正则表达式校验)

另一个常用的校验功能是 [`pattern`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-pattern) 属性, 以 [Regular Expression](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_Expressions) 作为 value 值. 正则表达式 (regex) 是一个可以用来匹配文本字符串中字符的组合的模式，所以它们是理想的表单校验器，也可以支持 JavaScript 中许多其它的用途。

正则表达式相当复杂，我们不打算在本文中详尽地教你。

下面是一些例子，让你对它们的工作原理有个基本的了解：

- `a` — 匹配一个字符`a`(不能匹配 `b`, `aa`等等.)
- `abc` — 匹配 `a`, 其次 `b`, 最后 `c`.
- `a*` — 匹配0个或者多个字符 `a` (`+` 代表至少匹配一个或者多个).
- `[^a]` — 匹配一个字符，但它**不能**是`a`.
- `a|b` — 匹配一个字符 `a` 或者 `b`.
- `[abc]` — 匹配一个字符，它可以是`a`,`b`或`c`.
- `[^abc]` — 匹配一个字符，但它**不可以**是`a`,`b`或`c`.
- `[a-z]` — 匹配字符范围 `a-z`且全部小写 (你可以使用 `[A-Za-z]` 涵盖大小写, 或 `[A-Z]` 来限制必须大写).
- `a.c` — 匹配字符 `a`,中间匹配任意一个字符,最后匹配字符` c`.
- `a{5}` — 匹配字符 `a`五次.
- `a{5,7}` — 匹配字符 `a`五到七次,不能多或者少.

你也可以在这些表达式中使用数字和其他字符, 例如:

- `[ -]` — 匹配一个空格或者虚线.
- `[0-9]` — 匹配数字范围0~9.

你可以任意地组合这些，你可以任意指定不同的部分:

- `[Ll].*k` — 匹配一个大写`L`或者小写的`l`, 之后匹配0个或多个任意类型的字符, 最后匹配一个小写字母 k.
- `[A-Z][A-Za-z' -]+` —  一个大写字母后面跟着匹配一个及以上的大小写字母或者中划线或者撇号或者空格. 这个可以用于校验英语会话中城市或城镇名,  但这需要首字母以大写开头,不包括其他字符，例如来自英国的Manchester, Ashton-under-lyne, 以及Bishop's  Stortford等.
- `[0-9]{3}[ -][0-9]{3}[ -][0-9]{4}` — 简单的匹配一个美国内的电话号码 — 三个数字 0`-`9, 后面跟着一个空格或者中划线, 之后匹配三个数字 0`-`9, 再跟着一个空格或者中划线, 最后跟着四个数字 0`-`9. 但实际情况可能更加复杂,因为有些人会给号码加上括号什么的,这里的表达式只是用来做一个简单的演示.

不管怎么说, 让我们来实现这些例子 — 更新你的html文档表单增加一个 `pattern` 属性, 如下:

```
<form>
  <label for="choose">Would you prefer a banana or a cherry?</label>
  <input id="choose" name="i_like" required pattern="banana|cherry">
  <button>Submit</button>
</form>
```



这个例子中, 该\<input>元素接受两个值中的一个: 字符串 "banana" 或者字符串"cherry".

在这个基础上, 尝试把`pattern` 属性内部的表达式改变成上面的几个例子, 然后看看这些表达式如何影响您可以输入的值以使输入值有效. 尝试写一些你自己设计的,看看它如何工作。尽量让他们与水果有关这样你的例子才会有意义.

**注意:** 一些 \<input>元素类型不需要[`pattern`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-pattern) 属性进行校验. 指定特定 `email` 类型 就会使用匹配电子邮件格式的正则表达式来校验(如果有 [`multiple`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-multiple) 属性请用逗号来分割多个邮箱). 进一步来说, 字段 `url` 类型则会自动校验输入的是否为一个合法的链接.

***注意: 该 \<textarea> 元素不支持[`pattern`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-pattern) 属性.***

### [限制输入的长度](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#限制输入的长度)

所有文本框 ([``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input) 或 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/textarea)) 都可以使用[`minlength`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-minlength) 和 [`maxlength`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-maxlength) 属性来限制长度. 如果输入的字段长度小于 [`minlength`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-minlength) 的值或大于 [`maxlength`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-maxlength) 值则无效. 浏览器通常不会让用户在文本字段中键入比预期更长的值，不过更精细的设置总归是更好的。

在数字条目中 (i.e. `<input type="number">`), 该 [`min`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-min) 和 [`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-max) 属性同样提供校验约束.如果字段的值小于[`min`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-min) 属性的值或大于 [`max`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-max) 属性的值,该字段则无效.

让我来看看另外一个例子. 创建一个 [fruit-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-start.html) 文件副本.

现在删除 `<body>` 元素中的内容, 替换成下面的代码:

```
<form>
  <div>
    <label for="choose">Would you prefer a banana or a cherry?</label>
    <input id="choose" name="i_like" required minlength="6" maxlength="6">
  </div>
  <div>
    <label for="number">How many would you like?</label>
    <input type="number" id="number" name="amount" value="1" min="1" max="10">
  </div>
  <div>
    <button>Submit</button>
  </div>
</form>
```

- 这里我们看到 `text` 条目的属性`minlength` 和 `maxlength` 都为6 — 这 banana 和 cherry的长度都为6. 输入少于这个长度的字符显示无效, 大多浏览器不能输入超过该限制的长度的字符.
- 我们同时也能让 `number` 条目数值限制在 `min` 为 1 和 一个 `max` 为 10 中 — 输入超出范围则显示无效, 并且您将无法使用递增/递减箭头将该值改变到此范围之外。

这里是运行的例子:



**注意**: `<input type="number">` (或者其他类型, 像 `range`) 也可以获取到一个[`step`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-step) 属性, 指定了值在增减过程固定改变的值 (如向上增加和向下减少的按钮).

### [完整的例子](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#完整的例子)

这里就是一个完整的展示 HTML 中使用校验属性的例子:

```
<form>
  <p>
    <fieldset>
      <legend>Title<abbr title="This field is mandatory">*</abbr></legend>
      <input type="radio" required name="title" id="r1" value="Mr"><label for="r1">Mr.</label>
      <input type="radio" required name="title" id="r2" value="Ms"><label for="r2">Ms.</label>
    </fieldset>
  </p>
  <p>
    <label for="n1">How old are you?</label>
    <!-- 这里的pattern属性可以用作不支持number类input浏览器的备用方法
         请注意当与数字输入框一起使用时，支持pattern属性的浏览器会使它沉默失效。
         它仅仅是在这里用作备用 -->
    <input type="number" min="12" max="120" step="1" id="n1" name="age"
           pattern="\d+">
  </p>
  <p>
    <label for="t1">What's your favorite fruit?<abbr title="This field is mandatory">*</abbr></label>
    <input type="text" id="t1" name="fruit" list="l1" required
           pattern="[Bb]anana|[Cc]herry|[Aa]pple|[Ss]trawberry|[Ll]emon|[Oo]range">
    <datalist id="l1">
      <option>Banana</option>
      <option>Cherry</option>
      <option>Apple</option>
      <option>Strawberry</option>
      <option>Lemon</option>
      <option>Orange</option>
    </datalist>
  </p>
  <p>
    <label for="t2">What's your e-mail?</label>
    <input type="email" id="t2" name="email">
  </p>
  <p>
    <label for="t3">Leave a short message</label>
    <textarea id="t3" name="msg" maxlength="140" rows="5"></textarea>
  </p>
  <p>
    <button>Submit</button>
  </p>
</form>
body {
  font: 1em sans-serif;
  padding: 0;
  margin : 0;
}

form {
  max-width: 200px;
  margin: 0;
  padding: 0 5px;
}

p > label {
  display: block;
}

input[type=text],
input[type=email],
input[type=number],
textarea,
fieldset {
/* 需要在基于WebKit的浏览器上对表单元素进行恰当的样式设置 */
  -webkit-appearance: none;

  width : 100%;
  border: 1px solid #333;
  margin: 0;

  font-family: inherit;
  font-size: 90%;

  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

input:invalid {
  box-shadow: 0 0 5px 1px red;
}

input:focus:invalid {
  outline: none;
}
```



### [自定义错误信息](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#自定义错误信息)

正如我们上面所看到的例子, 每次我们提交无效的表单数据时, 浏览器总会显示错误信息. 但是显示的信息取决于你所使用的浏览器.

这些自动生成的错误有两个缺点:

- 没有标准可以让 CSS 来改变他们的界面外观.
- 这依赖于他们使用的浏览器环境, 意味着你可能在这种语言的页面里得到另一种语言的错误提示.

| 浏览器                 | 渲染                                                         |
| ---------------------- | ------------------------------------------------------------ |
| Firefox 17 (Windows 7) | ![Example of an error message with Firefox in French on an English page](https://developer.mozilla.org/files/4329/error-firefox-win7.png) |
| Chrome 22 (Windows 7)  | ![Example of an error message with Chrome in French on an English page](https://developer.mozilla.org/files/4327/error-chrome-win7.png) |
| Opera 12.10 (Mac OSX)  | ![Example of an error message with Opera in French on an English page](https://developer.mozilla.org/files/4331/error-opera-macos.png) |

要自定义这些消息的外观和文本, 你必须使用 JavaScript; 不能使用 HTML 和 CSS 来改变.

HTML5 提供 [constraint validation API](https://www.w3.org/TR/html5/forms.html#the-constraint-validation-api) 来检测和自定义表单元素的状态. 除此之外,他可以改变错误信息的文本. 让我们快速的看一个例子:

```
<form>
  <label for="mail">I would like you to provide me an e-mail</label>
  <input type="email" id="mail" name="mail">
  <button>Submit</button>
</form>
```

在JavaScript 中, 你调用 [`setCustomValidity()`](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation#constraint_api's_element.setcustomvalidity()) 方法:

```
var email = document.getElementById("mail");

email.addEventListener("input", function (event) {
  if (email.validity.typeMismatch) {
    email.setCustomValidity("I expect an e-mail, darling!");
  } else {
    email.setCustomValidity("");
  }
});
```



### [ 使用 JavaScript校验表单](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#使用_javascript校验表单)

如果你想控制原生错误信息的界面外观，或者你想处理不支持HTML内置表单校验的浏览器，则必须使用 Javascript。

### [约束校验的 API](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#约束校验的_api)

越来越多的浏览器支持限制校验API，并且这逐渐变得可靠。这些 API 由成组的方法和属性构成，可在特定的表单元素接口上调用：

- [HTMLButtonElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLButtonElement)
- [HTMLFieldSetElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFieldSetElement)
- [HTMLInputElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
- [HTMLOutputElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOutputElement)
- [HTMLSelectElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement)
- [HTMLTextAreaElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTextAreaElement)

#### 约束校验的 API 及属性

| 属性                       | 描述                                                         |
| -------------------------- | ------------------------------------------------------------ |
| `validationMessage`        | 一个本地化消息，描述元素不满足校验条件时（如果有的话）的文本信息。如果元素无需校验（`willValidate` 为 `false`），或元素的值满足校验条件时，为空字符串。 |
| `validity`                 | 一个 [`ValidityState`](https://developer.mozilla.org/zh-CN/docs/Web/API/ValidityState) 对象，描述元素的验证状态。详见有关可能的验证状态的文章。 |
| `validity.customError`     | 如果元素设置了自定义错误，返回 `true` ；否则返回`false`。    |
| `validity.patternMismatch` | 如果元素的值不匹配所设置的正则表达式，返回 `true`，否则返回 `false`。          当此属性为 `true` 时，元素将命中 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `validity.rangeOverflow`   | 如果元素的值高于所设置的最大值，返回 `true`，否则返回 `false`。          当此属性为 `true` 时，元素将命中 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `validity.rangeUnderflow`  | 如果元素的值低于所设置的最小值，返回 `true`，否则返回 `false`。          当此属性为 `true` 时，元素将命中 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `validity.stepMismatch`    | 如果元素的值不符合 step 属性的规则，返回 `true`，否则返回 `false`。          当此属性为 `true` 时，元素将命中 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `validity.tooLong`         | 如果元素的值超过所设置的最大长度，返回 `true`，否则返回 `false`。          当此属性为 `true` 时，元素将命中 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `validity.typeMismatch`    | 如果元素的值出现语法错误，返回 `true`，否则返回 `false`。          当此属性为 `true` 时，元素将命中 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `validity.valid`           | 如果元素的值不存在校验问题，返回 `true`，否则返回 `false`。          当此属性为 `true` 时，元素将命中 [`:valid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:valid) CSS 伪类，否则命中 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `validity.valueMissing`    | 如果元素设置了 required 属性且值为空，返回 `true`，否则返回 `false`。          当此属性为 true 时，元素将命中  [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) CSS 伪类。 |
| `willValidate`             | 如果元素在表单提交时将被校验，返回 `true`，否则返回 `false`。 |

#### 约束校验 API 的方法

| 方法                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `checkValidity()`                                            | 如果元素的值不存在校验问题，返回 `true`，否则返回 `false`。如果元素校验失败，此方法会触发`invalid (en-US)` 事件。 |
| [`HTMLFormElement.reportValidity()`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLFormElement/reportValidity) | 如果元素或它的子元素控件符合校验的限制，返回 `true` . 当返回为 `false` 时, 对每个无效元素可撤销 `invalid (en-US)` 事件会被唤起并且校验错误会报告给用户 。 |
| `setCustomValidity(*message*)`                               | 为元素添加一个自定义的错误消息；如果设置了自定义错误消息，该元素被认为是无效的，则显示指定的错误。这允许你使用 JavaScript 代码来建立校验失败，而不是用标准约束校验 API 所提供的。这些自定义信息将在向用户报告错误时显示。          如果参数为空，则清空自定义错误。 |

对于旧版浏览器，可以使用 [polyfill（例如 Hyperform](https://hyperform.js.org/)），来弥补其对约束校验 API 支持的不足。既然你已经使用 JavaScript，在您的网站或 Web 应用程序的设计和实现中使用 polyfill 并不是累赘。

#### 使用约束校验 API 的例子

让我们看看如何使用这个 API 来构建自定义错误消息。首先，HTML：

```
<form novalidate>
  <p>
    <label for="mail">
      <span>Please enter an email address:</span>
      <input type="email" id="mail" name="mail">
      <span class="error" aria-live="polite"></span>
    </label>
  </p>
  <button>Submit</button>
</form>
```

这个简单的表单使用 [`novalidate`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-novalidate) 属性关闭浏览器的自动校验；这允许我们使用脚本控制表单校验。但是，这并不禁止对约束校验 API的支持或是以下 CSS 伪类：[`:valid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:valid)、[`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid)、[`:in-range`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:in-range) 、[`:out-of-range`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:out-of-range) 的应用。这意味着，即使浏览器在发送数据之前没有自动检查表单的有效性，您仍然可以自己做，并相应地设置表单的样式。

[`aria-live`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions) 属性确保我们的自定义错误信息将呈现给所有人，包括使用屏幕阅读器等辅助技术的人。

##### CSS

以下 CSS 样式使我们的表单和其错误输出看起来更有吸引力。

```
/* 仅为了使示例更好看 */
body {
  font: 1em sans-serif;
  padding: 0;
  margin : 0;
}

form {
  max-width: 200px;
}

p * {
  display: block;
}

input[type=email]{
  -webkit-appearance: none;

  width: 100%;
  border: 1px solid #333;
  margin: 0;

  font-family: inherit;
  font-size: 90%;

  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

/* 校验失败的元素样式 */
input:invalid{
  border-color: #900;
  background-color: #FDD;
}

input:focus:invalid {
  outline: none;
}

/* 错误消息的样式 */
.error {
  width  : 100%;
  padding: 0;

  font-size: 80%;
  color: white;
  background-color: #900;
  border-radius: 0 0 5px 5px;

  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

.error.active {
  padding: 0.3em;
}
```

##### JavaScript

以下 JavaScript 代码演示如何设置自定义错误校验。

```
// 有许多方式可以获取 DOM 节点；在此我们获取表单本身和
// email 输入框，以及我们将放置错误信息的 span 元素。

var form  = document.getElementsByTagName('form')[0];
var email = document.getElementById('mail');
var error = document.querySelector('.error');

email.addEventListener("input", function (event) {
  // 当用户输入信息时，校验 email 字段
  if (email.validity.valid) {
    // 如果校验通过，清除已显示的错误消息
    error.innerHTML = ""; // 重置消息的内容
    error.className = "error"; // 重置消息的显示状态
  }
}, false);
form.addEventListener("submit", function (event) {
  // 当用户提交表单时，校验 email 字段
  if (!email.validity.valid) {

    // 如果校验失败，显示一个自定义错误
    error.innerHTML = "I expect an e-mail, darling!";
    error.className = "error active";
    // 还需要阻止表单提交事件，以取消数据传送
    event.preventDefault();
  }
}, false);
```

这是运行结果：



约束校验 API 为您提供了一个强大的工具来处理表单校验，让您可以对用户界面进行远超过仅仅使用 HTML 和 CSS所能得到的控制。

### [不使用内建 API 时的表单校验](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#不使用内建_api_时的表单校验)

有时，例如使用旧版浏览器或[自定义小部件](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls)，您将无法（或不希望）使用约束校验API。 在这种情况下，您仍然可以使用 JavaScript 来校验您的表单。 校验表单比起真实数据校验更像是一个用户界面问题。

要校验表单，您必须问自己几个问题：

- 我应该进行什么样的校验？

  你需要确定如何校验你的数据：字符串操作，类型转换，正则表达式等。这取决于你。 只要记住，表单数据一般都是文本，并总是以字符串形式提供给脚本。

- 如果表单校验失败，我该怎么办?

  这显然是一个 UI 问题。 您必须决定表单的行为方式：表单是否发送数据？ 是否突出显示错误的字段？是否显示错误消息？

- 如何帮助用户纠正无效数据?

  为了减少用户的挫折感，提供尽可能多的有用的信息是非常重要的，以便引导他们纠正他们的输入。 您应该提供前期建议，以便他们知道预期的输入是什么以及明确的错误消息。 如果您想深入了解表单校验用户界面要求，那么您应该阅读一些有用的文章：   SmashingMagazine: [Form-Field Validation: The Errors-Only Approach](http://uxdesign.smashingmagazine.com/2012/06/27/form-field-validation-errors-only-approach/)  SmashingMagazine: [Web Form Validation: Best Practices and Tutorials](http://www.smashingmagazine.com/2009/07/07/web-form-validation-best-practices-and-tutorials/)  Six Revision: [Best Practices for Hints and Validation in Web Forms](http://sixrevisions.com/user-interface/best-practices-for-hints-and-validation-in-web-forms/)  A List Apart: [Inline Validation in Web Forms](https://www.alistapart.com/articles/inline-validation-in-web-forms/)  

#### 不使用约束校验API 的例子

为了说明这一点，让我们重构一下前面的例子，以便它可以在旧版浏览器中使用：

```
<form>
  <p>
    <label for="mail">
        <span>Please enter an email address:</span>
        <input type="text" class="mail" id="mail" name="mail">
        <span class="error" aria-live="polite"></span>
    </label>
  <p>
  <!-- Some legacy browsers need to have the `type` attribute
       explicitly set to `submit` on the `button`element -->
  <button type="submit">Submit</button>
</form>
```

正如你所看到的，HTML 几乎是一样的；我们只是关闭了 HTML 校验功能。 请注意，[ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) 是与 HTML5 无关的独立规范。

##### CSS

同样的，CSS也不需要太多的改动， 我们只需将 [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) 伪类变成真实的类，并避免使用不适用于 Internet Explorer 6 的属性选择器。

```
/* 仅为了使示例更好看 */
body {
  font: 1em sans-serif;
  padding: 0;
  margin : 0;
}

form {
  max-width: 200px;
}

p * {
  display: block;
}

input.mail {
  -webkit-appearance: none;

  width: 100%;
  border: 1px solid #333;
  margin: 0;

  font-family: inherit;
  font-size: 90%;

  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

/* 校验失败的元素样式 */
input.invalid{
  border-color: #900;
  background-color: #FDD;
}

input:focus.invalid {
  outline: none;
}

/* 错误消息的样式 */
.error {
  width  : 100%;
  padding: 0;

  font-size: 80%;
  color: white;
  background-color: #900;
  border-radius: 0 0 5px 5px;

  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

.error.active {
  padding: 0.3em;
}
```

##### JavaScript

JavaScript 代码有很大的变化，需要做更多的工作。

```
// 使用旧版浏览器选择 DOM 节点的方法较少
var form  = document.getElementsByTagName('form')[0];
var email = document.getElementById('mail');

// 以下是在 DOM 中访问下一个兄弟元素的技巧
// 这比较危险，很容易引起无限循环
// 在现代浏览器中，应该使用 element.nextElementSibling
var error = email;
while ((error = error.nextSibling).nodeType != 1);

// 按照 HTML5 规范
var emailRegExp = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;

// 许多旧版浏览器不支持 addEventListener 方法
// 这只是其中一种简单的处理方法
function addEvent(element, event, callback) {
  var previousEventCallBack = element["on"+event];
  element["on"+event] = function (e) {
    var output = callback(e);

    // 返回 `false` 来停止回调链，并中断事件的执行
    if (output === false) return false;

    if (typeof previousEventCallBack === 'function') {
      output = previousEventCallBack(e);
      if(output === false) return false;
    }
  }
};

// 现在我们可以重构字段的约束校验了
// 由于不使用 CSS 伪类, 我们必须明确地设置 valid 或 invalid 类到 email 字段上
addEvent(window, "load", function () {
  // 在这里验证字段是否为空（请记住，该字段不是必需的）
  // 如果非空，检查它的内容格式是不是合格的 e-mail 地址
  var test = email.value.length === 0 || emailRegExp.test(email.value);

  email.className = test ? "valid" : "invalid";
});

// 处理用户输入事件
addEvent(email, "input", function () {
  var test = email.value.length === 0 || emailRegExp.test(email.value);
  if (test) {
    email.className = "valid";
    error.innerHTML = "";
    error.className = "error";
  } else {
    email.className = "invalid";
  }
});

// 处理表单提交事件
addEvent(form, "submit", function () {
  var test = email.value.length === 0 || emailRegExp.test(email.value);

  if (!test) {
    email.className = "invalid";
    error.innerHTML = "I expect an e-mail, darling!";
    error.className = "error active";

    // 某些旧版浏览器不支持 event.preventDefault() 方法
    return false;
  } else {
    email.className = "valid";
    error.innerHTML = "";
    error.className = "error";
  }
});
```

该结果如下:



正如你所看到的，建立自己的校验系统并不难。 困难的部分是使其足够通用，以跨平台和任何形式使用它可以创建。 有许多库可用于执行表单校验; 你应该毫不犹豫地使用它们。 这里有一些例子：

- 独立的库（原生 Javascript 实现）：  
  - [Validate.js](http://rickharrison.github.com/validate.js/)
- jQuery 插件:  
  - [Validation](http://bassistance.de/jquery-plugins/jquery-plugin-validation/)
  - [Valid8](http://unwrongest.com/projects/valid8/)

####  远程校验

在某些情况下，执行一些远程校验可能很有用。 当用户输入的数据与存储在应用程序服务器端的附加数据绑定时，这种校验是必要的。  一个应用实例就是注册表单，在这里你需要一个用户名。 为了避免重复，执行一个 AJAX  请求来检查用户名的可用性，要比让先用户发送数据，然后因为表单重复了返回错误信息要好得多。

执行这样的校验需要采取一些预防措施：

- 它要求公开 API 和一些数据；您需要确保它不是敏感数据。
- 网络滞后需要执行异步校验。这需要一些用户界面的工作，以确保如果校验没有适当的执行，用户不会被阻止。

### [结论](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Form_validation#结论)

表单校验并不需要复杂的 JavaScript，但它需要对用户的仔细考虑。 一定要记住帮助您的用户更正他提供的数据。 为此，请务必：

- 显示明确的错误消息。
- 放宽输入格式限制。
- 指出错误发生的位置（特别是在大型表单中）。

## 发送表单数据

### [数据都去哪儿了？](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#数据都去哪儿了？)

在这里，我们将讨论在提交表单时数据会发生什么。

### [客户端/服务器体系结构](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#客户端服务器体系结构)

web基于非常基本的客户端/服务器体系结构，可以总结如下:客户端(通常是web浏览器)向服务器发送请求(大多数情况下是[Apache](https://httpd.apache.org/)、[Nginx](http://nginx.com/)、[IIS](http://www.iis.net/)、[Tomcat](http://tomcat.apache.org/)等web服务器)，使用[HTTP 协议](https://developer.mozilla.org/en-US/docs/Web/HTTP)。服务器使用相同的协议来回答请求。

![A basic schema of the Web client/server architecture](https://developer.mozilla.org/files/4291/client-server.png)

在客户端，HTML表单只不过是一种方便的用户友好的方式，可以配置HTTP请求将数据发送到服务器。这使用户能够提供在HTTP请求中传递的信息。

**注意：**为了更好地了解客户端—服务器架构是如何工作的，请阅读我们的[服务器端网站编程的第一个步骤](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps)模块。

### [在客户端:定义如何发送数据](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#在客户端定义如何发送数据)

[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)元素定义了如何发送数据。它的所有属性都是为了让您配置当用户点击提交按钮时发送的请求。两个最重要的属性是[`action`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-action)和[`method`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-method)。

####  [`action`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-action) 属性

这个属性定义了发送数据要去的位置。它的值必须是一个有效的URL。如果没有提供此属性，则数据将被发送到包含这个表单的页面的URL。

在这个例子中，数据被发送到一个绝对URL —— `http://foo.com`：

```
<form action="http://foo.com">
```

这里，我们使用相对URL——数据被发送到服务器上的不同URL

```
<form action="/somewhere_else">
```

在没有属性的情况下，像下面一样，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form)数据被发送到表单出现的相同页面上：

```
<form>
```

许多较老的页面使用下面的符号表示数据应该被发送到包含表单的相同页面；这是必需的，因为直到HTML5[`action`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-action)属性都需要该符号。现在，这不再需要了。

```
<form action="#">
```

**注意：**可以指定使用HTTPS(安全HTTP)协议的URL。当您这样做时，数据将与请求的其余部分一起加密，即使表单本身是托管在使用HTTP访问的不安全页面上。另一方面，如果表单是在安全页面上托管的，但是您指定了一个不安全的HTTP URL，它带有[`action`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-action)属性，所有的浏览器都会在每次尝试发送数据时向用户显示一个安全警告，因为数据不会被加密。

####  [`method`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-method)属性

该属性定义了如何发送数据。[HTTP协议](https://developer.mozilla.org/en-US/docs/Web/HTTP)提供了几种执行请求的方法；HTML表单数据可以通过许多不同的方法进行数据传输，其中最常见的是`GET`方法和`POST`方法。

为了理解这两种方法之间的区别，让我们回过头来看看HTTP是如何工作的。
 每当您想要访问Web上的资源时，浏览器都会向URL发送一个请求。
 HTTP请求由两个部分组成：一个包含关于浏览器功能的全局元数据集的头部，和一个包含服务器处理特定请求所需信息的主体。

##### GET 方法

`GET`方法是浏览器使用的方法，请求服务器返回给定的资源:“嘿，服务器，我想要得到这个资源。”在这种情况下，浏览器发送一个空的主体。由于主体是空的，如果使用该方法发送一个表单，那么发送到服务器的数据将被追加到URL。

考虑下面这个表单：

```
<form action="http://foo.com" method="get">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

由于已经使用了`GET`方法，当你提交表单的时候，您将看到`www.foo.com/?say=Hi&to=Mom`在浏览器地址栏里。

![img](https://mdn.mozillademos.org/files/14685/url-parameters.png)数据作为一系列的名称/值对被附加到URL。在URL web地址结束之后，我们得到一个问号(`?`)，后面跟着由一个与符号(`&`)互相分隔开的名称/值对。在本例中，我们将两个数据传递给服务器。

- `say`, 它有一个 `Hi`的值。
- `to`, 它有一个 `Mom`的值。

HTTP请求如下：

```
GET /?say=Hi&to=Mom HTTP/2.0
Host: foo.com
```

**注意：**你可以在GitHub 上看到本例子——见 [get-method.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/get-method.html) ([预览版](https://mdn.github.io/learning-area/html/forms/sending-form-data/get-method.html)).

##### POST 方法

`POST`方法略有不同。这是浏览器在询问响应时使用与服务器通信的方法，该响应考虑了HTTP请求正文中提供的数据:“嘿，服务器，看一下这些数据，然后给我回一个适当的结果。”如果使用该方法发送表单，则将数据追加到HTTP请求的主体中。

让我们来看一个例子，这是我们在上面的`GET`部分中所看到的相同的形式，但是使用[`method`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-method)属性设置为`post`。

```
<form action="http://foo.com" method="post">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

当使用`POST`方法提交表单时，没有数据会附加到URL，HTTP请求看起来是这样的，而请求主体中包含的数据是这样的：

```
POST / HTTP/2.0
Host: foo.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 13

say=Hi&to=Mom
```

`Content-Length`数据头表示主体的大小，`Content-Type`数据头表示发送到服务器的资源类型。稍后我们将讨论这些标头。

**注意：**你可以在 GitHub 上看到本例—— 见 [post-method.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/post-method.html) ([预览版](https://mdn.github.io/learning-area/html/forms/sending-form-data/post-method.html)).

#### 查看HTTP请求

HTTP请求永远不会显示给用户(如果您想要看到它们，您需要使用诸如[Firefox Network Monitor](https://developer.mozilla.org/en-US/docs/Tools/Network_Monitor)或[Chrome Developer Tools](https://developers.google.com/chrome-developer-tools/)之类的工具)。例如，您的表单数据将显示在Chrome网络选项卡中：

1. 按下 F12
2. 选择 "Network"
3. 选择 "All"
4. 在 "Name" 标签页选择 "foo.com"
5. 选择 "Headers"

你可以获得表单数据，像下图显示的那样

![img](https://mdn.mozillademos.org/files/14691/network-monitor.png)

唯一显示给用户的是被调用的URL。正如我们上面提到的，使用`GET`请求用户将在他们的URL栏中看到数据，但是使用`POST`请求用户将不会看到。这一点很重要，有两个原因：

1. 如果您需要发送一个密码(或其他敏感数据)，永远不要使用`GET`方法否则数据会在URL栏中显示，这将非常不安全。
2. 如果您需要发送大量的数据，那么`POST`方法是首选的，因为一些浏览器限制了URL的大小。此外，许多服务器限制它们接受的URL的长度。

### [在服务器端:检索数据](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#在服务器端检索数据)

无论选择哪种HTTP方法，服务器都会接收一个字符串并解析，以便将数据作为键/值对序列获取。您访问这个序列的方式取决于您使用的开发平台以及您可能使用的任何特定框架。您使用的技术也决定了如何处理密钥副本；通常，最近收到的密钥的值是优先的。

#### 例如：原始PHP

[PHP](http://php.net/)提供了一些全局对象来访问数据。假设您已经使用了`POST`方法，那么下面的示例将获取数据并将其显示给用户。当然，你对数据的处理取决于你自己。您可以显示它，将它存储到数据库中，通过电子邮件发送它，或者以其他方式处理它。

```
<?php
  // The global $_POST variable allows you to access the data sent with the POST method by name
  // To access the data sent with the GET method, you can use $_GET
  $say = htmlspecialchars($_POST['say']);
  $to  = htmlspecialchars($_POST['to']);

  echo  $say, ' ', $to;
?>
```

这个例子显示了一个带有我们发送的数据的页面。您可以在我们的示例[php-example.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/php-example.html)中看到这一点——该文件包含与我们之前看到的相同的示例表单，它使用了`post`的`method`和`php-example.php`的`action`。当提交时，它将表单数据发送到[php-example.php](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/php-example.php)，其中包含了上述代码块中所见的php代码。当执行此代码时，浏览器中的输出是`Hi Mom`。

![img](https://mdn.mozillademos.org/files/14693/php-result.png)

**注意：**当您将本例加载到本地浏览器中时，这个示例将无法工作---浏览器无法解析PHP代码，因此当提交表单时，浏览器只会为您提供下载PHP文件。为了让它生效，您需要通过某种类型的PHP服务器运行这个示例。本地PHP测试的好选择有[MAMP](https://www.mamp.info/en/downloads/)(Mac和Windows)和[AMPPS](http://ampps.com/download)(Mac、Windows、Linux)。

#### 例子： Python

这个例子展示了如何使用Python完成同样的事情——在web页面上显示提交的数据。
 这将使用[Flask framework](http://flask.pocoo.org/)来呈现模板、处理表单数据提交等(参见[python-example.py](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/python-example.py))。

```
from flask import Flask, render_template, request
app = Flask(__name__)

@app.route('/', methods=['GET', 'POST'])
def form():
    return render_template('form.html')

@app.route('/hello', methods=['GET', 'POST'])
def hello():
    return render_template('greeting.html', say=request.form['say'], to=request.form['to'])

if __name__ == "__main__":
    app.run()
```

以上代码中引用的两个模板如下：

- [form.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/templates/form.html): 与我们在[The POST method](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#the_post_method)小节中看到的相同的表单，但是将`action`设置为`{{ url_for('hello') }}`。(这是一个[Jinja2](http://jinja.pocoo.org/docs/2.9/)模板，它基本上是HTML，但是可以包含对运行包含在花括号中的web服务器的Python代码的调用。`url_for('hello')`基本上是在“提交表单时重定向到`/hello`”。
- [greeting.html](https://github.com/mdn/learning-area/blob/master/html/forms/sending-form-data/templates/greeting.html): 这个模板只包含一行，用于呈现渲染时传递给它的两个数据块。
    这是通过前面所见的`hello()`函数完成的，该函数在`/hello`URL被导向时运行。

**注意：**同样，如果您只是尝试将其直接加载到浏览器中，那么这段代码将无法工作。Python的工作方式与PHP略有不同——要在本地运行此代码，您需要[安装Python/pip](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/development_environment#installing_python_3)，然后使用`pip3 install flask`安装Flask。此时，您应该能够使用`python3 python-example.py`来运行这个示例，然后在浏览器中导航到`localhost:5000`。

#### 其他语言和框架

还有许多其他的服务器端技术可以用于表单处理，包括[Perl](https://developer.mozilla.org/en-US/docs/Web)、[Java](https://developer.mozilla.org/en-US/docs/Web)、 [.Net](https://www.microsoft.com/net)、[Ruby](https://developer.mozilla.org/en-US/docs/Web)等。只挑你最喜欢的用就好。话虽如此，但值得注意的是，直接使用这些技术并不常见，因为这可能很棘手。更常见的是使用许多优秀的框架，这些框架使处理表单变得更容易，例如：

- [Django](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django) for Python （比[Flask](http://flask.pocoo.org/)要重量级一些，但是有更多的工具和选项。）
- [Express](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs) for Node.js
- [Laravel](https://laravel.com/) for PHP
- [Ruby On Rails](https://rubyonrails.org/) for Ruby
- [Phoenix](https://phoenixframework.org/) for Elixir

要注意的是，即使使用这些框架，使用表单也不一定很容易。但这比从头开始编写所有功能要简单得多，而且会节省很多时间。

**注意：**向您介绍任何服务器端语言或框架超出了本文的范围。如果你想要学习这些它们，上面的链接会给你一些帮助。

### [特殊案例:发送文件](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#特殊案例发送文件)

用HTML表单发送文件是一个特殊的例子。文件是二进制数据——或者被认为是这样的——而所有其他数据都是文本数据。由于HTTP是一种文本协议，所以处理二进制数据有特殊的要求。

### [`enctype`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-enctype) 属性

该属性允许您指定在提交表单时所生成的请求中的`Content-Type`的HTTP数据头的值。这个数据头非常重要，因为它告诉服务器正在发送什么样的数据。默认情况下，它的值是`application/x-www-form-urlencoded`。它的意思是：“这是已编码为URL参数的表单数据。”

如果你想要发送文件，你需要额外的三个步骤：

- 将[`method`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-method)属性设置为`POST`，因为文件内容不能放入URL参数中。
- 将[`enctype`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form#attr-enctype)的值设置为`multipart/form-data`，因为数据将被分成多个部分，每个文件单独占用一个部分，表单正文中包含的文本数据（如果文本也输入到表单中）占用一个部分。
- 包含一个或多个[File picker](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#file_picker)小部件，允许用户选择将要上传的文件。

例如：

```
<form method="post" enctype="multipart/form-data">
  <div>
    <label for="file">Choose a file</label>
    <input type="file" id="file" name="myFile">
  </div>
  <div>
    <button>Send the file</button>
  </div>
</form>
```

**注意：**一些浏览器支持[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)的[`multiple`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input#attr-multiple)属性，它允许只用一个 `<input>` 元素选择一个以上的文件上传。服务器如何处理这些文件取决于服务器上使用的技术。如前所述，使用框架将使您的生活更轻松。

**警告：**为了防止滥用，许多服务器配置了文件和HTTP请求的大小限制。在发送文件之前，先检查服务器管理员的权限是很重要的。

### [常见的安全问题](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#常见的安全问题)

每次向服务器发送数据时，都需要考虑安全性。到目前为止，HTML表单是最常见的攻击路径(可能发生攻击的地方)。这些问题从来都不是来自HTML表单本身，它们来自于服务器如何处理数据。

根据你所做的事情，你会遇到一些非常有名的安全问题：

### [XSS 和 CSRF](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#xss_和_csrf)

跨站脚本(XSS)和跨站点请求伪造(CSRF)是常见的攻击类型，它们发生在当您将用户发送的数据显示给这个用户或另一个用户时。

XSS允许攻击者将客户端脚本注入到其他用户查看的Web页面中。攻击者可以使用跨站点脚本攻击的漏洞来绕过诸如[同源策略](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)之类的访问控制。这些攻击的影响可能从一个小麻烦到一个重大的安全风险。

CSRF攻击类似于XSS攻击，因为它们以相同的方式开始攻击——向Web页面中注入客户端脚本——但它们的目标是不同的。CSRF攻击者试图将权限升级到特权用户(比如站点管理员)的级别，以执行他们不应该执行的操作(例如，将数据发送给一个不受信任的用户)。

XSS攻击利用用户对web站点的信任，而CSRF攻击则利用网站对其用户的信任。

为了防止这些攻击，您应该始终检查用户发送给服务器的数据(如果需要显示)，尽量不要显示用户提供的HTML内容。相反，您应该对用户提供的数据进行处理，这样您就不会逐字地显示它。当今市场上几乎所有的框架都实现了一个最小的过滤器，它可以从任何用户发送的数据中删除HTML[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/script)、[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/iframe) 和[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/object) 元素。这有助于降低风险，但并不一定会消除风险。

### [SQL注入](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#sql注入)

SQL 注入是一种试图在目标web站点使用的数据库上执行操作的攻击类型。这通常包括发送一个SQL请求，希望服务器能够执行它（通常发生在应用服务器试图存储由用户发送的数据时）。这实际上是[攻击网站的主要途径之一](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project)。 

其后果可能是可怕的，从数据丢失到通过使用特权升级控制整个网站基础设施的攻击。这是一个非常严重的威胁，您永远不应该存储用户发送的数据，而不执行一些清理工作(例如，在php/mysql基础设施上使用`mysql_real_escape_string()`。

### [HTTP数据头注入和电子邮件注入](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#http数据头注入和电子邮件注入)

这种类型的攻击出现在当您的应用程序基于表单上用户的数据输入构建HTTP头部或电子邮件时。这些不会直接损害您的服务器或影响您的用户，但它们会引发一个更深入的问题，例如会话劫持或网络钓鱼攻击。

这些攻击大多是无声的，并且可以将您的服务器变成[僵尸](http://en.wikipedia.org/wiki/Zombie_(computer_science))。

### [偏执:永远不要相信你的用户](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#偏执永远不要相信你的用户)

那么，你如何应对这些威胁呢?这是一个远远超出本指南的主题，不过有一些规则需要牢记。最重要的原则是:永远不要相信你的用户，包括你自己；即使是一个值得信赖的用户也可能被劫持。

所有到达服务器的数据都必须经过检查和消毒。总是这样。没有例外。

- 远离有潜在危险的字符转义。应该如何谨慎使用的特定字符取决于所使用的数据的上下文和所使用的服务器平台，但是所有的服务器端语言都有相应的功能。
- 限制输入的数据量，只允许有必要的数据。
- 沙箱上传文件(将它们存储在不同的服务器上，只允许通过不同的子域访问文件，或者通过完全不同的域名访问文件更好)。

如果你遵循这三条规则，你应该避免很多问题，但是如果你想要得到一个有能力的第三方执行的安全检查，这是一个好主意。不要以为你已经看到了所有可能的问题。

**注意：**我们的[服务器端](https://developer.mozilla.org/en-US/docs/Learn/Server-side)学习主题的[网站安全性文章](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security)更详细地讨论了上述威胁和潜在的解决方案。

### [结论](https://developer.mozilla.org/zh-CN/docs/Learn/Forms/Sending_and_retrieving_form_data#结论)

如您所见，发送表单数据很容易，但要确保应用程序的安全性是很棘手的。请记住，前端开发人员不是应该定义数据安全模型的人。是的，我们将看到，[执行客户端数据验证](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)是可能的，但是服务器不能信任这种验证，因为它无法真正知道客户端到底发生了什么。

# 如何创建自定义表单控件

There are some cases where the available native HTML form  controls may seem like they are not enough. For example, if you need to [perform advanced styling](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling) on some controls such as the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element or if you want to provide custom behaviors, you may consider building your own controls.

In this article, we will discuss how to build a custom control. To that end, we will work with an example: rebuilding the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element. We will also discuss how, when, and whether building your own  control makes sense, and what to consider when building a control is a  requirement.

**Note:** We'll focus on building the control, not on  how to make the code generic and reusable; that would involve some  non-trivial JavaScript code and DOM manipulation in an unknown context,  and that is out of the scope of this article.

## [Design, structure, and semantics](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#design_structure_and_semantics)

Before building a custom control, you should start by figuring out exactly  what you want. This will save you some precious time. In particular,  it's important to clearly define all the states of your control. To do  this, it's good to start with an existing control whose states and  behavior are well known, so that you can mimic those as much as  possible.

In our example, we will rebuild the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element. Here is the result we want to achieve:

  ![The three states of a select box](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls/custom-select.png)

This screenshot shows the three main states of our control: the  normal state (on the left); the active state (in the middle) and the  open state (on the right).

In terms of behavior, we are recreating a native HTML element.  Therefore it should have the same behaviors and semantics as the native  HTML element. We require our control to be usable with a mouse as well  as with a keyboard, and comprehensible to a screen reader, just like any native control. Let's start by defining how the control reaches each  state:

**The control is in its normal state when:**

- the page loads.
- the control was active and the user clicks anywhere outside it.
- ​    the control was active and the user moves the focus to another control using the keyboard (e.g. the    Tab    key).  

**The control is in its active state when:**

- the user clicks on it or touches it on a touch screen.
- the user hits the tab key and it gains focus.
- the control was in its open state and the user clicks on it.

**The control is in its open state when:**

- the control is in any other state than open and the user clicks on it.

Once we know how to change states, it is important to define how to change the control's value:

**The value changes when:**

- the user clicks on an option when the control is in the open state.
- the user hits the up or down arrow keys when the control is in its active state.

**The value does not change when:**

- the user hits the up arrow key when the first option is selected.
- the user hits the down arrow key when the last option is selected.

Finally, let's define how the control's options will behave:

- When the control is opened, the selected option is highlighted
- When the mouse is over an option, the option is highlighted and  the previously highlighted option is returned to its normal state

For the purposes of our example, we'll stop with that; however, if  you're a careful reader, you'll notice that some behaviors are missing.  For example, what do you think will happen if the user hits the tab key  while the control is in its open state? The answer is... nothing. OK,  the right behavior seems obvious but the fact is, because it's not  defined in our specs, it is very easy to overlook this behavior. This is especially true in a team environment when the people who design the  control's behavior are different from the ones who implement it.

Another fun example: what will happen if the user hits the up or down arrow keys while the control is in the open state? This one is a little bit trickier. If you consider that the active state and the open state  are completely different, the answer is again "nothing will happen"  because we did not define any keyboard interactions for the opened  state. On the other hand, if you consider that the active state and the  open state overlap a bit, the value may change but the option will  definitely not be highlighted accordingly, once again because we did not define any keyboard interactions over options when the control is in  its opened state (we have only defined what should happen when the  control is opened, but nothing after that).

We have to think a little further: what about the escape key? Pressing Esc key closes an open select. Remember, if you want to provide the same functionality as the existing native [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), it should behave the exact same way as the select for all users, from  keyboard to mouse to touch to screen reader, and any other input device.

In our example, the missing specifications are obvious so we will  handle them, but it can be a real problem for exotic new controls. When  it comes to standardized elements, of which the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) is one, the specification authors spent an inordinate amount of time  specifying all interactions for every use case for every input device.  Creating new controls is not that easy, especially if you are creating  something that has not been done before, and therefore which nobody has  the slightest idea of what the expected behaviors and interactions are.  At least select has been done before, so we know how it should behave!

Designing new interactions is generally only an option for very large industry players who have enough reach that an interaction they create  can become a standard. For example, Apple introduced the scroll wheel  with the iPod in 2001. They had the market share to successfully  introduce a completely new way of interacting with a device, something  most device companies can't do.

It is best not to invent new user interactions. For any interaction  you do add, it is vital to spend time in the design stage; if you define a behavior poorly, or forget to define one, it will be very hard to  redefine it once the users have gotten used to it. If you have doubts,  ask for the opinions of others, and if you have the budget for it, do  not hesitate to [perform user tests](https://en.wikipedia.org/wiki/Usability_testing). This process is called UX Design. If you want to learn more about this  topic, you should check out the following helpful resources:

- [UXMatters.com](https://www.uxmatters.com/)
- [UXDesign.com](http://uxdesign.com/)
- [The UX Design section of SmashingMagazine](https://uxdesign.smashingmagazine.com/)

**Note:** Also, in most systems there is a way to open the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element with the keyboard to look at all the available choices (this is the same as clicking the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element with a mouse). This is achieved with Alt + Down  on Windows. We didn't implement this in our example, but it would be  easy to do so, as the mechanism has already been implemented for the `click` event.

## [Defining the HTML structure and (some) semantics](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#defining_the_html_structure_and_some_semantics)

Now that the control's basic functionality has been decided upon, it's time to start building it. The first step is to define its HTML structure  and to give it some basic semantics. Here is what we need to rebuild a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element:

```
<!-- This is our main container for our control.
     The tabindex attribute is what allows the user to focus the control.
     We'll see later that it's better to set it through JavaScript. -->
<div class="select" tabindex="0">

  <!-- This container will be used to display the current value of the control -->
  <span class="value">Cherry</span>

  <!-- This container will contain all the options available for our control.
       Because it's a list, it makes sense to use the ul element. -->
  <ul class="optList">
    <!-- Each option only contains the value to be displayed, we'll see later
         how to handle the real value that will be sent with the form data -->
    <li class="option">Cherry</li>
    <li class="option">Lemon</li>
    <li class="option">Banana</li>
    <li class="option">Strawberry</li>
    <li class="option">Apple</li>
  </ul>

</div>
```

Note the use of class names; these identify each relevant part  regardless of the actual underlying HTML elements used. This is  important to make sure that we don't bind our CSS and JavaScript to a  strong HTML structure, so that we can make implementation changes later  without breaking code that uses the control. For example, what if you  wish to implement the equivalent of the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/optgroup) element later on?

Class names, however, provide no semantic value. In this current  state, the screen reader user only "sees" an unordered list. We will add ARIA semantics in a bit.

## [Creating the look and feel using CSS](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#creating_the_look_and_feel_using_css)

Now that we have a structure, we can start designing our control. The whole point of building this custom control is to be able to style it exactly how we want. To that end, we will split our CSS work into two parts:  the first part will be the CSS rules absolutely necessary to make our  control behave like a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element, and the second part will consist of the fancy styles used to make it look the way we want.

### [Required styles](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#required_styles)

The required styles are those necessary to handle the three states of our control.

```
.select {
  /* This will create a positioning context for the list of options;
     adding this to .select:focus-within will be a better option when fully supported
  */
  position: relative;

  /* This will make our control become part of the text flow and sizable at the same time */
  display : inline-block;
}
```

We need an extra class `active` to define the look and  feel of our control when it is in its active state. Because our control  is focusable, we double this custom style with the [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus) pseudo-class in order to be sure they will behave the same.

```
.select .active,
.select:focus {
  outline: none;

  /* This box-shadow property is not exactly required, however it's imperative to ensure
     active state is visible, especially to keyboard users, that we use it as a default value. */
  box-shadow: 0 0 3px 1px #227755;
}
```

Now, let's handle the list of options:

```
/* The .select selector here helps to make we only select
   element inside our control. */
.select .optList {
  /* This will make sure our list of options will be displayed below the value
     and out of the HTML flow */
  position : absolute;
  top      : 100%;
  left     : 0;
}
```

We need an extra class to handle when the list of options is hidden.  This is necessary in order to manage the differences between the active  state and the open state that do not exactly match.

```
.select .optList.hidden {
  /* This is a simple way to hide the list in an accessible way;
     we will talk more about accessibility in the end */
  max-height: 0;
  visibility: hidden;
}
```

**Note:** We could also have used `transform: scale(1, 0)` to give the optionlist no height and full width.

### [Beautification](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#beautification)

So now that we have the basic functionality in place, the fun can start.  The following is just an example of what is possible, and will match the screenshot at the beginning of this article. However, you should feel  free to experiment and see what you can come up with.

```
.select {
  /* The computations are made assuming 1em == 16px which is the default value in most browsers.
     If you are lost with px to em conversion, try http://riddle.pl/emcalc/ */
  font-size   : 0.625em; /* this (10px) is the new font size context for em value in this context */
  font-family : Verdana, Arial, sans-serif;

  box-sizing : border-box;

  /* We need extra room for the down arrow we will add */
  padding : .1em 2.5em .2em .5em;
  width   : 10em; /* 100px */

  border        : .2em solid #000;
  border-radius : .4em;
  box-shadow    : 0 .1em .2em rgba(0,0,0,.45);

  /* The first declaration is for browsers that do not support linear gradients. */
  background : #F0F0F0;
  background : linear-gradient(0deg, #E3E3E3, #fcfcfc 50%, #f0f0f0);
}

.select .value {
  /* Because the value can be wider than our control, we have to make sure it will not
     change the control's width. If the content overflows, we display an ellipsis */
  display  : inline-block;
  width    : 100%;
  overflow : hidden;
  white-space : nowrap;
  text-overflow: ellipsis;
  vertical-align: top;
}
```

We don't need an extra element to design the down arrow; instead, we're using the `:after` pseudo-element. It could also be implemented using a simple background image on the `select` class.

```
.select:after {
  content : "▼"; /* We use the unicode character U+25BC; make sure to set a charset meta tag */
  position: absolute;
  z-index : 1; /* This will be important to keep the arrow from overlapping the list of options */
  top     : 0;
  right   : 0;

  box-sizing : border-box;

  height  : 100%;
  width   : 2em;
  padding-top : .1em;

  border-left  : .2em solid #000;
  border-radius: 0 .1em .1em 0;

  background-color : #000;
  color : #FFF;
  text-align : center;
}
```

Next, let's style the list of options:

```
.select .optList {
  z-index : 2; /* We explicitly said the list of options will always be on top of the down arrow */

  /* this will reset the default style of the ul element */
  list-style: none;
  margin : 0;
  padding: 0;

  box-sizing : border-box;

  /* If the values are smaller than the control, the list of options
     will be as wide as the control itself */
  min-width : 100%;

  /* In case the list is too long, its content will overflow vertically
     (which will add a vertical scrollbar automatically) but never horizontally
     (because we haven't set a width, the list will adjust its width automatically.
     If it can't, the content will be truncated) */
  max-height: 10em; /* 100px */
  overflow-y: auto;
  overflow-x: hidden;

  border: .2em solid #000;
  border-top-width : .1em;
  border-radius: 0 0 .4em .4em;

  box-shadow: 0 .2em .4em rgba(0,0,0,.4);
  background: #f0f0f0;
}
```

For the options, we need to add a `highlight` class to be able to identify the value the user will pick (or has picked).

```
.select .option {
  padding: .2em .3em; /* 2px 3px */
}

.select .highlight {
  background: #000;
  color: #FFFFFF;
}
```

So here's the result with our three states:

| Basic state                                                  | Active state | Open state |
| ------------------------------------------------------------ | ------------ | ---------- |
|                                                              |              |            |
| [Check out the source code](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls/Example_1) |              |            |

## [Bringing your control to life with JavaScript](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#bringing_your_control_to_life_with_javascript)

Now that our design and structure are ready, we can write the JavaScript code to make the control actually work.

**Warning:** The following is educational code, not  production code, and should not be used as-is. It is neither  future-proof nor will not work on legacy browsers. It also has redundant parts that should be optimized in production code.

### [Why isn't it working?](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#why_isnt_it_working)

Before starting, it's important to remember **JavaScript in the browser is an unreliable technology**. Custom controls rely on JavaScript to tie everything together. However, there are cases in which JavaScript isn't able to run in the browser:

- The user has turned off JavaScript: This is unusual; very few people turn off JavaScript nowadays.
- The script did not load: This is one of the most common cases,  especially in the mobile world where the network is not very reliable.
- The script is buggy: You should always consider this possibility.
- The script is in conflict with a third party script: This can happen with tracking scripts or any bookmarklets the user uses.
- The script is in conflict with, or is affected by, a browser extension (such as Firefox's [NoScript](https://addons.mozilla.org/fr/firefox/addon/noscript/) extension or Chrome's [NotScripts](https://chrome.google.com/webstore/detail/notscripts/odjhifogjcknibkahlpidmdajjpkkcfn) extension).
- The user is using a legacy browser, and one of the features you  require is not supported: This will happen frequently when you make use  of cutting-edge APIs.
- The user is interacting with the content before the JavaScript has been fully downloaded, parsed, and executed.

Because of these risks, it's really important to seriously consider  what will happen if your JavaScript doesn't work. We'll discuss options  to consider and cover the basics in our example (a full discussion of  solving this issue for all scenarios would require a book). Just  remember, it is vital make your script generic and reusable.

In our example, if our JavaScript code isn't running, we'll fall back to displaying a standard [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element. We include our control and the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select); which one is displayed depends on the class of the body element, with  the class of the body element being updated by the script that makes the control function, when it loads successfully

To achieve this, we need two things:

First, we need to add a regular [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element before each instance of our custom control. There is a benefit  to having this "extra" select even if our JavaScript works as hoped: we  will use this select to send data from our custom control along with the rest of our form data. We will discuss this in greater depth later.

```
<body class="no-widget">
  <form>
    <select name="myFruit">
      <option>Cherry</option>
      <option>Lemon</option>
      <option>Banana</option>
      <option>Strawberry</option>
      <option>Apple</option>
    </select>

    <div class="select">
      <span class="value">Cherry</span>
      <ul class="optList hidden">
        <li class="option">Cherry</li>
        <li class="option">Lemon</li>
        <li class="option">Banana</li>
        <li class="option">Strawberry</li>
        <li class="option">Apple</li>
      </ul>
    </div>
  </form>

</body>
```

Second, we need two new classes to let us hide the unneeded element: we visually hide the "real" [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element if our script isn't running, or the custom control if it is  running. Note that, by default, our HTML code hides our custom control.

```
.widget select,
.no-widget .select {
  /* This CSS selector basically says:
     - either we have set the body class to "widget" and thus we hide the actual <select> element
     - or we have not changed the body class, therefore the body class is still "no-widget",
       so the elements whose class is "select" must be hidden */
  position : absolute;
  left     : -5000em;
  height   : 0;
  overflow : hidden;
}
```

This CSS visually hides one of the elements, but it is still available to screen readers.

Now we need a JavaScript switch to determine if the script is running or not. This switch is a couple of lines: if at page load time our  script is running, it will remove the `no-widget` class and add the `widget` class, thereby swapping the visibility of the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element and the custom control.

```
window.addEventListener("load", function () {
  document.body.classList.remove("no-widget");
  document.body.classList.add("widget");
});
```

| Without JS                                                   | With JS |
| ------------------------------------------------------------ | ------- |
|                                                              |         |
| [Check out the source code](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls/Example_2) |         |

**Note:** If you really want to make your code generic and reusable, instead of doing a class switch it's far better to just  add the widget class to hide the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) elements, and to dynamically add the DOM tree representing the custom control after every [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element in the page.

### [Making the job easier](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#making_the_job_easier)

In the code we are about to build, we will use the standard JavaScript and DOM APIs to do all the work we need. The features we plan to use are  the following:

1. [`classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
2. [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
3. [`forEach`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
4. [`querySelector()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector) and [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll)

Beyond the availability of those specific features, there is still  one issue remaining before starting. The object returned by the [`querySelectorAll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelectorAll) function is a [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) rather than an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). This is important because `Array` objects support the [`forEach`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) function, but [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) doesn't. Because [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) really looks like an `Array` and because `forEach` is so convenient to use, we can easily add the support of `forEach` to [`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList) in order to make our life easier, like so:

```
NodeList.prototype.forEach = function (callback) {
  Array.prototype.forEach.call(this, callback);
}
```

If you need to support legacy browsers, ensure the browsers support  these features. If not, you can iterate through the list or you may need to use a library or polyfill.

### [Building event callbacks](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#building_event_callbacks)

The groundwork is done. We can now start to define all the functions that  will be used each time the user interacts with our control.

```
// This function will be used each time we want to deactivate a custom control
// It takes one parameter
// select : the DOM node with the `select` class to deactivate
function deactivateSelect(select) {

  // If the control is not active there is nothing to do
  if (!select.classList.contains('active')) return;

  // We need to get the list of options for the custom control
  var optList = select.querySelector('.optList');

  // We close the list of option
  optList.classList.add('hidden');

  // and we deactivate the custom control itself
  select.classList.remove('active');
}

// This function will be used each time the user wants to (de)activate the control
// It takes two parameters:
// select : the DOM node with the `select` class to activate
// selectList : the list of all the DOM nodes with the `select` class
function activeSelect(select, selectList) {

  // If the control is already active there is nothing to do
  if (select.classList.contains('active')) return;

  // We have to turn off the active state on all custom controls
  // Because the deactivateSelect function fulfills all the requirements of the
  // forEach callback function, we use it directly without using an intermediate
  // anonymous function.
  selectList.forEach(deactivateSelect);

  // And we turn on the active state for this specific control
  select.classList.add('active');
}

// This function will be used each time the user wants to open/closed the list of options
// It takes one parameter:
// select : the DOM node with the list to toggle
function toggleOptList(select) {

  // The list is kept from the control
  var optList = select.querySelector('.optList');

  // We change the class of the list to show/hide it
  optList.classList.toggle('hidden');
}

// This function will be used each time we need to highlight an option
// It takes two parameters:
// select : the DOM node with the `select` class containing the option to highlight
// option : the DOM node with the `option` class to highlight
function highlightOption(select, option) {

  // We get the list of all option available for our custom select element
  var optionList = select.querySelectorAll('.option');

  // We remove the highlight from all options
  optionList.forEach(function (other) {
    other.classList.remove('highlight');
  });

  // We highlight the right option
  option.classList.add('highlight');
};
```

You need these in order to handle the various states of the custom control.

Next, we bind these functions to the appropriate events:

```
// We handle the event binding when the document is loaded.
window.addEventListener('load', function () {
  var selectList = document.querySelectorAll('.select');

  // Each custom control needs to be initialized
  selectList.forEach(function (select) {

    // as well as all its `option` elements
    var optionList = select.querySelectorAll('.option');

    // Each time a user hovers their mouse over an option, we highlight the given option
    optionList.forEach(function (option) {
      option.addEventListener('mouseover', function () {
        // Note: the `select` and `option` variable are closures
        // available in the scope of our function call.
        highlightOption(select, option);
      });
    });

    // Each times the user clicks on or taps a custom select element
    select.addEventListener('click', function (event) {
      // Note: the `select` variable is a closure
      // available in the scope of our function call.

      // We toggle the visibility of the list of options
      toggleOptList(select);
    });

    // In case the control gains focus
    // The control gains the focus each time the user clicks on it or each time
    // they use the tabulation key to access the control
    select.addEventListener('focus', function (event) {
      // Note: the `select` and `selectList` variable are closures
      // available in the scope of our function call.

      // We activate the control
      activeSelect(select, selectList);
    });

    // In case the control loses focus
    select.addEventListener('blur', function (event) {
      // Note: the `select` variable is a closure
      // available in the scope of our function call.

      // We deactivate the control
      deactivateSelect(select);
    });

    // Loose focus if the user hits `esc`
    select.addEventListener('keyup', function (event) {

      // deactivate on keyup of `esc`
      if (event.keyCode === 27) {
         deactivateSelect(select);
      }
    });
});
});
```

At that point, our control will change state according to our design, but its value doesn't get updated yet. We'll handle that next.

| Live example                                                 |
| ------------------------------------------------------------ |
|                                                              |
| [Check out the source code](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls/Example_3) |

### [Handling the control's value](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#handling_the_controls_value)

Now that our control is working, we have to add code to update its value  according to user input and make it possible to send the value along  with form data.

The easiest way to do this is to use a native control under the hood. Such a control will keep track of the value with all the built-in  controls provided by the browser, and the value will be sent as usual  when a form is submitted. There's no point in reinventing the wheel when we can have all this done for us.

As seen previously, we already use a native select control as a  fallback for accessibility reasons; we can synchronize its value with  that of our custom control:

```
// This function updates the displayed value and synchronizes it with the native control.
// It takes two parameters:
// select : the DOM node with the class `select` containing the value to update
// index  : the index of the value to be selected
function updateValue(select, index) {
  // We need to get the native control for the given custom control
  // In our example, that native control is a sibling of the custom control
  var nativeWidget = select.previousElementSibling;

  // We also need  to get the value placeholder of our custom control
  var value = select.querySelector('.value');

  // And we need the whole list of options
  var optionList = select.querySelectorAll('.option');

  // We set the selected index to the index of our choice
  nativeWidget.selectedIndex = index;

  // We update the value placeholder accordingly
  value.innerHTML = optionList[index].innerHTML;

  // And we highlight the corresponding option of our custom control
  highlightOption(select, optionList[index]);
};

// This function returns the current selected index in the native control
// It takes one parameter:
// select : the DOM node with the class `select` related to the native control
function getIndex(select) {
  // We need to access the native control for the given custom control
  // In our example, that native control is a sibling of the custom control
  var nativeWidget = select.previousElementSibling;

  return nativeWidget.selectedIndex;
};
```

With these two functions, we can bind the native controls to the custom ones:

```
// We handle event binding when the document is loaded.
window.addEventListener('load', function () {
  var selectList = document.querySelectorAll('.select');

  // Each custom control needs to be initialized
  selectList.forEach(function (select) {
    var optionList = select.querySelectorAll('.option'),
        selectedIndex = getIndex(select);

    // We make our custom control focusable
    select.tabIndex = 0;

    // We make the native control no longer focusable
    select.previousElementSibling.tabIndex = -1;

    // We make sure that the default selected value is correctly displayed
    updateValue(select, selectedIndex);

    // Each time a user clicks on an option, we update the value accordingly
    optionList.forEach(function (option, index) {
      option.addEventListener('click', function (event) {
        updateValue(select, index);
      });
    });

    // Each time a user uses their keyboard on a focused control, we update the value accordingly
    select.addEventListener('keyup', function (event) {
      var length = optionList.length,
          index  = getIndex(select);

      // When the user hits the down arrow, we jump to the next option
      if (event.keyCode === 40 && index < length - 1) { index++; }

      // When the user hits the up arrow, we jump to the previous option
      if (event.keyCode === 38 && index > 0) { index--; }

      updateValue(select, index);
    });
  });
});
```

In the code above, it's worth noting the use of the [`tabIndex`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/tabIndex) property. Using this property is necessary to ensure that the native control will never gain focus, and to make sure that our custom control gains focus  when the user uses their keyboard or mouse.

With that, we're done! Here's the result:

| Live example                                                 |
| ------------------------------------------------------------ |
|                                                              |
| [Check out the source code](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls/Example_4) |

But wait a second, are we really done?

## [Making it accessible](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#making_it_accessible)

We have built something that works and though we're far from a  fully-featured select box, it works nicely. But what we've done is  nothing more than fiddle with the DOM. It has no real semantics, and  even though it looks like a select box, from the browser's point of view it isn't one, so assistive technologies won't be able to understand  it's a select box. In short, this pretty new select box isn't  accessible!

Fortunately, there is a solution and it's called [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA). ARIA stands for "Accessible Rich Internet Application", and it's [a W3C specification](https://www.w3.org/TR/wai-aria/) specifically designed for what we are doing here: making web  applications and custom controls accessible. It's basically a set of  attributes that extend HTML so that we can better describe roles, states and properties as though the element we've just devised was the native  element it tries to pass for. Using these attributes can be done by  editing the HTML markup. We also update the ARIA attributes via  JavaScript as the user updates their selected value.

### [The `role` attribute](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#the_role_attribute)

The key attribute used by [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) is the [`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques) attribute. The [`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques) attribute accepts a value that defines what an element is used for.  Each role defines its own requirements and behaviors. In our example, we will use the [`listbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listbox_role) role. It's a "composite role", which means elements with that role  expect to have children, each with a specific role (in this case, at  least one child with the `option` role).

It's also worth noting that ARIA defines roles that are applied by default to standard HTML markup. For example, the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) element matches the role `grid`, and the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element matches the role `list`. Because we use a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element, we want to make sure the `listbox` role of our control will supersede the `list` role of the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element. To that end, we will use the role `presentation`. This role is designed to let us indicate that an element has no special meaning, and is used solely to present information. We will apply it to our [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) element.

To support the [`listbox`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/listbox_role) role, we just have to update our HTML like this:

```
<!-- We add the role="listbox" attribute to our top element -->
<div class="select" role="listbox">
  <span class="value">Cherry</span>
  <!-- We also add the role="presentation" to the ul element -->
  <ul class="optList" role="presentation">
    <!-- And we add the role="option" attribute to all the li elements -->
    <li role="option" class="option">Cherry</li>
    <li role="option" class="option">Lemon</li>
    <li role="option" class="option">Banana</li>
    <li role="option" class="option">Strawberry</li>
    <li role="option" class="option">Apple</li>
  </ul>
</div>
```

**Note:** Including both the `role` attribute and a `class` attribute is not necessary. Instead of using `.option` use the `[role="option"]` [attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) in your CSS .

### [The `aria-selected` attribute](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#the_aria-selected_attribute)

Using the [`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques) attribute is not enough. [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) also provides many states and property attributes. The more and better  you use them, the better your control will be understood by assistive  technologies. In our case, we will limit our usage to one attribute: `aria-selected`.

The `aria-selected` attribute is used to mark which option is currently selected; this lets assistive technologies inform the user what the current selection is. We will use it dynamically with  JavaScript to mark the selected option each time the user chooses one.  To that end, we need to revise our `updateValue()` function:

```
function updateValue(select, index) {
  var nativeWidget = select.previousElementSibling;
  var value = select.querySelector('.value');
  var optionList = select.querySelectorAll('[role="option"]');

  // We make sure that all the options are not selected
  optionList.forEach(function (other) {
    other.setAttribute('aria-selected', 'false');
  });

  // We make sure the chosen option is selected
  optionList[index].setAttribute('aria-selected', 'true');

  nativeWidget.selectedIndex = index;
  value.innerHTML = optionList[index].innerHTML;
  highlightOption(select, optionList[index]);
};
```

It might have seemed simpler to let a  screen reader focus on the off-screen select and ignore our stylized  one, but this is not an accessible solution. Screen readers are not  limited to blind people; people with low vision and even perfect vision  use them as well. For this reason, you can not have the screen reader  focus on an off-screen element.

Here is the final result of all these changes (you'll get a better  feel for this by trying it with an assistive technology such as [NVDA](http://www.nvda-project.org/) or [VoiceOver](https://www.apple.com/accessibility/voiceover/)):

| Live example                                                 |
| ------------------------------------------------------------ |
|                                                              |
| [Check out the final source code](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls/Example_5) |

If you want to move forward, the code in this example needs some  improvement before it becomes generic and reusable. This is an exercise  you can try to perform. Two hints to help you in this: the first  argument for all our functions is the same, which means those functions  need the same context. Building an object to share that context would be wise.

## [An alternative approach: Using radio buttons](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#an_alternative_approach_using_radio_buttons)

In the above example, we reinvented a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element using non-semantic HTML, CSS, and JavaScript. This select was  selecting one option from a limited number of options, which is the same functionality of a same-named group of [radio](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio) buttons.

We could therefore reinvent this using radio buttons instead; let's look at this option.

We can start with a completely semantic, accessible, unordered list of [radio](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio) buttons with an associated [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label), labeling the entire group with a semantically appropriate [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset) and [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/legend) pair.

```
 <fieldset>
  <legend>Pick a fruit</legend>
    <ul class="styledSelect">
      <li><input type="radio" name="fruit" value="Cherry" id="fruitCherry" checked><label for="fruitCherry">Cherry</label></li>
      <li><input type="radio" name="fruit" value="Lemon" id="fruitLemon"><label for="fruitLemon">Lemon</label></li>
      <li><input type="radio" name="fruit" value="Banana" id="fruitBanana"><label for="fruitBanana"">Banana</label></li>
      <li><input type="radio" name="fruit" value="Strawberry" id="fruitStrawberry"><label for="fruitStrawberry">Strawberry</label></li>
      <li><input type="radio" name="fruit" value="Apple" id="fruitApple"><label for="fruitApple">Apple</label></li>
    </ul>
  </fieldset>
```

We'll do a little styling of the radio  button list (not the legend/fieldset) to make it look somewhat like the  earlier example, just to show that it can be done:

```
.styledSelect {
  display: inline-block;
  padding: 0;
}
.styledSelect li {
  list-style-type: none;
  padding: 0;
  display: flex;
}
.styledSelect [type=radio] {
  position: absolute;
  left: -100vw;
  top: -100vh;
}
.styledSelect label {
  margin: 0;
  line-height: 2;
  padding: 0 0 0 4px;
}
.styledSelect:not(:focus-within) input:not(:checked) + label {
  height: 0;
  outline: none;
  overflow: hidden;
}
.styledSelect:not(:focus-within) input:checked + label {
  border: .2em solid #000;
  border-radius: .4em;
  box-shadow: 0 .1em .2em rgba(0,0,0,.45);
}
.styledSelect:not(:focus-within) input:checked + label::after {
  content : "▼";
  background: black;
  float: right;
  color: white;
  padding: 0 4px;
  margin: 0 -4px 0 4px;
}
.styledSelect:focus-within {
  border: .2em solid #000;
  border-radius: .4em;
  box-shadow: 0 .1em .2em rgba(0,0,0,.45);
}
.styledSelect:focus-within input:checked + label {
  background-color: #333;
  color: #fff;
  width: 100%;
}
```

With no JavaScript, and just a little bit of  CSS, we are able to style the list of radio buttons to display only the  checked item. When the focus is within the `<ul>` in the `<fieldset>`, the list opens up, and the up and down (and left and right) arrows work to select the previous and next items. Try it out:

<iframe class="sample-code-frame" title="An alternative approach Using radio buttons sample" id="frame_An_alternative_approach_Using_radio_buttons" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/How_to_build_custom_form_controls/_sample_.An_alternative_approach_Using_radio_buttons.html" loading="lazy" width="200" height="240"></iframe>

This works, to some extent, without JavaScript. We've created a  similar control to our custom control, that works even if the JavaScript fails. Looks like a great solution, right? Well, not 100%. It does work with the keyboard, but not as expected with a mouse click. It likely  makes more sense to use web standards as the basis for custom controls  instead of relying on frameworks to create elements with no native  semantics. However, our control doesn't have the same functionality that a `<select>` has natively.

On the plus side, this control is fully accessible to a screen reader and fully navigable via the keyboard. However, this control isn't a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) replacement. There is functionality that differs and/or is missing. For example, all four arrows navigate through the options, but clicking the down arrow when the user is on the last button takes them to the first  button; it doesn't stop at the top and bottom of the option list like a `<select>` does.

We'll leave adding this missing functionality as a reader exercise.

## [Conclusion](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls#conclusion)

We have seen all the basics of building a custom form control, but as you  can see it's not trivial to do. Before creating your own customized  control, consider whether HTML provides alternative elements that can be used to adequately support your requirements. If you do need to create a custom control, it is often easier to rely on third-party libraries  instead of building your own. But, if you do create your own, modify  existing elements, or use a framework to implement a pre-baked control,  remember that creating a usable and accessible form control is more  complicated than it looks.

Here are a few libraries you should consider before coding your own:

- [jQuery UI](https://jqueryui.com/)
- [AXE accessible custom select dropdowns](https://www.webaxe.org/accessible-custom-select-dropdowns)
- [msDropDown](https://github.com/marghoobsuleman/ms-Dropdown)
- [Nice Forms](https://www.emblematiq.com/lab/niceforms/)

If you do create alternative controls via radio buttons, your own  JavaScript, or with a 3rd party library, ensure it is accessible and  feature-proof; that is, it needs to be able to work better with a  variety of browsers whose compatibility with the Web standards they use  vary. Have fun!

# 通过 JavaScript 发送表单

HTML 表单可以声明性地发送[HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)请求。但是表单也可以准备 HTTP 请求以通过 JavaScript 发送，例如通过`XMLHttpRequest`. 本文探讨了此类方法。

## [表格并不总是表格](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#a_form_is_not_always_a_form)

对于渐进式 Web 应用程序、单页应用程序和基于框架的应用程序，在接收到响应数据时使用[HTML 表单](https://developer.mozilla.org/en-US/docs/Learn/Forms)发送数据而不加载新文档是很常见的。让我们首先谈谈为什么这需要不同的方法。

### [获得对全局接口的控制](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#gaining_control_of_the_global_interface)

标准 HTML 表单提交，如前一篇文章中所述，加载发送数据的 URL，这意味着浏览器窗口以完整页面加载进行导航。避免整个页面加载可以通过避免网络延迟和闪烁等可能的视觉问题来提供更流畅的体验。

许多现代 UI 仅使用 HTML 表单来收集用户的输入，而不是用于数据提交。当用户尝试发送数据时，应用程序将控制并在后台异步传输数据，只更新需要更改的 UI 部分。

异步发送任意数据一般称为[AJAX](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX)，代表**“Asynchronous JavaScript And XML”**。

### [有什么不同？](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#how_is_it_different)

该[`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)（XHR）DOM对象可以建立HTTP请求，向他们发送和检索其结果。从历史上看，[`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)它旨在获取和发送[XML](https://developer.mozilla.org/en-US/docs/Web/XML)作为交换格式，此后已被[JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON)取代。但是 XML 和 JSON 都不适合表单数据请求编码。表单数据 ( `application/x-www-form-urlencoded`) 由 URL 编码的键/值对列表组成。为了传输二进制数据，HTTP 请求被重构为`multipart/form-data`.

**注：**该[提取API，](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)经常被用来代替XHR这些天-这是XHR的现代化，更新版本，以类似的方式工作，但有一定的优势。您将在本文中看到的大部分 XHR 代码都可以替换为 Fetch。

如果您控制前端（在浏览器中执行的代码）和后端（在服务器上执行的代码），您可以发送 JSON/XML 并根据需要处理它们。

但是如果你想使用第三方服务，你需要以服务要求的格式发送数据。

那么我们应该如何发送这样的数据呢？您需要的不同技术在下面完成。

## [发送表单数据](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#sending_form_data)

有3种方式发送表单数据：

- `XMLHttpRequest`手动构建。
- 使用独立`FormData`对象。
- 使用`FormData`绑定到`<form>`元素。

让我们详细看看它们。

### [手动构建 XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#building_an_xmlhttprequest_manually)

[`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)是最安全、最可靠的 HTTP 请求方式。使用 发送表单数据[`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)，通过 URL 编码准备数据，并遵守表单数据请求的细节。

让我们看一个例子：

```
<button>Click Me!</button>
```

复制到剪贴板

现在是 JavaScript：

```
const btn = document.querySelector('button');

function sendData( data ) {
  console.log( 'Sending data' );

  const XHR = new XMLHttpRequest();

  let urlEncodedData = "",
      urlEncodedDataPairs = [],
      name;

  // Turn the data object into an array of URL-encoded key/value pairs.
  for( name in data ) {
    urlEncodedDataPairs.push( encodeURIComponent( name ) + '=' + encodeURIComponent( data[name] ) );
  }

  // Combine the pairs into a single string and replace all %-encoded spaces to
  // the '+' character; matches the behavior of browser form submissions.
  urlEncodedData = urlEncodedDataPairs.join( '&' ).replace( /%20/g, '+' );

  // Define what happens on successful data submission
  XHR.addEventListener( 'load', function(event) {
    alert( 'Yeah! Data sent and response loaded.' );
  } );

  // Define what happens in case of error
  XHR.addEventListener( 'error', function(event) {
    alert( 'Oops! Something went wrong.' );
  } );

  // Set up our request
  XHR.open( 'POST', 'https://example.com/cors.php' );

  // Add the required HTTP header for form data POST requests
  XHR.setRequestHeader( 'Content-Type', 'application/x-www-form-urlencoded' );

  // Finally, send our data.
  XHR.send( urlEncodedData );
}

btn.addEventListener( 'click', function() {
  sendData( {test:'ok'} );
} )
```

复制到剪贴板

这是现场结果：

<iframe class="sample-code-frame" title="手动构建 XMLHttpRequest 示例" id="frame_Building_an_XMLHttpRequest_manually" width="100%" height="60" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript/_sample_.Building_an_XMLHttpRequest_manually.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

**注意：**如果您想将数据发送到第三方网站，这种使用[`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)受[同源政策的](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy)约束。对于跨域请求，您将需要[CORS 和 HTTP 访问控制](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)。

### [使用 XMLHttpRequest 和 FormData 对象](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#using_xmlhttprequest_and_the_formdata_object)

手动构建 HTTP 请求可能会让人不知所措。幸运的是，该[XMLHttpRequest 规范](https://www.w3.org/TR/XMLHttpRequest/)提供了一种更新、更简单的方法来处理[`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData)对象的表单数据请求。

该[`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData)对象可用于构建表单数据以进行传输，或获取表单元素中的数据以管理其发送方式。请注意，[`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData)对象是“只写”的，这意味着您可以更改它们，但不能检索它们的内容。

使用[FormData Objects 中](https://developer.mozilla.org/en-US/docs/Web/API/FormData/Using_FormData_Objects)详细介绍了如何使用此对象，但这里有两个示例：

#### 使用独立的 FormData 对象

```
<button>Click Me!</button>
```

复制到剪贴板

您应该熟悉该 HTML 示例。现在对于 JavaScript：

```
const btn = document.querySelector('button');

function sendData( data ) {
  const XHR = new XMLHttpRequest(),
        FD  = new FormData();

  // Push our data into our FormData object
  for( name in data ) {
    FD.append( name, data[ name ] );
  }

  // Define what happens on successful data submission
  XHR.addEventListener( 'load', function( event ) {
    alert( 'Yeah! Data sent and response loaded.' );
  } );

  // Define what happens in case of error
  XHR.addEventListener(' error', function( event ) {
    alert( 'Oops! Something went wrong.' );
  } );

  // Set up our request
  XHR.open( 'POST', 'https://example.com/cors.php' );

  // Send our FormData object; HTTP headers are set automatically
  XHR.send( FD );
}

btn.addEventListener( 'click', function()
  { sendData( {test:'ok'} );
} )
```

复制到剪贴板

这是现场结果：

<iframe class="sample-code-frame" title="使用独立的 FormData 对象示例" id="frame_Using_a_standalone_FormData_object" width="100%" height="60" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript/_sample_.Using_a_standalone_FormData_object.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

#### 使用绑定到表单元素的 FormData

您还可以将`FormData`对象绑定到[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)元素。这将创建一个`FormData`表示表单中包含的数据的对象。

HTML 是典型的：

```
<form id="myForm">
  <label for="myName">Send me your name:</label>
  <input id="myName" name="name" value="John">
  <input type="submit" value="Send Me!">
</form>
```

复制到剪贴板

但是 JavaScript 接管了表单：

```
window.addEventListener( "load", function () {
  function sendData() {
    const XHR = new XMLHttpRequest();

    // Bind the FormData object and the form element
    const FD = new FormData( form );

    // Define what happens on successful data submission
    XHR.addEventListener( "load", function(event) {
      alert( event.target.responseText );
    } );

    // Define what happens in case of error
    XHR.addEventListener( "error", function( event ) {
      alert( 'Oops! Something went wrong.' );
    } );

    // Set up our request
    XHR.open( "POST", "https://example.com/cors.php" );

    // The data sent is what the user provided in the form
    XHR.send( FD );
  }

  // Access the form element...
  const form = document.getElementById( "myForm" );

  // ...and take over its submit event.
  form.addEventListener( "submit", function ( event ) {
    event.preventDefault();

    sendData();
  } );
} );
```

复制到剪贴板

这是现场结果：

<iframe class="sample-code-frame" title="使用绑定到表单元素示例的 FormData" id="frame_Using_FormData_bound_to_a_form_element" width="100%" height="60" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript/_sample_.Using_FormData_bound_to_a_form_element.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

您甚至可以通过使用表单的[`elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)属性获取表单中所有数据元素的列表并一次手动管理一个，从而更多地参与该过程。要了解更多相关信息，请参阅[访问](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements#accessing_the_element_list's_contents)[HTMLFormElement.elements 中](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements)[的元素列表内容](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements#accessing_the_element_list's_contents)中的示例。

## [处理二进制数据](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#dealing_with_binary_data)

如果您将[`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData)对象与包含`<input type="file">`小部件的表单一起使用，数据将被自动处理。但是要手动发送二进制数据，还有额外的工作要做。

有二进制数据，其中包括许多来源[`FileReader`](https://developer.mozilla.org/en-US/docs/Web/API/FileReader)，[`Canvas`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement)和[的WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia)。不幸的是，一些旧浏览器无法访问二进制数据或需要复杂的解决方法。要了解有关`FileReader`API 的更多信息，请参阅[使用来自 Web 应用程序的文件](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)。

发送二进制数据[`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData)最简单的`append()`方法是使用's方法，如上所示。如果你必须手动完成，那就更棘手了。

在以下示例中，我们使用[`FileReader`](https://developer.mozilla.org/en-US/docs/Web/API/FileReader)API 访问二进制数据，然后手动构建多部分表单数据请求：

```
<form id="theForm">
  <p>
    <label for="theText">text data:</label>
    <input id="theText" name="myText" value="Some text data" type="text">
  </p>
  <p>
    <label for="theFile">file data:</label>
    <input id="theFile" name="myFile" type="file">
  </p>
  <button>Send Me!</button>
</form>
```

复制到剪贴板

如您所见，HTML 是标准的`<form>`. 没有什么神奇的事情发生。“魔法”在 JavaScript 中：

```
// Because we want to access DOM nodes,
// we initialize our script at page load.
window.addEventListener( 'load', function () {

  // These variables are used to store the form data
  const text = document.getElementById( "theText" );
  const file = {
        dom    : document.getElementById( "theFile" ),
        binary : null
      };

  // Use the FileReader API to access file content
  const reader = new FileReader();

  // Because FileReader is asynchronous, store its
  // result when it finishes to read the file
  reader.addEventListener( "load", function () {
    file.binary = reader.result;
  } );

  // At page load, if a file is already selected, read it.
  if( file.dom.files[0] ) {
    reader.readAsBinaryString( file.dom.files[0] );
  }

  // If not, read the file once the user selects it.
  file.dom.addEventListener( "change", function () {
    if( reader.readyState === FileReader.LOADING ) {
      reader.abort();
    }

    reader.readAsBinaryString( file.dom.files[0] );
  } );

  // sendData is our main function
  function sendData() {
    // If there is a selected file, wait it is read
    // If there is not, delay the execution of the function
    if( !file.binary && file.dom.files.length > 0 ) {
      setTimeout( sendData, 10 );
      return;
    }

    // To construct our multipart form data request,
    // We need an XMLHttpRequest instance
    const XHR = new XMLHttpRequest();

    // We need a separator to define each part of the request
    const boundary = "blob";

    // Store our body request in a string.
    let data = "";

    // So, if the user has selected a file
    if ( file.dom.files[0] ) {
      // Start a new part in our body's request
      data += "--" + boundary + "\r\n";

      // Describe it as form data
      data += 'content-disposition: form-data; '
      // Define the name of the form data
            + 'name="'         + file.dom.name          + '"; '
      // Provide the real name of the file
            + 'filename="'     + file.dom.files[0].name + '"\r\n';
      // And the MIME type of the file
      data += 'Content-Type: ' + file.dom.files[0].type + '\r\n';

      // There's a blank line between the metadata and the data
      data += '\r\n';

      // Append the binary data to our body's request
      data += file.binary + '\r\n';
    }

    // Text data is simpler
    // Start a new part in our body's request
    data += "--" + boundary + "\r\n";

    // Say it's form data, and name it
    data += 'content-disposition: form-data; name="' + text.name + '"\r\n';
    // There's a blank line between the metadata and the data
    data += '\r\n';

    // Append the text data to our body's request
    data += text.value + "\r\n";

    // Once we are done, "close" the body's request
    data += "--" + boundary + "--";

    // Define what happens on successful data submission
    XHR.addEventListener( 'load', function( event ) {
      alert( 'Yeah! Data sent and response loaded.' );
    } );

    // Define what happens in case of error
    XHR.addEventListener( 'error', function( event ) {
      alert( 'Oops! Something went wrong.' );
    } );

    // Set up our request
    XHR.open( 'POST', 'https://example.com/cors.php' );

    // Add the required HTTP header to handle a multipart form data POST request
    XHR.setRequestHeader( 'Content-Type','multipart/form-data; boundary=' + boundary );

    // And finally, send our data.
    XHR.send( data );
  }

  // Access our form...
  const form = document.getElementById( "theForm" );

  // ...to take over the submit event
  form.addEventListener( 'submit', function ( event ) {
    event.preventDefault();
    sendData();
  } );
} );
```

复制到剪贴板

这是现场结果：

<iframe class="sample-code-frame" title="处理二进制数据样本" id="frame_Dealing_with_binary_data" width="100%" height="150" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript/_sample_.Dealing_with_binary_data.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

## [结论](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript#conclusion)

根据浏览器和您处理的数据类型，通过 JavaScript 发送表单数据可能容易也可能困难。该[`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData)对象一般是答案，而且可以使用[填充物](https://github.com/jimmywarting/FormData) 因为它在旧版浏览器上。

# CSS属性与表单控件的适配性总结表

The following compatibility tables try to summarize the state of CSS support for HTML forms. Due to the complexity of CSS and HTML forms, these tables can't be considered a perfect reference. However, they will give you good insight into what can and can't be done, which will help you learn how to do things.

## [How to read the tables](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#how_to_read_the_tables)

### [Values](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#values)

For each property, there are four possible values:

- Yes

  There's reasonably consistent support for the property across browsers. You may still face strange side effects in certain edge cases.

- Partial

  While the property works, you may frequently face strange side effects or inconsistencies. You should probably avoid these properties unless you master those side effects first.

- No

  The property doesn't work or is so inconsistent that it's not reliable.

- n.a.

  The property has no meaning for this type of widget.

### [Rendering](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#rendering)

For each property there are two possible renderings:

- N (Normal)

  Indicates that the property is applied as it is

- T (Tweaked)

  Indicates that the property is applied with the extra rule below:

```
* {
  /* Turn off the native look and feel */
  -webkit-appearance: none;
  appearance: none;

/* for Internet Explorer */
  background: none;
}
```

Copy to Clipboard

## [Compatibility tables](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#compatibility_tables)

### [Global behaviors](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#global_behaviors)

Some behaviors are common to many browsers at a global level:

- [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border), [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background), [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height)

  Using one of these properties can partially or fully turn off the native look & feel of widgets on some browsers. Be careful when you use them.

- [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)

  This property is supported inconsistently across browsers and you should avoid it.

- [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)

  This property is not supported by Opera on form widgets.

- [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow)

  Opera, Safari, and IE9 do not support this property on form widgets.

- [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)

  Opera does not support [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) on form widgets and IE9 does not support it at all.

### [Text fields](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#text_fields)

See the `text`, `search`, and `password` input types.

| Property                                                     |       N       |     T      | Note                                                         |
| :----------------------------------------------------------- | :-----------: | :--------: | :----------------------------------------------------------- |
| *CSS box model*                                              |               |            |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |      Yes      |    Yes     |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) | Partial[1][2] |    Yes     | WebKit browsers (mostly on Mac OSX and iOS) use the native look & feel for the search fields. Therefore, it's required to use `-webkit-appearance:none` to be able to apply this property to search fields.On Windows 7, Internet Explorer 9 does not apply the border unless `background:none` is applied. |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) | Partial[1][2] |    Yes     | WebKit browsers (mostly on Mac OSX and iOS) use the native look & feel for the search fields. Therefore, it's required to use `-webkit-appearance:none` to be able to apply this property to search fields.On Windows 7, Internet Explorer 9 does not apply the border unless `background:none` is applied. |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |      Yes      |    Yes     |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) | Partial[1][2] |    Yes     | WebKit browsers (mostly on Mac OSX and iOS) use the native look & feel for the search fields. Therefore, it's required to use `-webkit-appearance:none` to be able to apply this property to search fields.On Windows 7, Internet Explorer 9 does not apply the border unless `background:none` is applied. |
| *Text and font*                                              |               |            |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)[1] |      Yes      |    Yes     | If the [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color) property is not set, some WebKit based browsers will apply the [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) property to the border as well as the font on `<textarea>`s. |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |      Yes      |    Yes     | See the note about [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |      Yes      |    Yes     |                                                              |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |      Yes      |    Yes     |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |    Partial    |  Partial   | See the note about Opera                                     |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |  Partial[1]   | Partial[1] | IE9 supports this property only on `<textarea>`s, whereas Opera only supports it on single line text fields. |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |    Partial    |  Partial   |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |    Partial    |  Partial   |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |      Yes      |    Yes     |                                                              |
| *Border and background*                                      |               |            |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |  Partial[1]   |    Yes     | WebKit browsers (mostly on Mac OSX and iOS) use the native look & feel for the search fields. Therefore, it's required to use `-webkit-appearance:none` to be able to apply this property to search fields. On Windows 7, Internet Explorer 9 does not apply the border unless `background:none` is applied. |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) | Partial[1][2] |    Yes     | WebKit browsers (mostly on Mac OSX and iOS) use the native look & feel for the search fields. Therefore, it's required to use `-webkit-appearance:none` to be able to apply this property to search fields. On Windows 7, Internet Explorer 9 does not apply the border unless `background:none` is applied.On Opera the [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) property is applied only if an explicit border is set. |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |      No       | Partial[1] | IE9 does not support this property.                          |

### [Buttons](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#buttons)

See the `button`, `submit`, and `reset` input types and the `<button>` element.

| Property                                                     |     N      |     T      | Note                                                         |
| :----------------------------------------------------------- | :--------: | :--------: | :----------------------------------------------------------- |
| *CSS box model*                                              |            |            |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |    Yes     |    Yes     |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) | Partial[1] |    Yes     | This property is not applied on WebKit based browsers on Mac OSX or iOS. |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |  Partial   |    Yes     |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |    Yes     |    Yes     |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) | Partial[1] |    Yes     | This property is not applied on WebKit based browsers on Mac OSX or iOS. |
| *Text and font*                                              |            |            |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |    Yes     |    Yes     |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |    Yes     |    Yes     | See the note about [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height). |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |    Yes     |    Yes     |                                                              |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |     No     |     No     |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |  Partial   |    Yes     |                                                              |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |    Yes     |    Yes     |                                                              |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |     No     |     No     |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |  Partial   |  Partial   |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |    Yes     |    Yes     |                                                              |
| *Border and background*                                      |            |            |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |    Yes     |    Yes     |                                                              |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |   Yes[1]   |   Yes[1]   | On Opera the [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) property is applied only if an explicit border is set. |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |     No     | Partial[1] | IE9 does not support this property.                          |

### [Number](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#number)

See the `number` input type. There is no standard way to change the style of spinners used to change the value of the field, with the spinners on Safari being outside the field.

| Property                                                     |     N      |     T      | Note                                                         |
| :----------------------------------------------------------- | :--------: | :--------: | :----------------------------------------------------------- |
| *CSS box model*                                              |            |            |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |    Yes     |    Yes     |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) | Partial[1] | Partial[1] | On Opera, the spinners are zoomed in, which can hide the content of the field. |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |    Yes     |    Yes     |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |    Yes     |    Yes     |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) | Partial[1] | Partial[1] | On Opera, the spinners are zoomed in, which can hide the content of the field. |
| *Text and font*                                              |            |            |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |    Yes     |    Yes     |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |    Yes     |    Yes     | See the note about [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height). |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |    Yes     |    Yes     |                                                              |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |    Yes     |    Yes     |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |  Partial   |  Partial   |                                                              |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |    Yes     |    Yes     |                                                              |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |     No     |     No     |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |  Partial   |  Partial   |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |    N.A.    |    N.A.    |                                                              |
| *Border and background*                                      |            |            |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |     No     |     No     | Supported but there is too much inconsistency between browsers to be reliable. |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |     No     |     No     |                                                              |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |     No     |     No     |                                                              |

### [Check boxes and radio buttons](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#check_boxes_and_radio_buttons)

See the `checkbox` and `radio` input types.

| Property                                                     |   N   |   T   | Note                                                         |
| :----------------------------------------------------------- | :---: | :---: | :----------------------------------------------------------- |
| *CSS box model*                                              |       |       |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) | No[1] | No[1] | Some browsers add extra margins and others stretch the widget. |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) | No[1] | No[1] | Some browsers add extra margins and others stretch the widget. |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |  No   |  No   |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |  Yes  |  Yes  |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) |  No   |  No   |                                                              |
| *Text and font*                                              |       |       |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) | N.A.  | N.A.  |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) | N.A.  | N.A.  |                                                              |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) | N.A.  | N.A.  |                                                              |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) | N.A.  | N.A.  |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) | N.A.  | N.A.  |                                                              |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) | N.A.  | N.A.  |                                                              |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) | N.A.  | N.A.  |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) | N.A.  | N.A.  |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) | N.A.  | N.A.  |                                                              |
| *Border and background*                                      |       |       |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |  No   |  No   |                                                              |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |  No   |  No   |                                                              |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |  No   |  No   |                                                              |

### [Select boxes (single line)](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#select_boxes_single_line)

See the `<select>`, `<optgroup>` and `<option>` elements.

| Property                                                     |       N       |       T       | Note                                                         |
| :----------------------------------------------------------- | :-----------: | :-----------: | :----------------------------------------------------------- |
| *CSS box model*                                              |               |               |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |  Partial[1]   |  Partial[1]   | This property is okay on the `<select>` element, but it cannot be the case on the `<option>` or `<optgroup>` elements. |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) |      No       |      Yes      |                                                              |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |    Partial    |      Yes      |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |      Yes      |      Yes      |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) |     No[1]     |  Partial[2]   | The property is applied, but in an inconsistent way between browsers on Mac OSX.The property is well applied on the `<select>` element, but is inconsistently handled on `<option>` and `<optgroup>` elements. |
| *Text and font*                                              |               |               |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |  Partial[1]   |  Partial[1]   | On Mac OSX, WebKit based browsers do not support this property on native widgets and they, along with Opera, do not support it at all on `<option>` and `<optgroup>` elements. |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |  Partial[1]   |  Partial[1]   | On Mac OSX, WebKit based browsers do not support this property on native widgets and they, along with Opera, do not support it at all on `<option>` and `<optgroup>` elements. |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |  Partial[1]   |  Partial[1]   | IE9 does not support this property on `<select>`, `<option>`, and `<optgroup>` elements; WebKit based browsers on Mac OSX do not support this property on `<option>` and `<optgroup>` elements. |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |     No[1]     |     No[1]     | IE9 on Windows 7 and WebKit based browsers on Mac OSX do not support this property on this widget. |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |  Partial[1]   |  Partial[1]   | Only Firefox provides full support for this property. Opera does not support this property at all and other browsers only support it on the `<select>` element. |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) | Partial[1][2] | Partial[1][2] | Most of the browsers only support this property on the `<select>` element.IE9 does not support this property. |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |      No       |      No       |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) | Partial[1][2] | Partial[1][2] | Most of the browsers only support this property on the `<select>` element.IE9 does not support this property. |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |  Partial[1]   |  Partial[1]   | Most of the browsers only support this property on the `<select>` element. |
| *Border and background*                                      |               |               |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |  Partial[1]   |  Partial[1]   | Most of the browsers only support this property on the `<select>` element. |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |  Partial[1]   |  Partial[1]   |                                                              |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |      No       |  Partial[1]   |                                                              |

Note Firefox does not provide any way to change the down arrow on the `<select>` element.

### [Select boxes (multiline)](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#select_boxes_multiline)

See the `<select>`, `<optgroup>` and `<option>` elements and the [`size` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/size).

| Property                                                     |     N      |     T      | Note                                                         |
| :----------------------------------------------------------- | :--------: | :--------: | :----------------------------------------------------------- |
| *CSS box model*                                              |            |            |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |    Yes     |    Yes     |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) |    Yes     |    Yes     |                                                              |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |    Yes     |    Yes     |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |    Yes     |    Yes     |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) | Partial[1] | Partial[1] | Opera does not support [`padding-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top) and [`padding-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom) on the `<select>` element. |
| *Text and font*                                              |            |            |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |    Yes     |    Yes     |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |    Yes     |    Yes     | See the note about [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height). |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) | Partial[1] | Partial[1] | IE9 does not support this property on `<select>`, `<option>`, and `<optgroup>` elements; WebKit based browsers on Mac OSX do not support this property on `<option>` and `<optgroup>` elements. |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |   No[1]    |   No[1]    | IE9 on Windows 7 and WebKit based browser on Mac OSX do not support this property on this widget. |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |   No[1]    |   No[1]    | Only supported by Firefox and IE9+.                          |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |     No     |     No     |                                                              |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |     No     |     No     |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |     No     |     No     |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) | Partial[1] | Partial[1] | Most of the browsers only support this property on the `<select>` element. |
| *Border and background*                                      |            |            |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |    Yes     |    Yes     |                                                              |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |   Yes[1]   |   Yes[1]   | On Opera the [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) property is applied only if an explicit border is set. |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |     No     | Partial[1] | IE9 does not support this property.                          |

### [Datalist](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#datalist)

See the `<datalist>` and `<input>` elements and the [`list` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/list).

| Property                                                     |  N   |  T   | Note |
| :----------------------------------------------------------- | :--: | :--: | :--- |
| *CSS box model*                                              |      |      |      |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |  No  |  No  |      |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) |  No  |  No  |      |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |  No  |  No  |      |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |  No  |  No  |      |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) |  No  |  No  |      |
| *Text and font*                                              |      |      |      |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |  No  |  No  |      |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |  No  |  No  |      |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |  No  |  No  |      |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |  No  |  No  |      |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |  No  |  No  |      |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |  No  |  No  |      |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |  No  |  No  |      |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |  No  |  No  |      |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |  No  |  No  |      |
| *Border and background*                                      |      |      |      |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |  No  |  No  |      |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |  No  |  No  |      |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |  No  |  No  |      |

### [File picker](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#file_picker)

See the `file` input type.

| Property                                                     |     N      |     T      | Note                                                         |
| :----------------------------------------------------------- | :--------: | :--------: | :----------------------------------------------------------- |
| *CSS box model*                                              |            |            |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |     No     |     No     |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) |     No     |     No     |                                                              |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |     No     |     No     |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |    Yes     |    Yes     |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) |     No     |     No     |                                                              |
| *Text and font*                                              |            |            |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |    Yes     |    Yes     |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |   No[1]    |   No[1]    | Supported, but there is too much inconsistency between browsers to be reliable. |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) | Partial[1] | Partial[1] | Many browsers apply this property to the select button.      |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |     No     |     No     |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |     No     |     No     |                                                              |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) | Partial[1] | Partial[1] | It acts more or less like an extra left margin outside the widget. |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |     No     |     No     |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |     No     |     No     |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |     No     |     No     |                                                              |
| *Border and background*                                      |            |            |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |   No[1]    |   No[1]    | Supported, but there is too much inconsistency between browsers to be reliable. |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |     No     |     No     |                                                              |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |     No     | Partial[1] | IE9 does not support this property.                          |

### [Date pickers](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#date_pickers)

See the `date` and `time` input types. Many properties are supported, but there is too much inconsistency between browsers to be reliable.

| Property                                                     |  N   |  T   | Note |
| :----------------------------------------------------------- | :--: | :--: | :--- |
| *CSS box model*                                              |      |      |      |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |  No  |  No  |      |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) |  No  |  No  |      |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |  No  |  No  |      |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) | Yes  | Yes  |      |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) |  No  |  No  |      |
| *Text and font*                                              |      |      |      |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |  No  |  No  |      |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |  No  |  No  |      |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |  No  |  No  |      |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |  No  |  No  |      |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |  No  |  No  |      |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |  No  |  No  |      |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |  No  |  No  |      |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |  No  |  No  |      |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |  No  |  No  |      |
| *Border and background*                                      |      |      |      |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |  No  |  No  |      |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |  No  |  No  |      |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |  No  |  No  |      |

### [Color pickers](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#color_pickers)

See the `color` input type:

| Property                                                     |   N   |   T   | Note                                                         |
| :----------------------------------------------------------- | :---: | :---: | :----------------------------------------------------------- |
| *CSS box model*                                              |       |       |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |  Yes  |  Yes  |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) | No[1] |  Yes  | Opera handles this like a select widget with the same restriction. |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |  Yes  |  Yes  |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |  Yes  |  Yes  |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) | No[1] |  Yes  | Opera handles this like a select widget with the same restriction. |
| *Text and font*                                              |       |       |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) | N.A.  | N.A.  |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) | N.A.  | N.A.  |                                                              |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) | N.A.  | N.A.  |                                                              |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) | N.A.  | N.A.  |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) | N.A.  | N.A.  |                                                              |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) | N.A.  | N.A.  |                                                              |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) | N.A.  | N.A.  |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) | N.A.  | N.A.  |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) | N.A.  | N.A.  |                                                              |
| *Border and background*                                      |       |       |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) | No[1] | No[1] | Supported, but there is too much inconsistency between browsers to be reliable. |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) | No[1] | No[1] |                                                              |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) | No[1] | No[1] |                                                              |

### [Meters and progress](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#meters_and_progress)

See the `<meter>` and `<progress>` elements:

| Property                                                     |    N    |     T      | Note                                                         |
| :----------------------------------------------------------- | :-----: | :--------: | :----------------------------------------------------------- |
| *CSS box model*                                              |         |            |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |   Yes   |    Yes     |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) |   Yes   |    Yes     |                                                              |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) | Partial |    Yes     |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |   Yes   |    Yes     |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) |   Yes   | Partial[1] | Chrome hides the `<progress>` and `<meter>` element when the [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) property is applied on a tweaked element. |
| *Text and font*                                              |         |            |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |  N.A.   |    N.A.    |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |  N.A.   |    N.A.    |                                                              |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |  N.A.   |    N.A.    |                                                              |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |  N.A.   |    N.A.    |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |  N.A.   |    N.A.    |                                                              |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |  N.A.   |    N.A.    |                                                              |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |  N.A.   |    N.A.    |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |  N.A.   |    N.A.    |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |  N.A.   |    N.A.    |                                                              |
| *Border and background*                                      |         |            |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |  No[1]  |   No[1]    | Supported, but there is too much inconsistency between browsers to be reliable. |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |  No[1]  |   No[1]    |                                                              |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |  No[1]  |   No[1]    |                                                              |

### [Range](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#range)

See the `range` input type. There is no standard way to change the style of the range grip and Opera has no way to tweak the default rendering of the range widget.

| Property                                                     |     N      |     T      | Note                                                         |
| :----------------------------------------------------------- | :--------: | :--------: | :----------------------------------------------------------- |
| *CSS box model*                                              |            |            |                                                              |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |    Yes     |    Yes     |                                                              |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) | Partial[1] | Partial[1] | Chrome and Opera add some extra space around the widget, whereas Opera on Windows 7 stretches the range grip. |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |     No     |    Yes     |                                                              |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |    Yes     |    Yes     |                                                              |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) | Partial[1] |    Yes     | The [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) is applied, but has no visual effect. |
| *Text and font*                                              |            |            |                                                              |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |    N.A.    |    N.A.    |                                                              |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |    N.A.    |    N.A.    |                                                              |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |    N.A.    |    N.A.    |                                                              |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |    N.A.    |    N.A.    |                                                              |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |    N.A.    |    N.A.    |                                                              |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |    N.A.    |    N.A.    |                                                              |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |    N.A.    |    N.A.    |                                                              |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |    N.A.    |    N.A.    |                                                              |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |    N.A.    |    N.A.    |                                                              |
| *Border and background*                                      |            |            |                                                              |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |   No[1]    |   No[1]    | Supported, but there is too much inconsistency between browsers to be reliable. |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) |   No[1]    |   No[1]    |                                                              |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) |   No[1]    |   No[1]    |                                                              |

### [Image buttons](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls#image_buttons)

See the `image` input type:

| Property                                                     |     N      |     T      | Note                                |
| :----------------------------------------------------------- | :--------: | :--------: | :---------------------------------- |
| *CSS box model*                                              |            |            |                                     |
| [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) |    Yes     |    Yes     |                                     |
| [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) |    Yes     |    Yes     |                                     |
| [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) |    Yes     |    Yes     |                                     |
| [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) |    Yes     |    Yes     |                                     |
| [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) |    Yes     |    Yes     |                                     |
| *Text and font*                                              |            |            |                                     |
| [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) |    N.A.    |    N.A.    |                                     |
| [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) |    N.A.    |    N.A.    |                                     |
| [`letter-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing) |    N.A.    |    N.A.    |                                     |
| [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) |    N.A.    |    N.A.    |                                     |
| [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) |    N.A.    |    N.A.    |                                     |
| [`text-indent`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-indent) |    N.A.    |    N.A.    |                                     |
| [`text-overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-overflow) |    N.A.    |    N.A.    |                                     |
| [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow) |    N.A.    |    N.A.    |                                     |
| [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform) |    N.A.    |    N.A.    |                                     |
| *Border and background*                                      |            |            |                                     |
| [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) |    Yes     |    Yes     |                                     |
| [`border-radius`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) | Partial[1] | Partial[1] | IE9 does not support this property. |
| [`box-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow) | Partial[1] | Partial[1] | IE9 does not support this property. |

# HTML：可访问性的良好基础

只要确保始终将正确的超文本标记语言元素用于正确的目的，就可以访问大量 Web 内容。本文详细介绍了如何使用 HTML 来确保最大程度的可访问性。

## [HTML 和可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#html_and_accessibility)

随着您对 HTML 的了解越来越多——阅读更多资源、查看更多示例等——您将不断看到一个共同的主题：使用语义 HTML（有时称为 POSH，或普通旧语义 HTML）的重要性。这意味着尽可能将正确的 HTML 元素用于其预期目的。

您可能想知道为什么这如此重要。毕竟，您可以结合使用 CSS 和 JavaScript 来使几乎任何 HTML 元素按照您想要的方式运行。例如，在您的网站上播放视频的控制按钮可以这样标记：

```
<div>Play video</div>
```

复制到剪贴板

但正如您稍后将更详细地看到的那样，为作业使用正确的元素是有意义的：

```
<button>Play video</button>
```

复制到剪贴板

HTML 不仅`<button>`默认应用了一些合适的样式（您可能希望覆盖这些样式），而且它们还具有内置的键盘可访问性——用户可以使用Tab键在按钮之间导航，并使用Return或激活他们的选择Enter。

如果您从项目开始就始终如一地编写语义 HTML，那么编写语义 HTML 不会比非语义（坏）标记花费更多时间。更好的是，语义标记除了可访问性之外还有其他好处：

1. **更容易开发**——如上所述，你可以免费获得一些功能，而且可以说它更容易理解。
2. **在移动设备上更好**——语义 HTML 可以说比非语义意大利面条代码在文件大小上更轻，并且更容易做出响应。
3. **有利于 SEO** — 搜索引擎更重视标题、链接等中的关键字，而不是非语义`<div>`等中包含的关键字，因此客户更容易找到您的文档。

让我们继续更详细地了解可访问的 HTML。

**注意：**最好在本地计算机上设置屏幕阅读器，以便您可以对下面显示的示例进行一些测试。有关更多详细信息，请参阅我们的[屏幕阅读器指南](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#screenreaders)。

## [良好的语义](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#good_semantics)

我们已经讨论了正确语义的重要性，以及为什么我们应该为这项工作使用正确的 HTML 元素。这是不可忽视的，因为如果处理不当，它是可访问性被严重破坏的主要地方之一。

在网络上，事实是人们使用 HTML 标记做一些非常奇怪的事情。HTML 的一些滥用是由于尚未完全忘记的遗留实践，而另一些只是无知。不管怎样，你应该替换掉这样糟糕的代码。

有时您无法摆脱糟糕的标记——您的页面可能是由某种您无法完全控制的服务器端框架生成的，或者您的页面上可能有第三方内容（例如广告横幅）您无法控制。

目标不是“全有或全无”；您可以做出的每一项改进都将有助于实现可访问性。

### [文字内容](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#text_content)

屏幕阅读器用户可以获得的最佳辅助功能之一是具有标题、段落、列表等的出色内容结构。一个出色的语义示例可能如下所示：

```
<h1>My heading</h1>

<p>This is the first section of my document.</p>

<p>I'll add another paragraph here too.</p>

<ol>
  <li>Here is</li>
  <li>a list for</li>
  <li>you to read</li>
</ol>

<h2>My subheading</h2>

<p>This is the first subsection of my document. I'd love people to be able to find this content!</p>

<h2>My 2nd subheading</h2>

<p>This is the second subsection of my content. I think is more interesting than the last one.</p>
```

复制到剪贴板

我们准备了一个文本较长的版本供您使用屏幕阅读器进行试用（请参阅 [好语义.html](https://mdn.github.io/learning-area/accessibility/html/good-semantics.html)）。如果您尝试浏览此内容，您会发现此内容非常易于浏览：

1. 当您浏览内容时，屏幕阅读器会读出每个标题，通知您标题是什么，什么是段落等。
2. 它在每个元素后停止，让您以适合您的任何速度前进。
3. 您可以在许多屏幕阅读器中跳转到下一个/上一个标题。
4. 您还可以在许多屏幕阅读器中调出所有标题的列表，允许您将它们用作方便的目录来查找特定内容。

人们有时会使用展示性 HTML 和换行符来编写标题、段落等，如下所示：

```
<font size="7">My heading</font>
<br><br>
This is the first section of my document.
<br><br>
I'll add another paragraph here too.
<br><br>
1. Here is
<br><br>
2. a list for
<br><br>
3. you to read
<br><br>
<font size="5">My subheading</font>
<br><br>
This is the first subsection of my document. I'd love people to be able to find this content!
<br><br>
<font size="5">My 2nd subheading</font>
<br><br>
This is the second subsection of my content. I think is more interesting than the last one.
```

复制到剪贴板

如果您使用屏幕阅读器尝试我们更长的版本（请参阅 [坏语义.html](https://mdn.github.io/learning-area/accessibility/html/bad-semantics.html))，你不会有很好的体验——屏幕阅读器没有任何东西可以用作路标，所以你不能检索有用的目录，整个页面被视为一个巨大的块，所以它是一口气读完的。

除了可访问性之外，还有其他问题——例如，使用 CSS 设置内容样式或使用 JavaScript 操作内容变得更加困难，因为没有可用作选择器的元素。

#### 使用清晰的语言

您使用的语言也会影响可访问性。一般来说，你应该使用清晰的语言，不要过于复杂，不要使用不必要的行话或俚语。这不仅使有认知障碍或其他障碍的人受益；它有益于那些文本不是用他们的母语写成的读者、年轻人……事实上，每个人！除此之外，您应该尽量避免使用屏幕阅读器无法清楚读出的语言和字符。例如：

- 如果可以避免，请不要使用破折号。不要写 5-7，而是写 5 到 7。
- 展开缩写——不要写 Jan，而是写 January。
- 扩展首字母缩略词，至少一次或两次。不是在第一个实例中编写 HTML，而是编写超文本标记语言。

### [页面布局](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#page_layouts)

在糟糕的过去，人们过去常常使用 HTML 表格创建页面布局——使用不同的表格单元格来包含页眉、页脚、侧边栏、主要内容列等。这不是一个好主意，因为屏幕阅读器可能会让人感到困惑读数，尤其是在布局复杂且有许多嵌套表格的情况下。

试试我们的例子 [表格布局.html](https://mdn.github.io/learning-area/accessibility/html/table-layout.html) 例如，它看起来像这样：

```
<table width="1200">
      <!-- main heading row -->
      <tr id="heading">
        <td colspan="6">

          <h1 align="center">Header</h1>

        </td>
      </tr>
      <!-- nav menu row  -->
      <tr id="nav" bgcolor="#ffffff">
        <td width="200">
          <a href="#" align="center">Home</a>
        </td>
        <td width="200">
          <a href="#" align="center">Our team</a>
        </td>
        <td width="200">
          <a href="#" align="center">Projects</a>
        </td>
        <td width="200">
          <a href="#" align="center">Contact</a>
        </td>
        <td width="300">
          <form width="300">
            <input type="search" name="q" placeholder="Search query" width="300">
          </form>
        </td>
        <td width="100">
          <button width="100">Go!</button>
        </td>
      </tr>
      <!-- spacer row -->
      <tr id="spacer" height="10">
        <td>

        </td>
      </tr>
      <!-- main content and aside row -->
      <tr id="main">
        <td id="content" colspan="4" bgcolor="#ffffff">

          <!-- main content goes here -->
        </td>
        <td id="aside" colspan="2" bgcolor="#ff80ff" valign="top">
          <h2>Related</h2>

          <!-- aside content goes here -->

        </td>
      </tr>
      <!-- spacer row -->
      <tr id="spacer" height="10">
        <td>

        </td>
      </tr>
      <!-- footer row -->
      <tr id="footer" bgcolor="#ffffff">
        <td colspan="6">
          <p>©Copyright 2050 by nobody. All rights reversed.</p>
        </td>
      </tr>
    </table>
```

复制到剪贴板

如果您尝试使用屏幕阅读器进行导航，它可能会告诉您有一个表格需要查看（尽管一些屏幕阅读器可以猜测表格布局和数据表格之间的区别）。然后，您可能（取决于您使用的屏幕阅读器）必须作为一个对象进入表格并单独查看其功能，然后再次离开表格以继续浏览内容。

表格布局是过去的遗物——当 CSS 支持在浏览器中不普遍时，它们是有意义的，但现在它们只会给屏幕阅读器用户造成混乱。此外，它们的源代码需要更多的标记，这使得它们不太灵活且更难以维护。您可以通过将您以前的经验与[更现代的网站结构示例](https://mdn.github.io/learning-area/html/introduction-to-html/document_and_website_structure/), 看起来像这样：

```
<header>
  <h1>Header</h1>
</header>

<nav>
  <!-- main navigation in here -->
</nav>

<!-- Here is our page's main content -->
<main>

  <!-- It contains an article -->
  <article>
    <h2>Article heading</h2>

    <!-- article content in here -->
  </article>

  <aside>
    <h2>Related</h2>

    <!-- aside content in here -->
  </aside>

</main>

<!-- And here is our main footer that is used across all the pages of our website -->

<footer>
  <!-- footer content in here -->
</footer>
```

复制到剪贴板

如果您使用屏幕阅读器尝试我们更现代的结构示例，您会发现布局标记不再妨碍并混淆内容读数。它在代码大小方面也更精简和更小，这意味着更容易维护代码，并且用户下载的带宽更少（尤其是那些连接速度较慢的用户）。

创建布局时的另一个考虑因素是使用 HTML5 语义元素，如上例所示（请参阅[内容分段](https://developer.mozilla.org/en-US/docs/Web/HTML/Element#content_sectioning)）——您可以仅使用嵌套[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)元素创建布局，但最好使用适当的分段元素来包装主导航 ( [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav))、页脚( [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer))、重复内容单元 ( [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)) 等。这些为屏幕阅读器（和其他工具）提供了额外的语义，为用户提供有关他们正在导航的内容的额外线索（请参阅[屏幕阅读器支持新的 HTML5 部分元素](https://www.weba11y.com/blog/2016/04/22/screen-reader-support-for-new-html5-section-elements/) 了解屏幕阅读器支持是什么样的）。

**注意：**除了具有良好的语义和吸引人的布局之外，您的内容在其源代码顺序上应该具有逻辑意义——您可以在以后使用 CSS 将其放置在您想要的位置，但您应该从一开始就获得正确的源代码顺序，因此屏幕阅读器用户读给他们的内容是有意义的。

### [用户界面控件](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#ui_controls)

通过 UI 控件，我们指的是用户与之交互的 Web 文档的主要部分——最常见的是按钮、链接和表单控件。在本节中，我们将了解创建此类控件时要注意的基本可访问性问题。后面关于 WAI-ARIA 和多媒体的文章将着眼于 UI 可访问性的其他方面。

UI 控件可访问性的一个关键方面是默认情况下，浏览器允许通过键盘操作它们。您可以使用我们的[本机键盘accessibility.html](https://mdn.github.io/learning-area/tools-testing/cross-browser-testing/accessibility/native-keyboard-accessibility.html) 示例（见 [源代码](https://github.com/mdn/learning-area/blob/master/tools-testing/cross-browser-testing/accessibility/native-keyboard-accessibility.html)）。在新选项卡中打开它，然后尝试按 Tab 键；按几下后，您应该会看到选项卡焦点开始在不同的可聚焦元素之间移动。每个浏览器中的焦点元素都有一个突出显示的默认样式（不同浏览器之间略有不同），这样您就可以知道哪个元素是焦点。

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/button-focused-unfocused.png)

**注意：**从 Firefox 84 开始，您还可以启用显示页面跳转顺序的叠加层。有关更多信息，请参阅： [辅助功能检查器 > 显示网页跳转顺序](https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector#show_web_page_tabbing_order)。

然后，您可以按 Enter/Return 跟随焦点链接或按一个按钮（我们已经包含了一些 JavaScript 以使按钮发出消息警报），或者开始键入以在文本输入中输入文本。其他表单元素有不同的控件，例如，[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)元素可以显示其选项并使用向上和向下箭头键在它们之间循环。

**注意：**不同的浏览器可能有不同的可用键盘控制选项。有关更多详细信息，请参阅[使用本机键盘辅助功能](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#using_native_keyboard_accessibility)。

您基本上可以免费获得这种行为，只需使用适当的元素，例如

```
<h1>Links</h1>

<p>This is a link to <a href="https://www.mozilla.org">Mozilla</a>.</p>

<p>Another link, to the <a href="https://developer.mozilla.org">Mozilla Developer Network</a>.</p>

<h2>Buttons</h2>

<p>
  <button data-message="This is from the first button">Click me!</button>
  <button data-message="This is from the second button">Click me too!</button>
  <button data-message="This is from the third button">And me!</button>
</p>

<h2>Form</h2>

<form>
  <div>
    <label for="name">Fill in your name:</label>
    <input type="text" id="name" name="name">
  </div>
  <div>
    <label for="age">Enter your age:</label>
    <input type="text" id="age" name="age">
  </div>
  <div>
    <label for="mood">Choose your mood:</label>
    <select id="mood" name="mood">
      <option>Happy</option>
      <option>Sad</option>
      <option>Angry</option>
      <option>Worried</option>
    </select>
  </div>
</form>
```

复制到剪贴板

这意味着适当地使用链接、按钮、表单元素和标签（包括[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)表单控件的元素）。

然而，人们有时会用 HTML 做奇怪的事情，这又是一种情况。例如，您有时会看到使用[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s标记的按钮，例如：

```
<div data-message="This is from the first button">Click me!</div>
<div data-message="This is from the second button">Click me too!</div>
<div data-message="This is from the third button">And me!</div>
```

复制到剪贴板

但是不建议使用这样的代码——如果您只使用[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)元素，您将立即失去本机键盘可访问性，而且您无法获得按钮获得的任何默认 CSS 样式。

#### 重新构建键盘可访问性

重新添加这些优势需要一些工作（您可以在我们的 [假div-buttons.html](https://mdn.github.io/learning-area/tools-testing/cross-browser-testing/accessibility/fake-div-buttons.html) 示例——另见 [源代码](https://github.com/mdn/learning-area/blob/master/tools-testing/cross-browser-testing/accessibility/fake-div-buttons.html)）。在这里，我们`<div>`通过为每个按钮赋予属性来赋予我们的假按钮聚焦的能力（包括通过选项卡）`tabindex="0"`：

```
<div data-message="This is from the first button" tabindex="0">Click me!</div>
<div data-message="This is from the second button" tabindex="0">Click me too!</div>
<div data-message="This is from the third button" tabindex="0">And me!</div>
```

复制到剪贴板

基本上，该[`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-tabindex)属性主要是为了允许可选项卡元素具有自定义选项卡顺序（以正数顺序指定），而不是仅以其默认源顺序进行选项卡切换。这几乎总是一个坏主意，因为它会导致严重的混乱。仅当您确实需要时才使用它，例如，如果布局以与源代码非常不同的视觉顺序显示事物，并且您想让事物更合乎逻辑地工作。还有另外两个选项`tabindex`：

- `tabindex="0"`— 如上所述，此值允许通常不可制表的元素变为可制表。这是 最有用的值`tabindex`。
- `tabindex="-1"` — 这允许通常不是可选项卡的元素以编程方式接收焦点，例如，通过 JavaScript，或作为链接的目标。

虽然上述添加允许我们使用 Tab 键切换到按钮，但它不允许我们通过 Enter/Return 键激活它们。为此，我们必须添加以下 JavaScript 技巧：

```
document.onkeydown = function(e) {
  if(e.keyCode === 13) { // The Enter/Return key
    document.activeElement.click();
  }
};
```

复制到剪贴板

在这里，我们向`document`对象添加了一个侦听器，以检测何时按下了键盘上的按钮。我们通过事件对象的[`keyCode`](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode)属性检查按下了什么按钮；如果它是与 Return/Enter 匹配的键码，我们使用 运行存储在按钮`onclick`处理程序中的函数`document.activeElement.click()`。[`activeElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement)这为我们提供了当前关注页面的元素。

重新构建功能会带来很多额外的麻烦。而且肯定会有其他问题。**最好首先将正确的元素用于正确的工作。**

#### 有意义的文字标签

UI 控件文本标签对所有用户都非常有用，但正确使用它们对于残障用户尤其重要。

您应该确保您的按钮和链接文本标签易于理解且与众不同。不要只对标签使用“单击此处”，因为屏幕阅读器用户有时会得到按钮和表单控件的列表。以下屏幕截图显示了我们的控件在 Mac 上被 VoiceOver 列出。

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/voiceover-formcontrols.png)

确保您的标签脱离上下文、单独阅读以及在它们所在段落的上下文中有意义。例如，以下显示了良好链接文本的示例：

```
<p>Whales are really awesome creatures. <a href="whales.html">Find out more about whales</a>.</p>
```

复制到剪贴板

但这是错误的链接文本：

```
<p>Whales are really awesome creatures. To find more out about whales, <a href="whales.html">click here</a>.</p>
```

复制到剪贴板

**注意：**您可以在我们的[创建超链接](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)文章中找到更多关于链接实现和最佳实践的信息。您还可以在以下位置查看一些好的和坏的示例[好链接.html](https://mdn.github.io/learning-area/accessibility/html/good-links.html) 和 [坏链接.html](https://mdn.github.io/learning-area/accessibility/html/bad-links.html).

表单标签对于让您了解需要在每个表单输入中输入的内容也很重要。以下似乎是一个足够合理的例子：

```
Fill in your name: <input type="text" id="name" name="name">
```

复制到剪贴板

但是，这对残疾用户来说不是很有用。上面的例子中没有任何内容可以明确地将标签与表单输入相关联，并明确说明如果看不到如何填写。如果您使用某些屏幕阅读器访问它，您可能只会看到“编辑文本”行的描述。

下面是一个更好的例子：

```
<div>
  <label for="name">Fill in your name:</label>
  <input type="text" id="name" name="name">
</div>
```

复制到剪贴板

使用这样的代码，标签将与输入明确关联；描述将更像是“填写您的姓名：编辑文本”。

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/voiceover-good-form-label.png)

作为一个额外的好处，在大多数浏览器中，将标签与表单输入相关联意味着您可以单击标签来选择或激活表单元素。这为输入提供了更大的命中区域，使其更容易选择。

**注意：**您可以在[good-form.html](https://mdn.github.io/learning-area/accessibility/html/good-form.html) 和 [坏表单.html](https://mdn.github.io/learning-area/accessibility/html/bad-form.html).

您可以在以下视频中找到有关正确文本标签的重要性以及如何使用[Firefox 辅助功能检查器](https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector)调查文本标签问题的很好的解释：

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/YhlAVlfH0rQ" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" loading="lazy" style="box-sizing: border-box; max-width: 100%; border: 0px;"></iframe>

## [可访问的数据表](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#accessible_data_tables)

可以使用非常简单的标记编写基本数据表，例如：

```
<table>
  <tr>
    <td>Name</td>
    <td>Age</td>
    <td>Gender</td>
  </tr>
  <tr>
    <td>Gabriel</td>
    <td>13</td>
    <td>Male</td>
  </tr>
  <tr>
    <td>Elva</td>
    <td>8</td>
    <td>Female</td>
  </tr>
  <tr>
    <td>Freida</td>
    <td>5</td>
    <td>Female</td>
  </tr>
</table>
```

复制到剪贴板

但这有问题——屏幕阅读器用户无法将行或列作为数据分组关联在一起。为此，您需要知道标题行是什么，以及它们是否在行、列等的标题中。这只能在上表中直观地完成（请参阅[坏表.html](https://mdn.github.io/learning-area/accessibility/html/bad-table.html) 并自己尝试这个例子）。

现在看看我们的 [朋克乐队表示例](https://github.com/mdn/learning-area/blob/master/css/styling-boxes/styling-tables/punk-bands-complete.html) — 您可以在此处看到一些可访问性辅助工具：

- 表格标题是使用`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/th)元素定义的——您还可以使用`scope`属性指定它们是行还是列的标题。这为您提供了完整的数据组，可供屏幕阅读器作为单个单元使用。
- 该`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption)元素和`<table>` `summary`属性都做类似的工作-他们作为一个表替代文字，给人一种屏幕阅读器用户的表的内容有用的摘要。该`<caption>`元素通常是首选，因为它使视力正常的用户也可以访问它的内容，他们也可能会发现它很有用。你真的不需要两者。

**注意：**有关可访问数据表的更多详细信息，请参阅我们的[HTML 表高级功能和可访问性](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced)文章。

## [替代文本](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#text_alternatives)

文本内容本质上是可访问的，但多媒体内容不一定如此——视觉障碍者无法看到图像和视频内容，听觉障碍者无法听到音频内容。我们在[可访问的多媒体](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia)中详细介绍了视频和音频内容，但在本文中，我们将着眼于不起眼的[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)元素的可访问性。

我们写了一个简单的例子， [可访问-image.html](https://mdn.github.io/learning-area/accessibility/html/accessible-image.html)，其中包含同一图像的四个副本：

```
<img src="dinosaur.png">

<img src="dinosaur.png"
     alt="A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.">

<img src="dinosaur.png"
     alt="A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth."
     title="The Mozilla red dinosaur">

<img src="dinosaur.png" aria-labelledby="dino-label">

<p id="dino-label">The Mozilla red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.</p>
```

复制到剪贴板

第一张图片，当通过屏幕阅读器查看时，并没有真正为用户提供太多帮助——例如，VoiceOver 读出“/dinosaur.png, image”。它读出文件名以尝试提供一些帮助。在这个例子中，用户至少会知道它是某种恐龙，但通常文件可能会以机器生成的文件名（例如来自数码相机）上传，并且这些文件名可能不提供图像内容的上下文。

**注意：**这就是为什么永远不要在图像中包含文本内容的原因——屏幕阅读器无法访问它。还有其他缺点 - 您无法选择它并复制/粘贴它。不要这样做！

当屏幕阅读器遇到第二张图片时，它会读出完整的 alt 属性——“一只红色的霸王龙：一只双腿恐龙像人类一样直立，手臂很小，头很大，有很多锋利的牙齿。”。

这突出了不仅在所谓的**替代文本**不可用的情况下使用有意义的文件名的重要性，而且还确保`alt`尽可能在属性中提供替代文本。请注意，`alt`属性的内容应始终提供图像的直接表示及其视觉传达的内容。这里不应该包含任何个人知识或额外的描述，因为它对之前没有遇到过图像的人没有用。

需要考虑的一件事是您的图像在您的内容中是否有意义，或者它们是否纯粹用于视觉装饰，因此没有意义。如果它们是装饰性的，最好编写一个空文本作为`alt`属性值（请参阅[Empty alt 属性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#empty_alt_attributes)）或仅将它们作为 CSS 背景图像包含在页面中。

**注意：**阅读[HTML 中的](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)[图像](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)和[响应式图像](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)以获取有关图像实现和最佳实践的更多信息。

如果您确实想提供额外的上下文信息，则应将其放在图像周围的文本中或`title`属性内，如上所示。在这种情况下，大多数屏幕阅读器会读出替代文本、标题属性和文件名。此外，浏览器在鼠标悬停时将标题文本显示为工具提示。

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML/title-attribute.png)

让我们再快速看一下第四种方法：

```
<img src="dinosaur.png" aria-labelledby="dino-label">

<p id="dino-label">The Mozilla red Tyrannosaurus ... </p>
```

复制到剪贴板

在这种情况下，我们根本没有使用该`alt`属性 - 相反，我们将图像的描述呈现为常规文本段落，给它一个`id`，然后使用该`aria-labelledby`属性来引用那个`id`，这会导致屏幕阅读器使用那个段落作为该图像的替代文本/标签。如果您想使用相同的文本作为多个图像的标签，这尤其有用——这是`alt`.

**注：** `aria-labelledby`是部分[围唱](https://www.w3.org/TR/wai-aria-1.1/)规范，它允许开发人员在他们的标记中添加额外的语义，以在需要时提高屏幕阅读器的可访问性。要了解有关其工作原理的更多信息，请阅读我们的[WAI-ARIA 基础](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics)文章。

### [其他文本替代机制](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#other_text_alternative_mechanisms)

图像还有另一种机制可用于提供描述性文本。例如，有一个`longdesc`属性旨在指向包含图像扩展描述的单独 Web 文档，例如：

```
<img src="dinosaur.png" longdesc="dino-info.html">
```

复制到剪贴板

这听起来是个好主意，特别是对于像大图表这样的信息图表，其中包含大量信息，这些信息或许可以表示为可访问的数据表（请参阅[可访问数据表](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#accessible_data_tables)）。但是，`longdesc`屏幕阅读器并不始终支持，并且非屏幕阅读器用户完全无法访问内容。将长描述包含在与图像相同的页面上可以说要好得多，或者使用常规链接链接到它。

HTML5 包括两个新元素——[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)和[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption)——它们应该将某种图形（它可以是任何东西，不一定是图像）与图形标题相关联：

```
<figure>
  <img src="dinosaur.png" alt="The Mozilla Tyrannosaurus">
  <figcaption>A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.</figcaption>
</figure>
```

复制到剪贴板

不幸的是，大多数屏幕阅读器似乎还没有将图形标题与他们的图形相关联。也就是说，元素结构对于 CSS 样式很有用，而且它提供了一种方法来将图像的描述放在源中。

### [空 alt 属性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#empty_alt_attributes)

```
<h3>
  <img src="article-icon.png" alt="">
  Tyrannosaurus Rex: the king of the dinosaurs
</h3>
```

复制到剪贴板

有时，页面设计中可能包含图像，但其主要目的是视觉装饰。您会在上面的代码示例中注意到图像的`alt`属性为空——这是为了让屏幕阅读器识别图像，但不会尝试描述图像（相反，他们只会说“图像”或类似的）。

使用空`alt`而不是不包含它的原因是因为如果没有`alt`提供，许多屏幕阅读器会宣布整个图像 URL 。在上面的示例中，图像充当与其关联的标题的视觉装饰。在这种情况下，以及图像只是装饰而没有内容值的情况下，您应该`alt`在`img`元素中包含一个空值。另一种选择是使用 aria[`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)属性，[`role="presentation"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/presentation_role)因为这也会阻止屏幕阅读器读出替代文本。

**注意：**如果可能，您应该使用 CSS 来显示仅具有装饰性的图像。

## [更多关于链接](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#more_on_links)

链接（[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)具有`href`属性的元素），取决于它们的使用方式，可以帮助或损害可访问性。默认情况下，链接在外观上是可访问的。它们可以通过帮助用户快速导航到文档的不同部分来提高可访问性。如果它们的可访问样式被删除或者 JavaScript 导致它们以意想不到的方式运行，它们也会损害可访问性。

### [链接样式](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#link_styling)

默认情况下，链接在颜色和[文本装饰](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)方面与其他文本在视觉上不同，链接默认为蓝色和下划线，访问时为紫色和下划线，当它们获得键盘焦点时带有[焦点环](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus)。

颜色不应用作区分链接与非链接内容的唯一方法。与所有文本一样，链接文本颜色必须与背景颜色明显不同（[对比度为 4.5:1](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable/Color_contrast)）。此外，链接在视觉上应该与非链接文本有显着的不同。链接文本和周围文本之间以及默认、访问和焦点/活动状态之间的最低对比度要求为 3:1，所有这些状态颜色和背景颜色之间的对比度要求为 4:5。

### [`onclick` 事件](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#onclick_events)

锚标签经常与`onclick`事件一起滥用，通过将**href**设置为`"#"`或`"javascript:void(0)"`阻止页面刷新来创建伪按钮。

在复制或拖动链接、在新选项卡或窗口中打开链接、添加书签以及 JavaScript 仍在下载、出错或被禁用时，这些值会导致意外行为。这也向辅助技术（例如，屏幕阅读器）传达了不正确的语义。在这些情况下，建议使用 a[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)代替。通常，您应该只使用锚点来使用正确的 URL 进行导航。

### [外部链接和非 HTML 资源的链接](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#external_links_and_linking_to_non-html_resources)

通过`target="_blank"`声明在新选项卡或窗口中打开的链接及其`href`值指向文件资源的链接应包含有关激活链接时将发生的行为的指示符。

当新选项卡、窗口或应用程序意外打开时，视力低下的人、借助屏幕阅读技术进行导航或有认知问题的人可能会感到困惑。旧版本的屏幕阅读软件甚至可能不会宣布该行为。

#### 打开新标签页或窗口的链接

```
<a target="_blank" href="https://www.wikipedia.org/">Wikipedia (opens in a new window)</a>
```

复制到剪贴板

#### 链接到非 HTML 资源

```
<a target="_blank" href="2017-annual-report.ppt">2017 Annual Report (PowerPoint)</a>
```

复制到剪贴板

如果使用图标代替文本来表示这种链接行为，请确保它包含[替代说明](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-alt)。

- [WebAIM：链接和超文本 - 超文本链接](https://webaim.org/techniques/hypertext/hypertext_links)
- [MDN 理解 WCAG，Guideline 3.2 解释](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#guideline_3.2_—_predictable_make_web_pages_appear_and_operate_in_predictable_ways)
- [G200：仅在必要时从链接打开新窗口和选项卡 | WCAG 2.0 的 W3C 技术](https://www.w3.org/TR/WCAG20-TECHS/G200.html)
- [G201：打开新窗口时给用户提前警告| WCAG 2.0 的 W3C 技术](https://www.w3.org/TR/WCAG20-TECHS/G201.html)

### [跳过链接](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#skip_links)

跳过链接，也称为skipnav，是`a`放置在尽可能靠近[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)链接到页面主要内容开头的开头元素的元素。此链接允许人们绕过网站上多个页面中重复的内容，例如网站的标题和主导航。

跳过链接对于借助开关控制、语音命令或口棒/头棒等辅助技术进行导航的人尤其有用，在这些技术中，通过重复链接移动的行为可能是一项费力的任务。

- [WebAIM：“跳过导航”链接](https://webaim.org/techniques/skipnav/)
- [操作方法：使用跳过导航链接 - A11Y 项目](https://www.a11yproject.com/posts/2013-05-11-skip-nav-links/)
- [MDN 理解 WCAG，Guideline 2.4 解释](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.4_—_navigable_provide_ways_to_help_users_navigate_find_content_and_determine_where_they_are)
- [理解成功标准 2.4.1 | W3C 理解 WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)

### [接近](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#proximity)

大量交互式内容（包括锚点）放置在视觉上非常接近的位置，应插入空间以将它们分开。这种间距对于患有精细运动控制问题并且可能在导航时意外激活错误交互内容的人是有益的。

可以使用 CSS 属性创建间距，例如[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin).

- [手颤和巨大的按钮问题 - Axess Lab](https://axesslab.com/hand-tremors/)

## [测试你的技能！](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#test_your_skills!)

您已读完本文，但您还记得最重要的信息吗？在继续之前，请参阅[测试您的技能：HTML 可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Test_your_skills:_HTML_accessibility)以验证您是否保留了此信息。

## [概括](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#summary)

您现在应该精通在大多数情况下编写可访问的 HTML。我们的 WAI-ARIA 基础文章将有助于填补这方面的知识空白，但这篇文章已经涵盖了基础知识。接下来，我们将探讨 CSS 和 JavaScript，以及它们的好坏如何影响可访问性。

# CSS 和 JavaScript 可访问性最佳实践

如果使用得当，CSS 和 JavaScript 也有可能实现可访问的 Web 体验……否则，如果滥用它们会严重损害可访问性。本文概述了一些应考虑的 CSS 和 JavaScript 最佳实践，以确保即使是复杂的内容也尽可能易于访问。

## [CSS 和 JavaScript 是否可以访问？](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#css_and_javascript_are_accessible)

CSS 和 JavaScript 对于可访问性的重要性不如 HTML，但它们仍然能够帮助或破坏可访问性，这取决于它们的使用方式。换句话说，考虑一些最佳实践建议以确保使用 CSS 和 JavaScript 不会破坏文档的可访问性是很重要的。

## [CSS](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#css)

让我们从查看 CSS 开始。

### [正确的语义和用户期望](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#correct_semantics_and_user_expectation)

可以使用 CSS 使任何 HTML 元素看起来像*任何东西*，但这并不意味着您应该这样做。正如我们在[HTML：可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)文章的[良好基础中](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)经常提到的那样，您应该尽可能为工作使用适当的语义元素。如果不这样做，可能会给每个人带来混乱和可用性问题，尤其是残障用户。使用正确的语义与用户的期望有很大关系——元素根据它们的功能以特定的方式外观和行为，而这些常见的约定是用户所期望的。

例如，如果开发人员没有适当地使用标题元素来标记内容，屏幕阅读器用户将无法通过标题元素导航页面。同理，如果您将标题设置为看起来不像标题，则标题将失去其视觉目的。

经验法则是，您可以更新页面功能的样式以适应您的设计，但不要对其进行过多更改，以免其外观或行为不再符合预期。以下部分总结了要考虑的主要 HTML 功能。

#### “标准”文本内容结构

标题、段落、列表——页面的核心文本内容：

```
<h1>Heading</h1>

<p>Paragraph</p>

<ul>
  <li>My list</li>
  <li>has two items.</li>
</ul>
```

复制到剪贴板

一些典型的 CSS 可能如下所示：

```
h1 {
  font-size: 5rem;
}

p, li {
  line-height: 1.5;
  font-size: 1.6rem;
}
```

复制到剪贴板

你应该：

- 选择合理的字体大小、行高、字母间距等，使您的文本合乎逻辑、清晰易读且易于阅读。
- 确保您的标题从正文中脱颖而出，通常像默认样式一样大而粗。您的列表应该看起来像列表。
- 您的文本颜色应与背景颜色形成鲜明对比。

有关详细信息，请参阅[HTML 文本基础知识](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)和[样式文本](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text)。

#### 强调文字

内联标记特别强调它所包装的文本：

```
<p>The water is <em>very hot</em>.</p>

<p>Water droplets collecting on surfaces is called <strong>condensation</strong>.</p>
```

复制到剪贴板

您可能想为强调的文本添加一些简单的颜色：

```
strong, em {
  color: #a60000;
}
```

复制到剪贴板

然而，您很少需要以任何重要的方式设置强调元素的样式。粗体和斜体文本的标准约定非常容易识别，改变样式会引起混淆。有关重点的更多信息，请参阅[重点和重要性](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#emphasis_and_importance)。

#### 缩写

允许缩写、首字母缩略词或初始化与其扩展相关联的元素：

```
<p>Web content is marked up using <abbr title="Hypertext Markup Language">HTML</abbr>.</p>
```

复制到剪贴板

同样，您可能希望以某种简单的方式对其进行样式设置：

```
abbr {
  color: #a60000;
}
```

复制到剪贴板

公认的缩写样式约定是虚线下划线，明显偏离这一点是不明智的。有关缩写的更多信息，请参阅[缩写](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting#abbreviations)。

#### 链接

超链接——您到达网络上新地方的方式：

```
<p>Visit the <a href="https://www.mozilla.org">Mozilla homepage</a>.</p>
```

复制到剪贴板

一些非常简单的链接样式如下所示：

```
a {
  color: #ff0000;
}

a:hover, a:visited, a:focus {
  color: #a60000;
  text-decoration: none;
}

a:active {
  color: #000000;
  background-color: #a60000;
}
```

复制到剪贴板

标准链接约定带有下划线，标准状态下的颜色不同（默认：蓝色），之前访问过链接时的另一种颜色变化（默认：紫色），激活链接时的另一种颜色（默认：红色） . 此外，当链接被鼠标悬停时，鼠标指针会变成一个指针图标，并且当链接被聚焦（例如通过 Tab 键）或被激活时，该链接会被突出显示。下图显示了 Firefox（虚线轮廓）和 Chrome（蓝色轮廓）中的突出显示：

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript/focus-highlight-firefox.png)

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript/focus-highlight-chrome.png)

只要您在用户与链接交互时不断向他们提供反馈，您就可以对链接样式发挥创意。当状态改变时肯定会发生一些事情，你不应该摆脱指针光标或轮廓——对于使用键盘控件的人来说，这两者都是非常重要的辅助工具。

#### 表单元素

允许用户将数据输入网站的元素：

```
<div>
  <label for="name">Enter your name</label>
  <input type="text" id="name" name="name">
</div>
```

复制到剪贴板

你可以在我们的 [表单-css.html](https://github.com/mdn/learning-area/blob/master/accessibility/css/form-css.html) 例子 （[现场观看](https://mdn.github.io/learning-area/accessibility/css/form-css.html) 还）。

您为表单编写的大部分 CSS 将用于调整元素大小、排列标签和输入，并使它们看起来整洁。

但是，您不应该偏离焦点时表单元素收到的预期视觉反馈，这与链接基本相同（见上文）。您可以设置表单焦点/悬停状态的样式，使这种行为在浏览器之间更加一致或更好地适应您的页面设计，但不要完全摆脱它——同样，人们依靠这些线索来帮助他们了解正在发生的事情.

#### 表

用于呈现表格数据的表格。

您可以在我们的 [table-css.html](https://github.com/mdn/learning-area/blob/master/accessibility/css/table-css.html) 例子 （[现场直播](https://mdn.github.io/learning-area/accessibility/css/table-css.html)）。

表格 CSS 通常用于使表格更适合您的设计并且看起来不那么难看。确保表格标题突出（通常使用粗体）是一个好主意，并使用斑马条纹使不同的行更容易解析。

### [颜色和颜色对比](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#color_and_color_contrast)

为您的网站选择配色方案时，请确保文本（前景）颜色与背景颜色形成鲜明对比。您的设计可能看起来很酷，但如果有色盲等视觉障碍的人无法阅读您的内容，那就不好了。

有一种简单的方法可以检查您的对比度是否足够大而不会引起问题。网上有许多对比度检查工具，您可以输入前景色和背景色来检查它们。例如 WebAIM 的[颜色对比检查器](https://webaim.org/resources/contrastchecker/) 使用简单，并解释了您需要什么才能符合关于颜色对比度的 WCAG 标准。

**注意：**高对比度还可以让任何使用带有光面屏幕的智能手机或平板电脑的人在阳光下等明亮环境中更好地阅读页面。

另一个提示是不要仅依赖颜色作为路标/信息，因为这对那些看不到颜色的人没有好处。例如，不要用红色标记所需的表单字段，而是用星号和红色标记它们。

### [藏东西](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#hiding_things)

在很多情况下，视觉设计要求并非一次显示所有内容。例如，在我们的[选项卡式信息框示例](https://mdn.github.io/learning-area/css/css-layout/practical-positioning-examples/info-box.html) （看 [源代码](https://github.com/mdn/learning-area/blob/master/css/css-layout/practical-positioning-examples/info-box.html)）我们有三个信息面板，但我们[定位](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)他们在彼此的顶部，提供可点击的显示每一个标签（也可以访问键盘-您也可以使用Tab键和回车键/返回，选择它们）。

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript/tabbed-info-box.png)

屏幕阅读器用户不关心这些 — 只要源顺序合理，他们对内容感到满意，并且他们可以获得所有内容。绝对定位（如本示例中使用的）通常被视为隐藏内容以获得视觉效果的最佳机制之一，因为它不会阻止屏幕阅读器访问它。

另一方面，您不应该使用or ，因为它们确实对屏幕阅读器隐藏了内容。当然，除非您有充分的理由希望对屏幕阅读器隐藏此内容。[`visibility`](https://developer.mozilla.org/en-US/docs/Web/CSS/visibility)`:hidden`[`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)`:none`

**笔记：** [仅适用于屏幕阅读器用户的不可见内容](https://webaim.org/techniques/css/invisiblecontent/) 有更多关于这个主题的有用细节。

### [接受用户可以覆盖样式](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#accept_that_users_can_override_styles)

#### 接受用户可以覆盖您的样式

用户可以使用自己的自定义样式覆盖您的样式，例如：

- 见莎拉·马多克斯 (Sarah Maddox) [如何在 Firefox 中使用自定义样式表 (CSS)](https://www.itsupportguides.com/knowledge-base/computer-accessibility/how-to-use-a-custom-style-sheet-css-with-firefox/) 有关如何在 Firefox 中手动执行此操作的有用指南，以及 [如何在 Internet Explorer 中使用自定义样式表 (CSS)](https://www.itsupportguides.com/knowledge-base/computer-accessibility/how-to-use-a-custom-style-sheet-css-with-internet-explorer/) 由 Adrian Gordon 提供的等效 IE 说明。
- 使用扩展可能更容易，例如 Stylish 扩展可用于 [火狐](https://addons.mozilla.org/en-US/firefox/addon/stylish/), [苹果浏览器](https://safari-extensions.apple.com/details/?id=com.sobolev.stylish-5555L95H45), [歌剧](https://addons.opera.com/en/extensions/details/stylish/)， 和 [铬合金](https://chrome.google.com/webstore/detail/stylish/fjnbnpbmkenffdnngjfgmeleoegfcffe).

用户可能出于多种原因这样做。视障用户可能希望在他们访问的所有网站上将文本放大，或者颜色严重不足的用户可能希望将所有网站置于易于查看的高对比度颜色中。无论需要什么，您都应该对此感到满意，并使您的设计足够灵活，以便此类更改能够在您的设计中发挥作用。例如，您可能希望确保您的主要内容区域可以处理更大的文本（也许它会开始滚动以允许看到所有内容），而不会只是隐藏它或完全中断。

## [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#javascript)

JavaScript 也会破坏可访问性，具体取决于它的使用方式。

现代 JavaScript 是一种强大的语言，如今我们可以用它做很多事情，从简单的内容和 UI 更新到成熟的 2D 和 3D 游戏。没有任何规则规定所有人都必须 100% 访问所有内容——您只需要尽您所能，并使您的应用程序尽可能易于访问。

简单的内容和功能可以说很容易访问——例如文本、图像、表格、表单和激活功能的按钮。正如我们在[HTML：可访问性的良好基础一文中所看到的](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)，主要考虑因素是：

- 良好的语义：为正确的工作使用正确的元素。例如，确保使用标题和段落以及[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)和[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)元素
- 确保内容以文本形式提供，无论是直接作为文本内容、表单元素的良好文本标签，还是[替代文本](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#text_alternatives)，例如图像的替代文本。

我们还查看了一个示例，说明如何使用 JavaScript 来构建缺失的功能——请参阅 中的[构建键盘可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#building_keyboard_accessibility_back_in)。这并不理想——实际上你应该为正确的工作使用正确的元素——但它表明在由于某种原因你无法控制所使用的标记的情况下这是可能的。提高非语义 JavaScript 驱动小部件的可访问性的另一种方法是使用 WAI-ARIA 为屏幕阅读器用户提供额外的语义。下一篇文章也会详细介绍这一点。

像 3D 游戏这样的复杂功能并不那么容易实现——使用[WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)创建的复杂 3D 游戏将在一个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)元素上呈现，该元素目前无法为严重视力受损的用户提供替代文本或其他信息以使用. 这是有争议的这样的游戏并不真的有这样一群人作为其主要目标受众的一部分，这将是不合理的，你要实现100％接触到盲人，但是你可以实现[键盘控制](https://developer.mozilla.org/en-US/docs/Games/Techniques/Control_mechanisms/Desktop_with_mouse_and_keyboard)等等它可供非鼠标用户使用，并使配色方案具有足够的对比度，以便有颜色缺陷的用户使用。

### [JavaScript 过多的问题](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#the_problem_with_too_much_javascript)

当人们过度依赖 JavaScript 时，问题往往就会出现。有时你会看到一个网站，所有的东西都是用 JavaScript 完成的——HTML 是由 JavaScript 生成的，CSS 是由 JavaScript 生成的，等等。这有各种各样的可访问性和其他相关的问题，所以它不是劝告。

除了为正确的工作使用正确的元素外，您还应该确保将正确的技术用于正确的工作！仔细考虑您是否需要闪亮的 JavaScript 驱动的 3D 信息框，或者纯旧文本是否可以。仔细考虑您是否需要复杂的非标准表单小部件，或者文本输入是否可以。并且尽可能不要使用 JavaScript 生成所有 HTML 内容。

### [保持低调](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#keeping_it_unobtrusive)

在创建内容时，您应该牢记**不引人注目的 JavaScript**。Unobtrusive JavaScript 的想法是应该尽可能使用它来增强功能，而不是完全构建它——理想情况下，基本功能应该在没有 JavaScript 的情况下工作，尽管这并不总是一种选择。但同样，其中很大一部分是在可能的情况下使用内置浏览器功能。

不引人注目的 JavaScript 的良好示例包括：

- 提供客户端表单验证，可以快速提醒用户他们的表单条目出现问题，而无需等待服务器检查数据。如果它不可用，表单仍然可以工作，但验证可能会更慢。
- 为`<video>`仅使用键盘的用户可以访问的HTML5 提供自定义控件，以及可用于在 JavaScript 不可用时访问视频的直接链接（默认`<video>`浏览器控件在大多数浏览器中无法通过键盘访问）。

例如，我们编写了一个快速而肮脏的客户端表单验证示例 - 请参阅 [表单验证.html](https://github.com/mdn/learning-area/blob/master/accessibility/css/form-validation.html) （还 [现场观看演示](https://mdn.github.io/learning-area/accessibility/css/form-validation.html)）。在这里你会看到一个简单的表格；当您尝试提交一个或两个字段为空的表单时，提交失败，并且会出现一个错误消息框，告诉您出了什么问题。

这种表单验证并不引人注目——您仍然可以在没有 JavaScript 可用的情况下完全使用表单，并且任何合理的表单实现都会激活服务器端验证，因为恶意用户很容易绕过客户端验证（例如，通过在浏览器中关闭 JavaScript）。客户端验证对于报告错误仍然非常有用——用户可以立即知道他们犯的错误，而不必等待往返服务器和页面重新加载。这是一个明确的可用性优势。

**注意：**在这个简单的演示中没有实现服务器端验证。

我们也让这个表单验证变得非常容易访问。我们使用[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)元素来确保表单标签明确链接到它们的输入，因此屏幕阅读器可以将它们一起读出：

```
<label for="name">Enter your name:</label>
<input type="text" name="name" id="name">
```

复制到剪贴板

我们只在提交表单时进行验证——这样我们就不会过于频繁地更新 UI 并可能混淆屏幕阅读器（可能还有其他）用户：

```
form.onsubmit = validate;

function validate(e) {
  errorList.innerHTML = '';
  for(let i = 0; i < formItems.length; i++) {
    const testItem = formItems[i];
    if(testItem.input.value === '') {
      errorField.style.left = '360px';
      createLink(testItem);
    }
  }

  if(errorList.innerHTML !== '') {
    e.preventDefault();
  }
}
```

复制到剪贴板

**注意：**在此示例中，我们使用绝对定位而不是其他方法（例如可见性或显示）来隐藏和显示错误消息框，因为它不会干扰屏幕阅读器从中读取内容。

真正的表单验证会比这复杂得多——您需要检查输入的姓名是否实际上看起来像姓名，输入的年龄实际上是一个数字并且是真实的（例如，非负数且少于 4 位数字）。在这里，我们刚刚实现了一个简单的检查，即每个输入字段 ( `if(testItem.input.value === '')`) 中都填充了一个值。

执行验证后，如果测试通过，则提交表单。如果有错误 ( `if(errorList.innerHTML !== '')`)，那么我们停止提交表单（使用[`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)），并显示已创建的任何错误消息（见下文）。这种机制意味着只有在有错误时才会显示错误，这对可用性更好。

对于提交表单时没有填写值的每个输入，我们创建一个带有链接的列表项并将其插入到`errorList`.

```
function createLink(testItem) {
  const listItem = document.createElement('li');
  const anchor = document.createElement('a');

  anchor.textContent = testItem.input.name + ' field is empty: fill in your ' + testItem.input.name + '.';
  anchor.href = '#' + testItem.input.name;
  anchor.onclick = function() {
    testItem.input.focus();
  };
  listItem.appendChild(anchor);
  errorList.appendChild(listItem);
}
```

复制到剪贴板

每个链接都有双重用途——它告诉您错误是什么，此外您可以单击它/激活它以直接跳转到有问题的输入元素并更正您的输入。

**注意：**`focus()`这个例子的部分有点棘手。Chrome 和 Edge（以及较新版本的 IE）将在单击链接时聚焦元素，而无需`onclick`/`focus()`块。Safari 只会突出显示带有链接的表单元素，因此需要`onclick`/`focus()`块来实际聚焦它。在这种情况下，Firefox 根本没有正确聚焦输入，因此 Firefox 用户目前无法利用这一点（尽管其他一切都正常）。Firefox 问题应该很快得到修复 - 正在努力使 Firefox 行为与其他浏览器相同（请参阅[错误 277178](https://bugzilla.mozilla.org/show_bug.cgi?id=277178)）。

此外，`errorField`被放置在源顺序的顶部（尽管它在使用 CSS 的 UI 中的位置不同），这意味着用户可以准确地找出他们提交的表单有什么问题，并通过返回找到有问题的输入元素直到页面的开头。

最后，我们在演示中使用了一些 WAI-ARIA 属性来帮助解决由于内容区域不断更新而无需重新加载页面（默认情况下屏幕阅读器不会选择或提醒用户）导致的可访问性问题：

```
<div class="errors" role="alert" aria-relevant="all">
  <ul>
  </ul>
</div>
```

我们将在下一篇文章中解释这些属性，其中更详细地介绍了[WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics)。

**注意：**你们中的一些人可能会考虑这样一个事实，即 HTML5 表单具有内置的验证机制，如`required`、`min`/`minlength`和`max`/`maxlength`属性（[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)有关更多信息，请参阅元素参考）。我们最终没有在演示中使用这些，因为对它们的跨浏览器支持是不完整的（例如仅 IE10 及更高版本）。

**注意：** WebAIM 的[可用和可访问的表单验证和错误恢复](https://webaim.org/techniques/formvalidation/) 提供了一些有关可访问表单验证的进一步有用信息。

### [其他 JavaScript 可访问性问题](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#other_javascript_accessibility_concerns)

在实现 JavaScript 和考虑可访问性时，还有其他事情需要注意。当我们找到它们时，我们会添加更多。

#### 鼠标特定事件

如您所知，大多数用户交互都是在客户端 JavaScript 中使用事件处理程序实现的，这允许我们运行函数以响应发生的某些事件。某些事件可能存在可访问性问题。您将遇到的主要示例是特定于鼠标的事件，例如[mouseover](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseover_event)、[mouseout](https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseout_event)、[dblclick](https://developer.mozilla.org/en-US/docs/Web/API/Element/dblclick_event)等。使用其他机制（例如键盘控件）无法访问响应这些事件而运行的功能。

为了缓解此类问题，您应该将这些事件与可以通过其他方式激活的类似事件（所谓的与设备无关的事件处理程序）加倍——[焦点](https://developer.mozilla.org/en-US/docs/Web/API/Element/focus_event)和[模糊](https://developer.mozilla.org/en-US/docs/Web/API/Element/blur_event)将为键盘用户提供可访问性。

让我们看一个突出显示何时有用的示例。也许我们想提供一个缩略图，当鼠标悬停或聚焦时显示更大版本的图像（就像您在电子商务产品目录中看到的那样）。

我们做了一个非常简单的例子，你可以在 [鼠标和键盘事件.html](https://mdn.github.io/learning-area/accessibility/css/mouse-and-keyboard-events.html) （另见 [源代码](https://github.com/mdn/learning-area/blob/master/accessibility/css/mouse-and-keyboard-events.html)）。该代码具有显示和隐藏放大图像的两个功能；这些由以下几行运行，将它们设置为事件处理程序：

```
imgThumb.onmouseover = showImg;
imgThumb.onmouseout = hideImg;

imgThumb.onfocus = showImg;
imgThumb.onblur = hideImg;
```

复制到剪贴板

前两行分别在鼠标指针悬停在缩略图上和停止悬停在缩略图上时运行函数。这将不允许我们通过键盘访问缩放视图 - 为了允许这一点，我们已经包含了最后两行，它们在图像聚焦和模糊时（当焦点停止时）运行函数。这可以通过标记图像来完成，因为我们已经包含`tabindex="0"`在它上面。

该[点击](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)事件是有趣的-这听起来鼠标依赖，但大多数浏览器将激活[的onclick](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick)事件处理程序的输入/按下具有焦点时，或者当这样的元素被点击触摸屏设备上的链接或表单元素上返回后。这在默认情况下不起作用，但是当您允许非默认可聚焦事件使用 tabindex 获得焦点时 - 在这种情况下，您需要专门检测何时按下该确切键（请参阅[后面的构建键盘可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#building_keyboard_accessibility_back_in)）。

# WAI-ARIA 基础知识

继上一篇文章之后，有时制作涉及非语义 HTML 和动态 JavaScript 更新内容的复杂 UI 控件可能很困难。WAI-ARIA 是一种技术，可以通过添加浏览器和辅助技术可以识别和使用的进一步语义来帮助解决此类问题，从而让用户知道发生了什么。在这里，我们将展示如何在基本级别使用它来提高可访问性。

## [什么是 WAI-ARIA？](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#what_is_wai-aria)

让我们先看看 WAI-ARIA 是什么，以及它可以为我们做什么。

### [一系列全新的问题](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#a_whole_new_set_of_problems)

随着网络应用开始变得更加复杂和动态，一系列新的辅助功能和问题开始出现。

例如，HTML5 引入了许多语义元素来定义常见的页面特征（[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)、[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)等）。在这些元素可用之前，开发人员会使用[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)带有 ID 或类的 s，例如`<div class="nav">`，但这些都是有问题的，因为没有简单的方法可以轻松地以编程方式查找特定页面功能，例如主导航。

最初的解决方案是在页面顶部添加一个或多个隐藏链接以链接到导航（或其他任何内容），例如：

```
<a href="#hidden" class="hidden">Skip to navigation</a>
```

复制到剪贴板

但这仍然不是很精确，只能在屏幕阅读器从页面顶部阅读时使用。

再举一个例子，应用程序开始具有复杂的控件，例如用于选择日期的日期选择器、用于选择值的滑块等。 HTML5 提供了特殊的输入类型来呈现此类控件：

```
<input type="date">
<input type="range">
```

复制到剪贴板

这些在浏览器中没有得到很好的支持，而且也很难设置它们的样式，这使得它们对于与网站设计的集成不是很有用。因此，开发人员经常依赖 JavaScript 库来生成诸如一系列嵌套[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s 或具有类名的表格元素之类的控件，然后使用 CSS 设置样式并使用 JavaScript 进行控制。

这里的问题是它们在视觉上是有效的，但屏幕阅读器根本无法理解它们是什么，他们的用户只是被告知他们可以看到一堆没有语义来描述它们的含义的元素。

### [进入 WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#enter_wai-aria)

[围唱](https://www.w3.org/TR/wai-aria-1.1/) （Web Accessibility Initiative - Accessible Rich Internet Applications）是由 W3C 编写的规范，定义了一组额外的 HTML 属性，这些属性可以应用于元素以提供额外的语义并在缺少它的地方改进可访问性。规范中定义了三个主要功能：

- **[角色](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)**- 这些定义元素是什么或做什么。这当中很多是所谓的标志性角色，这在很大程度上复制HTML5结构元素例如语义值`role="navigation"`（[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)）或`role="complementary"`（[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)），但也有其他人描述不同的页面结构，如`role="banner"`，`role="search"`，`role="tabgroup"`，`role="tab"`，等等，这些都是常见的在用户界面中找到。
- **属性**- 这些定义元素的属性，可用于赋予它们额外的含义或语义。例如，`aria-required="true"`指定需要填写表单输入才能有效，而`aria-labelledby="label"`允许您将 ID 放在元素上，然后将其作为页面上其他任何内容的标签引用，包括多个元素，即不可能使用`<label for="input">`. 例如，您可以使用`aria-labelledby`指定包含在 a 中的关键描述[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)是多个表格单元格的标签，或者您可以将其用作图像替代文本的替代——将页面上的现有信息指定为图像的替代文本，而不是而不是必须在`alt`属性内重复它。您可以在[文本替代 中](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML?document_saved=true#Text_alternatives)看到这样的示例。
- **状态**- 定义元素当前条件的特殊属性，例如`aria-disabled="true"`，向屏幕阅读器指定表单输入当前已禁用。状态与属性的不同之处在于，属性不会在应用程序的整个生命周期中更改，而状态可以更改，通常通过 JavaScript 以编程方式更改。

关于 WAI-ARIA 属性的一个重要点是它们不会影响网页的任何内容，除了浏览器的可访问性 API 公开的信息（屏幕阅读器从中获取信息）。WAI-ARIA 不会影响网页结构、DOM 等，尽管这些属性对于通过 CSS 选择元素很有用。

**注意：**您可以在 WAI-ARIA 规范中找到所有 ARIA 角色及其用途的有用列表，以及指向更多信息的链接——请参阅[角色定义](https://www.w3.org/TR/wai-aria-1.1/#role_definitions)— 在此站点上 — 请参阅[ARIA 角色](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)。

该规范还包含所有属性和状态的列表，以及指向更多信息的链接——参见 [状态和属性的定义（所有 aria-* 属性）](https://www.w3.org/TR/wai-aria-1.1/#state_prop_def).

### [哪里支持 WAI-ARIA？](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#where_is_wai-aria_supported)

这不是一个容易回答的问题。很难找到一个确凿的资源来说明支持 WAI-ARIA 的哪些功能以及支持哪些功能，因为：

1. WAI-ARIA 规范中有很多特性。
2. 有许多操作系统、浏览器和屏幕阅读器的组合需要考虑。

最后一点是关键——首先要使用屏幕阅读器，您的操作系统需要运行具有必要的可访问性 API 的浏览器，以公开屏幕阅读器完成工作所需的信息。大多数流行的操作系统都有一两个浏览器可供屏幕阅读器使用。Paciello Group 有一篇相当最新的帖子，为此提供了数据——见[粗略指南：更新了浏览器、操作系统和屏幕阅读器支持](https://www.paciellogroup.com/blog/2014/10/rough-guide-browsers-operating-systems-and-screen-reader-support-updated/).

接下来，您需要担心相关浏览器是否支持 ARIA 功能并通过其 API 公开它们，还要担心屏幕阅读器是否识别该信息并将其以有用的方式呈现给用户。

1. 浏览器支持通常非常好——在撰写本文时， [caniuse.com](https://caniuse.com/#feat=wai-aria) 表示全球浏览器对 WAI-ARIA 的支持率约为 88%。
2. 屏幕阅读器对 ARIA 功能的支持还没有达到这个水平，但最流行的屏幕阅读器已经达到了这个水平。您可以通过查看 Powermapper 了解支持级别[WAI-ARIA 屏幕阅读器兼容性](https://www.powermapper.com/tests/screen-readers/aria/) 文章。

在本文中，我们不会试图涵盖所有 WAI-ARIA 功能及其确切的支持细节。相反，我们将介绍最重要的 WAI-ARIA 功能供您了解；如果我们没有提及任何支持细节，您可以认为该功能得到了很好的支持。我们将明确提及任何例外情况。

**注意：**一些 JavaScript 库支持 WAI-ARIA，这意味着当它们生成复杂表单控件等 UI 功能时，它们会添加 ARIA 属性以提高这些功能的可访问性。如果您正在寻找用于快速 UI 开发的 3rd 方 JavaScript 解决方案，那么在做出选择时，您绝对应该将其 UI 小部件的可访问性视为一个重要因素。很好的例子是 jQuery UI（见[关于 jQuery UI：深度可访问性支持](https://jqueryui.com/about/#deep-accessibility-support)), [扩展程序](https://www.sencha.com/products/extjs/)， 和 [道场/迪吉特](https://dojotoolkit.org/reference-guide/1.10/dijit/a11y/statement.html).

### [什么时候应该使用 WAI-ARIA？](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#when_should_you_use_wai-aria)

之前我们谈到了促使 WAI-ARIA 被创建的一些问题，但本质上，WAI-ARIA 有四个主要方面是有用的：

1. **路标/地标**：ARIA的[`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)属性值可以作为地标，要么复制HTML5元素的语义（例如[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)），或超越HTML5语义以提供路标不同的功能区，例如`search`，`tabgroup`，`tab`，`listbox`，等。
2. **动态内容更新**：屏幕阅读器往往难以报告不断变化的内容；使用 ARIA，我们可以`aria-live`在内容区域更新时通知屏幕阅读器用户，例如通过[XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)或[DOM API](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)。
3. **增强键盘可访问性**：有具有原生键盘可访问性的内置 HTML 元素；当其他元素与 JavaScript 一起使用来模拟类似的交互时，键盘可访问性和屏幕阅读器报告会因此受到影响。在不可避免的情况下，WAI-ARIA 提供了一种允许其他元素获得焦点的方法（使用`tabindex`）。
4. **非语义控件的可访问性**：当使用一系列嵌套的`<div>`s 和 CSS/JavaScript 来创建复杂的 UI 功能时，或者通过 JavaScript 大大增强/更改本机控件时，可访问性可能会受到影响 - 屏幕阅读器用户会发现很难在没有语义或其他线索的情况下计算出该功能的作用。在这些情况下，ARIA 可以通过组合角色（如`button`、`listbox`、 或`tabgroup`）和属性（如`aria-required`或 ）`aria-posinset`来帮助提供缺失的内容，以提供有关功能的进一步线索。

不过要记住一件事——**你应该只在需要的时候使用 WAI-ARIA！**理想情况下，您应该*始终*使用[原生 HTML 功能](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)来提供屏幕阅读器所需的语义，以告诉用户正在发生的事情。有时这是不可能的，要么是因为您对代码的控制有限，要么是因为您正在创建一些复杂的东西而没有一个简单的 HTML 元素来实现它。在这种情况下，WAI-ARIA 可以成为一种有价值的可访问性增强工具。

但同样，仅在必要时使用它！

**注意：**另外，尽量确保你的网站有各种*真实*用户——非残疾人、使用屏幕阅读器的人、使用键盘导航的人等。他们会比你更了解网站的工作情况。

## [实用的 WAI-ARIA 实现](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#practical_wai-aria_implementations)

在下一节中，我们将更详细地研究这四个方面，以及实际示例。在继续之前，您应该设置一个屏幕阅读器测试设置，以便您可以在执行过程中测试一些示例。

有关更多信息，请参阅我们关于[测试屏幕阅读器](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Accessibility#screenreaders)的部分。

### [路标/地标](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#signpostslandmarks)

WAI-ARIA 添加了 [`role` 属性](https://www.w3.org/TR/wai-aria-1.1/#role_definitions)到浏览器，它允许您在需要时为站点上的元素添加额外的语义值。第一个有用的主要领域是为屏幕阅读器提供信息，以便他们的用户可以找到常见的页面元素。让我们看一个例子——我们的[网站无角色](https://github.com/mdn/learning-area/tree/master/accessibility/aria/website-no-roles) 例子 （[现场观看](https://mdn.github.io/learning-area/accessibility/aria/website-no-roles/)) 具有以下结构：

```
<header>
  <h1>...</h1>
  <nav>
    <ul>...</ul>
    <form>
      <!-- search form  -->
    </form>
  </nav>
</header>

<main>
  <article>...</article>
  <aside>...</aside>
</main>

<footer>...</footer>
```

复制到剪贴板

如果您尝试在现代浏览器中使用屏幕阅读器测试该示例，您将已经获得一些有用的信息。例如，VoiceOver 为您提供以下内容：

- 在`<header>`元素上 — “横幅，2 项”（它包含一个标题和`<nav>`）。
- 在`<nav>`元素上——“导航 2 项”（它包含一个列表和一个表单）。
- 在`<main>`元素上——“主要 2 项”（它包含一篇文章和一篇旁白）。
- 在`<aside>`元素上——“互补的 2 个项目”（它包含一个标题和一个列表）。
- 在搜索表单输入——“搜索查询，在文本开头插入”。
- 在`<footer>`元素上 — “页脚 1 项”。

如果您转到 VoiceOver 的地标菜单（使用 VoiceOver 键 + U 访问，然后使用光标键在菜单选项之间循环），您会看到大部分元素都很好地列出，因此可以快速访问。

![img](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics/landmarks-list.png)

但是，我们可以在这里做得更好。搜索表单是人们想要查找的非常重要的地标，但它并未列在地标菜单中，也未将其视为显着地标，超出了被称为搜索输入 ( `<input type="search">`)的实际输入。此外，一些较旧的浏览器（尤其是 IE8）无法识别 HTML5 元素的语义。

让我们通过使用一些 ARIA 功能来改进它。首先，我们将向[`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)HTML 结构添加一些属性。您可以尝试复制我们的原始文件（请参阅[索引.html](https://github.com/mdn/learning-area/blob/master/accessibility/aria/website-no-roles/index.html) 和 [样式文件](https://github.com/mdn/learning-area/blob/master/accessibility/aria/website-no-roles/style.css))，或导航到我们的 [网站-咏叹调-角色](https://github.com/mdn/learning-area/tree/master/accessibility/aria/website-aria-roles) 例子 （[现场观看](https://mdn.github.io/learning-area/accessibility/aria/website-aria-roles/))，其结构如下：

```
<header>
  <h1>...</h1>
  <nav role="navigation">
    <ul>...</ul>
    <form role="search">
      <!-- search form  -->
    </form>
  </nav>
</header>

<main>
  <article role="article">...</article>
  <aside role="complementary">...</aside>
</main>

<footer>...</footer>
```

复制到剪贴板

在这个例子中，我们还给了你一个额外的特性——[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)元素已经被赋予了属性[`aria-label`](https://www.w3.org/TR/wai-aria-1.1/#aria-label)，即使我们没有包含[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)元素，它也会给它一个描述性标签，供屏幕阅读器读出。在这种情况下，这非常有用——像这样的搜索表单是一个非常常见、易于识别的功能，添加视觉标签会破坏页面设计。

```
<input type="search" name="q" placeholder="Search query" aria-label="Search through site content">
```

复制到剪贴板

现在如果我们使用 VoiceOver 来查看这个例子，我们会得到一些改进：

- 搜索表单在浏览页面和 Landmarks 菜单时都作为一个单独的项目被调用。
- `aria-label`当突出显示表单输入时，将读出属性中包含的标签文本。

除此之外，使用旧版浏览器（如 IE8）的用户更有可能访问该网站；值得为此目的包含 ARIA 角色。如果出于某种原因，您的站点仅使用`<div>`s构建，则您绝对应该包含 ARIA 角色以提供这些急需的语义！

搜索表单的改进语义显示了当 ARIA 超越 HTML5 中可用的语义时可以实现的功能。您将在下面看到更多关于这些语义和 ARIA 属性/属性的力量，特别是在[非语义控件](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#accessibility_of_non-semantic_controls)的[可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#accessibility_of_non-semantic_controls)部分。不过现在，让我们看看 ARIA 如何帮助动态内容更新。

### [动态内容更新](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#dynamic_content_updates)

加载到 DOM 中的内容可以使用屏幕阅读器轻松访问，从文本内容到附加到图像的替代文本。因此，具有大量文本内容的传统静态网站很容易让视障人士访问。

问题在于，现代 Web 应用程序通常不仅仅是静态文本——它们往往具有大量动态更新的内容，即无需通过[XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)、[Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)或[DOM API](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)等机制重新加载整个页面即可更新的内容。这些有时被称为**实时区域**。

让我们看一个简单的例子——见 [aria-no-live.html](https://github.com/mdn/learning-area/blob/master/accessibility/aria/aria-no-live.html) （还 [现场直播](https://mdn.github.io/learning-area/accessibility/aria/aria-no-live.html)）。在这个例子中，我们有一个简单的随机引用框：

```
<section>
  <h1>Random quote</h1>
  <blockquote>
    <p></p>
  </blockquote>
</section>
```

复制到剪贴板

我们的 JavaScript 通过[`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)包含一系列随机引号及其作者加载 JSON 文件。完成后，我们启动一个[`setInterval()`](https://developer.mozilla.org/en-US/docs/Web/API/setInterval)循环，每 10 秒将一个新的随机引用加载到引用框中：

```
let intervalID = window.setInterval(showQuote, 10000);
```

复制到剪贴板

这工作正常，但它对可访问性不利——屏幕阅读器不会检测到内容更新，因此他们的用户不会知道发生了什么。这是一个相当简单的例子，但试想一下，如果您正在创建一个包含大量不断更新内容的复杂用户界面，例如聊天室、策略游戏用户界面或实时更新的购物车显示 - 将不可能使用应用程序以任何有效的方式在没有某种方式提醒用户更新的情况下使用。

幸运的是，WAI-ARIA 提供了一种有用的机制来提供这些警报—— [`aria-live`](https://www.w3.org/TR/wai-aria-1.1/#aria-live)财产。将此应用于元素会导致屏幕阅读器读出更新的内容。读取内容的紧急程度取决于属性值：

- `off:`默认。不应宣布更新。
- `polite`：只有在用户空闲时才应宣布更新。
- `assertive`：应尽快向用户宣布更新。

我们希望您复印一份 [aria-no-live.html](https://github.com/mdn/learning-area/blob/master/accessibility/aria/aria-no-live.html) 和 [报价.json](https://github.com/mdn/learning-area/blob/master/accessibility/aria/quotes.json)，并按`<section>`如下方式更新您的标签：

```
<section aria-live="assertive">
```

复制到剪贴板

这将导致屏幕阅读器在内容更新时读出内容。

**注意：**如果您尝试`XMLHttpRequest`从`file://`URL进行调用，大多数浏览器将抛出安全异常，例如，如果您只是通过将文件直接加载到浏览器（通过双击等）来加载文件。要让它运行，您需要将它上传到网络服务器，例如[使用 GitHub](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Using_Github_pages)或本地网络服务器，如[Python 的 SimpleHTTPServer](https://www.pythonforbeginners.com/modules-in-python/how-to-use-simplehttpserver/).

这里还有一个额外的考虑——只读出更新的文本位。如果我们也总是读出标题可能会很好，这样用户就可以记住正在读出的内容。为此，我们可以添加[`aria-atomic`](https://www.w3.org/TR/wai-aria-1.1/#aria-atomic)部分的属性。`<section>`再次更新您的标签，如下所示：

```
<section aria-live="assertive" aria-atomic="true">
```

复制到剪贴板

该`aria-atomic="true"`属性告诉屏幕阅读器将整个元素内容作为一个原子单元读出，而不仅仅是更新的位。

**注意：**您可以在以下位置查看完成的示例[咏叹调-live.html](https://github.com/mdn/learning-area/blob/master/accessibility/aria/aria-live.html) ([现场直播](https://mdn.github.io/learning-area/accessibility/aria/aria-live.html)）。

**注：**该[`aria-relevant`](https://www.w3.org/TR/wai-aria-1.1/#aria-relevant)属性对于控制更新活动区域时读取的内容也非常有用。例如，您只能读取内容添加或删除。

### [增强键盘可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#enhancing_keyboard_accessibility)

正如在模块中的其他几个地方所讨论的，HTML 在可访问性方面的主要优势之一是按钮、表单控件和链接等功能的内置键盘可访问性。通常，您可以使用 Tab 键在控件之间移动，使用 Enter/Return 键选择或激活控件，有时还可以根据需要使用其他控件（例如，使用上下光标在`<select>`框中的选项之间移动）。

但是，有时您最终将不得不编写使用非语义元素作为按钮（或其他类型的控件）的代码，或者使用可聚焦控件来实现不太正确的目的。您可能正在尝试修复一些您继承的错误代码，或者您可能正在构建某种需要它的复杂小部件。

在使不可聚焦的代码可聚焦方面，WAI-ARIA`tabindex`使用一些新值扩展了该属性：

- `tabindex="0"`— 如上所述，此值允许通常不可制表的元素变为可制表。这是 最有用的值`tabindex`。
- `tabindex="-1"` — 这允许通常不是可选项卡的元素以编程方式接收焦点，例如通过 JavaScript，或作为链接的目标。

我们更详细地讨论了这一点，并在我们的 HTML 可访问性文章中展示了一个典型的实现 - 请参阅[在](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#building_keyboard_accessibility_back_in).

### [非语义控制的可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#accessibility_of_non-semantic_controls)

这是上一节的后续——当一系列嵌套的`<div>`s 和 CSS/JavaScript 用于创建复杂的 UI 功能时，或者通过 JavaScript 大大增强/更改本机控件时，不仅键盘可访问性会受到影响，屏幕阅读器也会受到影响如果没有语义或其他线索，用户会发现很难弄清楚该功能的作用。在这种情况下，ARIA 可以帮助提供那些缺失的语义。

#### 表单验证和错误警报

首先，让我们回顾一下我们在 CSS 和 JavaScript 可访问性文章中第一次看到的表单示例（阅读[保持不显眼](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#keeping_it_unobtrusive)的完整回顾）。在本节的末尾，我们展示了我们在错误消息框中包含了一些 ARIA 属性，当您尝试提交表单时，这些属性会显示任何验证错误：

```
<div class="errors" role="alert" aria-relevant="all">
  <ul>
  </ul>
</div>
```

复制到剪贴板

- [`role="alert"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/alert_role)自动将应用到的元素转换为活动区域，因此会读出对它的更改；它还在语义上将其标识为警报消息（重要的时间/上下文敏感信息），并代表一种更好、更易于向用户发送警报的方式（像[`alert()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)呼叫这样的模态对话框有许多可访问性问题；请参阅[弹出窗口](https://webaim.org/techniques/javascript/other#popups) 通过 WebAIM）。
- 一个 [`aria-relevant`](https://www.w3.org/TR/wai-aria-1.1/#aria-relevant)值`all`指示屏幕阅读器在对其进行任何更改时读出错误列表的内容 - 即当添加或删除错误时。这很有用，因为用户想知道还剩下哪些错误，而不仅仅是列表中添加或删除了哪些错误。

我们可以进一步使用 ARIA，并提供更多验证帮助。首先说明是否需要字段，年龄应该在什么范围内如何？

1. 此时，复制我们的 [表单验证.html](https://github.com/mdn/learning-area/blob/master/accessibility/css/form-validation.html) 和 [验证.js](https://github.com/mdn/learning-area/blob/master/accessibility/css/validation.js) 文件，并将它们保存在本地目录中。

2. 在文本编辑器中打开它们，看看代码是如何工作的。

3. 首先，在开始

   ```
   <form>
   ```

   标签的正上方添加一个段落，如下所示，并

   ```
   <label>
   ```

   用星号标记两个表单。这通常是我们为视力正常的用户标记必填字段的方式。

   ```
   <p>Fields marked with an asterisk (*) are required.</p>
   ```

   复制到剪贴板

4. 这具有视觉意义，但对于屏幕阅读器用户来说并不容易理解。幸运的是，WAI-ARIA 提供了

   `aria-required`

   属性给屏幕阅读器提示他们应该告诉用户需要填写表单输入。更新

   ```
   <input>
   ```

   元素，如下所示：

   ```
   <input type="text" name="name" id="name" aria-required="true">
   
   <input type="number" name="age" id="age" aria-required="true">
   ```

   复制到剪贴板

5. 如果您现在保存示例并使用屏幕阅读器对其进行测试，您应该会听到类似“输入您的姓名星号，必填，编辑文本”之类的内容。

6. 如果我们让屏幕阅读器用户和视力正常的用户了解年龄值应该是多少，这也可能很有用。这通常作为工具提示或表单字段内的占位符呈现。WAI-ARIA 确实包括

   `aria-valuemin`

    和 

   `aria-valuemax`

   指定最小值和最大值的属性，但这些目前似乎没有得到很好的支持；一个更好的支持特性是 HTML5

   ```
   placeholder
   ```

   属性，它可以包含一条消息，当没有输入值时，它会显示在输入中，并由许多屏幕阅读器读出。像这样更新您的数字输入：

   ```
   <input type="number" name="age" id="age" placeholder="Enter 1 to 150" aria-required="true">
   ```

   复制到剪贴板

**注意：**您可以在以下位置实时查看完成的示例[表单验证-updated.html](https://mdn.github.io/learning-area/accessibility/aria/form-validation-updated.html).

WAI-ARIA 还启用了一些超越经典[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)元素的高级表单标签技术。我们已经讨论过使用[`aria-label`](https://www.w3.org/TR/wai-aria-1.1/#aria-label)属性提供一个标签，我们不希望标签对视力正常的用户可见（请参阅上面的[路标/地标](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#signposts/landmarks)部分）。还有一些其他标记技术使用其他属性，例如[`aria-labelledby`](https://www.w3.org/TR/wai-aria-1.1/#aria-labelledby)如果要将非`<label>`元素指定为标签或使用相同标签为多个表单输入添加标签，以及[`aria-describedby`](https://www.w3.org/TR/wai-aria-1.1/#aria-describedby), 如果您想将其他信息与表单输入相关联并将其读出。看[WebAIM 的高级表单标签文章](https://webaim.org/techniques/forms/advanced) 更多细节。

还有许多其他有用的属性和状态，用于指示表单元素的状态。例如，`aria-disabled="true"`可用于指示表单字段已禁用。许多浏览器只会跳过禁用的表单字段，它们甚至不会被屏幕阅读器读出，但在某些情况下它们会被感知，因此包含此属性是一个好主意，让屏幕阅读器知道禁用的输入实际上是禁用的。

如果输入的禁用状态可能会改变，那么最好指明它何时发生以及结果是什么。例如，在我们的[表单验证-checkbox-disabled.html](https://mdn.github.io/learning-area/accessibility/aria/form-validation-checkbox-disabled.html)演示有一个复选框，当检查时，可以进一步输入其他表单输入以允许进一步输入信息。我们设置了一个隐藏的实时区域：

```
<p class="hidden-alert" aria-live="assertive"></p>
```

复制到剪贴板

这是使用绝对定位隐藏的。当检查/取消选中此时，我们更新隐藏的实时区域内的文本，以告诉ScreenReader用户检查此复选框的结果，以及更新`aria-disabled`状态，以及一些可视指示符

```
function toggleMusician(bool) {
  let instruItem = formItems[formItems.length-1];
  if(bool) {
    instruItem.input.disabled = false;
    instruItem.label.style.color = '#000';
    instruItem.input.setAttribute('aria-disabled', 'false');
    hiddenAlert.textContent = 'Instruments played field now enabled; use it to tell us what you play.';
  } else {
    instruItem.input.disabled = true;
    instruItem.label.style.color = '#999';
    instruItem.input.setAttribute('aria-disabled', 'true');
    instruItem.input.removeAttribute('aria-label');
    hiddenAlert.textContent = 'Instruments played field now disabled.';
  }
}
```

复制到剪贴板

#### 将非语义按钮描述为按钮

在本课程中，我们已经多次提到按钮、链接或表单元素的本机可访问性（以及使用其他元素伪造背后的可访问性问题）（请参阅HTML 可访问性文章中的[UI 控件](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#ui_controls)和[增强键盘可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#enhancing_keyboard_accessibility)，多于）。基本上，在许多情况下，您可以使用`tabindex`一些 JavaScript重新添加键盘可访问性，而不会带来太多麻烦。

但是屏幕阅读器呢？他们仍然不会将元素视为按钮。如果我们测试我们的[假div-buttons.html](https://mdn.github.io/learning-area/tools-testing/cross-browser-testing/accessibility/fake-div-buttons.html) 例如在屏幕阅读器中，我们的假按钮将使用诸如“单击我！，组”之类的短语来报告，这显然令人困惑。

我们可以使用 WAI-ARIA 角色来解决这个问题。制作本地副本[假div-buttons.html](https://github.com/mdn/learning-area/blob/master/tools-testing/cross-browser-testing/accessibility/fake-div-buttons.html)，并添加[`role="button"`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)到每个按钮`<div>`，例如：

```
<div data-message="This is from the first button" tabindex="0" role="button">Click me!</div>
```

现在，当您使用屏幕阅读器尝试此操作时，您将使用诸如“单击我！按钮”之类的短语来报告按钮 — 好多了。

**注意：**但是不要忘记，在可能的情况下使用正确的语义元素总是更好。如果你想创建一个按钮，并且可以使用一个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)元素，你应该使用一个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)元素！

#### 引导用户完成复杂的小部件

还有一大堆其他的 [角色](https://www.w3.org/TR/wai-aria-1.1/#role_definitions) 例如，可以将非语义元素结构识别为超出标准 HTML 中可用功能的通用 UI 功能 [`combobox`](https://www.w3.org/TR/wai-aria-1.1/#combobox), [`slider`](https://www.w3.org/TR/wai-aria-1.1/#slider), [`tabpanel`](https://www.w3.org/TR/wai-aria-1.1/#tabpanel), [`tree`](https://www.w3.org/TR/wai-aria-1.1/#tree). 您可以在[德克大学代码库](https://dequeuniversity.com/library/)，让您了解如何访问此类控件。

让我们来看一个我们自己的例子。我们将返回到我们简单的绝对定位选项卡式界面（请参阅在我们的 CSS 和 JavaScript 可访问性文章中[隐藏内容](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#hiding_things)），您可以在以下位置找到[选项卡式信息框示例](https://mdn.github.io/learning-area/css/css-layout/practical-positioning-examples/info-box.html) （看 [源代码](https://github.com/mdn/learning-area/blob/master/css/css-layout/practical-positioning-examples/info-box.html)）。

这个示例在键盘可访问性方面运行良好 - 您可以愉快地在不同选项卡之间切换并选择它们以显示选项卡内容。它也非常易于访问——您可以滚动浏览内容并使用标题进行导航，即使您看不到屏幕上正在发生的事情。然而，内容是什么并不那么明显——屏幕阅读器当前将内容报告为链接列表，有些内容具有三个标题。它不会让您了解内容之间的关系。为用户提供有关内容结构的更多线索总是好的。

为了改进，我们创建了一个名为的示例的新版本 [aria-tabbed-info-box.html](https://github.com/mdn/learning-area/blob/master/accessibility/aria/aria-tabbed-info-box.html) ([现场直播](https://mdn.github.io/learning-area/accessibility/aria/aria-tabbed-info-box.html)）。我们更新了选项卡式界面的结构，如下所示：

```
<ul role="tablist">
  <li class="active" role="tab" aria-selected="true" aria-setsize="3" aria-posinset="1" tabindex="0">Tab 1</li>
  <li role="tab" aria-selected="false" aria-setsize="3" aria-posinset="2" tabindex="0">Tab 2</li>
  <li role="tab" aria-selected="false" aria-setsize="3" aria-posinset="3" tabindex="0">Tab 3</li>
</ul>
<div class="panels">
  <article class="active-panel" role="tabpanel" aria-hidden="false">
    ...
  </article>
  <article role="tabpanel" aria-hidden="true">
    ...
  </article>
  <article role="tabpanel" aria-hidden="true">
    ...
  </article>
</div>
```

复制到剪贴板

**注意：**这里最显着的变化是我们删除了示例中最初存在的链接，只使用列表项作为选项卡——这样做是因为它让屏幕阅读器用户不那么困惑（链接不真的不会带你去任何地方；他们只是改变了视图），并且它允许设置特征中的设置大小/位置更好地工作——当这些被放在链接上时，浏览器一直报告“1 of 1”，而不是“ 1 of 3”、“2 of 3”等。

新功能如下：

- 新角色—— [`tablist`](https://www.w3.org/TR/wai-aria-1.1/#tablist), [`tab`](https://www.w3.org/TR/wai-aria-1.1/#tab), [`tabpanel`](https://www.w3.org/TR/wai-aria-1.1/#tabpanel) — 这些标识了选项卡式界面的重要区域 — 选项卡的容器、选项卡本身和相应的选项卡面板。
- [`aria-selected`](https://www.w3.org/TR/wai-aria-1.1/#aria-selected)— 定义当前选择的选项卡。当用户选择不同的选项卡时，不同选项卡上的该属性值通过 JavaScript 更新。
- [`aria-hidden`](https://www.w3.org/TR/wai-aria-1.1/#aria-hidden)— 隐藏元素不被屏幕阅读器读出。当用户选择不同的选项卡时，不同选项卡上的该属性值通过 JavaScript 更新。
- `tabindex="0"` — 因为我们已经删除了链接，所以我们需要为列表项提供这个属性以使其具有键盘焦点。
- [`aria-setsize`](https://www.w3.org/TR/wai-aria-1.1/#aria-setsize) — 此属性允许您向屏幕阅读器指定某个元素是某个系列的一部分，以及该系列有多少项。
- [`aria-posinset`](https://www.w3.org/TR/wai-aria-1.1/#aria-posinset)— 此属性允许您指定元素在系列中的哪个位置。与 一起`aria-setsize`，它为屏幕阅读器提供足够的信息来告诉您您当前位于“第 1 个，共 3 个”等项目上。在许多情况下，浏览器应该能够从元素层次结构中推断出这些信息，但这肯定有助于提供更多线索。

在我们的测试中，这种新结构确实有助于改善整体情况。选项卡现在被识别为选项卡（例如“选项卡”由屏幕阅读器朗读），所选选项卡由带有选项卡名称的“选定”指示，并且屏幕阅读器还会告诉您当前所在的选项卡编号。此外，由于`aria-hidden`设置（只有非隐藏选项卡曾经`aria-hidden="false"`设置过），非隐藏内容是您可以向下导航的唯一内容，这意味着更容易找到所选内容。

**注意：**如果您明确不希望屏幕阅读器读出任何内容，您可以为它们提供`aria-hidden="true"` 属性。

## [测试你的技能！](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#test_your_skills!)

您已读完本文，但您还记得最重要的信息吗？在继续之前，您可以找到一些进一步的测试来验证您是否保留了这些信息 - 请参阅[测试您的技能：WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics/Test_your_skills:_WAI-ARIA)。

## [概括](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#summary)

本文并未涵盖 WAI-ARIA 中可用的所有内容，但它应该为您提供了足够的信息以了解如何使用它，并了解您将遇到的一些需要它的最常见模式。

## [也可以看看](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#see_also)

- [角色定义](https://www.w3.org/TR/wai-aria-1.1/#role_definitions) — ARIA 角色参考。
- [状态和属性的定义（所有 aria-* 属性）](https://www.w3.org/TR/wai-aria-1.1/#state_prop_def) — 属性和状态参考。
- [德克大学代码库](https://dequeuniversity.com/library/) — 一个非常有用的实用示例库，展示了使用 WAI-ARIA 功能可以访问的复杂 UI 控件。
- [WAI-ARIA 创作实践](https://w3c.github.io/aria-practices/) — 来自 W3C 的非常详细的设计模式，解释了如何实现不同类型的复杂 UI 控件，同时使用 WAI-ARIA 功能使其可访问。
- [HTML 中的 ARIA](https://www.w3.org/TR/html-aria/) — 一个 W3C 规范，它为每个 HTML 功能定义了浏览器隐式设置的功能的可访问性 (ARIA) 语义，以及如果需要额外的语义，您可以在其上设置哪些 WAI-ARIA 功能。

# 无障碍多媒体

另一类可能造成可访问性问题的内容是多媒体——视频、音频和图像内容需要提供适当的文本替代方案，以便辅助技术及其用户能够理解它们。这篇文章展示了如何。

## [多媒体和可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#multimedia_and_accessibility)

到目前为止，在本模块中，我们已经研究了各种内容以及需要做些什么来确保其可访问性，从简单的文本内容到数据表、图像、原生控件（如表单元素和按钮），甚至更复杂的标记结构（具有[WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics)属性）。

另一方面，本文着眼于另一类一般的内容，这些内容可以说是不容易确保可访问性——多媒体。图像、音轨、视频、[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)元素等并不容易被屏幕阅读器理解或通过键盘导航，我们需要帮助他们。

但不要绝望 - 在这里，我们将帮助您浏览使多媒体更易于访问的可用技术。

## [简单的图像](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#simple_images)

我们已经在我们的[HTML](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)中介绍了 HTML 图像的简单文本替代[：可访问性](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)文章的[良好基础](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML)- 您可以参考那里的完整详细信息。简而言之，您应该确保在可能的情况下，视觉内容具有可供屏幕阅读器选择并阅读给用户的替代文本。

例如：

```
<img src="dinosaur.png"
     alt="A red Tyrannosaurus Rex: A two legged dinosaur standing upright like a human, with small arms, and a large head with lots of sharp teeth.">
```

复制到剪贴板

## [可访问的音频和视频控件](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#accessible_audio_and_video_controls)

为基于 Web 的音频/视频实施控制应该不是问题，对吧？让我们调查一下。

### [原生 HTML5 控件的问题](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#the_problem_with_native_html5_controls)

HTML5 视频和音频实例甚至带有一组内置控件，允许您直接控制媒体。例如（见`native-controls.html` [源代码](https://github.com/mdn/learning-area/blob/master/accessibility/multimedia/native-controls.html) 和 [居住](https://mdn.github.io/learning-area/accessibility/multimedia/native-controls.html))：

```
<audio controls>
  <source src="viper.mp3" type="audio/mp3">
  <source src="viper.ogg" type="audio/ogg">
  <p>Your browser doesn't support HTML5 audio. Here is a <a href="viper.mp3">link to the audio</a> instead.</p>
</audio>

<br>

<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>
```

复制到剪贴板

控件属性提供播放/暂停按钮、搜索栏等——您期望从媒体播放器获得的基本控件。在 Firefox 和 Chrome 中看起来是这样：

![Firefox 中视频控件的屏幕截图](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia/native-controls-firefox.png)

![Chrome 中视频控件的屏幕截图](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia/native-controls-chrome.png)

但是，这些控件存在问题：

- 它们在大多数浏览器中无法通过键盘访问，即您无法在本机播放器内的控件之间切换。Opera 和 Chrome 在某种程度上提供了这一点，但它仍然不理想。
- 不同的浏览器赋予本机控件不同的样式和功能，并且它们没有样式，这意味着它们不容易遵循站点样式指南。

为了解决这个问题，我们可以创建我们自己的自定义控件。让我们看看如何。

### [创建自定义音频和视频控件](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#creating_custom_audio_and_video_controls)

HTML5 视频和音频共享一个 API — HTML 媒体元素 — 允许您将自定义功能映射到按钮和其他控件 — 两者都是您自己定义的。

让我们从上面的视频示例中添加自定义控件。

#### 基本设置

首先，获取我们的副本 [自定义控件-start.html](https://github.com/mdn/learning-area/blob/master/accessibility/multimedia/custom-controls-start.html), [自定义控件.css](https://github.com/mdn/learning-area/blob/master/accessibility/multimedia/custom-controls.css), [兔子320.mp4](https://raw.githubusercontent.com/mdn/learning-area/master/accessibility/multimedia/rabbit320.mp4)， 和 [兔子320.webm](https://raw.githubusercontent.com/mdn/learning-area/master/accessibility/multimedia/rabbit320.webm) 文件并将它们保存在硬盘驱动器上的新目录中。

创建一个名为 main.js 的新文件并将其保存在同一目录中。

首先，让我们看一下视频播放器的 HTML，在 HTML 中：

```
<section class="player">
  <video controls>
    <source src="rabbit320.mp4" type="video/mp4">
    <source src="rabbit320.webm" type="video/webm">
    <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
  </video>

  <div class="controls">
    <button class="playpause">Play</button>
    <button class="stop">Stop</button>
    <button class="rwd">Rwd</button>
    <button class="fwd">Fwd</button>
    <div class="time">00:00</div>
  </div>
</section>
```

复制到剪贴板

#### JavaScript 基本设置

我们在视频下方插入了一些简单的控制按钮。这些控件在默认情况下当然不会做任何事情；为了添加功能，我们将使用 JavaScript。

我们首先需要存储对每个控件的引用——将以下内容添加到 JavaScript 文件的顶部：

```
const playPauseBtn = document.querySelector('.playpause');
const stopBtn = document.querySelector('.stop');
const rwdBtn = document.querySelector('.rwd');
const fwdBtn = document.querySelector('.fwd');
const timeLabel = document.querySelector('.time');
```

复制到剪贴板

接下来，我们需要获取对视频/音频播放器本身的引用——在前几行下面添加这一行：

```
const player = document.querySelector('video');
```

复制到剪贴板

它持有对一个[`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)对象的引用，该对象有几个有用的属性和方法，可用于将功能连接到我们的按钮。

在继续创建我们的按钮功能之前，让我们移除原生控件，这样它们就不会妨碍我们的自定义控件。再次在 JavaScript 底部添加以下内容：

```
player.removeAttribute('controls');
```

复制到剪贴板

这样做的好处是，如果我们的 JavaScript 由于任何原因失败，用户仍然可以使用一些控件，而不是一开始就不包含控件属性。

#### 连接我们的按钮

首先，让我们设置播放/暂停按钮。我们可以通过一个简单的条件函数在播放和暂停之间切换，如下所示。将其添加到您的代码中，在底部：

```
playPauseBtn.onclick = function() {
  if(player.paused) {
    player.play();
    playPauseBtn.textContent = 'Pause';
  } else {
    player.pause();
    playPauseBtn.textContent = 'Play';
  }
};
```

复制到剪贴板

接下来，将此代码添加到底部，用于控制停止按钮：

```
stopBtn.onclick = function() {
  player.pause();
  player.currentTime = 0;
  playPauseBtn.textContent = 'Play';
};
```

复制到剪贴板

s`stop()`上没有可用[`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)的函数，因此我们改为使用`pause()`它，同时将 设置`currentTime`为 0。

接下来，我们的倒带和快进按钮 - 将以下块添加到您的代码底部：

```
rwdBtn.onclick = function() {
  player.currentTime -= 3;
};

fwdBtn.onclick = function() {
  player.currentTime += 3;
  if(player.currentTime >= player.duration || player.paused) {
    player.pause();
    player.currentTime = 0;
    playPauseBtn.textContent = 'Play';
  }
};
```

复制到剪贴板

这些非常简单，只需在`currentTime`每次单击时增加或减少 3 秒。在真正的视频播放器中，您可能需要更精细的搜索栏或类似的。

请注意，当按下 Fwd 按钮时，我们还会检查 是否`currentTime`大于媒体总数`duration`，或者媒体是否未播放。如果任一条件为真，我们将停止视频，以避免用户界面在视频未播放时尝试快进或快进超过视频结尾时出现错误。

最后，在代码末尾添加以下内容，以控制经过的时间显示：

```
player.ontimeupdate = function() {
  let minutes = Math.floor(player.currentTime / 60);
  let seconds = Math.floor(player.currentTime - minutes * 60);
  let minuteValue;
  let secondValue;

  if (minutes<10) {
    minuteValue = "0" + minutes;
  } else {
    minuteValue = minutes;
  }

  if (seconds<10) {
    secondValue = "0" + seconds;
  } else {
    secondValue = seconds;
  }

  mediaTime = minuteValue + ":" + secondValue;
  timeLabel.textContent = mediaTime;
};
```

复制到剪贴板

每次时间更新（每秒一次），我们都会触发这个函数。它从给定的 currentTime 值（以秒为单位）计算分钟和秒数，如果分钟或秒值小于 10，则添加前导 0，然后创建显示读数并将其添加到时间标签.

#### 进一步阅读

这为您提供了如何向视频/音频播放器实例添加自定义播放器功能的基本概念。有关如何向视频/音频播放器添加更复杂功能的更多信息，请参阅：

- [音频和视频传输](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery)
- [视频播放器样式基础知识](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/Video_player_styling_basics)
- [创建一个跨浏览器的视频播放器](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/cross_browser_video_player)

我们还创建了一个高级示例来展示您如何创建一个面向对象的系统，该系统可以找到页面上的每个视频和音频播放器（无论有多少）并向其中添加我们的自定义控件。看[自定义控件-oojs](https://mdn.github.io/learning-area/accessibility/multimedia/custom-controls-OOJS/) （还 [查看源代码](https://github.com/mdn/learning-area/tree/master/accessibility/multimedia/custom-controls-OOJS)）。

## [音频记录](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#audio_transcripts)

为了让聋人能够访问音频内容，您确实需要创建文本抄本。这些可以以某种方式包含在与音频相同的页面上，也可以包含在单独的页面中并链接到。

在实际创建成绩单方面，您的选择是：

- 商业服务——您可以聘请专业人士来进行转录，例如，请参阅像这样的公司 [抄写员](https://scribie.com/), [铸造词](https://castingwords.com/)， 或者 [牧师](https://www.rev.com/). 环顾四周并寻求建议，以确保您找到一家信誉良好的公司，您可以与之有效合作。
- 社区/草根/自我转录——如果您是工作场所活跃社区或团队的一员，那么您可以向他们寻求帮助进行翻译。你甚至可以尝试自己做。
- 自动化服务——有可用的人工智能服务，比如 [特林特](https://trint.com/) 或者 [抄写员](https://transcribear.com/index.html). 将视频/音频文件上传到该站点，它会自动为您转录。在 YouTube 上，您可以选择生成自动字幕/成绩单。根据口语音频的清晰程度，最终的转录质量会有很大差异。

与生活中的大多数事情一样，您往往会得到所付出的；不同的服务在准确性和制作成绩单所需的时间方面会有所不同。如果您花钱请一家信誉良好的公司或 AI 服务来进行转录，您可能会快速且高质量地完成转录。如果您不想为此付费，您很可能会以较低的质量和/或缓慢地完成它。

发布音频资源但承诺稍后发布成绩单是不行的——这样的承诺通常不会兑现，这会削弱您和您的用户之间的信任。如果您呈现的音频类似于面对面会议或现场演讲表演，则可以在表演过程中做笔记，将它们与音频一起完整发布，然后寻求帮助清理笔记。

### [成绩单示例](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#transcript_examples)

如果您使用自动化服务，那么您可能必须使用该工具提供的用户界面。例如，看看我们的 [等等，ARIA 角色有类别吗？](https://www.youtube.com/watch?v=mwF-PpJOjMs)视频并选择三点菜单 (...) *> Show Transcript*。您会在单独的面板中看到成绩单。

如果您正在创建自己的用户界面来呈现您的音频和相关的转录本，您可以随心所欲地进行，但将其包含在可显示/可隐藏面板中可能更有意义；看到我们的[音频转录-ui](https://mdn.github.io/learning-area/accessibility/multimedia/audio-transcript-ui/) 示例（另见 [源代码](https://github.com/mdn/learning-area/tree/master/accessibility/multimedia/audio-transcript-ui)）。

### [音频描述](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#audio_descriptions)

有时，您的音频伴随着视觉效果，您需要提供某种类型的音频描述来描述额外的内容。

在许多情况下，这将采用视频的形式，在这种情况下，您可以使用本文下一部分中描述的技术来实现字幕。

但是，也有一些边缘情况。例如，您可能有一个会议的录音，其中引用了电子表格或图表等随附资源。在这种情况下，您应该确保资源与音频 + 抄本一起提供，并在抄本中提到的地方专门链接到它们。这当然会帮助所有用户，而不仅仅是聋人。

**注意：**音频抄本通常会帮助多个用户组。除了让聋哑用户访问音频中包含的信息之外，还可以考虑使用低带宽连接的用户，他们会发现下载音频不方便。还想一想在酒吧或酒吧等嘈杂环境中的用户，他试图访问信息但在噪音中听不到信息。

## [视频文本轨道](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#video_text_tracks)

为了让聋人、盲人甚至其他用户组（例如低带宽用户或不了解视频录制语言的用户）可以访问视频，您需要在视频内容中包含文本轨道。

**注意：**文本轨道对于潜在的任何用户也很有用，而不仅仅是残障人士。例如，一些用户可能无法听到音频，因为他们处于嘈杂的环境中（例如正在播放体育比赛时拥挤的酒吧），或者如果他们在安静的地方（例如图书馆）可能不想打扰他人.)

这不是一个新概念——电视服务提供隐藏式字幕已经很长时间了：

![来自老式卡通的框架，带有隐藏式字幕“干得好，戈尔迪。坚持下去！”](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia/closed-captions.png)

鉴于许多国家/地区提供带有以本国语言编写的字幕的英文电影，例如，DVD 上通常提供不同语言的字幕

![一部带德语字幕的英语电影“Emo, warum erkennst du nicht die Schonheit dieses Ortes？”](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia/subtitles_german.png)

有不同类型的文本轨道用于不同的目的。你会遇到的主要是：

- 字幕 - 为听不见音轨的聋哑用户提供帮助，包括正在说的话，以及上下文信息，例如谁说的话，人们是否生气或悲伤，以及音乐当前创造的情绪.
- 字幕 — 包括音频对话的翻译，适用于不懂所讲语言的用户。
- 描述 - 这些包括对无法观看视频的盲人的描述，例如场景的外观。
- 章节标题——旨在帮助用户浏览媒体资源的章节标记

### [实现 HTML5 视频文本轨道](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia#implementing_html5_video_text_tracks)

用于显示 HTML5 视频的文本轨道需要用 WebVTT 编写，这是一种包含多个文本字符串以及元数据的文本格式，例如您希望每个文本字符串在视频中的显示时间，甚至是有限的样式/定位信息。这些文本字符串称为提示。

典型的 WebVTT 文件如下所示：

```
WEBVTT

1
00:00:22.230 --> 00:00:24.606
This is the first subtitle.

2
00:00:30.739 --> 00:00:34.074
This is the second.

  ...
```

要使其与 HTML 媒体播放一起显示，您需要：

- 将其保存为 .vtt 文件在一个合理的地方。
- 链接到带有[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track)元素的 .vtt 文件。`<track>`应该放在`<audio>`或内`<video>`，但毕竟是`<source>`元素。使用该[`kind`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-kind)属性指定提示是副标题、标题还是说明。此外，用于[`srclang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-srclang)告诉浏览器您用什么语言编写字幕。

下面是一个例子：

```
<video controls>
  <source src="example.mp4" type="video/mp4">
  <source src="example.webm" type="video/webm">
  <track kind="subtitles" src="subtitles_en.vtt" srclang="en">
</video>
```

复制到剪贴板

这将导致显示字幕的视频，有点像这样：

![带有标准控件的视频播放器，例如播放、停止、音量和字幕的打开和关闭。 播放的视频显示了一名男子手持长矛状武器的场景，标题为“Esta hoja tiene pasado oscuro”。](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Multimedia/video-player-with-captions.png)

有关更多详细信息，请阅读[向 HTML5 视频添加字幕和副标题](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/Adding_captions_and_subtitles_to_HTML5_video)。你可以找到[这个例子](https://iandevlin.github.io/mdn/video-player-with-captions/) 伴随着这篇文章在 Github 上，由 Ian Devlin 撰写（参见 [源代码](https://github.com/iandevlin/iandevlin.github.io/tree/master/mdn/video-player-with-captions)也是。）这个例子使用 JavaScript 来允许用户在不同的字幕之间进行选择。请注意，要打开字幕，您需要按“CC”按钮并选择一个选项 — 英语、德语或西班牙语。

**注意：**文本跟踪和转录也可以帮助您进行[SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO)，因为搜索引擎特别喜欢文本。文本轨道甚至允许搜索引擎直接链接到视频中途的某个地方。

# 移动端可访问性

由于移动设备上的 Web 访问非常流行且知名平台（例如 iOS 和 Android）具有成熟的辅助功能工具，因此考虑您的 Web 内容在这些平台上的可访问性非常重要。本文着眼于特定于移动设备的可访问性注意事项。

## [移动设备上的辅助功能](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#accessibility_on_mobile_devices)

可访问性状态——以及对网络标准的总体支持——在现代移动设备中表现良好。移动设备运行与桌面浏览器完全不同的网络技术的日子已经一去不复返了，这迫使开发人员使用浏览器嗅探并为它们提供完全独立的站点（尽管很多公司仍然检测移动设备的使用情况并为它们提供单独的移动域）。

如今，移动设备通常可以处理功能齐全的网站，主要平台甚至内置了屏幕阅读器，使视障用户能够成功使用它们。现代移动浏览器也往往对[WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics)有很好的支持 。

要使网站在移动设备上可访问和可用，您只需要遵循一般良好的网页设计和可访问性最佳实践。

有一些例外情况需要对移动设备进行特殊考虑；主要有：

- 控制机制——确保在手机（即主要是触摸屏）以及台式机/笔记本电脑（主要是鼠标/键盘）上可以访问诸如按钮之类的界面控件。
- 用户输入——使用户在移动设备上的输入要求尽可能轻松（例如，在表单中，尽量减少打字）。
- 响应式设计——确保布局适用于移动设备，节省图像下载大小，并考虑为高分辨率屏幕提供图像。

## [Android 和 iOS 屏幕阅读器测试总结](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#summary_of_screenreader_testing_on_android_and_ios)

最常见的移动平台具有功能齐全的屏幕阅读器。这些功能与桌面屏幕阅读器的功能大致相同，只是它们主要使用触摸手势而不是组合键进行操作。

让我们看看主要的两个：Android 上的 TalkBack 和 iOS 上的 VoiceOver。

### [安卓话语提示](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#android_talkback)

TalkBack 屏幕阅读器内置于 Android 操作系统中。

要打开它，请查看您的手机型号和 Android 版本，然后查看 TalkBack 菜单的位置。它往往在 Android 版本之间甚至不同手机型号之间差异很大。一些手机制造商（例如三星）甚至在较新的手机中都没有 TalkBack，而是选择了他们自己的屏幕阅读器。

找到 TalkBack 菜单后，按下滑块开关以打开 TalkBack。按照出现的任何其他屏幕提示进行操作。

打开 TalkBack 后，您的 Android 设备的基本控件会有所不同。例如：

1. 单击一个应用程序将选择它，设备将读出该应用程序是什么。
2. 如果您在控制栏中，向左和向右滑动将在应用程序或按钮/控件之间移动。设备将读出每个选项。
3. 在任意位置双击将打开应用程序/选择选项。
4. 您还可以“通过触摸进行探索”——将手指按住屏幕并四处拖动，您的设备将读出您移动的不同应用程序/项目。

如果您想关闭 TalkBack：

1. 导航回 TalkBack 菜单屏幕（使用当前启用的不同手势。）
2. 导航到滑块开关并激活它以将其关闭。

**注意：**您可以随时向上和向左滑动平滑地进入主屏幕。如果您有多个主屏幕，您可以通过左右滑动两根手指在它们之间移动。

如需更完整的 TalkBack 手势列表，请参阅 [使用 TalkBack 手势](https://support.google.com/accessibility/android/answer/6151827).

#### 解锁手机

当 TalkBack 开启时，解锁手机有点不同。

您可以从锁定屏幕底部向上滑动两根手指。如果您设置了用于解锁设备的密码或图案，您将被带到相关的输入屏幕以进行输入。

您也可以通过触摸来探索 屏幕底部中间的 *解锁*按钮，然后双击。

#### 全局和本地菜单

TalkBack 允许您访问全局和本地上下文菜单，无论您在设备上导航到何处。前者提供与整个设备相关的全局选项，后者提供仅与您所在的当前应用程序/屏幕相关的选项。

要访问这些菜单：

1. 通过快速向下然后向右滑动来访问全局菜单。
2. 通过快速向上然后向右滑动来访问本地菜单。
3. 左右滑动可在不同选项之间循环。
4. 选择所需选项后，双击以选择该选项。

有关全局和本地上下文菜单下所有可用选项的详细信息，请参阅 [使用全局和本地上下文菜单](https://support.google.com/accessibility/android/answer/6007066).

#### 浏览网页

您可以在 Web 浏览器中使用本地上下文菜单来查找仅使用标题、表单控件或链接导航网页的选项，或逐行导航等。

例如，打开 TalkBack：

1. 打开您的网络浏览器。
2. 激活 URL 栏。
3. 输入一个带有一堆标题的网页，例如 bbc.co.uk 的首页。要输入 URL 的文本：
   - 通过向左/向右轻扫直到到达，然后双击来选择 URL 栏。
   - 在虚拟键盘上按住手指，直到获得所需的字符，然后松开手指进行键入。对每个字符重复。
   - 完成后，找到 Enter 键并按下它。
4. 左右滑动可在页面上的不同项目之间移动。
5. 以平滑的动作向上和向右滑动以进入本地内容菜单。
6. 向右滑动，直到找到“标题和地标”选项。
7. 双击以选择它。现在，您可以左右滑动以在标题和 ARIA 地标之间移动。
8. 要返回默认模式，请通过向上和向右滑动再次进入本地上下文菜单，选择“默认”，然后双击以激活。

**注意：**见 [使用 TalkBack 开始使用 Android](https://support.google.com/accessibility/android/answer/6283677?hl=en&ref_topic=3529932) 获取更完整的文档。

### [iOS 旁白](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#ios_voiceover)

移动版的 VoiceOver 内置于 iOS 操作系统中。

要打开它，请转到“您的 *设置”* 应用并选择“*辅助功能”>“VoiceOver”*。按下 *VoiceOver* 滑块以启用它（您还将在此页面上看到许多与 VoiceOver 相关的其他选项）。

**注意：**一些较旧的 iOS 设备在*“设置”应用程序*>“*通用”* >“*辅助功能”* >“ *VoiceOver* *”中*有 VoiceOver 菜单。

启用 VoiceOver 后，iOS 的基本控制手势会有所不同：

1. 单击将导致您点击的项目被选中；您的设备将朗读您点击的项目。
2. 您还可以通过左右滑动在屏幕上的项目之间进行导航，或通过在屏幕上左右滑动手指在不同项目之间移动（当您找到想要的项目时，您可以移开手指来选择它）。
3. 要激活选定的项目（例如，打开选定的应用程序），请双击屏幕上的任意位置。
4. 用三指滑动以滚动页面。
5. 用两根手指点击以执行与上下文相关的操作 - 例如，在相机应用程序中拍照。

要再次关闭它，请 使用上述手势导航回 *“设置”>“通用”>“辅助功能”>“VoiceOver* ”，然后将“ *VoiceOver”* 滑块切换 回关闭状态。

#### 解锁手机

要解锁手机，您需要像往常一样按下主页按钮（或滑动）。如果您设置了密码，则可以通过滑动/滑动（如上所述）来选择每个数字，然后在找到正确的数字后双击以输入每个数字。

#### 使用转子

打开 VoiceOver 后，您可以使用名为 Rotor 的导航功能，它允许您从许多常用的有用选项中快速选择。要使用它：

1. 在屏幕上转动两根手指，就像转动表盘一样。当您进一步旋转时，每个选项都会被大声朗读。您可以来回循环浏览选项。
2. 找到所需选项后：
   - 松开手指以选择它。
   - 如果它是一个选项，您可以迭代其值（例如音量或语速），您可以向上或向下滑动以增加或减少所选项目的值。

Rotor 下可用的选项是上下文相关的——它们会根据您所在的应用程序或视图而有所不同（请参见下面的示例）。

#### 浏览网页

让我们来看看使用 VoiceOver 浏览网页：

1. 打开您的网络浏览器。
2. 激活 URL 栏。
3. 输入一个带有一堆标题的网页，例如 bbc.co.uk 的首页。要输入 URL 的文本：
   - 通过向左/向右轻扫直到到达，然后双击来选择 URL 栏。
   - 对于每个字符，在虚拟键盘上按住手指，直到获得所需的字符，然后松开手指以选择它。点按两次即可键入。
   - 完成后，找到 Enter 键并按下它。
4. 左右滑动可在页面上的项目之间移动。您可以双击一个项目来选择它（例如，点击链接）。
5. 默认情况下，选定的转子选项将为讲话速率；您目前可以上下滑动以提高或降低语速。
6. 现在像拨盘一样在屏幕上转动两根手指以显示转子并在其选项之间移动。以下是一些可用选项的示例：
   - *语速*：更改语速。
   - *Containers*：在页面上的不同语义容器之间移动。
   - *标题*：在页面上的*标题*之间移动。
   - *链接*：在页面上的*链接*之间移动。
   - *表单控件*：在页面上的*表单控件*之间移动。
   - *语言*：在不同的翻译之间移动（如果可用）。
7. 选择 *标题*。现在，您将能够上下滑动以在页面上的标题之间移动。

**注意：**有关可用的 VoiceOver 手势和其他有关 iOS 辅助功能测试的提示的更完整参考，请参阅 [使用 VoiceOver 在您的设备上测试辅助功能](https://developer.apple.com/library/content/technotes/TestingAccessibilityOfiOSApps/TestAccessibilityonYourDevicewithVoiceOver/TestAccessibilityonYourDevicewithVoiceOver.html#//apple_ref/doc/uid/TP40012619-CH3).

## [控制机制](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#control_mechanisms)

在我们的 CSS 和 JavaScript 可访问性文章中，我们研究了特定于特定类型控制机制的事件的想法（请参阅 [鼠标特定事件](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#mouse-specific_events)）。概括地说，这些会导致可访问性问题，因为其他控制机制无法激活相关功能。

例如， [单击](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick) 事件在可访问性方面表现良好——可以通过单击设置了处理程序的元素、按 Tab 键并按 Enter/Return 或在触摸屏设备上点击它来调用关联的事件处理程序。试试我们的 [simple-button-example.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/simple-button-example.html) 例子 （[现场直播](https://mdn.github.io/learning-area/accessibility/mobile/simple-button-example.html)) 看看我们的意思。

或者，特定于[鼠标的](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown)事件（例如[mousedown](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmousedown) 和 [mouseup）会](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onmouseup) 产生问题 — 无法使用非鼠标控件调用它们的事件处理程序。

如果您试图控制我们的 [simple-box-drag.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/simple-box-drag.html) ([现场观看示例](https://mdn.github.io/learning-area/accessibility/mobile/simple-box-drag.html)) 使用键盘或触摸的示例，您将看到问题。发生这种情况是因为我们正在使用如下代码：

```
div.onmousedown = function() {
  initialBoxX = div.offsetLeft;
  initialBoxY = div.offsetTop;
  movePanel();
}

document.onmouseup = stopMove;
```

复制到剪贴板

要启用其他形式的控制，您需要使用不同但等效的事件——例如，触摸事件在触摸屏设备上起作用：

```
div.ontouchstart = function(e) {
  initialBoxX = div.offsetLeft;
  initialBoxY = div.offsetTop;
  positionHandler(e);
  movePanel();
}

panel.ontouchend = stopMove;
```

复制到剪贴板

我们提供了一个简单的例子，展示了如何一起使用鼠标和触摸事件——见 [multi-control-box-drag.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/multi-control-box-drag.html) ([现场观看示例](https://mdn.github.io/learning-area/accessibility/mobile/multi-control-box-drag.html) 还）。

**注意：**您还可以在[实现游戏控制机制中](https://developer.mozilla.org/en-US/docs/Games/Techniques/Control_mechanisms)查看显示如何实现不同控制机制的完整功能示例 。

## [响应式设计](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#responsive_design)

[响应式设计](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Responsive/responsive_design_building_blocks) 是根据屏幕大小和分辨率等因素使应用程序的布局和其他功能动态变化的做法，因此它们可供不同设备类型的用户使用和访问。

特别是，移动需要解决的最常见问题是：

- 布局对移动设备的适用性。例如，多列布局在窄屏幕上效果不佳，并且可能需要增加文本大小以使其清晰易读。此类问题可以通过使用[媒体查询](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)、 [视口](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)和 [flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)等技术创建响应式布局来解决。
- 保存下载的图像大小。一般来说，小屏幕设备不需要与桌面设备一样大的图像，而且它们更有可能使用慢速网络连接。因此，明智的做法是将较小的图像适当地提供给窄屏设备。您可以使用[响应式图像技术](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)处理此问题 。
- 考虑高分辨率。许多移动设备具有高分辨率屏幕，因此需要更高分辨率的图像，以便显示能够继续看起来清晰锐利。同样，您可以使用响应式图像技术酌情提供图像。此外，使用 SVG 矢量图像格式可以满足许多图像要求，这种格式在当今的浏览器中得到了很好的支持。SVG 具有较小的文件大小，无论显示的大小如何，都将保持清晰（ 有关详细信息，请参阅 [向 Web 添加矢量图形](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Adding_vector_graphics_to_the_Web)）。

**注意：**我们不会在这里全面讨论响应式设计技术，因为它们在 MDN 的其他地方都有介绍（见上面的链接）。

### [特定的移动注意事项](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#specific_mobile_considerations)

在使网站更易于在移动设备上访问时，还需要考虑其他重要问题。我们在这里列出了一些，但当我们想到它们时我们会添加更多。

#### 不禁用缩放

使用 [viewport](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)，可以禁用缩放。始终确保启用调整大小，并将宽度设置为设备的宽度[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)：

```
<meta name="viewport" content="width=device-width; user-scalable=yes">
```

复制到剪贴板

`user-scalable=no`如果可能，您永远不应该设置 ——许多人依靠缩放来查看您网站的内容，因此取消此功能是一个非常糟糕的主意。在某些情况下，缩放可能会破坏 UI；在这种情况下，如果您觉得您绝对需要禁用缩放，您应该提供一些其他类型的等效项，例如以不破坏 UI 的方式增加文本大小的控件。

#### 保持菜单可访问

由于移动设备上的屏幕要窄得多，因此使用媒体查询和其他技术将导航菜单缩小为显示屏顶部的一个小图标是很常见的 - 只有在以下情况下才能按下该图标以显示菜单它是必需的——当在移动设备上查看网站时。这通常由“三条水平线”图标表示，因此该设计模式被称为“汉堡菜单”。

在实现这样的菜单时，您需要确保显示它的控件可以通过适当的控制机制（通常是移动设备的触摸）访问，如上面的[控制机制中](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#control_mechanisms)所述，并且页面的其余部分被移开或在访问菜单时以某种方式隐藏，以避免与导航混淆。

单击此处获取 [好的汉堡菜单示例](https://fritz-weisshart.de/meg_men/).

## [用户输入](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/Mobile#user_input)

在移动设备上，输入数据对于用户来说往往比在台式计算机上的等效体验更烦人。与触摸屏虚拟键盘或微型移动物理键盘相比，使用台式机或笔记本电脑键盘将文本输入到表单输入中更为方便。

出于这个原因，值得尝试尽量减少所需的打字量。例如，不是让用户每次使用常规文本输入填写他们的职位，而是提供一个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)包含最常见选项的菜单（这也有助于数据输入的一致性），并提供“其他”选项，显示一个文本字段来输入任何异常值。你可以看到这个想法在行动中的一个简单例子 [通用作业类型.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/common-job-types.html) （见 [常见工作示例直播](https://mdn.github.io/learning-area/accessibility/mobile/common-job-types.html)）。

还值得考虑使用 HTML5 表单输入类型，例如移动平台上的日期，因为它们处理得很好——例如，Android 和 iOS 都显示与设备体验非常匹配的可用小部件。看 [html5-form-examples.html](https://github.com/mdn/learning-area/blob/master/accessibility/mobile/html5-form-examples.html) 一些例子（见 [HTML5 表单示例现场直播](https://mdn.github.io/learning-area/accessibility/mobile/html5-form-examples.html)) — 尝试加载这些并在移动设备上操作它们。例如：

- 类型 `number`， `tel`和 `email` 显示合适的虚拟键盘用于输入数字/电话号码。
- 键入 `time` 并 `date` 显示用于选择时间和日期的合适选择器。

如果您想为桌面提供不同的解决方案，您始终可以使用功能检测为您的移动设备提供不同的标记。看 [输入类型](https://diveinto.html5doctor.com/detect.html#input-types) 有关检测不同输入类型的原始信息，还可以查看我们的 [特征检测文章](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) 以获取更多信息。

# 客户端工具概览

在本文中，我们提供了现代web工具的概述，有哪些工具可用，在web应用程序开发的生命周期中您将在哪里遇到它们，以及如何使用各个工具寻求帮助。

## [现代工具概述](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#现代工具概述)

随着时间的推移，为网络编写软件已经变得越来越复杂。尽管“手工”编写HTML、CSS和JavaScript仍然是完全合理的，但现在有大量的工具可供开发人员使用，以加快构建web站点或应用程序的过程。

有一些非常完善的工具已经成为开发社区中常见的“家喻户晓的名字”，并且每天都在编写和发布新的工具来解决特定的问题。您甚至可能发现自己正在编写一个软件来帮助您自己的开发过程，以解决现有工具似乎无法处理的特定问题。

单个项目中包含的大量工具很容易让人不知所措。同样，像Webpack这样的工具的一个配置文件可能有数百行之长，其中大多数都是神奇的咒语，似乎可以完成工作，但只有大神级工程师才能完全理解

有时，即使是最有经验的web开发人员也会因为工具问题而陷入困境;甚至在接触到一行应用程序代码之前，都可能浪费数小时来尝试让工具管道工作。如果你发现自己在过去挣扎，那么用担心，你并不孤独。



在这篇文章中，我们将不会回答所有关于web工具的所有问题，但我们将为您提供一个了解基本原理的有用起点，你可以从中构建。对于任何复杂的主题，最好从小处开始，然后逐步进行更高级的使用。

## [现代工具系统](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#现代工具系统)

当今的现代开发人员工具生态系统非常庞大，因此对这些工具正在解决的主要问题有一个大致的概念是非常有用的。如果你跳到你最喜欢的搜索引擎上，搜索“前端开发工具”，你会得到一系列的结果，从文本编辑器到浏览器，再到你可以用来做笔记的笔。

虽然您选择的代码编辑器肯定是一种工具选择，但本系列文章将不止于此，重点关注帮助您更有效地生成web代码的开发人员工具。

从高层次来看，您可以将客户端工具放入以下三大类需要解决的问题中：

- **安全网络** — 在代码开发期间有用的工具。
- **转换** — 以某种方式转换代码的工具，例如将一种中间语言转换为浏览器可以理解的JavaScript。
- **开发后阶段** — 编写完代码后有用的工具，如测试和部署工具。

让我们更详细地看看每一个。

### [安全网络](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#安全网络)

这些工具可以使您编写的代码更好一些。

这一部分的工具应该特定于您自己的开发环境，尽管对于公司来说，有某种策略或可用于安装的预备配置，以便所有开发人员都使用相同的流程的情况并不少见。

这包括使您的开发过程更容易生成稳定可靠的代码的任何内容。安全网络工具还应该帮助您避免错误或自动纠正错误，而不必每次都从头开始构建代码。

您将发现开发人员正在使用的一些非常常见的安全网络工具类型如下。

#### Linters

**Linters** 是检查您的代码并告诉您存在任何错误的工具，它们是什么类型的错误，以及它们出现在哪些代码行上。通常，linters不仅可以被配置为报告错误，还可以报告任何违反您的团队可能正在使用的指定样式指南的行为(例如代码使用了错误的缩进空格数，或者使用了[template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) 而不是常规的字符串文本)。

[eslint](https://eslint.org/) 业界标准的JavaScript linter是一种高度可配置的工具，用于捕获潜在的语法错误，并在代码中鼓励“最佳实践”。一些公司和项目也是这样 [shared their eslint configs](https://www.npmjs.com/search?q=keywords:eslintconfig)。

您还可以找到用于其他语言的linting工具，比如[csslint](http://csslint.net/)。

同样值得一看的是 [webhint](https://webhint.io/), 一个可配置的，开放源码的网页链接，展示了最佳实践，包括可访问性，性能，跨浏览器兼容性 [MDN's browser compatibility data](https://github.com/mdn/browser-compat-data), 安全, PWAs测试等等。它可以作为 [Node.js command-line tool](https://webhint.io/docs/user-guide/) 和 [VS Code extension](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint).

#### 源代码控制

也称为版本控制系统(VCS)，源代码控制对于备份工作和在团队中工作至关重要。典型的VCS包括拥有您要对其进行更改的代码的本地版本。然后将更改“推”到存储在某个服务器上的远程存储库中的代码的“主”版本。通常有一种方法来控制和协调对代码的“主”副本做了什么更改，以及什么时候做更改，这样开发团队就不会一直覆盖彼此的工作。

[Git](https://git-scm.com/) 是现在大多数人使用的源代码控制系统。它主要通过命令行访问，但也可以通过友好的用户界面访问。使用git存储库中的代码，您可以将其推到自己的服务器实例中，或者使用托管的源代码控制网站，如[GitHub](https://github.com/), [GitLab](https://about.gitlab.com/), or [BitBucket](https://bitbucket.org/product/features).

我们将在这个模块中使用GitHub。你可以在网站上找到更多关于它的信息[Git and GitHub](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/GitHub).

#### 代码格式化

代码格式化程序与linters有些关联，除了它们不是指出代码中的错误，而是根据你的样式规则，确保你的代码被正确格式化，理想情况下自动修复它们发现的错误。

[Prettier](https://prettier.io/) 是一个非常流行的代码格式化程序示例，稍后我们将在模块中使用它。

#### 打包工具

这些工具让你的代码准备生产,例如，通过tree-shaking来确保只有实际使用的代码库的部分被放到最终的生产代码中,或“缩减”删除所有空格在生产代码中,使其尽可能小之前上传到服务器。

[Parcel](https://parceljs.org/) 是一个特别好用的工具,都属于这个类别可以完成上面的任务,但也有助于资产包像HTML, CSS和图像文件方便的包,你可以继续部署,也为您自动添加依赖项当你试着使用它们。它甚至可以为您处理一些代码转换任务。

[Webpack](https://webpack.js.org/) 是一个非常流行的代码格式化程序示例，稍后我们将在模块中使用它。

### [转换](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#转换)

web应用程序生命周期的这个阶段通常允许您编写“未来代码”(比如最新的CSS或JavaScript特性，这些特性可能还没有得到浏览器的本地支持)，或者完全使用另一种语言编写代码，比如 [TypeScript](https://www.typescriptlang.org/). 转换工具将为您生成与浏览器兼容的代码，以用于生产。

通常web开发被认为是三种语言: [HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML), [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS), and [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript), 所有这些语言都有转换工具。转换提供了两个主要好处(还有其他好处)

1. 能够使用最新的语言特性编写代码，并将其转换为可在日常设备上使用的代码。例如，您可能希望使用尖端的新语言特性来编JavaScript，但是您的最终产品代码仍然可以在不支持这些特性的旧浏览器上工作。例如：

   - [Babel](https://babeljs.io/):一个JavaScript编译器，允许开发人员使用最前沿的JavaScript编写代码，然后Babel将其转换为老式的JavaScript，让更多的浏览器能够理解。开发人员也可以编写和发布[plugins for Babel](https://babeljs.io/docs/en/plugins).

   - PostCSS

     :和Babel做同样的事情，但是有先进的CSS特性。如果没有相同的方法使用旧的CSS特性来做一些事情，PostCSS将安装一个JavaScript填充来模拟您想要的CSS效果。

     

2. 选择用一种完全不同的语言编写代码，并将其转换为与web兼容的语言。例如：

   - [Sass/SCSS](https://sass-lang.com/):这个CSS扩展允许您使用变量、嵌套规则、混合、函数和许多其他特性，其中一些特性在本地CSS中是可用的(比如变量)，而另一些则不是。
   - [TypeScript](https://www.typescriptlang.org/):TypeScript是JavaScript的一个超集，它提供了一堆额外的特性。TypeScript编译器在生成产品时将TypeScript代码转换为JavaScript。
   - 框架例如 [React](https://reactjs.org/), [Ember](https://emberjs.com/), and [Vue](https://vuejs.org/):框架提供了许多免费的功能，并允许您通过构建在普通JavaScript之上的自定义语法来使用它们。在后台，框架的JavaScript代码努力解释这个定制语法，并将其呈现为最终的web应用程序。

### [开发后阶段](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#开发后阶段)

开发后阶段工具可以确保您的软件能够访问web并继续运行。这包括部署流程、测试框架、审计工具等等。

在开发过程的这个阶段，您希望与之进行最少的主动交互，这样，一旦配置完毕，它基本上是自动运行的，只有在出现错误时才弹出窗口打招呼。

#### 测试工具

它们通常采用一种工具的形式，该工具将自动对您的代码运行测试，以确保在进行进一步操作之前它是正确的(例如，当您试图将更改推送到GitHub repo时)。这可能包括linting，但也包括更复杂的过程，如单元测试，在这里运行部分代码，以确保它们按照应有的方式运行。

- 框架包括编写测试[Jest](https://jestjs.io/), [Mocha](https://mochajs.org/), 和 [Jasmine](https://jasmine.github.io/).
- 自动测试运行和通知系统包括[Travis CI](https://travis-ci.org/), [Jenkins](https://jenkins.io/), [Circle CI](https://circleci.com/), 和 [others](https://en.m.wikipedia.org/wiki/List_of_build_automation_software#Continuous_integration).

#### 配置工具

配置系统允许您发布网站，可用于静态和动态站点，通常与测试系统一起工作。例如，典型的工具链会等待您将更改推送到远程回购，运行一些测试以查看更改是否正确，然后如果测试通过，则自动将您的应用程序部署到生产站点。

[Netlify](https://netlify.com/) 是目前最流行的部署工具之一，但其他包括[Vercel](https://vercel.com/) 和 [Github Pages](https://pages.github.com/).

#### 其他的

在开发后期阶段，还有许多其他可用的工具类型，包括 [Code Climate](https://codeclimate.com/) 对于收集代码质量度量， [webhint browser extension](https://webhint.io/docs/user-guide/extensions/extension-browser/) 用于执行跨浏览器兼容性的运行时分析和其他检查, [Github bots](https://probot.github.io/) 提供更强大的GitHub功能, [Updown](https://updown.io/) 提供应用程序运行时间监控等等。

### [工具种类的想法](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#工具种类的想法)

在开发生命周期中应用不同的工具类型当然是有顺序的，但请放心，您不必在发布一个网站时将所有这些工具都准备就绪。事实上，你不需要这些。然而，在您的过程中包括这些工具将改善您自己的开发体验，并可能提高代码的总体质量。

新的开发人员工具通常需要一段时间才能适应其复杂性。Webpack是最著名的工具之一，它以使用起来过于复杂而著称，但是在最新的主要版本中，它大力简化了常用的用法，因此所需的配置被减少到绝对最小。

绝对没有银弹可以保证工具的成功，但是随着你经验的增加，你会发现适合你或者你的团队和他们的项目的工作流程。一旦过程中所有的扭结被平展，你的工具链应该是你可以忘记的东西，它应该只是工作。

## [如何选择并寻求特殊工具的帮助](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#如何选择并寻求特殊工具的帮助)

大多数工具往往是独立编写和发布的，因此，尽管几乎可以肯定有可用的帮助，但它们的位置或格式永远不会相同。因此，很难找到使用工具的帮助，甚至很难选择使用什么工具。关于哪些是最好的工具的知识是有点部落式的，这意味着如果您还没有进入web社区，就很难确定到底应该使用哪些工具!这是我们编写本系列文章的原因之一，希望能够提供其他方法难以找到的第一步。

您可能需要以下内容的组合

- 有经验的老师、导师、同学或有一定经验的同事以前解决过这类问题，并能提出建议。

- 一个有用的特定地方搜索。对前端开发人员工具的一般web搜索通常是无用的，除非您已经知道您正在搜索的工具的名称。

  - 例如，如果您正在使用npm包管理器来管理依赖项，那么转到[npm homepage](https://www.npmjs.com/) 并搜索您正在寻找的工具的类型，例如，如果您想要日期格式化实用程序，请尝试搜索“date”，如果您想要搜索通用代码格式化程序，则尝试搜索“formatter”。请注意流行度、质量和维护分数，以及软件包最近更新的时间。还可以点击工具页面，了解每个包每月有多少下载，以及它是否有好的文档，可以用来了解它是否完成了您需要它做的事情。以这些标准为基础[date-fns library](https://www.npmjs.com/package/date-fns) 看起来是一个很好的日期格式化工具。在本模块的第3章中，您将看到这个工具的实际应用，并了解更多关于包管理器的信息。

  - 如果您正在寻找将工具功能集成到代码编辑器中的插件，请查看代码编辑器的“插件/扩展名”页面-请参阅

     

    Atom packages

     

    and

     

    VSCode extensions

    ,为例。看一看首页上的特色扩展，然后再次尝试搜索你想要的扩展类型(或者工具名称，例如在VSCode扩展页面上搜索“eslint”)。当你得到结果的时候，看看这个扩展有多少颗星或者下载了多少，作为它质量的一个指标。

    

- 例如，与开发相关的论坛，询问关于使用什么工具的问题[MDN Learn Discourse](https://discourse.mozilla.org/c/mdn/learn), or [Stack Overflow](https://stackoverflow.com/).

当您选择要使用的工具时，第一个端口应该是工具项目主页。这可能是一个完整的网站，也可能是代码库中的一个readme文档。例如 [date-fns docs](https://date-fns.org/docs/Getting-Started)就很好、很完整、很容易理解。然而，有些文档可能相当技术性和学术性，并不适合您的学习需求。

相反，您可能希望找到一些关于如何开始使用特定类型的工具的专门教程。好的起点是搜索网站喜欢[CSS Tricks](https://css-tricks.com/), [Dev](https://dev.to/), [freeCodeCamp](https://www.freecodecamp.org/), and [Smashing Magazine](https://www.smashingmagazine.com/), 因为它们是为web开发行业量身定做的。

同样，在搜索适合自己的工具时，您可能会使用几种不同的工具，试用它们，看看它们是否有意义，是否得到良好的支持，并执行您希望它们执行的任务。这很好，这对学习很有好处，而且随着你获得更多经验，道路会变得更平坦。

## [总结](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#总结)

以上是我们对客户端web工具主题的简要介绍的最后一部分。接下来，我们将为您提供一个关于命令行的速成课程，许多工具都是从命令行调用的。我们将看一看命令行可以做什么，然后尝试安装和使用我们的第一个工具。

# 命令行速成课程

在您的开发过程中，您无疑需要在终端中（或在“命令行”上运行一些命令——这些实际上是同一件事）。本文介绍了终端、您需要输入的基本命令、如何将命令链接在一起以及如何添加您自己的命令行界面 (CLI) 工具。

## [欢迎来到终端](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#welcome_to_the_terminal)

终端是一个文本界面，用于执行基于文本的程序。如果您正在运行任何用于 Web 开发的工具，则几乎可以保证您必须打开命令行并运行一些命令才能使用您选择的工具（您经常会看到此类工具称为**CLI 工具**）命令行界面工具）。

通过在命令行中键入命令可以使用大量工具；许多已经预先安装在您的系统上，还有大量其他的可以从软件包注册表中安装。包注册表类似于应用程序商店，但（主要）用于基于命令行的工具和软件。我们将在本章稍后看到如何安装一些工具，我们将在下一章中了解有关包注册表的更多信息。

对命令行最大的批评之一是它在用户体验方面非常缺乏。第一次查看命令行可能是一种令人生畏的体验：一个空白屏幕和一个闪烁的光标，几乎没有明显的帮助可用于做什么。

从表面上看，它们远非受欢迎，但您可以用它们做很多事情，我们保证，通过一些指导和练习，使用它们会变得更容易！这就是我们提供本章的原因——帮助您在这个看似不友好的环境中入门。

### [终端从哪里来？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#where_did_the_terminal_come_from)

终端起源于 1950 年代至 60 年代左右，其原始形式与我们今天使用的完全不同（为此我们应该感谢）。你可以在维基百科的条目中阅读一些历史[电脑终端](https://en.wikipedia.org/wiki/Computer_terminal).

从那时起，终端一直是所有操作系统的一个不变特征——从台式机到隐藏在云中的服务器，再到像 Raspberry PI Zero 这样的微型计算机，甚至到手机。它提供对计算机底层文件系统和低级功能的直接访问，因此如果您知道自己在做什么，则对于快速执行复杂任务非常有用。

它对于自动化也很有用——例如编写一个命令来立即更新数百个文件的标题，比如从“ch01-xxxx.png”到“ch02-xxxx.png”。如果您使用查找程序或资源管理器 GUI 应用程序更新文件名，则需要很长时间。

无论如何，终端不会很快消失。

### [终端是什么样子的？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#what_does_the_terminal_look_like)

您可以在下方看到一些不同风格的程序，这些程序可以让您进入终端。

下图显示了 Windows 中可用的命令提示符——从“cmd”程序到“powershell”有很多选项——可以通过键入程序名称从开始菜单运行。

![一个 vanilla windows cmd 行窗口和一个 windows powershell 窗口](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/win-terminals.png)

在下面，您可以看到 macOS 终端应用程序。

![一个基本的 vanilla mac 终端](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/mac-terminal.png)

### [您如何访问终端？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#how_do_you_access_the_terminal)

如今，许多开发人员都在使用基于 Unix 的工具（例如终端，以及您可以通过它访问的工具）。当今网络上存在的许多教程和工具都支持（并且可悲地假设）基于 Unix 的系统，但不用担心——它们在大多数系统上都可用。在本节中，我们将了解如何访问您选择的系统上的终端。

#### Linux/Unix

如上所述，Linux/Unix 系统默认有一个可用的终端，列在您的应用程序中。

#### 苹果系统

macOS 有一个名为 Darwin 的系统，位于图形用户界面下方。Darwin 是类 Unix 系统，它提供终端和对低级工具的访问。macOS Darwin 与 Unix 基本相同，当然足够好，不会让我们在阅读本文时产生任何担忧。

该终端在 macOS 上的应用程序/实用程序/终端中可用。

#### 视窗

与其他一些编程工具一样，在 Windows 上使用终端（或命令行）传统上不像在其他操作系统上那样简单或容易。但情况正在好转。

长期以来，Windows 传统上都有自己的类似终端的程序，称为 cmd（“命令提示符”），但这绝对与 Unix 命令不具有同等性，并且等同于旧式的 Windows DOS 提示符。

存在更好的程序来在 Windows 上提供终端体验，例如 Powershell ([请参阅此处查找安装程序](https://github.com/PowerShell/PowerShell)) 和 Gitbash（作为 [适用于 Windows 的 git](https://gitforwindows.org/) 工具集）

然而，现代 Windows 的最佳选择是适用于 Linux 的 Windows 子系统 (WSL)——一个直接从 Windows 10 内部运行 Linux 操作系统的兼容层，允许您直接在 Windows 上运行“真正的终端”，而无需一个虚拟机。

这可以直接从 Windows 商店免费安装。您可以在[适用于 Linux 的 Windows 子系统文档](https://docs.microsoft.com/en-us/windows/wsl).

![linux 文档的 windows 子系统的屏幕截图](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/wsl.png)

至于在 Windows 上选择什么选项，我们强烈建议尝试安装 WSL。您可以坚持使用默认的命令提示符 ( `cmd`)，并且许多工具都可以正常工作，但是如果您对 Unix 工具有更好的了解，您会发现一切都变得更容易。

#### 旁注：命令行和终端有什么区别？

通常，您会发现这两个术语可以互换使用。从技术上讲，终端是启动并连接到外壳的软件。shell 是您的会话和会话环境（可以自定义提示和快捷方式等内容）。命令行是您输入命令且光标闪烁的文字行。

### [你*必须*使用终端吗？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#do_you_have_to_use_the_terminal)

尽管命令行中有大量可用的工具，但如果您使用诸如 [视觉工作室代码](https://code.visualstudio.com/)还有大量扩展可以用作使用终端命令的代理，而无需直接使用终端。但是，您不会为您想要做的所有事情找到代码编辑器扩展——最终您必须获得一些终端经验。

## [基本的内置终端命令](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#basic_built-in_terminal_commands)

话不多说——让我们开始看一些终端命令！开箱即用，以下是命令行可以执行的一些操作，以及每种情况下相关工具的名称：

- 浏览计算机的文件系统以及基本级别的任务，例如创建、复制、重命名和删除：
  - 移动您的目录结构： `cd`
  - 创建目录： `mkdir`
  - 创建文件（并修改它们的元数据）： `touch`
  - 复制文件： `cp`
  - 移动文件： `mv`
  - 删除文件或目录： `rm`
- 下载在特定 URL 中找到的文件： `curl`
- 在较大的文本正文中搜索文本片段： `grep`
- 逐页查看文件的内容：`less`,`cat`
- 操作和转换文本流（例如`<div>`，将 HTML 文件中s 的所有实例更改为`<article>`）：`awk`, `tr`,`sed`

**注意：**网上有很多很好的教程，可以更深入地了解网上的命令行——这只是一个简短的介绍！

让我们继续前进，看看在命令行上使用其中的一些工具。在继续之前，请打开您的终端程序！

### [在命令行上导航](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#navigation_on_the_command_line)

当您访问命令行时，您将不可避免地需要导航到特定目录以“执行某些操作”。所有操作系统（假设默认设置）都会在您的“主”目录中启动它们的终端程序，您可能希望从那里移动到不同的位置。

该`cd`命令可让您更改目录。从技术上讲，cd 不是程序而是内置程序。这意味着您的操作系统提供了开箱即用的功能，而且您不会意外删除它——谢天谢地！您无需过多担心命令是否是内置命令，但请记住，所有基于 unix 的系统上都会出现内置命令。

要更改目录，请`cd`在终端中键入，然后是要移动到的目录。假设该目录在您的主目录内，您可以使用`cd Desktop`（请参见下面的屏幕截图）。

![在各种 Windows 终端中运行 cd Desktop 命令的结果 - 终端位置移动到桌面](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/win-terminals-cd.png)

尝试在系统终端中输入以下内容：

```
cd Desktop
```

复制到剪贴板

如果要返回上一个目录，可以使用两个点：

```
cd ..
```

复制到剪贴板

**注意：**一个非常有用的终端快捷方式是使用tab键来自动完成您知道存在的名称，而不必输入整个内容。例如，在键入上述两个命令后，尝试键入`cd D`并按tab- 它应该`Desktop`为您自动完成目录名称，前提是它存在于当前目录中。在您前进时请记住这一点。

如果您要转到的目录嵌套很深，则需要知道到达它的路径。随着您对文件系统的结构更加熟悉，这通常会变得更容易，但是如果您不确定路径，您通常可以通过组合`ls`命令（见下文）并通过在资源管理器中单击来确定路径/Finder 窗口以查看目录相对于您当前所在的位置。

例如，如果您想转到名为 的目录`src`，该目录`project`位于名为 的目录中，位于 上`Desktop`，您可以键入以下三个命令从您的主文件夹到达那里：

```
cd Desktop
cd project
cd src
```

复制到剪贴板

但这很浪费时间——相反，您可以键入一个命令，用正斜杠分隔路径中的不同项目，就像在 CSS、HTML 或 JavaScript 代码中指定图像或其他资产的路径时所做的那样：

```
cd Desktop/project/src
```

复制到剪贴板

请注意，在路径上包含前导斜杠会使路径成为绝对路径，例如`/Users/your-user-name/Desktop`. 像我们上面所做的那样省略前导斜杠使路径相对于您当前的工作目录。这与您在 Web 浏览器中看到的 URL 完全相同。前导斜线表示“在网站的根部”，而省略斜线表示“URL 是相对于我当前页面的”。

**注意：**在 Windows 上你使用反斜杠而不是正斜杠，例如 `cd Desktop\project\src`——这可能看起来很奇怪，但如果你对为什么感兴趣，[观看此 YouTube 剪辑](https://www.youtube.com/watch?v=5T3IJfBfBmI) 由 Microsoft 的一位首席工程师进行解释。

### [列出目录内容](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#listing_directory_contents)

另一个内置的 Unix 命令是`ls`（list 的缩写），它列出您当前所在目录的内容。请注意，如果您使用默认的 Windows 命令提示符 ( `cmd`) ，这将不起作用- 等效的有`dir`.

现在尝试在您的终端中运行它：

```
ls
```

复制到剪贴板

这会为您提供当前工作目录中的文件和目录列表，但信息非常基本——您只能获得每个项目的名称，而不是文件或目录，或其他任何内容。幸运的是，对命令用法的一个小小的改变就可以为您提供更多的信息。

### [介绍命令选项](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#introducing_command_options)

大多数终端命令都有选项——这些是您添加到命令末尾的修饰符，它们的行为方式略有不同。它们通常由命令名称后的空格、破折号和一个或多个字母组成。

例如，试一试，看看你会得到什么：

```
ls -l
```

复制到剪贴板

在 的情况下`ls`，`-l`( *dash ell* ) 选项为您提供一个列表，每行一个文件或目录，并显示更多信息。可以通过在行的最左侧查找字母“d”来识别目录。这些是我们可以`cd`进入的。

下面是一个屏幕截图，顶部是一个“vanilla”macOS 终端，还有一个定制的终端，带有一些额外的图标和颜色以使其看起来生动——两者都显示了运行的结果`ls -l`：

![一个 vanilla mac 终端和一个更丰富多彩的自定义 mac 终端，显示文件列表 - 运行 ls -l 命令的结果](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/mac-terminals-ls.png)

**注意：**要准确了解每个命令有哪些可用选项，您可以查看其[手册页](https://en.wikipedia.org/wiki/Man_page). 这是通过键入`man`命令，后跟要查找的命令的名称来完成的，例如`man ls`。这将在终端的默认文本文件查看器中打开手册页（例如，[`less`](https://en.wikipedia.org/wiki/Less_(Unix))在我的终端中），然后您应该能够使用箭头键或一些类似的机制滚动页面。手册页非常详细地列出了所有选项，开始时可能有点吓人，但至少您知道如果需要它就在那里。浏览完手册页后，您需要使用文本查看器的退出命令（"q" in `less`；如果不明显，您可能需要在网上搜索才能找到它）退出它。

**注意：**要同时运行具有多个选项的命令，通常可以将它们全部放在短划线字符后的单个字符串中，例如`ls -lah`, 或`ls -ltrh`。尝试查看`ls`手册页以了解这些额外选项的作用！

既然我们已经讨论了两个基本命令，请稍微浏览一下您的目录，看看您是否可以从一个地方导航到另一个地方。

### [创建、复制、移动、删除](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#creating_copying_moving_removing)

还有许多其他基本实用程序命令，您在使用终端时可能会经常使用它们。它们非常简单，因此我们不会像前一对那样详细地解释它们。

在您在某处创建的测试目录中尝试使用它们，这样您就不会意外删除任何重要的内容，使用以下示例命令作为指导：

- `mkdir`— 这会在您所在的当前目录中创建一个新目录，并在命令名称后使用您提供的名称。例如，`mkdir my-awesome-website`将创建一个名为`my-awesome-website`.
- `rmdir`— 删除命名目录，但前提是它为空。例如`rmdir my-awesome-website`将删除我们上面创建的目录。如果要删除非空目录（并删除其中包含的所有内容），则可以使用该`-r`选项（递归），但这很危险。确保以后目录中没有您可能需要的任何东西，因为它将永远消失。
- `touch`— 在当前目录中创建一个新的空文件。例如，`touch mdn-example.md`创建一个名为`mdn-example.md`.
- `mv`— 例如，将文件从第一个指定的文件位置移动到第二个指定的文件位置`mv mdn-example.md mdn-example.txt`（这些位置写为文件路径）。该命令将`mdn-example.md`当前目录中调用的文件移动到当前目录中调用的文件`mdn-example.txt`中。从技术上讲，文件正在被移动，但从实际角度来看，此命令实际上是重命名文件。
- `cp`-在使用类似的`mv`，`cp`创建指定的文件中的第一位置的副本，在指定的第二位置。例如，`cp mdn-example.txt mdn-example.txt.bak`创建一个`mdn-example.txt`被调用的副本`mdn-example.txt.bak`（如果你愿意，你当然可以称它为别的）。
- `rm`— 删除指定的文件。例如，`rm mdn-example.txt`删除一个名为`mdn-example.txt`. 请注意，此删除是永久性的，无法通过桌面用户界面上的回收站撤消。

**注意：**许多终端命令允许您使用星号作为“通配符”字符，意思是“任何字符序列”。这允许您一次对潜在的大量文件运行操作，所有这些文件都匹配指定的模式。例如，`rm mdn-*`将删除所有以`mdn-`. `rm mdn-*.bak`将删除所有`mdn-`以`.bak`.开头和结尾的文件。

## [终端——被认为是有害的？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#terminal_—_considered_harmful)

我们之前已经提到过这一点，但要清楚 - 您需要小心终端。简单的命令不会带来太大的危险，但是当您开始组合更复杂的命令时，您需要仔细考虑该命令的作用，并在最终在预期目录中运行它们之前先尝试对其进行测试。

假设您在一个目录中有 1000 个文本文件，并且您想遍历它们并且只删除文件名中包含特定子字符串的那些。如果您不小心，那么您最终可能会删除一些重要的内容，从而在此过程中丢失大量工作。养成的一个好习惯是在文本编辑器中编写终端命令，弄清楚您认为它应该是什么样子，然后备份您的目录并尝试先在该目录上运行该命令，以对其进行测试。

另一个很好的提示——如果你不习惯在自己的机器上尝试终端命令，一个安全的好地方就结束了 [Glitch.com](https://glitch.com/). 除了是试用 Web 开发代码的好地方外，这些项目还让您可以访问终端，因此您可以直接在该终端中运行所有这些命令，因为您不会破坏自己的机器。

![显示 glitch.com 主页和故障终端模拟器的双重屏幕截图](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/glitch.png)

快速了解特定终端命令的一个很好的资源是 [文件](https://tldr.sh/). 这是一个社区驱动的文档服务，类似于 MDN，但特定于终端命令。

在下一节中，让我们将其提升一个档次（或实际上是几个档次），看看我们如何在命令行上将工具连接在一起，以真正了解终端如何优于常规桌面用户界面。

## [用管道连接命令](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#connecting_commands_together_with_pipes)

当您开始使用`|`（管道）符号将命令链接在一起时，终端才真正发挥作用。让我们看一个非常简单的例子来说明这意味着什么。

我们已经看过了`ls`，它输出当前目录的内容：

```
ls
```

复制到剪贴板

但是如果我们想快速计算当前目录中的文件和目录的数量呢？`ls`不能独自做到这一点。

还有另一个可用的 Unix 工具，称为`wc`. 这会计算输入到其中的任何内容的字数、行数、字符数或字节数。这可以是一个文本文件——下面的例子输出 中的行数`myfile.txt`：

```
wc -l myfile.txt
```

复制到剪贴板

但它也可以计算通过**管道**输入的任何输出的行数。例如，下面的命令计算命令输出的行数`ls`（如果它自己运行，它通常会打印到终端）并将计数输出到终端：

```
ls | wc -l
```

复制到剪贴板

由于`ls`在自己的行上打印每个文件或目录，这有效地为我们提供了目录和文件计数。

那么这里发生了什么？(unix) 命令行工具的一般理念是它们将文本打印到终端（也称为“打印到标准输出”或`STDOUT`）。许多命令还可以从流输入（称为“标准输入”或`STDIN`）中读取内容。

管道操作符可以*将*这些输入和输出*连接*在一起，使我们能够构建越来越复杂的操作以满足我们的需求——一个命令的输出可以成为下一个命令的输入。在这种情况下，`ls`通常会将其输出打印到`STDOUT`，但是`ls`的输出正在通过管道传输到 中`wc`，它将该输出作为输入，计算它包含的行数，并将该计数打印到`STDOUT`。

## [一个稍微复杂的例子](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#a_slightly_more_complex_example)

让我们来看看更复杂的东西。

我们将首先尝试使用`curl`命令（可用于从 URL 请求内容）从`https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch`. 现在就试试：

```
curl https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch
```

复制到剪贴板

您不会得到输出，因为页面已被重定向（到[/Web/API/fetch](https://developer.mozilla.org/en-US/docs/Web/API/fetch)）。我们需要`curl`使用`-L`标志明确告诉跟随重定向。

让我们也看看这头`developer.mozilla.org`使用回报`curl`的`-I`标志，并通过管道输出打印所有位置重定向将其发送到终端，`curl`到`grep`（我们要求`grep`返回所有包含单词‘位置’的行）。

尝试运行以下命令（您会看到在我们到达最后一页之前只有一个重定向）：

```
curl https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch -L -I | grep location
```

复制到剪贴板

您的输出应如下所示（`curl`将首先输出一些下载计数器等）：

```
location: /en-US/docs/Web/API/fetch
```

复制到剪贴板

虽然人为设计，但我们可以更进一步地处理这个结果并转换`location:`行内容，将基本原点添加到每个内容的开头，以便我们打印出完整的 URL。为此，我们将添加`awk`到组合中（这是一种类似于 JavaScript 或 Ruby 或 Python 的编程语言，只是更老了！）。

尝试运行这个：

```
curl https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch -L -I | grep location | awk '{ print "https://developer.mozilla.org" $2 }'
```

复制到剪贴板

您的最终输出应如下所示：

```
https://developer.mozilla.org/en-US/docs/Web/API/fetch
```

复制到剪贴板

通过组合这些命令，我们自定义了输出以显示当我们请求`/docs/Web/API/WindowOrWorkerGlobalScope/fetch`URL时 Mozilla 服务器正在重定向的完整URL。了解您的系统将在未来几年证明是有用的——了解这些单一服务工具的工作原理以及它们如何成为您解决小众问题的工具的一部分。

## [添加通电](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#adding_powerups)

现在我们已经了解了系统自带的一些内置命令，让我们看看如何安装第三方 CLI 工具并使用它。

用于前端 Web 开发的可安装工具的庞大生态系统目前主要存在于内部 [新产品经理](https://www.npmjs.com/)，一种与 Node.js 密切合作的私有包托管服务。这正在缓慢扩展 - 随着时间的推移，您可以期望看到更多的软件包提供者。

[安装 Node.js](https://nodejs.org/en/)还安装了 npm 命令行工具（以及一个名为 npx 的补充性以 npm 为中心的工具），它提供了安装其他命令行工具的途径。Node.js 和 npm 在所有系统上的工作方式相同：macOS、Windows 和 Linux。

立即在您的系统上安装 npm，方法是转到上面的 URL 并下载并运行适合您的操作系统的 Node.js 安装程序。如果出现提示，请确保将 npm 作为安装的一部分。

![Windows 上的 node.js 安装程序，显示包含 npm 的选项](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line/npm-install-option.png)

尽管我们将在下一篇文章中介绍许多不同的工具，但我们将切入正题 [更漂亮](https://prettier.io/). Prettier 是一个固执的代码格式化程序，它有“很少的选择”。更少的选择往往意味着更简单。考虑到工具有时会在复杂性方面失控，“很少有选择”可能非常有吸引力。

### [在哪里安装我们的 CLI 工具？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#where_to_install_our_cli_tools)

在我们开始安装 Prettier 之前，有一个问题需要回答——“我们应该安装到哪里？”

随着`npm`我们在全球安装工具的选择-所以我们可以在任何地方访问它们-或本地到当前项目目录。

每种方式都有优点和缺点 - 全局安装的优点和缺点列表远非详尽无遗：

| 全局安装的优点           | 全局安装的缺点                                               |
| :----------------------- | :----------------------------------------------------------- |
| 可在终端中的任何位置访问 | 可能与您项目的代码库不兼容                                   |
| 只安装一次               | 您团队中的其他开发人员将无法访问这些工具，例如，如果您通过 git 等工具共享代码库。 |
| 使用更少的磁盘空间       | 与上一点相关，它使项目代码更难复制（如果您在本地安装工具，则可以将它们设置为依赖项并使用 安装`npm install`）。 |
| 总是一样的版本           |                                                              |
| 感觉像任何其他 unix 命令 |                                                              |

尽管*缺点*列表较短，但全局安装的负面影响可能远大于收益。但是，现在我们会在简单性方面犯错并全局安装以保持简单。我们将在下一篇文章中更多地了解本地安装以及它们为何如此出色。

### [安装 Prettier](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#installing_prettier)

在本文中，我们将安装 Prettier 作为全局命令行实用程序。

Prettier 是面向前端开发人员的固执的代码格式化工具，专注于基于 JavaScript 的语言并添加对 HTML、CSS、SCSS、JSON 等的支持。更漂亮可以：

- 节省在所有代码文件中手动保持样式一致的认知开销；Prettier 可以自动为您执行此操作。
- 帮助 Web 开发新手以最佳实践方式格式化他们的代码。
- 安装在任何操作系统上，甚至作为项目工具的直接组成部分，确保处理您的代码的同事和朋友使用您正在使用的代码风格。
- 配置为在保存时、在键入时甚至在发布代码之前运行（使用我们稍后将在模块中看到的其他工具）。

安装节点后，打开终端并运行以下命令来安装 Prettier：

```
npm install --global prettier
```

复制到剪贴板

命令完成运行后，Prettier 工具现在可以在您的终端中的文件系统中的任何位置使用。

与许多其他命令一样，不带任何参数运行该命令将提供用法和帮助信息。现在试试这个：

```
prettier
```

复制到剪贴板

您的输出应如下所示：

```
Usage: prettier [options] [file/glob ...]

By default, output is written to stdout.
Stdin is read if it is piped to Prettier and no files are given.

…
```

复制到剪贴板

至少浏览一下使用信息总是值得的，即使它很长。它将帮助您更好地了解该工具的用途。

### [玩漂亮的](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#playing_with_prettier)

让我们快速玩一下 Prettier，这样您就可以看到它是如何工作的。

首先，在文件系统的某个位置创建一个易于查找的新目录。也许是`prettier-test`在您的`Desktop`.

现在将以下代码保存在`index.js`测试目录中名为 的新文件中：

```
const myObj = {
a:1,b:{c:2}}
function printMe(obj){console.log(obj.b.c)}
printMe(myObj)
```

复制到剪贴板

我们可以针对代码库运行更漂亮的代码来检查我们的代码是否需要调整。`cd`进入您的目录，然后尝试运行以下命令：

```
prettier --check index.js
```

复制到剪贴板

您应该按照以下方式进行输出

```
Checking formatting...
index.js
Code style issues found in the above file(s). Forgot to run Prettier?
```

复制到剪贴板

所以有一些代码样式可以修复。没问题。将`--write`选项添加到更漂亮的命令将修复这些问题，让我们专注于实际编写有用的代码。

现在尝试运行这个版本的命令：

```
prettier --write index.js
```

复制到剪贴板

你会得到这样的输出

```
Checking formatting...
index.js
Code style issues fixed in the above file(s).
```

复制到剪贴板

但更重要的是，如果您回顾一下您的 JavaScript 文件，您会发现它已被重新格式化为如下所示：

```
const myObj = {
  a: 1,
  b: { c: 2 },
};
function printMe(obj) {
  console.log(obj.b.c);
}
printMe(myObj);
```

复制到剪贴板

根据您的工作流程（或您选择的工作流程），您可以将其作为流程的自动化部分。自动化确实是工具的优势所在；我们的个人偏好是那种“就发生”而无需配置任何东西的自动化。

使用 Prettier 可以通过多种方式实现自动化，虽然它们超出了本文的范围，但有一些优秀的在线资源可以提供帮助（其中一些已链接到）。您可以调用更漂亮的：

- 在使用以下命令将代码提交到 git 存储库之前 [沙哑](https://github.com/typicode/husky).
- 每当您在代码编辑器中点击“保存”时， [VS代码](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), [原子](https://atom.io/packages/prettier-atom)， 或者 [崇高的文字](https://packagecontrol.io/packages/JsPrettier).
- 作为持续集成检查的一部分，使用诸如 [Github 操作](https://github.com/features/actions).

我们的个人偏好是第二个——在使用 VS Code 时，每次我们点击保存时，Prettier 都会启动并清理它需要执行的任何格式。您可以在[更漂亮的文档](https://prettier.io/docs/en/).

## [其他可以玩的工具](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#other_tools_to_play_with)

如果您想尝试更多工具，这里有一个简短的列表，可以尝试一下：

- [`bat`](https://github.com/sharkdp/bat)— “更好” `cat`（`cat`用于打印文件的内容）。
- [`prettyping`](https://denilson.sa.nom.br/prettyping/)—`ping`在命令行上，但可视化（`ping`是检查服务器是否响应的有用工具）。
- [`htop`](https://hisham.hm/htop/) — 进程查看器，当某些事情使您的 CPU 风扇表现得像喷气发动机并且您想识别有问题的程序时非常有用。
- [`tldr`](https://tldr.sh/#installation) — 本章前面提到过，但可作为命令行工具使用。

请注意，上面的一些建议可能需要使用 npm 进行安装，就像我们在 Prettier 中所做的那样。

## [概括](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line#summary)

这使我们结束了对终端/命令行的简要介绍。接下来，我们将更详细地了解包管理器，以及我们可以用它们做什么。

# 包管理（Package management）

In this article we'll look at package managers in some detail to understand how we can use them in our own projects — to install project tool dependencies, keep them up-to-date, and more.

## [A dependency in your project](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#a_dependency_in_your_project)

A **dependency** is a third-party bit of software that was probably written by someone else and ideally solves a single problem for you. A web project can have any number of dependencies, ranging from none to many, and your dependencies might include sub-dependencies that you didn't explicitly install — your dependencies may have their own dependencies.

A simple example of a useful dependency that your project might need is some code to calculate relative dates as human-readable text. You could certainly code this yourself, but there's a strong chance that someone else has already solved this problem — why waste time reinventing the wheel? Moreover, a reliable third-party dependency will likely have been tested in a lot of different situations, making it more robust and cross-browser compatible than your own solution.

A project dependency can be an entire JavaScript library or framework — such as React or Vue — or a very small utility like our human-readable date library, or it can be a command line tool such as Prettier or eslint, which we talked about in previous articles.

Without modern build tools, dependencies like this might be included in your project using a simple [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element, but this might not work right out of the box and you will likely need some modern tooling to bundle your code and dependencies together when they are released on the web. A bundle is the term that’s generally used to refer to a single file on your web server that contains all the JavaScript for your software — typically compressed as much as possible to help reduce the time it takes to get your software downloaded and displayed in your visitors’ browser.

In addition, what happens if you find a better tool that you want to use instead of the current one, or a new version of your dependency is released that you want to update to? This is not too painful for a couple of dependencies, but in larger projects with many dependencies this kind of thing can become really challenging to keep track of. It makes more sense to use a **package manager** such as npm, as this will guarantee that the code is added and removed cleanly, as well as a host of other advantages.

## [What exactly is a package manager?](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#what_exactly_is_a_package_manager)

We've met [npm](https://www.npmjs.com/) already, but stepping back from npm itself, a package manager is a system that will manage your project dependencies.

The package manager will provide a method to install new dependencies (also referred to as "packages"), manage where packages are stored on your file system, and offer capabilities for you to publish your own packages.

In theory you may not need a package manager and you could manually download and store your project dependencies, but a package manager will seamlessly handle installing and uninstalling packages. If you didn't use one, you'd have to manually handle:

- Finding all the correct package JavaScript files.
- Checking them to make sure they don't have any known vulnerabilities.
- Downloading them and putting them in the correct locations in your project.
- Writing the code to include the package(s) in your application (this tends to be done using [JavaScript modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules), another subject that is worth reading up on and understanding).
- Doing the same thing for all of the packages' sub-dependencies, of which there could be tens, or hundreds.
- Removing all the files again if you want to remove the packages.

In addition, package managers handle duplicate dependencies (something that becomes important and common in front-end development).

In the case of npm (and JavaScript- and Node-based package managers) you have two options for where you install your dependencies. As we touched on in the previous article, dependencies can be installed globally or locally to your project. Although there tend to be more pros for installing globally, the pros for installing locally are more important — such as code portability and version locking.

For example, if your project relied on Webpack with a certain configuration, you'd want to ensure that if you installed that project on another machine or returned to it much later on, the configuration would still work. If a different version of Webpack was installed, it may not be compatible. To mitigate this dependencies are installed locally to a project.

To see local dependencies really shine, all you need to do is try to download and run an existing project — if it works and all the dependencies work right out of the box, then you have local dependencies to thank for the fact that the code is portable.

**Note:** npm is not the only package manager available. A successful and popular alternative package manager is [Yarn](https://yarnpkg.com/). Yarn resolves the dependencies using a different algorithm that can mean a faster user experience. There are also a number of other emerging clients, such as [pnpm](https://pnpm.js.org/).

## [Package registries](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#package_registries)

For a package manager to work, it needs to know where to install packages from, and this comes in the form of a package registry. The registry is a central place that a package is published to and thus can be installed from. npm, as well as being a package manager, is also the name of the most commonly-used package registry for JavaScript packages. The npm registry exists at [npmjs.com](https://www.npmjs.com/).

npm is not the only option. You could manage your own package registry — products like [Microsoft Azure](https://azure.microsoft.com/en-us/) allow you to create proxies to the npm registry (so you can override or lock certain packages), [GitHub also offers a package registry service](https://github.com/features/packages), and there will be likely more options appearing as time goes on.

What is important is that you ensure you've chosen the best registry for you. Many projects will use npm, and we’ll stick to this in our examples throughout the rest of the module.

## [Using the package ecosystem](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#using_the_package_ecosystem)

Let’s run through an example to get you started with using a package manager and registry to install a command line utility.

[Parcel](https://parceljs.org/) is a(nother) tool that developers commonly use in their development process. Parcel is clever in that it can watch the contents of our code for calls to dependencies and automatically installs any dependencies it sees that our code needs. It can also automatically build our code.

In our previous chapter we installed Prettier as a global tool. Here however, let’s use npm to install Parcel as a local tool, as best practices dictate. We'll install it as part of an experimental app.

### [Setting up the app as an npm package](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#setting_up_the_app_as_an_npm_package)

First of all, create a new directory to store our experimental app in, somewhere sensible that you’ll find again. We’ll call it parcel-experiment, but you can call it whatever you like:

```
mkdir parcel-experiment
cd parcel-experiment
```

Copy to Clipboard

Next, let's initialise our app as an npm package, which creates a config file — `package.json` — that allows us to save our configuration details in case we want to recreate this environment later on, or even publish the package to the npm registry (although this is somewhat beyond the scope of this article).

Type the following command, making sure you are inside the `parcel-experiment` directory:

```
npm init
```

Copy to Clipboard

You will now be asked some questions; npm will then create a default `package.json` file based on the answers:

- `name`: A name to identify the app. Just press Return to accept the default `parcel-experiment`.
- `version`: The starting version number for the app: Again, Just press Return to accept the default `1.0.0`.
- `description`: A quick description of the app's purpose. Type in something really simple, like "A simple npm package to learn about using npm", then press Return .
- `entry point`: This will be the top-level JavaScript file of the app. The default `index.js` is fine for now — press Return .
- `test command`, `git repository`, and `keywords`: press Return to leave each of these blank for now.
- `author`: The author of the project. Type your own name, and press Return .
- `license`: The license to publish the package under: Press Return to accept the default for now.

Press Return one more time to accept these settings.

Go into your `parcel-experiment` directory and you should now find you've got a package.json file. Open it up and it should look something like this:

```
{
  "name": "parcel-experiment",
  "version": "1.0.0",
  "description": "A simple npm package to learn about using npm",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Chris Mills",
  "license": "ISC"
}
```

Copy to Clipboard

So this is the config file that defines your package. This is good for now, so let's move on.

### [Installing parcel](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#installing_parcel)

Run the following command to install Parcel locally:

```
npm install parcel-bundler
```

Copy to Clipboard

Once that's done *All The Things*, we're now ready for some "modern client-side development" (which really means using build tools to make the developer experience a little easier). First of all however, take another look at your package.json file. You'll see that npm has added a new field, dependencies:

```
"dependencies": {
  "parcel-bundler": "^1.12.4"
}
```

Copy to Clipboard

This is part of the npm magic — if in future you move your codebase to another location, on another machine, you can recreate the same set up by running the command `npm install`, and npm will look at the dependencies and install them for you.

One disadvantage is that Parcel is only available inside our `parcel-experiment` app; you won't be able to run it in a different directory. But the advantages outweigh the disadvantages.

### [Setting up our example app](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#setting_up_our_example_app)

Anyway, on with the setup.

Parcel expects an `index.html` and an `index.js` file to work with, but otherwise it is very unopinionated about how you structure your project. Other tools can be very different, but at least Parcel makes it easy for our initial experiment.

So now we need to add an `index.html` file to our working directory. Create `index.html` in your test directory, and give it the following contents:

```
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <script src="./index.js"></script>
  </body>
</html>
```

Copy to Clipboard

Next, we need to add an `index.js` file in the same directory as `index.html`. For now `index.js` can be empty; it just needs to exist. Create this now.

### [Having fun with Parcel](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#having_fun_with_parcel)

Now we’ll run our newly installed Parcel tool. In your terminal, run the following command:

```
 parcel index.html
```

Copy to Clipboard

You should see something like this printed to your terminal:

```
Server running at http://localhost:1234
✨  Built in 193ms.
```

Copy to Clipboard

**Note:** If you have trouble with the terminal returning a "command not found" type error, try running the above command with the `npx` utility, i.e. `npx parcel index.html`.

Now we're ready to benefit from the full JavaScript package ecosystem. For a start, there is now a local web server running at `http://localhost:1234`. Go there now and you’ll not see anything for now, but what is cool is that when you do make changes to your app, Parcel will rebuild it and refresh the server automatically so you can instantly see the effect your update had.

Now for some page content. Let's say we want to show human-readable relative dates, such as "2 hours ago", "4 days ago" and so on. The [`date-fns`](https://date-fns.org/) package’s `formatDistanceToNow()` method is useful for this (there's other packages that do the same thing too).

In the `index.js` file, add the following code and save it:

```
import { formatDistanceToNow } from 'date-fns'

const date = '1996-09-13 10:00:00';
document.body.textContent = formatDistanceToNow(new Date(date)) + ' ago';
```

Copy to Clipboard

Go back to `http://localhost:1234` and you'll see how long ago it is since the author turned 18.

What's particularly special about the code above is that it is using the `formatDistanceToNow()` function from the `date-fns` package, which we didn’t install! Parcel has spotted that you need the module, searched for it in the `npmjs.com` package registry, and installed it locally for us, automatically. You can prove this by looking in our `package.json` file again — you'll see that the `dependencies` field have been updated for us:

```
"dependencies": {
  "date-fns": "^2.12.0",
  "parcel-bundler": "^1.12.4"
}
```

Copy to Clipboard

Parcel has also added the files required for someone else to pick up this project and install any dependencies that we’ve used. If you take a look in the directory you ran the `parcel` command in, you’ll find a number of new files; the most interesting of which are:

- `node_modules`: The dependency files of Parcel and date-fns.
- `dist`: The distribution directory — these are the automatically packaged, minified files Parcel has built for us, and the files it is serving at `localhost:1234`. These are the files you would upload to your web server when releasing the site online for public consumption.

So long as we know the package name, we can use it in our code and Parcel will go off, fetch, and install (actually "copy") the package into our local directory (under `node_modules`).

### [Building our code for production](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#building_our_code_for_production)

However, this code is not ready for production. Most build tooling systems will have a "development mode" and a "production mode". The important difference is that a lot of the helpful features you will use in development are not needed in the final site, so will be stripped out for production, e.g. "hot module replacement", "live reloading", and "uncompressed and commented source code". Though far from exhaustive, these are some of the common web development features that are very helpful at the development stage, but are not very useful in production. In production, they will just bloat your site.

Now stop the previous Parcel command (using Ctrl + C).

We can now prepare our bare bones example site for an imaginary deployment. Parcel provides an additional command to generate files that are suited to publication, making bundles (mentioned earlier) with the build option.

Run the following command:

```
parcel build index.html
```

Copy to Clipboard

You should see an output like so:

```
✨  Built in 9.35s.

dist/my-project.fb76efcf.js.map    648.58 KB     64ms
dist/my-project.fb76efcf.js        195.74 KB    8.43s
dist/index.html                        288 B    806ms
```

Copy to Clipboard

Again, the destination for our production files is the `dist` directory.

### [Reducing your app's file size](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#reducing_your_apps_file_size)

However, as with all tools that "help" developers there's often a trade off. In this particular case it's the file size. The JavaScript bundle my-project.fb76efcf.js is a whopping 195K — very large, given that all it does is print a line of text. Sure there's some calculation, but we definitely don’t need 195K worth of JavaScript to do this!.

When you use development tooling it's worth questioning whether they're doing the right thing for you. In this case, the bundle is nearly 200K because it has in fact included the entire `date-fns` library, not just the function we're using.

If we had avoided any development tools and pointed a `<script src=””>` element to a hosted version of `date-fns`, roughly the same thing would have happened — all of the library would be downloaded when our example page is loaded in a browser.

However, this is where development tooling has a chance to shine. Whilst the tooling is on our machine, we can ask the software to inspect our use of the code and only include the functions that we're actually using in production — a process known as "Tree Shaking".

This makes a lot of sense as we want to reduce file size and thus make our app load as quickly as possible. Different tooling will let you tree shake in different ways.

Although the list grows by the month, there are three main offerings for tools that generate bundles from our source code: Webpack, [Rollup](https://rollupjs.org/guide/en/), and Parcel. There will be more available than this, but these are popular ones:

- The RollUp tool offers tree shaking and code splitting as its core features.
- Webpack requires some configuration (though “some” might be understating the complexity of some developers’ Webpack configurations).
- In the case of Parcel (prior to Parcel version 2), there's a special flag required — `--experimental-scope-hoisting` — which will tree shake while building.

Let’s stick with Parcel for now, given that we’ve already got it installed. Try running the following command:

```
parcel build index.html --experimental-scope-hoisting
```

Copy to Clipboard

You’ll see that this makes a huge difference:

```
✨  Built in 7.87s.

dist/my-project.86f8a5fc.js    10.34 KB    7.17s
dist/index.html                   288 B    753ms
```

Copy to Clipboard

Now the bundle is approximately 10K. Much better.

If we were to release this project to a server, we would only release the files in the `dist` folder. Parcel has automatically handled all the filename changes for us. We would recommend having a look at the source code in `dist/index.html` just so you can see what changes Parcel has performed automatically.

**Note:** At time of writing, Parcel 2 had not been released. However when it does, these commands will all still work because the authors of Parcel have had the good sense to name the tool slightly differently. To install Parcel 1.x you have to install `parcel-bundler`, but parcel 2.x is called `parcel`.

There's a lot of tools available and the JavaScript package ecosystem is growing at an unprecedented rate, which has pros and cons. There's improvements being made all the time and the choice, for better or worse, is constantly increasing. Faced with the overwhelming choice of tooling, probably the most important lesson is to learn what the tool you select is capable of.

## [A rough guide to package manager clients](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#a_rough_guide_to_package_manager_clients)

This tutorial installed the Parcel package using npm, but as mentioned earlier on there are some alternatives and it's worth at least knowing they exist and having some vague idea of the common commands across the tools. You've already seen some in action, but lets look at the others.

The list will grow over time, but at time of writing, the following main package managers are available:

- npm at [npmjs.org](https://www.npmjs.com/)
- pnpm at [pnpm.js.org](https://pnpm.js.org/)
- yarn at [yarnpkg.com](https://yarnpkg.com/)

npm and pnpm are similar from a command line point of view — in fact pnpm aims to have full parity over the argument options that npm offers. It differs in that it uses a different method for downloading and storing the packages on your computer, aiming to reduce the overall disk space required.

Where npm is shown in the examples below, pnpm can be swapped in and the command will work.

yarn is often thought to be quicker than npm in terms of installation process (though your mileage may vary). This is important to developers because there can be a significant amount of time wasted on waiting for dependencies to install (and copy to the computer).

**Note:** The npm package manager is **not** required to install packages from the npm registry, even though they share the same name. pnpm and yarn can consume the same `package.json` format as npm, and can install any package from the npm and other package registries.

Let’s review the common actions you’ll want to perform with package managers.

### [Initialise a new project](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#initialise_a_new_project)

```
npm init
yarn init
```

Copy to Clipboard

As shown above, this will prompt and walk you through a series of questions to describe your project (name, license, description and so on) then generate a `package.json` for you that contains meta information about your project and its dependencies.

### [Installing dependencies](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#installing_dependencies)

```
npm install date-fns
yarn add date-fns
```

Copy to Clipboard

We also saw `install` in action above. This would directly add the `date-fns` package to the working directory in a sub-directory called `node_modules`, along with `date-fns`’s own dependencies.

By default this command will install the latest version of `date-fns`, but you can control this too. You can ask for `date-fns@1`, which gives you the latest 1.x version (which is 1.30.1). Or you could try `date-fns@^2.3.0`, which means the latest version after or including 2.3.0 (2.8.1 at the time of writing).

### [Updating dependencies](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#updating_dependencies)

```
npm update
yarn upgrade
```

Copy to Clipboard

This will look at the currently installed dependencies and update them, if there is an update available, within the range that's specified in the package.

The range is specified in the version of the dependency in your `package.json`, such as `date-fns@^2.0.1` — in this case the caret character `^` means all minor and patch releases after and including 2.0.1, up to but excluding 3.0.0.

This is determined using a system called [semver](https://semver.org/), which might look a bit complicated from the documentation but can be simplified by considering only the summary information and that a version is represented by `MAJOR.MINOR.PATCH`, such as 2.0.1 being major version 2 with patch version 1. An excellent way to try out semver values is to use the [semver calculator](https://semver.npmjs.com/).

It's important to remember that `npm update` will not upgrade the dependencies to beyond the range defined in the `package.json` — to do this you will need to install that version specifically.

### [Audit for vulnerabilities](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#audit_for_vulnerabilities)

```
npm audit
yarn audit
```

Copy to Clipboard

This will check all of the dependency tree for your project and run the specific versions you're using against a vulnerability database and notify you if there are potential vulnerable packages in your project.

A good starting point for learning about vulnerabilities is the [Snyk project](https://snyk.io/), which covers both JavaScript packages and other programming languages.

### [Checking on a dependency](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#checking_on_a_dependency)

```
npm ls date-fns
yarn why date-fns
```

Copy to Clipboard

This command will show what version of a dependency is installed and how it came to be included in your project. It's possible that another, top level, package could have pulled in `date-fns`. It's equally possible (and not ideal) that you have multiple versions of a package in your project (this has been seen many times over with the [lodash](https://lodash.com/) package, as it's so useful).

Although the package manager will do it’s best to deduplicate packages you may want to investigate exactly which version is installed.

### [More commands](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#more_commands)

You can find out more about the individual commands for [npm](https://docs.npmjs.com/cli-documentation/) and [yarn](https://yarnpkg.com/en/docs/cli/) online. Again, [pnpm](https://pnpm.js.org/en/cli/add) commands will have parity with npm, with a handful of additions.

## [Making your own commands](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#making_your_own_commands)

The package managers also support creating your own commands and executing them from the command line. For instance, we could create the following command:

```
npm run dev
# or yarn run dev
```

Copy to Clipboard

This would run a custom script for starting our project in “development mode”. In fact, we regularly include this in all projects as the local development setup tends to run slightly differently to how it would run in production.

If you tried running this in your Parcel test project from earlier it would (likely) claim the “dev script is missing”. This is because npm, yarn (and the like) are looking for a property called dev in the `scripts` property of your `package.json` file.

Parcel can run a development server using the command `parcel serve filename.html`, and we’d like to use that often during our development.

So let’s create a custom shorthand command — “dev” — in our `package.json`.

If you followed the tutorial from earlier, you should have a `package.json` file inside your parcel-experiment directory. Open it up, and its `scripts` member should look like this:

```
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
},
```

Copy to Clipboard

Update it so that it looks like this, and save the file:

```
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "dev": "parcel serve index.html"
},
```

Copy to Clipboard

We’ve added a custom `dev` command as an npm script.

Now try running the following in your terminal, making sure you are inside the `parcel-experiment` directory:

```
 npm run dev
```

Copy to Clipboard

This should start Parcel and serve up your `index.html` at the local development server, as we saw before:

```
Server running at http://localhost:1234
✨  Built in 5.48s.
```

Copy to Clipboard

In addition, the npm (and yarn) commands are clever in that they will search for command line tools that are locally installed to the project before trying to find them through conventional methods (where your computer will normally store and allow software to be found). You can [learn more about the technical intricacies of the `run` command](https://docs.npmjs.com/cli/run-script), although in most cases your own scripts will run just fine.

You can add all kinds of things to the `scripts` property that help you do your job. We certainly have, and [others have too](https://github.com/facebook/create-react-app/blob/c5b96c2853671baa3f1f297ec3b36d7358898304/package.json#L6).

## [Summary](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management#summary)

This brings us to the end of our tour of package managers. Our next move is to build up a sample toolchain, putting all that we've learnt so far into practice.

# 完整工具链的例子

​       https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Introducing_complete_toolchain

# 部署App

https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Deployment

# 客户端框架介绍

在本章节我们开始大致了解框架, 简要回顾JavaScript和框架的历史,为什么框架会存在以及它们提供了什么, 如何开始考虑选择一个框架并学习, 以及对于客户端框架还有什么替代方案.

## [简史](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#简史)

当JavaScript在1996被发布后, 它给网络增加了少许的交互性和乐趣, 直到那时, 网页仍由静态文档组成. 网络应该不仅仅是阅读,更是创造的地方. 随着JavaScript的流行. 使用JavaScript的开发者们创造工具来解决他们遇到的问题, 并且将其打包成称为**库**的可复用组件, 这样就能和他人共享解决方案. 这种共享库的体系帮助塑造了网络的增长.

现在, JavaScript是网络的基本部分, [used on 95% of all websites](https://w3techs.com/technologies/details/cp-javascript), 而且网络又是现代生活的基本部分. 用户在网络上写文章, 管理预算, 听音乐, 看电影, 以及和相隔万里的人通过文字, 音频, 视频聊天来瞬时交流. 网络让我们能够做到那些过去只能在电脑上安装本地应用程序才能做到的事. 这些现代的, 复杂的, 具有交互性的网站通常被称为 **网络应用程序**.

现代JavaScript框架的到来加快了打造高度动态化和交互性强的应用程序的速度. **框架** 就是提供该如何构建应用程序的意见的库。这些意见能使应用具有可预测性和同质性。可预测性让软件能在扩展到很大规模的同时仍保持可维护性。可预测性和可维护性对于一个软件的长久健康运行是十分重要的。

在现代网络中，JavaScript框架为众多令人印象深刻的软件提供支持——包括许多你可能每天都使用的网站。你正在阅读的这个MDN Web 文档页面, 就是使用React / ReactDOM框架为其前端提供动力。

## [有哪些框架?](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#有哪些框架)

有很多框架可供你选择，但以下主要介绍目前公认的“四大框架”。

### [Ember](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#ember)

[Ember](https://emberjs.com/)于2011年12月发布，最初作为[SproutCore](https://en.wikipedia.org/wiki/SproutCore)项目的延续而开始。比其新式的替代品（例如React和Vue），作为老框架它的用户人数要少得多。但因其稳定性、社区支持以及一些明智的编程原则，它仍然享有很高的知名度。

### [Angular](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#angular)

[Angular ](https://angular.io/)是一个开源 Web 应用程序框架，正式发布于2016年9月14日。它由构建[AngularJS](https://angularjs.org/) 的团队完全重写，并由 Google 的 Angular 团队以及个人和公司社区共同领导。

Angular 是一种基于组件的框架，使用声明式的HTML模板。在应用构建时，框架的编译器将 HTML 模板转换为优化好的 JavaScript 指令，这一过程对开发者是透明的。Angular 使用 TypeScript，它是 JavaScript 的超集，我们将在下一章中对其进行更多介绍。

### [Vue](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#vue)

在工作和学习了 [AngularJS](https://angularjs.org/) 的源码之后，Evan You （尤雨溪） 在2014年第一次发布 [Vue](https://vuejs.org/) 。Vue 是“四大框架”中最年轻的，但在最近，它的人气迅速上升。

Vue，就像 [AngularJS](https://angularjs.org/)，用它自己的代码拓展了 HTML。除此之外，它完全依赖于现代的、标准化的 JavaScript。

### [React](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#react)

Facebook 在 2013 发布了 React。在当时 React 已经被Facebook内部用来解决许多问题。 严格来说 React 本身并不是框架，而是一个用来渲染UI 组件的库。 React 被用来组合*其它*用来构建应用的库 —— React 和 [React Native](https://reactnative.dev/) 让开发者能够用 JavaScript 构建移动应用； React 和 [ReactDOM](https://reactjs.org/docs/react-dom.html) 使他们能够被用来制作 web 应用程序等。

因为 React 和 ReactDOM 被经常放在一起使用，通俗地讲，React 可以被理解为是一个 JavaScript 框架。当你通读了这个模块时，我们将使用这种口语化的理解进行工作。

React 用类似 HTML 的语法的 [JSX](https://reactjs.org/docs/introducing-jsx.html) 拓展了 JavaScript。

## [框架为何会存在?](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#框架为何会存在)

我们已经讨论了因为什么契机而创造了框架，但我们仍不知道为什么开发者认为有必要创造它。要知道这个问题的答案，我们首先需要检查软件开发中的各种挑战。

设想一个很常见的软件：一个To-Do清单创建器，在接下来的章节中我们会使用各种框架来实现它。这个应用应让用户可以完成诸如呈现任务列表、添加和删除任务等操作，且在完成这些操作的同时能可靠地跟踪和更新应用程序的底层数据。在软件开发中，这种底层数据被称为状态。

上述每个目标理论上都很简单。我们可以遍历数据来列出清单，添加一个对象来创建新任务，使用标识符来查找、编辑和删除任务。需要注意的是，用户都是在浏览器中使用应用的这些功能，然而这就引出了一些问题： **每当我们修改应用的数据时，我们都需要更新用户界面以使其匹配。** 

我们可以通过To-Do应用的一个功能来检验这个问题的难点：呈现任务清单。

## [冗长的DOM操作](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#冗长的dom操作)

Building HTML elements and rendering them in the browser at the appropriate time takes a surprising amount of code. Let's say that our state is an array of objects structured like this:

```
const state = [
  {
    id: 'todo-0',
    name: 'Learn some frameworks!'
  }
]
```

Copy to Clipboard

How do we show one of those tasks to our user? We want to represent each task as a list item – an HTML `<li>` element inside of an unordered list element (a `<ul>`). How do we make it? That could look something like this:

```
function buildTodoItemEl(id, name) {
  const item = document.createElement('li');
  const span = document.createElement('span');
  const textContent = document.createTextNode(name);

  span.appendChild(textContent)

  item.id = id;
  item.appendChild(span);
  item.appendChild(buildDeleteButtonEl(id));

  return item;
}
```

Copy to Clipboard

Here, we use the `document.createElement()` method to make our `<li>`, and several more lines of code to create the properties and children it needs.

The tenth line of this snippet references another build function: `buildDeleteButtonEl()`. It follows a similar pattern to the one we used to build a list item element:

```
function buildDeleteButtonEl(id) {
  const button = document.createElement('button');
  const textContent = document.createTextNode('Delete');

  button.setAttribute('type', 'button');
  button.appendChild(textContent);

  return button;
}
```

Copy to Clipboard

This button doesn't do anything yet, but it will later once we decide to implement our delete feature. The code that will render our items on the page might read something like this:

```
function renderTodoList() {
  const frag = document.createDocumentFragment();
  state.tasks.forEach(task => {
    const item = buildTodoItemEl(task.id, task.name);
    frag.appendChild(item);
  });

  while (todoListEl.firstChild) {
    todoListEl.removeChild(todoListEl.firstChild);
  }
  todoListEl.appendChild(frag);
}
```

Copy to Clipboard

We've now got well over thirty lines of code dedicated *just* to the UI – *just* to the step of rendering something in the DOM – and at no point do we add classes that we could use later to style our list-items!

Working directly with the DOM, as in this example, requires understanding many things about how the DOM works: how to make elements; how to change their properties; how to put elements inside of each other; how to get them on the page. None of this code actually handles user interactions, or addresses adding or deleting a task. If we add those features, we have to remember to update our UI in the right time and in the right way.

JavaScript frameworks were created to make this kind of work a little easier — they exist to provide a better *developer experience*. They don't bring brand-new powers to JavaScript; they give you easier access to JavaScript's powers so you can build for today's web.

If you want to see code samples from this section in action, you can check out a [working version of the app on CodePen](https://codepen.io/dengeist/pen/XWbPNmw), which also allows users to add and delete new tasks.

Read more about the JavaScript used in this section:

- `document.createElement()`
- `document.createTextNode()`
- `document.createDocumentFragment()`
- `eventTarget.addEventListener()`
- `node.appendChild()`
- `node.removeChild()`

## [另一种打造UIs的方式](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#另一种打造uis的方式)

Every JavaScript framework offers a way to write user interfaces more *declaratively*. That is, they allow you to write code that describes how your UI should look, and the framework makes it happen in the DOM behind the scenes.

The vanilla JavaScript approach to building out new DOM elements in repetition was difficult to understand at a glance. By contrast, the following block of code illustrates the way you might use Vue to describe our list of tasks:

```
<ul>
  <li v-for="task in tasks" v-bind:key="task.id">
    <span>{{task.name}}</span>
    <button type="button">Delete</button>
  </li>
</ul>
```

Copy to Clipboard

That's it. This snippet reduces approximately thirty-two lines of code down to six lines. If the curly braces and `v-` attributes here are unfamiliar to you, that's okay; you’ll learn about Vue-specific syntax later on in the module. The thing to take away here is that this code looks like the UI it represents, whereas the vanilla JavaScript code does not.

Thanks to Vue, we didn't have to write our own functions for building the UI; the framework will handle that for us in an optimized, efficient way. Our only role here was to describe to Vue what each item should look like. Developers who are familiar with Vue can join our project and quickly work out what is going on. Vue is not alone in this: using a framework improves team as well as individual efficiency.

It's possible to do things *similar* to this in vanilla JavaScript. [Template literal strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) make it easy to write strings of HTML that represent what the final element would look like. That might be a useful idea for something as simple as our to-do list application, but it's not maintainable for large applications that manage thousands of records of data, and could render just as many unique elements in a user interface.

## [框架提供给我们的其他功能](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#框架提供给我们的其他功能)

Let's look at some of the other advantages conferred upon us by frameworks. As we've alluded to before, the advantages of frameworks are achievable in vanilla JavaScript, but using a framework takes away all of the cognitive load of having to solve these problems yourself.

### [Tooling](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#tooling)

Because each of the frameworks in this module have a large, active community, each framework's ecosystem provides tooling that Improves the developer experience. These tools make it easy to add things like testing (to ensure that your application behaves as it should) or linting (to ensure that your code is error-free and stylistically consistent).

**Note**: If you want to find out more details about web tooling concepts, have a read of our [Client-side tooling overview](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview).

### [Compartmentalization](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#compartmentalization)

Most major frameworks encourage developers to abstract the different parts of their user interfaces into *components* — maintainable, reusable chunks of code that can communicate with one another. All the code related to a given component can live in one file (or a couple of specific files), so that you as a developer know exactly where to go to make changes to that component. In a vanilla JavaScript app, you'd have to create your own set of conventions to achieve this in an efficient, scalable way. Many JavaScript developers, if left to their own devices, could end up with all the code related to one part of the UI being spread out all over a file — or in another file altogether.

### [Routing](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#routing)

The most essential feature of the web is that it allows users to navigate from one page to another – it is, after all, a network of interlinked documents. When you follow a link on this very website, your browser communicates with a server and fetches new content to display for you. As it does so, the URL in your address bar changes. You can save this new URL and come back to the page later on, or share it with others so they can easily find the same page. Your browser remembers your navigation history and allows you to navigate back and forth, too. This is called **server-side routing**.

Modern web applications typically do not fetch and render new HTML files — they load a single HTML shell, and continually update the DOM inside it (referred to as **single page apps**, or **SPAs**) without navigating users to new addresses on the web. Each new pseudo-webpage is usually called a *view*, and by default, no routing is done.

When an SPA is complex enough, and renders enough unique views, it's important to bring routing functionality into your application. People are used to being able to link to specific pages in an application, travel forward and backward in their navigation history, etc., and their experience suffers when these standard web features are broken. When routing is handled by a client application in this fashion, it is aptly called **client-side routing**.

It's *possible* to make a router using the native capabilities of JavaScript and the browser, but popular, actively developed frameworks have companion libraries that make routing a more intuitive part of the development process.

## [使用框架的注意事项](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#使用框架的注意事项)

Being an effective web developer means using the most appropriate tools for the job. JavaScript frameworks make front-end application development easy, but they are not a silver bullet that will solve all problems. This section talks about some of the things you should consider when using frameworks. Bear in mind that you might not need a framework at all — beware that you don't end up using a framework just for the sake of it.

### [Familiarity with the tool](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#familiarity_with_the_tool)

Just like vanilla JavaScript, frameworks take time to learn and have their quirks. Before you decide to use a framework for a project, be sure you have time to learn enough of its features for it to be useful to you rather than it working against you, and be sure that your teammates are comfortable with it as well.

### [Overengineering](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#overengineering)

If your web development project is a personal portfolio with a few pages, and those pages have little or no interactive capability, a framework (and all of its JavaScript) may not be necessary at all. That said, frameworks are not a monolith, and some of them are better-suited to small projects than others. In an article for Smashing Magazine, Sarah Drasner writes about how [Vue can replace jQuery](https://www.smashingmagazine.com/2018/02/jquery-vue-javascript/) as a tool for making small portions of a webpage interactive.

### [Larger code base and abstraction](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#larger_code_base_and_abstraction)

Frameworks allow you to write more declarative code – and sometimes *less* code overall – by dealing with the DOM interactions for you, behind the scenes. This abstraction is great for your experience as a developer, but it isn't free. In order to translate what you write into DOM changes, frameworks have to run their own code, which in turn makes your final piece of software larger and more computationally expensive to operate.

Some extra code is inevitable, and a framework that supports tree-shaking (removal of any code that isn't actually used in the app during the build process) will allow you to keep your applications small, but this is still a factor you need to keep in mind when considering your app's performance, especially on more network/storage-constrained devices, like mobile phones.

The abstraction of frameworks affects not only your JavaScript, but your relationship with the very nature of the web. No matter how you build for the web, the end result, the layer that your users ultimately interact with, is HTML. Writing your whole application in JavaScript can make you lose sight of HTML and the purpose of its various tags, and lead you to produce an HTML document that is un-semantic and inaccessible. In fact, it's possible to write a fragile application that depends entirely on JavaScript and will not function without it.

Frameworks are not the source of our problems. With the wrong priorities, it's possible for *any* application to be fragile, bloated, and inaccessible. Frameworks do, however, amplify our priorities as developers. If your priority is to make a complex web app, it's easy to do that. However, if your priorities don't carefully guard performance and accessibility, frameworks will amplify your fragility, your bloat, and your inaccessibility. Modern developer priorities, amplified by frameworks, have inverted the structure of the web in many places. Instead of a robust, content-first network of documents, the web now often puts JavaScript first and user experience last.

## [框架驱动页面的可访问性](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#框架驱动页面的可访问性)

Let's build on what we said in the previous section, and talk a bit more about accessibility. Making user interfaces accessible always requires some thought and effort, and frameworks can complicate that process. You often have to employ advanced framework APIs to access native browser features like ARIA [live regions](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions) or focus management.

In some cases, framework applications create accessibility barriers that do not exist for traditional websites. The biggest example of this is in client-side routing, as mentioned earlier.

With traditional (server-side) routing, navigating the web has predictable results. The browser knows to set focus to the top of the page and assistive technologies will announce the title of the page. These things happen every time you navigate to a new page.

With client-side routing, your browser is not loading new web pages, so it doesn't know that it should automatically adjust focus or announce a new page title. Framework authors have devoted immense time and labor to writing JavaScript that recreates these features, and even then, no framework has done so perfectly.

The upshot is that you should consider accessibility from the very start of *every* web project, but bear in mind that abstracted codebases that use frameworks are more likely to suffer from major accessibility issues if you don't.

## [如何选择一个框架](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#如何选择一个框架)

Each of the frameworks discussed in this module take different approaches to web application development. Each is regularly improving or changing, and each has its pros and cons. Choosing the right framework is a team- and project-dependent process, and you should do your own research to uncover what suits your needs. That said, we've identified a few questions you can ask in order to research your options more effectively:

1. What browsers does the framework support?
2. What domain-specific languages does the framework utilize?
3. Does the framework have a strong community and good docs (and other support) available?

The table in this section provides a glanceable summary of the current *browser support* offered by each framework, as well as the **domain-specific languages** with which it can be used.

Broadly, domain-specific languages (**DSLs**) are programming languages relevant in specific areas of software development. In the context of frameworks, DSLs are variations on JavaScript or HTML that make it easier to develop with that framework. Crucially, none of the frameworks *require* a developer to use a specific DSL, but they have almost all been designed with a specific DSL in mind. Choosing not to employ a framework’s preferred DSL will mean you miss out on features that would otherwise improve your developer experience.

You should seriously consider the support matrix and DSLs of a framework when making a choice for any new project. Mismatched browser support can be a barrier to your users; mismatched DSL support can be a barrier to you and your teammates.

| Framework | Browser support                     | Preferred DSL | Supported DSLs         |
| :-------- | :---------------------------------- | :------------ | :--------------------- |
| Angular   | IE9+                                | TypeScript    | HTML-based; TypeScript |
| React     | Modern (IE9+ with Polyfills)        | JSX           | JSX; TypeScript        |
| Vue       | IE9+                                | HTML-based    | HTML-based, JSX, Pug   |
| Ember     | Modern (IE9+ in Ember version 2.18) | Handlebars    | Handlebars, TypeScript |

**Note**: DSLs we've described as "HTML-based" do not have official names. They are not really true DSLs, but they are non-standard HTML, so we believe they are worth highlighting.

Citations for this table:

- [React browser support: official docs](https://reactjs.org/docs/react-dom.html#browser-support)
- [Ember browser support: Ember 3.0 release announcement](https://blog.emberjs.com/2018/02/14/ember-3-0-released.html)
- [Ember templating language (official docs)](https://guides.emberjs.com/v3.3.0/templates/handlebars-basics/)

### [Does the framework have a strong community?](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#does_the_framework_have_a_strong_community)

This is perhaps the hardest metric to measure, because community size does not correlate directly to easy-to-access numbers. You can check a project's number of GitHub stars or weekly npm downloads to get an idea of its popularity, but sometimes the best thing to do is search a few forums or talk to other developers. It is not just about the community's size, but also how welcoming and inclusive it is, and how good available documentation is.

### [Opinions on the web](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#opinions_on_the_web)

Don't just take our word on this matter — there are discussions all over the web. The Wikimedia Foundation recently chose to use Vue for its front-end, and posted a [request for comments (RFC) on framework adoption](https://phabricator.wikimedia.org/T241180). Eric Gardner, the author of the RFC, took time to outline the needs of the Wikimedia project and why certain frameworks were good choices for the team. This RFC serves as a great example of the kind of research you should do for yourself when planning to use a front-end framework.

The [State of JavaScript survey](https://stateofjs.com/) is a helpful collection of feedback from JavaScript developers. It covers many topics related to JavaScript, including data about both the use of frameworks and developer sentiment toward them. Currently, there are several years of data available, allowing you to get a sense of a framework's popularity.

The Vue team has [exhaustively compared Vue to other popular frameworks](https://vuejs.org/v2/guide/comparison.html). There may be some bias in this comparison (which they note), but it's a valuable resource nonetheless.

## [客户端框架的替代方案](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#客户端框架的替代方案)

If you’re looking for tools to expedite the web development process, and you know your project isn’t going to require intensive client-side JavaScript, you could reach for one of a handful of other solutions for building the web:

- A content management system
- Server-side rendering
- A static site generator

### [Content management systems](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#content_management_systems)

**Content-management systems** (**CMSes**) are any tools that allow a user to create content for the web without directly writing code themselves. They're a good solution for large projects, especially projects that require input from content writers who have limited coding ability, or for programmers who want to save time. They do, however, require a significant amount of time to set up, and utilizing a CMS means that you surrender at least some measure of control over the final output of your website. For example: if your chosen CMS doesn't author accessible content by default, it's often difficult to improve this.

Popular examples include [Wordpress](https://wordpress.com/), [Joomla](https://www.joomla.org/), and [Drupal](https://www.drupal.org/).

### [Server-side rendering](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#server-side_rendering)

**Server-side rendering** (**SSR**) is an application architecture in which it is the *server'*s job to render a single-page application. This is the opposite of *client-side rendering*, which is the most common and most straightforward way to build a JavaScript application. Server-side rendering is easier on the client's device, because you're only sending a rendered HTML file to them, but it can be difficult to set up compared to a client-side-rendered application.

All of the frameworks covered in this module support server-side rendering as well as client-side rendering. Check out [Next.js](https://nextjs.org/) for React, [Nuxt.js](https://nuxtjs.org/) for Vue (yes it is confusing, and no, these projects are not related!), [FastBoot](https://github.com/ember-fastboot/ember-cli-fastboot) for Ember, and [Angular Universal](https://angular.io/guide/universal) for Angular.

**Note**: Some SSR solutions are written and maintained by the community, whereas some are "official" solutions provided by the framework's maintainer.

### [Static site generators](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#static_site_generators)

Static site generators are programs that dynamically generate all the webpages of a multi-page website — including any relevant CSS or JavaScript — so that they can be published in any number of places. The publishing host could be a GitHub pages branch, a Netlify instance, or any private server of your choosing, for example. There are a number of advantages of this approach, mostly around performance (your user's device isn’t building the page with JavaScript; it's already complete) and security (static pages have fewer attack vectors). These sites can still utilize JavaScript where they need to, but they are not *dependent* upon it. Static site generators take time to learn, just like any other tool, which can be a barrier to your development process.

Static sites can have as few or as many unique pages as you want. Just as frameworks empower you to quickly write client-side JavaScript applications, static site generators allow you a way to quickly create HTML files you would otherwise have written individually. Like frameworks, static site generators allow developers to write components that define common pieces of your web pages, and to compose those components together to create a final page. In the context of static site generators, these components are called **templates**. Web pages built by static site generators can even be home to framework applications: if you want one specific page of your statically-generated website to boot up a React application when your user visits it for example, you can do that.

Static site generators have been around for quite a long time, but they have seen a bit of a revival in the recent history of the web. A handful of powerful options are now available, such as [Hugo](https://gohugo.io/), [Jekyll](https://jekyllrb.com/), [Eleventy](https://www.11ty.dev/), and [Gatsby](https://www.gatsbyjs.org/).

If you'd like to learn more about static site generators on the whole, check out Tatiana Mac's [Beginner's guide to Eleventy](https://tatianamac.com/posts/beginner-eleventy-tutorial-parti/). In the first article of the series, she explains what a static site generator is, and how it relates to other means of publishing web content.

## [总结](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#总结)

And that brings us to the end of our introduction to frameworks — we’ve not taught you any code yet, but hopefully we've given you a useful background on why you'd use frameworks in the first place and how to go about choosing one, and made you excited to learn more and get stuck in!

Our next article goes down to a lower level, looking at the specific kinds of features frameworks tend to offer, and why they work like they do.



- [Overview: Client-side JavaScript frameworks](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks)
- [下一页](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features)



## [In this module](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#in_this_module)

- [Introduction to client-side frameworks](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction)
- [Framework main features](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features)
- React
  - [Getting started with React](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started)
  - [Beginning our React todo list](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning)
  - [Componentizing our React app](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components)
  - [React interactivity: Events and state](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state)
  - [React interactivity: Editing, filtering, conditional rendering](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering)
  - [Accessibility in React](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility)
  - [React resources](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources)
- Ember
  - [Getting started with Ember](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_getting_started)
  - [Ember app structure and componentization](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_structure_componentization)
  - [Ember interactivity: Events, classes and state](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_interactivity_events_state)
  - [Ember Interactivity: Footer functionality, conditional rendering](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_conditional_footer)
  - [Routing in Ember](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_routing)
  - [Ember resources and troubleshooting](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Ember_resources)
- Vue
  - [Getting started with Vue](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_getting_started)
  - [Creating our first Vue component](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_first_component)
  - [Rendering a list of Vue components](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_rendering_lists)
  - [Adding a new todo form: Vue events, methods, and models](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_methods_events_models)
  - [Styling Vue components with CSS](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_styling)
  - [Using Vue computed properties](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_computed_properties)
  - [Vue conditional rendering: editing existing todos](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_conditional_rendering)
  - [Focus management with Vue refs](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_refs_focus_management)
  - [Vue resources](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_resources)

# 框架的主要特性

- [上一页](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction)
- [概述：客户端 JavaScript 框架](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks)
- [下一页](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started)

一起更新JavaScript框架自己不同的方式，处理浏览器事件，为开发者提供愉快的使用体验，这篇文章将探索“四大”框架的主要特性，从高级视角探讨框架的工作方式以及他们之间的区别。

| 先决条件： | 熟悉核心语言的 [HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML)、[CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS) 和 [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript)。 |
| :--------- | ------------------------------------------------------------ |
| 目标：     | 了解框架主要代码的特性。                                     |

## [Domain-specific languages](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#domain-specific_languages)

本模块中讨论的所有框架都由 JavaScript 提供支持，并且都允许您使用域特定语言 (DSL) 来构建您的应用程序。特别是 React 已经普及了使用**JSX**来编写其组件，而 Ember 使用**Handlebars**。与 HTML 不同，这些语言知道如何读取数据变量，并且这些数据可用于简化编写 UI 的过程。

Angular 应用程序经常大量使用**TypeScript**。TypeScript 不关心用户界面的编写，但它是一种特定于领域的语言，与普通的 JavaScript 有很大的不同。

DSL 不能被浏览器直接读取；它们必须首先转换为 JavaScript 或 HTML。[转换是开发过程中的一个额外步骤](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Overview#transformation)，但框架工具通常包含处理此步骤所需的工具，或者可以调整以包含此步骤。虽然可以在不使用这些特定领域语言的情况下构建框架应用程序，但拥抱它们将简化您的开发过程，并更容易从这些框架周围的社区中找到帮助。

### [JSX](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#jsx)

[JSX](https://reactjs.org/docs/introducing-jsx.html)，代表 JavaScript 和 XML，是 JavaScript 的扩展，它将类似 HTML 的语法引入 JavaScript 环境。它是由 React 团队发明的，用于 React 应用程序，但可用于开发其他应用程序——例如 Vue 应用程序。

下面显示了一个简单的 JSX 示例：

```
const subject = "World";
const header = (
  <header>
    <h1>Hello, {subject}!</h1>
  </header>
);
```

复制到剪贴板

此表达式表示一个 HTML`<header>`元素，其中包含一个`<h1>`元素。第`subject`4 行的花括号告诉应用程序读取`subject`常量的值并将其插入到我们的`<h1>`.

当与 React 一起使用时，上一个片段中的 JSX 将被编译为：

```
var subject = "World";
var header = React.createElement("header", null,
  React.createElement("h1", null, "Hello, ", subject, "!")
);
```

复制到剪贴板

当最终由浏览器呈现时，上述代码段将生成如下所示的 HTML：

```
<header>
  <h1>Hello, World!</h1>
</header>
```

复制到剪贴板

### [Handlebars](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#handlebars)

这 [车把](https://handlebarsjs.com/)模板语言并不特定于 Ember 应用程序，但它在 Ember 应用程序中被大量使用。Handlebars 代码类似于 HTML，但它可以选择从其他地方提取数据。此数据可用于影响应用程序最终构建的 HTML。

和 JSX 一样，Handlebars 使用花括号来注入变量的值。Handlebars 使用双对花括号，而不是单对花括号。

鉴于此 Handlebars 模板：

```
<header>
  <h1>Hello, {{subject}}!</h1>
</header>
```

复制到剪贴板

而这个数据：

```
{
  subject: "World"
}
```

复制到剪贴板

Handlebars 会像这样构建 HTML：

```
<header>
  <h1>Hello, World!</h1>
</header>
```

复制到剪贴板

### [TypeScrip](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#typescript)

[打字稿](https://www.typescriptlang.org/)是JavaScript的*超集*，这意味着它扩展了 JavaScript——所有 JavaScript 代码都是有效的 TypeScript，但反之则不然。TypeScript 非常有用，因为它允许开发人员强制执行他们的代码。举例来说，假设一个函数`add()`，采用整数`a`并`b`返回它们的总和。

在 JavaScript 中，该函数可以这样编写：

```
function add(a, b) {
  return a + b;
}
```

复制到剪贴板

对于习惯使用 JavaScript 的人来说，这段代码可能是微不足道的，但它仍然可以更清晰。JavaScript 允许我们使用`+`运算符将字符串连接在一起，因此如果`a`并且`b`是字符串，这个函数在技术上仍然可以工作——它可能不会给你期望的结果。如果我们只想让数字传入这个函数怎么办？TypeScript 使这成为可能：

```
function add(a: number, b: number) {
  return a + b;
}
```

复制到剪贴板

`: number`这里每个参数后面的写法告诉 TypeScript`a`和 都`b`必须是数字。如果我们使用这个函数并将`'2'`其作为参数传递给它，TypeScript 会在编译期间引发错误，我们将被迫修复我们的错误。我们可以编写自己的 JavaScript 来为我们引发这些错误，但这会使我们的源代码变得更加冗长。让 TypeScript 为我们处理此类检查可能更有意义。

## [Writing components](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#writing_components)

如前一章所述，大多数框架都有某种组件模型。React 组件可以使用 JSX 编写，Ember 组件使用 Handlebars 编写，Angular 和 Vue 组件可以使用模板语法轻松扩展 HTML。

不管他们对应该如何编写组件的看法如何，每个框架的组件都提供了一种描述它们可能需要的外部属性、组件应该管理的内部状态以及用户可以在组件的标记上触发的事件的方法。

本节其余部分的代码片段将使用 React 作为示例，并使用 JSX 编写。

### [Properties](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#properties)

属性或**props**是组件渲染所需的外部数据。假设您正在为在线杂志建立一个网站，并且您需要确保每位撰稿人都因其工作而获得赞誉。您可以`AuthorCredit`为每篇文章创建一个组件。该组件需要显示作者的肖像和关于他们的简短署名。为了知道要渲染什么图像，要打印什么署名，`AuthorCredit`需要接受一些道具。

该`AuthorCredit`组件的React 表示可能如下所示：

```
function AuthorCredit(props) {
  return (
    <figure>
      <img src={props.src} alt={props.alt} />
      <figcaption>{props.byline}</figcaption>
    </figure>
  );
}
```

复制到剪贴板

`{props.src}`, `{props.alt}`, 和`{props.byline}`代表我们的道具将被插入到组件中的位置。为了渲染这个组件，我们会在我们想要渲染它的地方（可能在另一个组件内）编写这样的代码：

```
<AuthorCredit
  src="./assets/zelda.png"
  alt="Portrait of Zelda Schiff"
  byline="Zelda Schiff is editor-in-chief of the Library Times."
/>
```

复制到剪贴板

这将最终`<figure>`在浏览器中呈现以下元素，其结构在`AuthorCredit`组件中定义，其内容在`AuthorCredit`组件调用中包含的 props 中定义：

```
<figure>
  <img
    src="assets/zelda.png"
    alt="Portrait of Zelda Schiff"
  >
  <figcaption>
    Zelda Schiff is editor-in-chief of the Library Times.
  </figcaption>
</figure>
```

复制到剪贴板

### [State](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#state)

我们在上一章中谈到了**状态**的概念——一个健壮的状态处理机制是有效框架的关键，每个组件可能都有需要控制状态的数据。只要组件在使用中，这种状态就会以某种方式持续存在。与 props 一样，state 可用于影响组件的呈现方式。

举个例子，考虑一个按钮，它计算它被点击了多少次。这个组件应该负责跟踪它自己的*计数*状态，可以这样写：

```
function CounterButton() {
  const [count] = useState(0);
  return (
    <button>Clicked {count} times</button>
  );
}
```

复制到剪贴板

`useState()` 是一个 **[反应钩子](https://reactjs.org/docs/hooks-intro.html)**给定初始数据值，它将在更新时跟踪该值。代码最初将在浏览器中呈现如下：

```
<button>Clicked 0 times</button>
```

复制到剪贴板

该`useState()`调用`count`在整个应用程序中以稳健的方式跟踪值，而无需您自己编写代码来执行此操作。

### [Events](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#events)

为了具有交互性，组件需要响应浏览器事件的方法，以便我们的应用程序可以响应我们的用户。每个框架都提供自己的语法来侦听浏览器事件，这些语法引用了等效的本机浏览器事件的名称。

在 React 中，监听`click`事件需要一个特殊的属性`onClick`. 让我们`CounterButton`从上面更新我们的代码以允许它计算点击次数：

```
function CounterButton() {
  const [count, setCount] = useState(0);
  return (
    <button onClick={() => setCount(count + 1)}>Clicked {count} times</button>
  );
}
```

复制到剪贴板

在这个版本中，我们使用额外的`useState()`功能来创建一个特殊的`setCount()`函数，我们可以调用它来更新 的值`count`。我们在第 4 行调用此函数，并将其设置`count`为当前值加一。

## [Styling Components](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#styling_components)

每个框架都提供了一种为您的组件或整个应用程序定义样式的方法。尽管每个框架定义组件样式的方法略有不同，但它们都为您提供了多种方法。通过添加一些帮助程序模块，您可以将您的框架应用程序设置为[萨斯](https://sass-lang.com/) 或者 [较少的](https://lesscss.org/)，或使用 [后CSS](https://postcss.org/).

## [处理依赖](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#handling_dependencies)

所有主要框架都提供了处理依赖关系的机制——使用其他组件内部的组件，有时具有多个层次结构。与其他功能一样，框架之间的确切机制会有所不同，但最终结果是相同的。组件倾向于使用标准的[JavaScript 模块语法](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)或至少类似的东西将组件导入到其他组件中。

### [组件中的组件](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#components_in_components)

基于组件的 UI 架构的一个主要好处是组件可以组合在一起。就像您可以在彼此内部编写 HTML 标签来构建网站一样，您可以使用其他组件内部的组件来构建 Web 应用程序。每个框架都允许您编写利用（并因此依赖）其他组件的组件。

例如，我们的`AuthorCredit`React 组件可能会在`Article`组件内部使用。这意味着`Article`需要导入`AuthorCredit`.

```
import AuthorCredit from "./components/AuthorCredit";
```

复制到剪贴板

完成后，`AuthorCredit`可以`Article`像这样在组件内部使用：

```
  ...

<AuthorCredit />

  ...
```

复制到剪贴板

### [依赖注入](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#dependency_injection)

实际应用程序通常会涉及具有多级嵌套的组件结构。`AuthorCredit`出于某种原因，嵌套多层深的组件可能需要来自我们应用程序最根级别的数据。

假设我们正在构建的杂志网站的结构如下：

```
<App>
  <Home>
    <Article>
      <AuthorCredit {/* props */} />
    </Article>
  </Home>
</App>
```

复制到剪贴板

我们的`App`组件有我们的`AuthorCredit`组件需要的数据。我们可以重写`Home`并`Article`让他们知道传递道具，但是如果我们的数据的来源和目的地之间有很多很多层次，这可能会变得乏味。这也太过分了：实际上`Home`并`Article`没有使用作者的肖像或署名，但是如果我们想将这些信息放入`AuthorCredit`，我们将需要更改`Home`并`Author`适应它。

通过多层组件传递数据的问题称为道具钻取，对于大型应用程序来说并不理想。

为了规避 prop 钻取，框架提供了称为依赖注入的功能，这是一种将某些数据直接获取到需要它的组件的方法，而无需通过中间级别。每个框架都以不同的名称、不同的方式实现依赖注入，但最终效果是一样的。

Angular 调用这个过程 [依赖注入](https://angular.io/guide/dependency-injection); Vue 有[`provide()`和`inject()`组件方法](https://vuejs.org/v2/api/#provide-inject); 反应有一个[上下文 API](https://reactjs.org/docs/context.html); Ember 共享状态通过[服务](https://guides.emberjs.com/release/services/).

### [生命周期](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#lifecycle)

在框架的上下文中，组件的**生命周期**是组件从浏览器呈现（通常称为*挂载*）到从 DOM 中移除（通常称为*卸载*）所经历的阶段的集合。每个框架都不同地命名这些生命周期阶段，并且并非所有框架都允许开发人员访问相同的阶段。所有框架都遵循相同的通用模型：它们允许开发人员在组件*挂载*、*渲染*、*卸载*以及这些之间的许多阶段执行某些操作。

在*渲染*阶段是最关键的理解，因为它是重复次数最多的为您的应用程序用户交互。每次浏览器需要呈现新信息时，它都会运行，无论新信息是对浏览器中内容的添加、删除还是对现有内容的编辑。

这 [React 组件的生命周期图](http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/) 提供了该概念的一般概述。

## [渲染元素](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#rendering_elements)

就像生命周期一样，框架采用不同但相似的方法来呈现您的应用程序。它们都跟踪浏览器 DOM 的当前呈现版本，并且每个都对 DOM 应该如何随着应用程序中的组件重新呈现而发生的变化做出略微不同的决定。由于框架会为您做出这些决定，因此您通常不会自己与 DOM 进行交互。这种对 DOM 的抽象比自己更新 DOM 更复杂、更占用内存，但如果没有它，框架将无法允许您以它们众所周知的声明式方式进行编程。

该**虚拟DOM**是一种方法，即你的浏览器的DOM信息存储在JavaScript中的内存。您的应用程序更新此 DOM 副本，然后将其与“真实”DOM（实际为用户呈现的 DOM）进行比较，以确定要呈现的内容。应用程序构建一个“差异”来比较更新后的虚拟 DOM 和当前呈现的 DOM 之间的差异，并使用该差异将更新应用于真实 DOM。React 和 Vue 都使用虚拟 DOM 模型，但它们在差异或渲染时不应用完全相同的逻辑。

你可以 [在 React 文档中阅读更多关于虚拟 DOM 的信息](https://reactjs.org/docs/faq-internals.html#what-is-the-virtual-dom).

该**增量DOM**类似于它建立一个DOM差异来决定渲染什么虚拟DOM，但不同之处在于它不使用JavaScript创建内存中的DOM的完整副本。它忽略不需要更改的 DOM 部分。Angular 是本模块迄今为止讨论的唯一使用增量 DOM 的框架。

你可以 [在 Auth0 博客上阅读有关增量 DOM 的更多信息](https://auth0.com/blog/incremental-dom/).

该**微光VM**是唯一的灰烬。它既不是虚拟 DOM，也不是增量 DOM；它是一个单独的过程，通过它 Ember 的模板被转换成一种比 JavaScript 更容易、更快阅读的“字节码”。

## [路由](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#routing)

如[前一章所述，路由](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Introduction#routing)是 Web 体验的重要组成部分。为了避免在具有大量视图的足够复杂的应用程序中出现糟糕的体验，本模块中涵盖的每个框架都提供了一个库（或多个库），可帮助开发人员在其应用程序中实现客户端路由。

## [测试](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#testing)

所有应用程序都受益于测试覆盖率，确保您的软件继续按照您期望的方式运行，Web 应用程序也不例外。每个框架的生态系统都提供了有助于编写测试的工具。测试工具并未内置于框架本身，但用于生成框架应用程序的命令行界面工具可让您访问适当的测试工具。

每个框架在其生态系统中都有广泛的工具，具有单元和集成测试等功能。

[测试库](https://testing-library.com/)是一套测试实用程序，具有适用于许多 JavaScript 环境的工具，包括 React、Vue 和 Angular。Ember 文档涵盖了[测试 Ember 应用程序](https://guides.emberjs.com/release/testing/).

这是我们`CounterButton`在 React 测试库的帮助下编写的快速测试——它测试了很多东西，比如按钮的存在，以及按钮在被点击 0、1 和 2 次后是否显示正确的文本：

```
import React from "react";
import { render, fireEvent } from "@testing-library/react";
import "@testing-library/jest-dom/extend-expect";

import CounterButton from "./CounterButton";

it("renders a semantic with an initial state of 0", () => {
  const { getByRole } = render(<CounterButton />);
  const btn = getByRole("button");

  expect(btn).toBeInTheDocument();
  expect(btn).toHaveTextContent("Clicked 0 times");
});

it("Increments the count when clicked", () => {
  const { getByRole } = render(<CounterButton />);
  const btn = getByRole("button");

  fireEvent.click(btn);
  expect(btn).toHaveTextContent("Clicked 1 times");

  fireEvent.click(btn);
  expect(btn).toHaveTextContent("Clicked 2 times");
});
```

复制到剪贴板

## [概括](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Main_features#summary)

在这一点上，您应该对使用框架创建应用程序时将使用的实际语言、特性和工具有了更多的了解。我敢肯定，您非常热衷于开始并实际进行一些编码，这就是您接下来要做的事情！此时，您可以选择要先开始学习的框架：

# React 入门

本文会引导我们进入一段 React 学习之旅。我们将逐步了解有关它的背景和用例的一些细节，在自己的电脑上建起基本的 React 工具链，创建并使用一个简单的入门应用程序，以学习一些关于 React 在此过程中如何工作的知识。

## [你好 React](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#你好_react)

如其官方口号所示，[React](https://reactjs.org/) 是一个用于构建用户界面的库。React 不是一个框架 —— 它的应用甚至不局限于 Web 开发，它可以与其他库一起使用以渲染到特定环境。例如，[React Native](https://reactnative.dev/) 可用于构建移动应用程序；[React 360](https://facebook.github.io/react-360/) 可用于构建虚拟现实应用程序……

为了构建 Web 应用，开发人员将 React 与 [ReactDOM 结合使用](https://reactjs.org/docs/react-dom.html)。React 和 ReactDOM 通常被与其他真正的 Web 开发框架相提并论，并用于解决相同的问题。当我们将 React 称为“框架”时，就是在进行口语化的理解。

React 的主要目标是最大程度地减少开发人员构建 UI 时发生的错误。它通过使用组件——描述部分用户界面的、自包含的逻辑代码段——来实现此目的。这些组件可以组合在一起以创建完整的 UI，React 将许多渲染工作进行抽象化，使您可以专注于 UI 设计(译者注：显而易见，此设计不等于视觉稿的设计)。

## [用例](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#用例)

与本模块中涵盖的其他框架不同，React 不会对代码约定或文件组织实施严格的规则。这使团队可以设置最适合自己的约定，并以他们希望的任何方式采用 React。React 可以处理一个按钮，一个界面的几个部分或应用程序的整个用户界面。

尽管 React 可以用于[界面的小片段](https://reactjs.org/docs/add-react-to-a-website.html)中，但要和 jQuery 这样的库，甚至是像 Vue 这样的框架那样“引入”应用程序并不容易 —— 当你使用 React 构建整个应用程序时更容易上手。

另外，许多开发人员的经验对于 React 应用程序也是有用处的，例如使用 JSX 编写界面是需要编译过程的。在网站上添加类似于 Babel 的编译器会让网站上代码的运行速度变慢，因此开发人员通常会在构建项目的时候设置这样的工具。React 对于工具的要求可以说是很高的，但这是能够学习解决的。

本文将重点介绍使用 React 通过 Facebook 的 [create-react-app](https://create-react-app.dev/) 内的工具渲染应用程序中整个用户界面的用例。

## [React 如何使用 JavaScript?](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#react_如何使用_javascript)

React 中的许多模式都使用了现代 JavaScript 的功能。React 与 JavaScript 的最大区别在于 [JSX](https://reactjs.org/docs/introducing-jsx.html) 语法的使用上。JSX 是在 JavaScript 语法上的拓展，因此类似于 HTML 的代码可以和 JSX 共存。例如：

```
const heading = <h1>Mozilla Developer Network</h1>;
```

Copy to Clipboard

该 heading 常量称为 **JSX 表达式**。React 可以使用它在我们的应用程序中渲染 `<h1>` 标签。

假设出于语义原因，我们想将 heading 包装 `<header>` 在标记中？JSX 方法允许我们将元素彼此嵌套，就像使用 HTML 一样：

```
const header = (
  <header>
    <h1>Mozilla Developer Network</h1>
  </header>
);
```

Copy to Clipboard

**注意**：上一个代码段中的括号并非 JSX 的一部分，它对您的应用程序没有任何影响，括号只是用来向您（和您的计算机）表明其中的多行代码属于同一个表达式(译者注：原文表述实在有点啰嗦)。因此上面的代码等同于：

```
const header = <header>
    <h1>Mozilla Developer Network</h1>
</header>
```

Copy to Clipboard

这看起来多少有点不适感，因为表达式前面的 `<header>` 标记没有缩进与其对应的结束标记相同的位置。

浏览器是无法读取直接解析 JSX 的。我们的 header 表达式经过（ [Babel](https://babeljs.io/) 或 [Parcel](https://parceljs.org/) 之类的工具）编译之后是这样的：

```
const header = React.createElement("header", null,
  React.createElement("h1", null, "Mozilla Developer Network")
);
```

Copy to Clipboard

*可以*跳过编译步骤，并使用 `React.createElement()` 自己编写 UI。但是，这样做会失去 JSX 的声明性优势，并且代码变得更难以阅读。编译是开发过程中的一个额外步骤，但是 React 社区中的许多开发人员都认为 JSX 的可读性值得。另外，流行的工具使 JSX-to-JavaScript 编译成为其设置过程的一部分。除非您愿意，否则不必自己配置编译。

由于 JSX 是 HTML 和 JavaScript 的结合，因此一些开发人员认为它很直观。其他人则说它的混合特性使它变得混乱。但是，一旦熟悉了它，它将使您能够更快，更直观地构建用户界面，并使其他人一眼就能更好地理解您的代码库。

要阅读有关 JSX 的更多信息，请查看 React 团队的 [JSX In Depth](https://reactjs.org/docs/jsx-in-depth.html) 文章。

## [设置您的第一个 React 应用](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#设置您的第一个_react_应用)

有很多使用 React 的方法，但是我们将使用命令行界面（CLI）工具 create-react-app，如前所述，该方法通过安装一些软件包并创建一些软件包来加快开发 React 应用程序的过程。文件供您处理上述工具。

通过将一些 `<script>` 元素复制到 HTML 文件中，可以在[没有 create-react-app 的情况下将 React 添加到网站](https://reactjs.org/docs/add-react-to-a-website.html)，但是 create-react-app CLI 是 React 应用程序的常见起点。使用它可以让您花费更多的时间来构建应用，而花更少的时间进行设置。

### [要求](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#要求)

为了使用 create-react-app，您需要安装 [Node.js](https://nodejs.org/en/)。建议您使用长期支持（LTS）版本。Node 包括 npm（Node 程序包管理器）和 npx（Node 程序包运行器）

您也可以使用 Yarn 软件包管理器作为替代方案，但是我们假设在这套教程中使用 npm。有关 npm 和 yarn 的更多信息，请参见[程序包管理基础 (en-US)](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management)。

如果您使用的是 Windows，则需要安装一些软件以与 Unix/macOS 终端保持同等地位，才能使用本教程中提到的终端命令。**Gitbash**（作为 [git Windows 工具集](https://gitforwindows.org/)的一部分提供）或**[适用于 Linux 的 Windows 子系统](https://docs.microsoft.com/en-us/windows/wsl/about)**（**WSL**）均适用。有关这些以及一般终端命令的更多信息，请参见[命令行速成课程](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)。

还请记住，React 和 ReactDOM 生成的应用程序只能在相当现代的一组浏览器上运行 —— 通过某些 polyfill 可以使用 IE9+。在阅读这些教程时，建议您使用 Firefox，Safari 或 Chrome 等现代浏览器。

另外，有关更多信息，请参见以下内容：

- ["What is npm" on nodejs.org](https://nodejs.org/en/knowledge/getting-started/npm/what-is-npm/)
- ["Introducing npx" on the npm blog](https://blog.npmjs.org/post/162869356040/introducing-npx-an-npm-package-runner)
- [The create-react-app documentation](https://create-react-app.dev/)

### [初始化您的应用](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#初始化您的应用)

`create-react-app` ，该命令接受一个参数：即你想给自己的应用所起的名字。`create-react-app` 将为此应用创建一个同名的文件夹，并在其中创建所需文件。在你打算放置你的应用程序的文件夹下打开你的命令终端，并键入命令：

```
npx create-react-app moz-todo-react
```

Copy to Clipboard

这句命令创建了一个名为 `moz-todo-react` 的文件夹， 并在此文件夹里做了如下工作：

- 为你的应用程序安装了一些 npm 包；
- 写入 react 应用启动所需要的脚本文件；
- 创建一系列结构化的子文件夹和文件，奠定应用程序的基础架构；
- 如果你的电脑上安装了 git 的话，顺便帮你把 git 仓库也建好。

**注意：如果你的电脑上安装了 yarn 的话， create-react-app 会默认使用 yarn 而非 npm。如果你同时安装了 yarn 和 npm ，但你希望使用 npm 的话，在 create-react-app 的时候需要输入** `--use-npm` **:**

```
npx create-react-app moz-todo-react --use-npm
```

Copy to Clipboard

`create-react-app` 运行的时候会在终端上显示一些与其状态相关的信息，通常情况下无需为此担心。运行需要一点时间，在此期间你可以适度放松一下。

处理完成之后，你可以 `cd` 到 `moz-todo-react` 文件夹下，然后键入 `npm start` 命令并回车，先前由 create-react-app 创建的脚本会启动一个地服务 [localhost:3000](localhost:3000)，并打开你的默认浏览器来访问这个服务。成功启动浏览器的话，你的浏览器上会显示如下画面：

![Firefox MacOS的屏幕截图，打开到localhost：3000，显示了默认的create-react-app应用程序](https://mdn.mozillademos.org/files/17203/default-create-react-app.png)

### [应用结构](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#应用结构)

create-react-app 提供了开发React应用所需的工具。它的初始文件结构如下：

```
moz-todo-react
├── README.md
├── node_modules
├── package.json
├── package-lock.json
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html
│   └── manifest.json
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    └── serviceWorker.js
```

目录 **`src`** 是我们花费时间最多的地方，因为它是我们React应用源码存放的目录。

目录 **`public`** 包含了开发应用时浏览器会读取的文件，其中最重要的就是 `index.html`。React将目录 **`src`** 中的代码嵌入这个文件，从而浏览器才能运行此文件。 `index.html`中的有些内容关乎create-react-app的运作，因此除非你知道自己在做什么样的修改，否则不建议编辑这个文件。当然，你可以修改`index.html`中的 `<title>` 元素的内容来表现此应用程序通俗易懂的名称。

目录 `public` 会在建立并部署此应用的时候更新。此教程不涉及部署，你可以参考 [Deploying our app](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Deployment) 这一篇教程。

文件 `package.json` 包含了Node.js/npm为了建立该应用程序所管理着的文件信息。这个文件不是React应用独有的。你无需理解这个文件也能看懂这篇教程。 不过，如果你想了解更多，你可以阅读 [What is the file `package.json`? on NodeJS.org](https://nodejs.org/en/knowledge/getting-started/npm/what-is-the-file-package-json/) 和 [Package management basics](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Package_management)。

## [探索第一个 React 组件 — ``](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#探索第一个_react_组件_—_)

在React中，组件是组成应用程序的可重复利用的模块。组件可大可小，但它们都只有单一的、明确的功能。

打开 `src/App.js`，之前打开的页面也提示我们对这个文件进行编辑。这个文件包含了我们第一个组件 `App`，内容如下：

```
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}
export default App;
```

Copy to Clipboard

文件 `App.js` 主要由三部分组成： 顶部的 `import` 语句， 中间的 `App` 组件，以及底部的 `export` 语句。大多数React组件都遵循这个模式。

### [import 语句](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#import_语句)

脚本开头的 `import` 语句允许在此脚本中使用其他文件中的代码，让我们更进一步地了解这些语句。

```
import React from 'react';
import logo from './logo.svg';
import './App.css';
```

Copy to Clipboard

第一句代码引入了 React 库，这是为了将代码中的 JSX 语句转为`React.createElement()`，所有的 React 模块都应该引入 React 模块，否则会抛错。

第二句代码引入了 `'./logo.svg'`。注意文件路径以 `./` 开头、由 `.svg` 尾——表明这是一个本地文件，并且它不是 JavaScript 文件。

我们没有指定 React 模块的路径——表明它并非来自本地文件，而是在 `package.json` 文件中列为依赖项。在整个学习过程中，请务必留心这两种引入方式的不同之处。

第三行引入了我们的组件所需的 CSS 文件。与上面两句不同，这里没有将引入的内容赋给任何变量、也没有用到 `from` 指令。请注意这种特殊的语法并非原生 JS 的语法 —— 它源自前端资源打包工具 webpack，而 create-react-app 正是基于 webpack 配置而来的。

译者补充：webpack 可用于打包 JS 和非 JS 的内容(当然，非 JS 的内容需要一些插件或加载器来处理)，但是 JavaScript 标准只有关于 JS 的内容，所以 webpack 社区使用这种特殊的 `import` 语句来声明对非 JS 内容的引用。

详情参见 webpack 官方和社区，截止目前(2020年下旬)，webpack 仍是现代前端工作中必不可少的技能之一。

### [`App` 组件](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#app_组件)

在 import 所需资源之后，我们定义了一个名为 App 的函数，尽管大部分 JavaScript 社区推崇使用驼峰式命名法，如：“helloWorld”。但 React 组件使用帕斯卡命名法，如 “HelloWorld”，来帮助用户辨认一个 JSX 元素是 React 组件而非普通的 HTML 标签。如果您将函数名 “App” 改为 “app”，您的浏览器会显示错误。

让我们进一步看下App方法。

```
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}
```

Copy to Clipboard

App方法返回一个JSX表达式，这个表达式定义了浏览器最终要渲染的DOM。

表达式中的元素就像以前写的HTML一样，都拥有属性，并且遵循 `attribute="value"` 的模式。 在第三行，开始标签 `<div>` 有着 `className` 属性。 这个属性与在HTML中的 `class` 属性相同，但是由于JSX就是JavaScript, 我们不能使用 `class` 属性 - 这个是关键字，意味着JavaScript已经用它执行其它任务，使用 `class` 属性将会在我们的代码中产生冲突。由于同样的原因，一些其它的HTML属性在JSX中也有着不同的书写方式，当我们碰到它们时，我们将会详述。

把第6行的 `<p>` 标签内容改为 "Hello, world!" 并保存文件。你会发现这个改变也会立即在浏览器的`http://localhost:3000` 中同步渲染。 现在删掉 `<a>` 标签并保存，"Learn React"链接也会同样被删除。

你的 `App` 组件应该如下所示:

```
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Hello, World!
        </p>
      </header>
    </div>
  );
}
```

Copy to Clipboard

### [Export 语句](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#export_statements)

在 `App.js` 文件的最底部, `export default App` 语句使得 `App` 组件能被其它模块使用.

## [Interrogating the index](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#interrogating_the_index)

现在让我们打开 `src/index.js`, 因为这也是 `App` 组件被用到的地方。 这个文件是我们 app 的入口点，在一开始它如下所示

```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

ReactDOM.render(<App />, document.getElementById('root'));

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();
```

Copy to Clipboard

就像 `App.js` 一样,这个文件一开始 import 了所有的 JS 模块和其它运行所需要的资源。`src/index.css`定义了运用于整个 app 的 global style。 我们可以看到我们的 `App` 组件也被 imported 了， 这是在 `App.js` 底部的语句让 import `App` 变得可行。

第七行调用 React 的 `ReactDOM.render()` 函数，并传入两个参数：

- 我们想要渲染的组件, 在这个例子中是 `<App />` .
- 我们想要渲染组件所在的 DOM 元素，在这个例子中是带着 `root` 标签的元素。 让我们看一下 `public/index.html` 的代码， 可以看到这有一个 `<div>` 元素 在 `<body>` 里。

上述所有都告诉 React 我们想把 `App` 组件作为 root 或者第一个组件来渲染我们的 React App。

**注意**: 在 JSX 中， React 组件和 HTML 元素必须有 closing slashes，如 `<App />`， 如果我们写 `<App>` 或者 `<img>` 将会报错。

[Service workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers) 能让我们的 App 离线运行，但它不在本篇文章的范围中，您可以删除第5行和第9到12行。

您最终的 `index.js` 文件应该如下所示：

```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';

ReactDOM.render(<App />, document.getElementById('root'));
```

Copy to Clipboard

## [Variables and props](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#variables_and_props)

接下来，我们将使用一些 JavaScript 的技巧来让我们在 React 中编辑组件以及处理数据更加顺手。我们将讨论如何在 JSX 中 使用 variables， 并且介绍 props， props是我们用来往组件里传入数据的一种方法， 传入之后我们可以用 variable 访问传入的变量。

### [Variables in JSX](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#variables_in_jsx)

回到 `App.js`, 让我们看一下第9行:

```
<img src={logo} className="App-logo" alt="logo" />
```

Copy to Clipboard

可以看到， `<img />` 标签的 `src` 属性只值是在大括号中的 -- `{logo}`. 这是JSX 识别变量的方式。 React 将会识别 `{logo}`， 知道您在指在我们 app 第二行引入的 logo， 然后 React 会读取这个文件它并渲染。

让我们试着设置一个我们自己的变量，在 `App` return 之前， 添加 `const subject = 'React';`。 您的代码现在应该如下所示：

```
function App() {
  const subject = "React";
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Hello, World!
        </p>
      </header>
    </div>
  );
}
```

Copy to Clipboard

把第8行的 "world" 替换成我们自己的变量 `subject` ，如下所示：

```
function App() {
  const subject = "React";
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Hello, {subject}!
        </p>
      </header>
    </div>
  );
}
```

Copy to Clipboard

当我们保存时， 浏览器将会显示 "Hello, React!"， 而不是 "Hello, world!"

变量十分方便，但是我们没有利用到 React 的特性， 接下来我们将介绍 Props。

### [Component props](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#component_props)

**prop** 是任何传入 React 组件的数据。Props 写在组件中，并且像 HTML 属性一样写成 `prop="value"`。 让我们打开 `index.js` 并且为我们的 `<App/>` 添加第一个 prop。

为 `<App/>` 组件添加一个叫 `subject` 并有着 `Clarice` 值的 prop。 当完成之后，您的代码应如下所示：

```
ReactDOM.render(<App subject="Clarice" />, document.getElementById('root'));
```

Copy to Clipboard

回到 `App.js`， 代码应该如下所示 （return 中的内容省略了）

```
function App() {
  const subject = "React";
  return (
    // return statement
  );
}
```

Copy to Clipboard

改变 `App` 的函数签名，让它接收 `props` 作为一个参数。 就像其它参数一样， 您可以把 `props` 放在 `console.log()` 中，让其在浏览器打印出来。 把它放在您的 `subject` 之后，以及 `return` 之前， 您的代码应如下所示：

```
function App(props) {
  const subject = "React";
  console.log(props);
  return (
    // return statement
  );
}
```

Copy to Clipboard

保存您的文件并检查您浏览器中的 JavaScript Console， 您将会发现如下所示的语句：

```
Object { subject: "Clarice" }
```

Copy to Clipboard

对象的 `subject` 属性与我们放入 `App` 函数签名的 prop 相对应，并且 `Clarice` 字符串与它的值相对应， 在 React 中的组件 props 总是用这种方式传入object 中。

现在 `subject` 是我们的 props 之一了， 让我们在 `App.js` 中使用它。 用 `props.subject` 替代原本的 `React` 字符串， 如果你想的话，也可以删除 `console.log()`， 您的代码将如下所示：

```
function App(props) {
  const subject = props.subject;
  return (
    // return statement
  );
}
```

Copy to Clipboard

当您保存之后， app 应该会输出 "Hello, Clarice!"。 如果您回到 `index.js`， 并且修改 `subject` 的值并保存， 您输出的字也会随之改变。

## [总结](https://developer.mozilla.org/zh-CN/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_getting_started#summary)

以上就是我们对 React 的初步认识， 包括如何在本地下载它， 创建一个初始 app， 以及一些基本的操作。 在下篇文章，我们将会开始创建我们的第一个 app -- 一个任务清单。在我们开始下篇文章之前，让我们先复习下我们现在所学的。

在 React 中:

- 组件可以 import 它们需要的模块，并且在文件底部将自身 export，以让其它组件使用。
- 组件是用 `PascalCase` 也就是帕斯卡命名法命名的。
- 通过把变量放在大括号中，您可以读取 JSX 的变量， 如`{so}`
- 一些 JSX 属性与 HTML 属性不相同，这样就不会与JavaScript的保留字相冲突，比如说，在 HTML 中的 `class` 会在 JSX 中转译为 `className`。 注意这些属性都是驼峰式命名的。
- Props 就像属性一样写在组件里，并且传入组件。

![image-20211228223523106](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20211228223523106.png)

![image-20211228223537935](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\image-20211228223537935.png)

# 开始我们的 React 待办事项列表

假设我们的任务是在 React 中创建一个概念验证——一个允许用户添加、编辑和删除他们想要处理的任务的应用程序，并将任务标记为完成而不删除它们。本文将引导您完成基本`App`组件结构和样式的设置，为单独的组件定义和交互做好准备，我们将在稍后添加这些内容。

**注意：**如果您需要根据我们的版本检查您的代码，您可以在我们的[待办事项反应库](https://github.com/mdn/todo-react). 有关正在运行的实时版本，请参阅https://mdn.github.io/todo-react-build/.

## [我们应用的用户需求](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning#our_apps_user_stories)

在软件开发中，从用户的角度来看，用户需求是一个可操作的目标。在我们开始工作之前定义用户需求将有助于我们专注于我们的工作。我们的应用程序应该满足以下需求：

作为用户，我可以

- 阅读任务列表。
- 使用鼠标或键盘添加任务。
- 使用鼠标或键盘将任何任务标记为已完成。
- 使用鼠标或键盘删除任何任务。
- 使用鼠标或键盘编辑任何任务。
- 查看特定任务子集：所有任务、仅活动任务或仅已完成任务。

我们将一一处理这些需求。

## [项目前期管理](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning#pre-project_housekeeping)

create-react-app 已经制作了一些我们根本不会在我们的项目中使用的文件。

- 我们不会编写每个组件的样式表，因此首先`App.css`从`App.js`.
- 我们也不打算使用该`logo.svg`文件，因此也删除该导入。

然后，将以下命令复制并粘贴到您的终端中以删除一些不需要的文件。确保您从应用程序的根目录开始！

```
# Move into the src directory of your project
cd src
# Delete a few files
rm -- App.test.js App.css logo.svg serviceWorker.js setupTests.js
# Move back up to the root of the project
cd ..
```

复制到剪贴板

笔记：

- 我们要删除的两个文件用于测试应用程序。我们不会在这里介绍测试。
- 如果您停止服务器以执行上述终端任务，则必须使用`npm start`.

## [项目启动代码](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning#project_starter_code)

作为这个项目的起点，我们将提供两件事：一个`App()`函数来替换你现在拥有的函数，以及一些 CSS 来设置你的应用程序的样式。

### [JSX](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning#the_jsx)

将以下代码段复制到剪贴板，然后将其粘贴到其中`App.js`以替换现有`App()`函数：

```
function App(props) {
  return (
    <div className="todoapp stack-large">
      <h1>TodoMatic</h1>
      <form>
        <h2 className="label-wrapper">
          <label htmlFor="new-todo-input" className="label__lg">
            What needs to be done?
          </label>
        </h2>
        <input
          type="text"
          id="new-todo-input"
          className="input input__lg"
          name="text"
          autoComplete="off"
        />
        <button type="submit" className="btn btn__primary btn__lg">
          Add
        </button>
      </form>
      <div className="filters btn-group stack-exception">
        <button type="button" className="btn toggle-btn" aria-pressed="true">
          <span className="visually-hidden">Show </span>
          <span>all</span>
          <span className="visually-hidden"> tasks</span>
        </button>
        <button type="button" className="btn toggle-btn" aria-pressed="false">
          <span className="visually-hidden">Show </span>
          <span>Active</span>
          <span className="visually-hidden"> tasks</span>
        </button>
        <button type="button" className="btn toggle-btn" aria-pressed="false">
          <span className="visually-hidden">Show </span>
          <span>Completed</span>
          <span className="visually-hidden"> tasks</span>
        </button>
      </div>
      <h2 id="list-heading">
        3 tasks remaining
      </h2>
      <ul
        role="list"
        className="todo-list stack-large stack-exception"
        aria-labelledby="list-heading"
      >
        <li className="todo stack-small">
          <div className="c-cb">
            <input id="todo-0" type="checkbox" defaultChecked={true} />
            <label className="todo-label" htmlFor="todo-0">
              Eat
            </label>
          </div>
          <div className="btn-group">
            <button type="button" className="btn">
              Edit <span className="visually-hidden">Eat</span>
            </button>
            <button type="button" className="btn btn__danger">
              Delete <span className="visually-hidden">Eat</span>
            </button>
          </div>
        </li>
        <li className="todo stack-small">
          <div className="c-cb">
            <input id="todo-1" type="checkbox" />
            <label className="todo-label" htmlFor="todo-1">
              Sleep
            </label>
          </div>
          <div className="btn-group">
            <button type="button" className="btn">
              Edit <span className="visually-hidden">Sleep</span>
            </button>
            <button type="button" className="btn btn__danger">
              Delete <span className="visually-hidden">Sleep</span>
            </button>
          </div>
        </li>
        <li className="todo stack-small">
          <div className="c-cb">
            <input id="todo-2" type="checkbox" />
            <label className="todo-label" htmlFor="todo-2">
              Repeat
            </label>
          </div>
          <div className="btn-group">
            <button type="button" className="btn">
              Edit <span className="visually-hidden">Repeat</span>
            </button>
            <button type="button" className="btn btn__danger">
              Delete <span className="visually-hidden">Repeat</span>
            </button>
          </div>
        </li>
      </ul>
    </div>
  );
}
```

复制到剪贴板

现在打开`public/index.html`并将[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)元素的文本更改为`TodoMatic`. 这样，它将匹配[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)我们应用程序顶部的 。

```
<title>TodoMatic</title>
```

复制到剪贴板

当您的浏览器刷新时，您应该看到如下内容：

![todo-matic 应用程序，无样式，显示混乱的标签、输入和按钮](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning/unstyled-app.png)

它很丑，而且还不能运行，但没关系——我们稍后会设计它的样式。首先，考虑我们拥有的 JSX，以及它如何对应我们的用户需求：

- 我们有一个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)元素，带有[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text)用于写出新任务的 ，以及用于提交表单的按钮。
- 我们有一组按钮用于过滤我们的任务。
- 我们有一个标题，告诉我们还有多少任务。
- 我们有 3 个任务，排列在一个无序列表中。每个任务都是一个列表项 ( [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li))，并具有用于编辑和删除它的按钮以及一个用于在完成时将其选中的复选框。

表格将允许我们*制作*任务；按钮将让我们*过滤*它们；标题和列表是我们*阅读*它们的方式。用于*编辑*任务的 UI目前明显不存在。没关系——我们稍后再写。

### [辅助功能](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning#accessibility_features)

您可能会注意到这里有一些不寻常的属性。例如：

```
<button type="button" className="btn toggle-btn" aria-pressed="true">
  <span className="visually-hidden">Show </span>
  <span>all</span>
  <span className="visually-hidden"> tasks</span>
</button>
```

复制到剪贴板

在这里，`aria-pressed`告诉辅助技术（如屏幕阅读器）该按钮可以处于以下两种状态之一：`pressed`或`unpressed`。想像这些类似物的`on`和`off`。设置值`true`表示默认按下按钮。

这个类`visually-hidden`还没有效果，因为我们还没有包含任何 CSS。但是，一旦我们设置好样式，具有此类的任何元素将对视力正常的用户隐藏，但屏幕阅读器用户仍然可以使用——这是因为视力正常的用户不需要这些词；他们在那里为没有额外视觉上下文来帮助他们的屏幕阅读器用户提供有关按钮功能的更多信息。

再往下，你可以找到我们的[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)元素：

```
<ul
  role="list"
  className="todo-list stack-large stack-exception"
  aria-labelledby="list-heading"
>
```

复制到剪贴板

该`role`属性帮助辅助技术解释标签代表什么样的元素。A`<ul>`在默认情况下被视为列表，但我们即将添加的样式将破坏该功能。此角色将恢复`<ul>` 元素的“列表”含义。如果你想了解更多关于为什么这是必要的，你可以查看[Scott O'Hara 的文章“修复清单”](https://www.scottohara.me/blog/2019/01/12/lists-and-safari.html).

该`aria-labelledby`属性告诉辅助技术，我们将列表标题视为描述其下方列表用途的标签。建立这种关联为列表提供了更多信息上下文，这可以帮助屏幕阅读器用户更好地理解它的目的。

最后，我们列表项中的标签和输入有一些 JSX 独有的属性：

```
<input id="todo-0" type="checkbox" defaultChecked={true} />
<label className="todo-label" htmlFor="todo-0">
  Eat
</label>
```

复制到剪贴板

 标签中的`defaultChecked`属性`<input/ >`告诉 React 最初选中这个复选框。如果我们`checked`像在常规 HTML 中那样使用 ，React 会在浏览器控制台中记录一些与处理复选框事件相关的警告，这是我们想要避免的。现在不要太担心这个——我们稍后会在我们开始使用事件时讨论这个。

该`htmlFor`属性对应`for`于 HTML 中使用的属性。我们不能`for`在 JSX 中用作属性，因为它`for`是一个保留字，所以 React 使用它`htmlFor`。

笔记：

- 要在 JSX 属性中使用布尔值（`true`和`false`），您必须将它们括在花括号中。如果你写`defaultChecked="true"`， 的值`defaultChecked`将是`"true"`— 一个字符串文字。记住——这实际上是 JavaScript，而不是 HTML！
- `aria-pressed`在我们之前的代码片段中使用的属性的值是`"true"` 因为`aria-pressed`不是真正的布尔属性`checked`。

### [实现我们的风格](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning#implementing_our_styles)

将以下 CSS 代码粘贴到其中`src/index.css`以替换当前存在的内容：

```
/* RESETS */
*,
*::before,
*::after {
  box-sizing: border-box;
}
*:focus {
  outline: 3px dashed #228bec;
  outline-offset: 0;
}
html {
  font: 62.5% / 1.15 sans-serif;
}
h1,
h2 {
  margin-bottom: 0;
}
ul {
  list-style: none;
  padding: 0;
}
button {
  border: none;
  margin: 0;
  padding: 0;
  width: auto;
  overflow: visible;
  background: transparent;
  color: inherit;
  font: inherit;
  line-height: normal;
  -webkit-font-smoothing: inherit;
  -moz-osx-font-smoothing: inherit;
  -webkit-appearance: none;
}
button::-moz-focus-inner {
  border: 0;
}
button,
input,
optgroup,
select,
textarea {
  font-family: inherit;
  font-size: 100%;
  line-height: 1.15;
  margin: 0;
}
button,
input {
  overflow: visible;
}
input[type="text"] {
  border-radius: 0;
}
body {
  width: 100%;
  max-width: 68rem;
  margin: 0 auto;
  font: 1.6rem/1.25 Arial, sans-serif;
  background-color: #f5f5f5;
  color: #4d4d4d;
}
@media screen and (min-width: 620px) {
  body {
    font-size: 1.9rem;
    line-height: 1.31579;
  }
}
/*END RESETS*/
/* GLOBAL STYLES */
.form-group > input[type="text"] {
  display: inline-block;
  margin-top: 0.4rem;
}
.btn {
  padding: 0.8rem 1rem 0.7rem;
  border: 0.2rem solid #4d4d4d;
  cursor: pointer;
  text-transform: capitalize;
}
.btn.toggle-btn {
  border-width: 1px;
  border-color: #d3d3d3;
}
.btn.toggle-btn[aria-pressed="true"] {
  text-decoration: underline;
  border-color: #4d4d4d;
}
.btn__danger {
  color: #fff;
  background-color: #ca3c3c;
  border-color: #bd2130;
}
.btn__filter {
  border-color: lightgrey;
}
.btn__primary {
  color: #fff;
  background-color: #000;
}
.btn-group {
  display: flex;
  justify-content: space-between;
}
.btn-group > * {
  flex: 1 1 49%;
}
.btn-group > * + * {
  margin-left: 0.8rem;
}
.label-wrapper {
  margin: 0;
  flex: 0 0 100%;
  text-align: center;
}
.visually-hidden {
  position: absolute !important;
  height: 1px;
  width: 1px;
  overflow: hidden;
  clip: rect(1px 1px 1px 1px);
  clip: rect(1px, 1px, 1px, 1px);
  white-space: nowrap;
}
[class*="stack"] > * {
  margin-top: 0;
  margin-bottom: 0;
}
.stack-small > * + * {
  margin-top: 1.25rem;
}
.stack-large > * + * {
  margin-top: 2.5rem;
}
@media screen and (min-width: 550px) {
  .stack-small > * + * {
    margin-top: 1.4rem;
  }
  .stack-large > * + * {
    margin-top: 2.8rem;
  }
}
.stack-exception {
  margin-top: 1.2rem;
}
/* END GLOBAL STYLES */
.todoapp {
  background: #fff;
  margin: 2rem 0 4rem 0;
  padding: 1rem;
  position: relative;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2), 0 2.5rem 5rem 0 rgba(0, 0, 0, 0.1);
}
@media screen and (min-width: 550px) {
  .todoapp {
    padding: 4rem;
  }
}
.todoapp > * {
  max-width: 50rem;
  margin-left: auto;
  margin-right: auto;
}
.todoapp > form {
  max-width: 100%;
}
.todoapp > h1 {
  display: block;
  max-width: 100%;
  text-align: center;
  margin: 0;
  margin-bottom: 1rem;
}
.label__lg {
  line-height: 1.01567;
  font-weight: 300;
  padding: 0.8rem;
  margin-bottom: 1rem;
  text-align: center;
}
.input__lg {
  padding: 2rem;
  border: 2px solid #000;
}
.input__lg:focus {
  border-color: #4d4d4d;
  box-shadow: inset 0 0 0 2px;
}
[class*="__lg"] {
  display: inline-block;
  width: 100%;
  font-size: 1.9rem;
}
[class*="__lg"]:not(:last-child) {
  margin-bottom: 1rem;
}
@media screen and (min-width: 620px) {
  [class*="__lg"] {
    font-size: 2.4rem;
  }
}
.filters {
  width: 100%;
  margin: unset auto;
}
/* Todo item styles */
.todo {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.todo > * {
  flex: 0 0 100%;
}
.todo-text {
  width: 100%;
  min-height: 4.4rem;
  padding: 0.4rem 0.8rem;
  border: 2px solid #565656;
}
.todo-text:focus {
  box-shadow: inset 0 0 0 2px;
}
/* CHECKBOX STYLES */
.c-cb {
  box-sizing: border-box;
  font-family: Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  font-weight: 400;
  font-size: 1.6rem;
  line-height: 1.25;
  display: block;
  position: relative;
  min-height: 44px;
  padding-left: 40px;
  clear: left;
}
.c-cb > label::before,
.c-cb > input[type="checkbox"] {
  box-sizing: border-box;
  top: -2px;
  left: -2px;
  width: 44px;
  height: 44px;
}
.c-cb > input[type="checkbox"] {
  -webkit-font-smoothing: antialiased;
  cursor: pointer;
  position: absolute;
  z-index: 1;
  margin: 0;
  opacity: 0;
}
.c-cb > label {
  font-size: inherit;
  font-family: inherit;
  line-height: inherit;
  display: inline-block;
  margin-bottom: 0;
  padding: 8px 15px 5px;
  cursor: pointer;
  touch-action: manipulation;
}
.c-cb > label::before {
  content: "";
  position: absolute;
  border: 2px solid currentColor;
  background: transparent;
}
.c-cb > input[type="checkbox"]:focus + label::before {
  border-width: 4px;
  outline: 3px dashed #228bec;
}
.c-cb > label::after {
  box-sizing: content-box;
  content: "";
  position: absolute;
  top: 11px;
  left: 9px;
  width: 18px;
  height: 7px;
  transform: rotate(-45deg);
  border: solid;
  border-width: 0 0 5px 5px;
  border-top-color: transparent;
  opacity: 0;
  background: transparent;
}
.c-cb > input[type="checkbox"]:checked + label::after {
  opacity: 1;
}
```

复制到剪贴板

保存并回顾您的浏览器，您的应用现在应该具有合理的样式。

## [概括](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_todo_list_beginning#summary)

现在我们的待办事项列表应用实际上看起来更像一个真正的应用！问题是：它实际上没有做任何事情。我们将在下一章开始修复它！

# 组件化我们的 React 应用程序

在这一点上，我们的应用程序是一个整体。在我们让它做事之前，我们需要将它分解成可管理的、描述性的组件。React 对于什么是组件和什么不是组件没有任何硬性规定——这取决于你！在本文中，我们将向您展示一种将我们的应用程序分解为组件的明智方法。

## [定义我们的第一个组件](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#defining_our_first_component)

在您进行一些练习之前，定义组件似乎很棘手，但要点是：

- 如果它代表您的应用程序的明显“块”，则它可能是一个组件
- 如果它经常被重用，它可能是一个组件。

第二个要点特别有价值：用常见的 UI 元素制作组件允许您在一个地方更改代码，并在使用该组件的任何地方查看这些更改。您也不必立即将所有内容分解为组件。让我们以第二个要点为灵感，用最重用、最重要的 UI 部分制作一个组件：待办事项列表项。

## [做一个 ``](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#make_a_todo_)

在我们制作组件之前，我们应该为它创建一个新文件。事实上，我们应该为我们的组件创建一个目录。以下命令创建一个`components`目录，然后在其中创建一个名为`Todo.js`. 在运行这些之前，请确保您位于应用程序的根目录中！

```
mkdir src/components
touch src/components/Todo.js
```

复制到剪贴板

我们的新`Todo.js`文件目前是空的！打开它并给它第一行：

```
import React from "react";
```

复制到剪贴板

由于我们将创建一个名为 的组件`Todo`，因此您也可以开始为该组件添加代码`Todo.js`，如下所示。在这段代码中，我们定义了函数并将其导出到同一行：

```
export default function Todo() {
  return (

  );
}
```

复制到剪贴板

到目前为止一切正常，但是我们的组件必须返回一些东西！返回到`src/App.js`，[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)从无序列表中复制第一个，并将其粘贴到其中`Todo.js`，使其显示如下：

```
export default function Todo() {
  return (
    <li className="todo stack-small">
      <div className="c-cb">
        <input id="todo-0" type="checkbox" defaultChecked={true} />
        <label className="todo-label" htmlFor="todo-0">
          Eat
        </label>
      </div>
      <div className="btn-group">
        <button type="button" className="btn">
          Edit <span className="visually-hidden">Eat</span>
        </button>
        <button type="button" className="btn btn__danger">
          Delete <span className="visually-hidden">Eat</span>
        </button>
      </div>
    </li>
  );
}
```

复制到剪贴板

**注意：**组件必须总是返回一些东西。如果在将来的任何时候您尝试渲染一个不返回任何内容的组件，React 将在您的浏览器中显示错误。

我们的`Todo`组件是完整的，至少现在是这样；现在我们可以使用它了。在 中`App.js`，在要导入的文件顶部附近添加以下行`Todo`：

```
import Todo from "./components/Todo";
```

复制到剪贴板

导入此组件后，您可以使用组件调用替换其中的所有`<li>`元素。你应该这样读：`App.js``<Todo />``<ul>`

```
<ul
  role="list"
  className="todo-list stack-large stack-exception"
  aria-labelledby="list-heading"
>
  <Todo />
  <Todo />
  <Todo />
</ul>
```

复制到剪贴板

当您回头查看浏览器时，您会注意到一些不幸的事情：您的列表现在重复了第一个任务三遍！

![我们的待办事项列表应用程序，由于标签被硬编码到组件中，所以有重复的待办事项组件](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components/todo-list-repeating-todos.png)

我们不仅要吃；我们还有其他事情要做——嗯——要做。接下来我们将看看如何让不同的组件调用呈现独特的内容。

## [打造*独一无二的* ``](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#make_a_unique_todo_)

组件很强大，因为它们让我们可以重用我们的 UI 部分，并引用一个地方作为该 UI 的来源。问题是，我们通常不想重用每个组件；我们希望重复使用大部分零件，并更改小零件。这就是道具的用武之地。

### [里面有什么`name`？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#whats_in_a_name)

为了跟踪我们想要完成的任务的名称，我们应该确保每个`<Todo />`组件呈现一个唯一的名称。

在 中`App.js`，给每个人`<Todo />`一个名字道具。让我们使用我们之前的任务名称：

```
<Todo name="Eat" />
<Todo name="Sleep" />
<Todo name="Repeat" />
```

复制到剪贴板

当您的浏览器刷新时，您将看到……与以前完全相同的内容。我们提供了`<Todo />`一些道具，但我们还没有使用它们。让我们回过头来`Todo.js`解决这个问题。

首先修改您的`Todo()`函数定义，使其`props`作为参数。你可以`console.log()`你`props`像我们以前那样，如果你想查看它们是否已被该组件正确接收。

一旦您确信您的组件正在获取它的`props`，您就可以`Eat`用您的`name`道具替换所有出现的。请记住：当您处于 JSX 表达式的中间时，您可以使用花括号来注入变量的值。

把所有这些放在一起，你的`Todo()`函数应该是这样的：

```
export default function Todo(props) {
  return (
    <li className="todo stack-small">
      <div className="c-cb">
        <input id="todo-0" type="checkbox" defaultChecked={true} />
        <label className="todo-label" htmlFor="todo-0">
          {props.name}
        </label>
      </div>
      <div className="btn-group">
        <button type="button" className="btn">
          Edit <span className="visually-hidden">{props.name}</span>
        </button>
        <button type="button" className="btn btn__danger">
          Delete <span className="visually-hidden">{props.name}</span>
        </button>
      </div>
    </li>
  );
}
```

复制到剪贴板

*现在*您的浏览器应该显示三个独特的任务。另一个问题仍然存在：默认情况下它们仍然被选中。

![我们的待办事项列表，具有不同的待办事项标签，现在它们作为道具传递到组件中](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components/todo-list-unique-todos.png)

### [是`completed`吗？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#is_it_completed)

在我们原来的静态列表中，只`Eat`被选中。再一次，我们想重用 组成组件的*大部分*UI `<Todo />`，但要改变一件事。这是另一个道具的好工作！`<Todo />`在`App.js`的新道具中进行每次调用`completed`。第一个 ( `Eat`) 的值应为`true`; 其余的应该是`false`：

```
<Todo name="Eat" completed={true} />
<Todo name="Sleep" completed={false} />
<Todo name="Repeat" completed={false} />
```

复制到剪贴板

和以前一样，我们必须回过头`Todo.js`来实际使用这些道具。更改 上的`defaultChecked`属性`<input />`，使其值等于`completed`道具。完成后，Todo 组件的`<input />`元素将如下所示：

```
<input id="todo-0" type="checkbox" defaultChecked={props.completed} />
```

复制到剪贴板

并且您的浏览器应该更新以显示仅`Eat`被检查：

![我们的待办事项列表应用程序，现在具有不同的选中状态 - 某些复选框已选中，其他复选框未选中](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components/todo-list-differing-checked-states.png)

如果您更改每个`<Todo />`组件的`completed`prop，您的浏览器将相应地选中或取消选中等效的渲染复选框。

### [`id`请给我一些](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#gimme_some_id_please)

现在，我们的`<Todo />`组件为每个任务赋予了一个`id`属性`todo-0`。这是糟糕的 HTML，因为[`id`属性](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id)必须是唯一的（它们被 CSS、JavaScript 等用作文档片段的唯一标识符）。这意味着我们应该给我们的组件一个`id`prop，它为每个`Todo`.

为了遵循我们最初的模式，让我们为`<Todo />`组件的每个实例提供一个格式为 的 ID `todo-i`，其中`i`每次都会变大：

```
<Todo name="Eat" completed={true} id="todo-0" />
<Todo name="Sleep" completed={false} id="todo-1" />
<Todo name="Repeat" completed={false} id="todo-2" />
```

复制到剪贴板

现在返回`Todo.js`并使用`id`道具。它需要替换元素的`id`属性值`<input />`，以及其标签的`htmlFor`属性值：

```
<div className="c-cb">
  <input id={props.id} type="checkbox" defaultChecked={props.completed} />
  <label className="todo-label" htmlFor={props.id}>
    {props.name}
  </label>
</div>
```

复制到剪贴板

## [到现在为止还挺好？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#so_far_so_good)

到目前为止，我们很好地利用了 React，但我们可以做得更好！我们的代码是重复的。渲染我们`<Todo />`组件的三行代码几乎相同，只有一个区别：每个 prop 的值。

我们可以使用 JavaScript 的一项核心能力：迭代来清理我们的代码。要使用迭代，我们应该首先重新考虑我们的任务。

## [作为数据的任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#tasks_as_data)

我们的每个任务目前都包含三条信息：它的名称、它是否被检查过以及它的唯一 ID。该数据可以很好地转换为对象。由于我们有多个任务，因此一组对象可以很好地表示这些数据。

在 中`src/index.js`，`const`在最终导入的下面创建一个新的，但在上面`ReactDOM.render()`：

```
const DATA = [
  { id: "todo-0", name: "Eat", completed: true },
  { id: "todo-1", name: "Sleep", completed: false },
  { id: "todo-2", name: "Repeat", completed: false }
];
```

复制到剪贴板

接下来，我们将传递`DATA`to`<App />`作为道具，称为`tasks`。最后一行`src/index.js`应该是这样的：

```
ReactDOM.render(<App tasks={DATA} />, document.getElementById("root"));
```

复制到剪贴板

此数组现在可作为 .app 组件使用`props.tasks`。`console.log()`如果你愿意，你可以检查一下。

**注意：** `ALL_CAPS`常量名在 JavaScript 中没有特殊意义；它们是一个约定，告诉其他开发人员“这些数据在此处定义后将永远不会改变”。

## [迭代渲染](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#rendering_with_iteration)

为了渲染我们的对象数组，我们必须将每个对象都变成一个`<Todo />`组件。JavaScript的为我们提供了将数据转换成别的东西数组方法：[`Array.prototype.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)。

在 的 return 语句上方`App()`，创建一个新的`const`调用`taskList`并用于对其`map()`进行转换。让我们先把我们的`tasks`数组变成简单的东西：`name`每个任务的：

```
const taskList = props.tasks?.map(task => task.name);
```

复制到剪贴板

让我们尝试更换所有的孩子`<ul>`有`taskList`：

```
<ul
  role="list"
  className="todo-list stack-large stack-exception"
  aria-labelledby="list-heading"
>
  {taskList}
</ul>
```

复制到剪贴板

这使我们能够再次显示所有组件，但我们还有更多工作要做：浏览器当前将每个任务的名称呈现为非结构化文本。我们缺少我们的 HTML 结构 -`<li>`和它的复选框和按钮！

![我们的待办事项列表应用程序的待办事项标签刚刚显示在一行上](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components/todo-list-unstructured-names.png)

为了解决这个问题，我们需要`<Todo />`从我们的`map()`函数中返回一个组件——记住 JSX 允许我们混合使用 JavaScript 和标记结构！让我们尝试以下而不是我们已经拥有的：

```
 const taskList = props.tasks.map(task => <Todo />);
```

复制到剪贴板

再看看你的应用程序；现在我们的任务看起来更像以前，但他们缺少任务本身的名称。请记住，每个任务中，我们在映射有`id`，`name`和`checked`我们想传递到我们的性能`<Todo />`组件。如果我们把这些知识放在一起，我们会得到这样的代码：

```
const taskList = props.tasks.map(task => (
  <Todo id={task.id} name={task.name} completed={task.completed} />
));
```

复制到剪贴板

现在该应用程序看起来像以前一样，并且我们的代码不再重复。

## [唯一键](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#unique_keys)

现在 React 正在从数组中渲染我们的任务，它必须跟踪哪个是哪个以便正确渲染它们。React 试图通过自己的猜测来跟踪事物，但我们可以通过将`key`prop传递给我们的`<Todo />`组件来帮助它。`key`是一个由 React 管理的特殊道具——你不能将这个词`key`用于任何其他目的。

因为键应该是唯一的，所以我们将重新使用`id`每个任务对象的键作为它的键。`taskList`像这样更新你的常量：

```
const taskList = props.tasks.map(task => (
    <Todo
      id={task.id}
      name={task.name}
      completed={task.completed}
      key={task.id}
    />
  )
);
```

复制到剪贴板

**您应该始终将唯一键传递给您使用迭代渲染的任何内容。**在您的浏览器中没有什么明显的变化，但是如果您不使用唯一键，React 会将警告记录到您的控制台，您的应用程序可能会出现奇怪的行为！

## [组件化应用程序的其余部分](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#componentizing_the_rest_of_the_app)

现在我们已经整理了最重要的组件，我们可以将应用程序的其余部分变成组件。记住组件要么是明显的 UI 片段，要么是重用的 UI 片段，或者两者兼而有之，我们可以再制作两个组件：

- `<Form/>`
- `<FilterButton/>`

由于我们知道我们需要两者，我们可以使用终端命令批处理一些文件创建工作。在终端中运行此命令，注意您位于应用程序的根目录中：

```
touch src/components/Form.js src/components/FilterButton.js
```

复制到剪贴板

### [这 ``](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#the_form_)

打开`components/Form.js`并执行以下操作：

- `React`在文件顶部导入，就像我们在`Todo.js`.
- 为自己创建一个`Form()`与 具有相同基本结构的新组件`Todo()`，然后导出该组件。
- `<form>`从内部复制标签以及它们之间的所有内容，然后将它们`App.js`粘贴到`Form()`的`return`语句中。
- `Form`在文件末尾导出。

你的`Form.js`文件应该是这样的：

```
import React from "react";

function Form(props) {
  return (
    <form>
      <h2 className="label-wrapper">
        <label htmlFor="new-todo-input" className="label__lg">
          What needs to be done?
        </label>
      </h2>
      <input
        type="text"
        id="new-todo-input"
        className="input input__lg"
        name="text"
        autoComplete="off"
      />
      <button type="submit" className="btn btn__primary btn__lg">
        Add
      </button>
    </form>
  );
}

export default Form;
```

复制到剪贴板

### [<过滤按钮 />](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#the_filterbutton_)

难道你没有创造同样的事情`Form.js`里面`FilterButton.js`，但调用组件`FilterButton()`和复制HTML为第一个按钮里面`<div>`与元素`class`的`filters`从`App.js`进`return`言。

该文件应如下所示：

```
import React from "react";

function FilterButton(props) {
  return (
    <button type="button" className="btn toggle-btn" aria-pressed="true">
      <span className="visually-hidden">Show </span>
      <span>all </span>
      <span className="visually-hidden"> tasks</span>
    </button>
  );
}

export default FilterButton;
```

复制到剪贴板

**注意：**您可能会注意到我们在这里犯了与我们第一次为`<Todo />`组件犯的错误相同的错误，因为每个按钮都是相同的。没关系！我们稍后将在[返回过滤器按钮中](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#back_to_the_filter_buttons)修复此组件。

## [导入我们所有的组件](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#importing_all_our_components)

让我们使用我们的新组件。

`import`在 , 的顶部添加更多语句`App.js`以导入它们。

然后，更新`return`语句以`App()`呈现我们的组件。完成后，`App.js`将是这样的：

```
import React from "react";
import Form from "./components/Form";
import FilterButton from "./components/FilterButton";
import Todo from "./components/Todo";

function App(props) {
  const taskList = props.tasks.map(task => (
    <Todo
        id={task.id}
        name={task.name}
        completed={task.completed}
        key={task.id}
      />
    )
  );
  return (
    <div className="todoapp stack-large">
      <h1>TodoMatic</h1>
      <Form />
      <div className="filters btn-group stack-exception">
        <FilterButton />
        <FilterButton />
        <FilterButton />
      </div>
      <h2 id="list-heading">3 tasks remaining</h2>
      <ul
        role="list"
        className="todo-list stack-large stack-exception"
        aria-labelledby="list-heading"
      >
        {taskList}
      </ul>
    </div>
  );
}

export default App;
```

复制到剪贴板

有了这个，我们*几乎*准备好在我们的 React 应用程序中处理一些交互性了！

## [概括](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_components#summary)

这就是本文的内容——我们已经深入探讨了如何将您的应用程序很好地分解为组件，并有效地呈现它们。现在我们将继续看看我们如何在 React 中处理事件，并开始添加一些交互性。

# React 交互性：事件和状态

随着我们的组件计划的制定，现在是时候开始将我们的应用程序从完全静态的 UI 更新为真正允许我们进行交互和更改的 UI。在本文中，我们将这样做，在此过程中深入研究事件和状态，最终得到一个应用程序，我们可以在其中成功添加和删除任务，并将任务切换为已完成。

## [处理事件](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#handling_events)

如果您之前只编写过原生 JavaScript，您可能习惯于拥有一个单独的 JavaScript 文件，您可以在其中查询一些 DOM 节点并将侦听器附加到它们。例如：

```
const btn = document.querySelector('button');

btn.addEventListener('click', () => {
  alert("hi!");
});
```

复制到剪贴板

在 React 中，我们直接在 JSX 中的元素上编写事件处理程序，如下所示：

```
<button
  type="button"
  onClick={() => alert("hi!")}
>
  Say hi!
</button>
```

复制到剪贴板

**注意：**对于倾向于建议不要在 HTML 上使用内联事件处理程序的最佳实践建议，这似乎违反直觉，但请记住，JSX 实际上是您的 JavaScript 的一部分。

在上面的例子中，我们向元素添加了一个`onClick`属性`<button>`。该属性的值是一个触发简单警报的函数。

该`onClick`属性在这里有特殊含义：它告诉 React 在用户单击按钮时运行给定的函数。还有一些其他的事情需要注意：

- 的驼峰式性质`onClick`很重要——JSX 不会识别`onclick`（同样，它已经在 JavaScript 中用于特定目的，这是相关但不同的——标准[`onclick`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onclick)处理程序属性）。
- 所有浏览器事件在 JSX 中都遵循这种格式 - `on`，后跟事件的名称。

让我们将其应用到我们的应用程序中，从`Form.js`组件开始。

### [处理表单提交](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#handling_form_submission)

在`Form()`组件函数的顶部，创建一个名为 的函数`handleSubmit()`。此函数应[防止`submit`事件的默认行为](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#preventing_default_behavior)。之后，它应该触发一个`alert()`，它可以说出你想要的任何内容。它最终应该看起来像这样：

```
function handleSubmit(e) {
  e.preventDefault();
  alert('Hello, world!');
}
```

复制到剪贴板

要使用此函数，请`onSubmit`向[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)元素添加一个属性，并将其值设置为`handleSubmit`函数：

```
<form onSubmit={handleSubmit}>
```

复制到剪贴板

现在，如果您返回浏览器并单击“添加”按钮，您的浏览器将显示一个带有“Hello, world!”字样的警报对话框。- 或者你选择在那里写的任何东西。

## [回调道具](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#callback_props)

在 React 应用程序中，交互性很少仅限于一个组件：发生在一个组件中的事件会影响应用程序的其他部分。当我们开始赋予自己创建新任务的能力时，`<Form />`组件中发生的事情将影响`<App />`.

我们希望我们的`handleSubmit()`函数最终帮助我们创建一个新任务，因此我们需要一种将信息从 传递`<Form />`到 的方法`<App />`。我们不能像使用标准 props 将数据从父级传递给子级一样，将数据从子级传递到父级。相反，我们可以编写一个函数`<App />`，将表单中的一些数据作为输入，然后将该函数`<Form />`作为道具传递给。这个函数作为道具被称为回调道具。一旦我们有了回调道具，我们就可以在内部调用它`<Form />`以将正确的数据发送到`<App />`.

### [通过回调处理表单提交](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#handling_form_submission_via_callbacks)

在我们的`App()`组件函数的顶部，创建一个名为的函数，`addTask()`它有一个参数`name`：

```
function addTask(name) {
  alert(name);
}
```

复制到剪贴板

接下来，我们将传递`addTask()`到`<Form />`作为道具。道具可以有任何你想要的名字，但选择一个你以后会理解的名字。类似的东西`addTask`，因为它匹配函数的名称以及函数将执行的操作。您的`<Form />`组件调用应更新如下：

```
<Form addTask={addTask} />
```

复制到剪贴板

最后，您可以`handleSubmit()`在`<Form />`组件的函数中使用这个 prop ！更新如下：

```
function handleSubmit(e) {
  e.preventDefault();
  props.addTask("Say hello!");
}
```

复制到剪贴板

单击浏览器中的“添加”按钮将证明`addTask()`回调函数有效，但如果我们能收到警报以显示我们在输入字段中输入的内容，那就太好了！这就是我们接下来要做的。

**注意：**我们决定命名我们的回调道具`addTask`，以便于理解道具将做什么。你在 React 代码中可能会遇到的另一个常见约定是在回调道具名称前加上单词`on`，然后是将导致它们运行的事件的名称。例如，我们可以给我们的表单一个`onSubmit`值为 的道具`addTask`。

## [状态和`useState`钩子](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#state_and_the_usestate_hook)

到目前为止，我们已经使用 props 通过我们的组件传递数据，这对我们很有用。然而，既然我们正在处理用户输入和数据更新，我们还需要更多的东西。

一方面，道具来自组件的父级。我们`<Form />`不会为我们的任务继承一个新名称；我们的`<input />` 元素直接位于 内部`<Form />`，因此`<Form/>`将直接负责创建该新名称。我们不能要求`<Form />`自发创建自己的道具，但我们*可以*要求它为我们跟踪一些自己的数据。组件本身拥有的此类数据称为**state**。状态是 React 的另一个强大工具，因为组件不仅*拥有*状态，而且可以在以后*更新*状态。无法更新组件接收到的 props；只是为了阅读它们。

React 提供了各种特殊的功能，使我们能够为组件提供新的功能，例如状态。这些函数称为**hooks**，`useState`顾名思义，hook 正是我们需要的一个，以便为我们的组件提供某种状态。

要使用 React 钩子，我们需要从 react 模块导入它。在 中`Form.js`，更改您的第一行，使其如下所示：

```
import React, { useState } from "react";
```

复制到剪贴板

这允许我们自己导入`useState()`函数，并在此文件的任何位置使用它。

`useState()`为组件创建一段状态，它的唯一参数决定了该状态的*初始值*。它返回两件事：状态和一个可用于稍后更新状态的函数。

这一次需要做很多事情，所以让我们尝试一下。我们将让自己成为一个`name`状态，以及一个更新`name`状态的函数。

在你的`handleSubmit()`函数上面写下以下内容，里面`Form()`：

```
const [name, setName] = useState('Use hooks!');
```

复制到剪贴板

这行代码发生了什么？

- 我们将初始`name`值设置为“使用钩子！”。
- 我们正在定义一个函数，其工作是修改`name`，称为`setName()`。
- `useState()`返回这两个东西，所以我们使用[数组解构](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)将它们都捕获到单独的变量中。

### [阅读状态](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#reading_state)

您可以立即看到正在运行的`name`状态。`value`向表单的输入添加一个属性，并将其值设置为`name`。您的浏览器将呈现“使用钩子！” 在输入里面。

```
<input
  type="text"
  id="new-todo-input"
  className="input input__lg"
  name="text"
  autoComplete="off"
  value={name}
/>
```

复制到剪贴板

更改“使用钩子！” 完成后变为空字符串；这就是我们想要的初始状态。

```
const [name, setName] = useState('');
```

复制到剪贴板

### [读取用户输入](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#reading_user_input)

在我们更改 的值之前`name`，我们需要在用户键入时捕获他们的输入。为此，我们可以监听`onChange`事件。让我们写一个`handleChange()`函数，并在`<input />`标签上监听它。

```
// near the top of the `Form` component
function handleChange(e) {
  console.log("Typing!");
}

// Down in the return statement
<input
  type="text"
  id="new-todo-input"
  className="input input__lg"
  name="text"
  autoComplete="off"
  value={name}
  onChange={handleChange}
/>
```

复制到剪贴板

目前，您输入的值不会随着您的输入而改变，但您的浏览器会记录“正在输入！”这个词。到 JavaScript 控制台，所以我们知道我们的事件侦听器附加到输入。为了改变输入的值，我们必须使用我们的`handleChange()`函数来更新我们的`name`状态。

要在更改时读取输入字段的内容，您可以访问输入的`value`属性。我们可以`handleChange()`通过阅读在里面做到这一点`e.target.value`。`e.target`代表触发`change`事件的元素——这是我们的输入。所以，`value`是里面的文字。

您可以`console.log()`在浏览器的控制台中查看此值。

```
function handleChange(e) {
  console.log(e.target.value);
}
```

复制到剪贴板

### [更新状态](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#updating_state)

日志记录是不够的——我们想要在输入值更改时实际存储名称的更新状态！更改`console.log()`为`setName()`，如下所示：

```
function handleChange(e) {
  setName(e.target.value);
}
```

复制到剪贴板

现在我们需要改变我们的`handleSubmit()`函数，让它`props.addTask`以名称作为参数调用——还记得我们的回调道具吗？这将用于将任务发送回`App`组件，因此我们可以在以后将其添加到我们的任务列表中。作为一个好的做法，您应该在表单提交后清除输入，因此我们将`setName()`再次使用空字符串调用来执行此操作：

```
function handleSubmit(e) {
  e.preventDefault();
  props.addTask(name);
  setName("");
}
```

复制到剪贴板

最后，您可以在浏览器的输入字段中输入一些内容，然后单击“*添加”* ——您输入的任何内容都会出现在警告对话框中。

你的`Form.js`文件现在应该是这样的：

```
import React, { useState } from "react";

function Form(props) {
  const [name, setName] = useState("");

  function handleChange(e) {
    setName(e.target.value);
  }

  function handleSubmit(e) {
    e.preventDefault();
    props.addTask(name);
    setName("");
  }
  return (
    <form onSubmit={handleSubmit}>
      <h2 className="label-wrapper">
        <label htmlFor="new-todo-input" className="label__lg">
          What needs to be done?
        </label>
      </h2>
      <input
        type="text"
        id="new-todo-input"
        className="input input__lg"
        name="text"
        autoComplete="off"
        value={name}
        onChange={handleChange}
      />
      <button type="submit" className="btn btn__primary btn__lg">
        Add
      </button>
    </form>
  );
}

export default Form;
```

复制到剪贴板

**注意：**您会注意到的一件事是，您只需按“添加”按钮即可提交空任务，而无需输入任务名称。你能想出一种方法来禁止添加空任务吗？作为提示，您可能需要在`handleSubmit()`函数中添加某种检查。

## [综合起来：添加任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#putting_it_all_together_adding_a_task)

现在我们已经练习了事件、回调道具和钩子，我们准备编写允许用户从浏览器添加新任务的功能。

### [任务作为状态](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#tasks_as_state)

导入`useState`到`App.js`，以便我们可以将我们的任务存储在状态 - 将`React`导入行更新为以下内容：

```
import React, { useState } from "react";
```

复制到剪贴板

我们希望传递`props.tasks`到`useState()`挂钩-这将保持其初始状态。在 App() 函数定义的顶部添加以下内容：

```
const [tasks, setTasks] = useState(props.tasks);
```

复制到剪贴板

现在，我们可以更改我们的`taskList`映射，使其成为 mapping 的结果`tasks`，而不是`props.tasks`。您的`taskList`常量声明现在应如下所示：

```
const taskList = tasks.map(task => (
    <Todo
        id={task.id}
        name={task.name}
        completed={task.completed}
        key={task.id}
      />
    )
  );
```

复制到剪贴板

### [添加任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#adding_a_task)

我们现在有一个`setTasks`钩子，我们可以在我们的`addTask()`函数中使用它来更新我们的任务列表。但是有一个问题：我们不能只传递into的`name`参数，因为是一个对象数组并且是一个字符串。如果我们尝试这样做，数组将被替换为字符串。`addTask()``setTasks``tasks``name`

首先，我们需要放入`name`一个与我们现有任务具有相同结构的对象。在`addTask()`函数内部，我们将创建一个`newTask`对象以添加到数组中。

然后我们需要创建一个新数组，其中添加了这个新任务，然后将任务数据的状态更新为这个新状态。为此，我们可以使用 spread 语法[复制现有数组](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax#copy_an_array)，并在最后添加我们的对象。然后我们将这个数组传递`setTasks()`给更新状态。

把所有这些放在一起，你的`addTask()`函数应该是这样的：

```
function addTask(name) {
  const newTask = { id: "id", name: name, completed: false };
  setTasks([...tasks, newTask]);
}
```

复制到剪贴板

现在您可以使用浏览器向我们的数据添加任务了！在表单中输入任何内容并单击“添加”（或按Enter键），您将看到新的待办事项出现在 UI 中！

**然而，我们还有另一个问题**：我们的`addTask()`函数给每个任务都相同的`id`. 这不利于可访问性，并使 React 无法通过`key`prop区分未来的任务。事实上，React 会在你的 DevTools 控制台中给你一个警告——“警告：遇到两个拥有相同密钥的孩子......”

我们需要解决这个问题。制作唯一标识符是一个难题——JavaScript 社区为此编写了一些有用的库。我们会用[纳米](https://github.com/ai/nanoid) 因为它很小，而且很有效。

确保您位于应用程序的根目录中并运行以下终端命令：

```
npm install nanoid
```

复制到剪贴板

**注意：**如果您使用纱线，则需要以下内容：`yarn add nanoid`

现在我们可以导入`nanoid`到顶部，`App.js`以便我们可以使用它为我们的新任务创建唯一的 ID。首先，在顶部包含以下导入行`App.js`：

```
import { nanoid } from "nanoid";
```

复制到剪贴板

现在让我们更新，`addTask()`使每个任务 ID 成为前缀 todo- 加上由 nanoid 生成的唯一字符串。将您的`newTask`常量声明更新为：

```
const newTask = { id: "todo-" + nanoid(), name: name, completed: false };
```

复制到剪贴板

保存所有内容，然后再次尝试您的应用程序 - 现在您可以添加任务而不会收到有关重复 ID 的警告。

## [绕道：计数任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#detour_counting_tasks)

现在我们可以添加新任务了，您可能会注意到一个问题：我们的标题显示剩余 3 个任务，无论我们有多少个任务！我们可以通过计算`taskList`标题的长度并相应地更改标题的文本来解决此问题。

在你的`App()`定义中添加这个，在 return 语句之前：

```
const headingText = `${taskList.length} tasks remaining`;
```

复制到剪贴板

嗯。这几乎是正确的，除了如果我们的列表包含单个任务，标题仍将使用“任务”一词。我们也可以把它变成一个变量。将刚才添加的代码更新如下：

```
const tasksNoun = taskList.length !== 1 ? 'tasks' : 'task';
const headingText = `${taskList.length} ${tasksNoun} remaining`;
```

复制到剪贴板

现在您可以用`headingText`变量替换列表标题的文本内容。`<h2>`像这样更新：

```
<h2 id="list-heading">{headingText}</h2>
```

复制到剪贴板

## [完成一项任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#completing_a_task)

您可能会注意到，当您单击复选框时，它会相应地选中和取消选中。作为 HTML 的一项功能，浏览器知道如何在没有我们帮助的情况下记住选中或取消选中哪些复选框输入。但是，此功能隐藏了一个问题：切换复选框不会更改我们的 React 应用程序中的状态。这意味着浏览器和我们的应用程序现在不同步。我们必须编写自己的代码来使浏览器与我们的应用程序同步。

### [证明错误](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#proving_the_bug)

在我们解决问题之前，让我们观察它的发生。

我们将从`toggleTaskCompleted()`在我们的`App()`组件中编写一个函数开始。这个函数将有一个`id`参数，但我们还不会使用它。现在，我们将数组中的第一个任务记录到控制台——我们将检查在浏览器中选中或取消选中它时会发生什么：

将其添加到您的`taskList`常量声明上方：

```
function toggleTaskCompleted(id) {
  console.log(tasks[0])
}
```

复制到剪贴板

接下来，我们将添加`toggleTaskCompleted`到`<Todo />`我们的内部渲染的每个组件的道具中`taskList`；像这样更新它：

```
const taskList = tasks.map(task => (
  <Todo
      id={task.id}
      name={task.name}
      completed={task.completed}
      key={task.id}
      toggleTaskCompleted={toggleTaskCompleted}
  />
));
```

复制到剪贴板

接下来，转到您的`Todo.js`组件`onChange`并向您的`<input />`元素添加一个处理程序，该处理程序应使用匿名函数以`props.toggleTaskCompleted()`参数`props.id`. 现在`<input />`应该是这样的：

```
<input
  id={props.id}
  type="checkbox"
  defaultChecked={props.completed}
  onChange={() => props.toggleTaskCompleted(props.id)}
/>
```

复制到剪贴板

保存所有内容并返回到您的浏览器，您会注意到我们的第一个任务“吃”已被选中。打开 JavaScript 控制台，然后单击 Eat 旁边的复选框。正如我们所料，它取消选中。但是，您的 JavaScript 控制台会记录如下内容：

```
Object { id: "task-0", name: "Eat", completed: true }
```

复制到剪贴板

该复选框在浏览器中取消选中，但我们的控制台告诉我们 Eat 仍然完成。我们接下来会解决这个问题！

### [将浏览器与我们的数据同步](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#synchronizing_the_browser_with_our_data)

让我们重新审视我们`toggleTaskCompleted()`在`App.js`. 我们希望它只更改`completed`被切换的任务的属性，而不要管其他所有任务。为此，我们将`map()`检查任务列表并更改我们已完成的任务列表。

将您的`toggleTaskCompleted()`函数更新为以下内容：

```
function toggleTaskCompleted(id) {
  const updatedTasks = tasks.map(task => {
    // if this task has the same ID as the edited task
    if (id === task.id) {
      // use object spread to make a new object
      // whose `completed` prop has been inverted
      return {...task, completed: !task.completed}
    }
    return task;
  });
  setTasks(updatedTasks);
}
```

复制到剪贴板

在这里，我们定义了一个`updatedTasks`映射到原始`tasks`数组的常量。如果任务的`id`属性与`id`提供给函数的属性匹配，我们使用[对象扩展语法](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) 创建一个新对象，并`checked`在返回之前切换该对象的属性。如果不匹配，我们返回原始对象。

然后我们调用`setTasks()`这个新数组来更新我们的状态。

## [删除任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#deleting_a_task)

删除任务将遵循与切换其完成状态类似的模式：我们需要定义一个函数来更新我们的状态，然后将该函数`<Todo />`作为 prop传入并在正确的事件发生时调用它。

### [该`deleteTask`回调道具](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#the_deletetask_callback_prop)

在这里，我们将首先`deleteTask()`在您的`App`组件中编写一个函数。就像`toggleTaskCompleted()`，这个函数将接受一个`id`参数，我们将把它记录`id`到控制台开始。添加以下内容`toggleTaskCompleted()`：

```
function deleteTask(id) {
  console.log(id)
}
```

复制到剪贴板

接下来，向我们的`<Todo />`组件数组添加另一个回调道具：

```
const taskList = tasks.map(task => (
  <Todo
    id={task.id}
    name={task.name}
    completed={task.completed}
    key={task.id}
    toggleTaskCompleted={toggleTaskCompleted}
    deleteTask={deleteTask}
  />
));
```

复制到剪贴板

在 中`Todo.js`，我们想在`props.deleteTask()`按下“删除”按钮时调用。`deleteTask()`需要知道调用它的任务的 ID，所以它可以从状态中删除正确的任务。

更新 Todo.js 中的“删除”按钮，如下所示：

```
<button
  type="button"
  className="btn btn__danger"
  onClick={() => props.deleteTask(props.id)}
>
  Delete <span className="visually-hidden">{props.name}</span>
</button>
```

复制到剪贴板

现在，当您单击应用程序中的任何“删除”按钮时，您的浏览器控制台应记录相关任务的 ID。

## [从状态和 UI 中删除任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#deleting_tasks_from_state_and_ui)

现在我们知道`deleteTask()`被正确调用了，我们可以调用我们的`setTasks()`钩子`deleteTask()`从应用程序的状态以及在应用程序 UI 中直观地删除该任务。由于`setTasks()`需要一个数组作为参数，我们应该为它提供一个复制现有任务的新数组，*不包括*ID 与传入的任务匹配的任务`deleteTask()`。

这是使用[`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter). 我们可以测试每个任务，并从新数组中排除一个任务，如果它的`id`prop 与`id`传入的参数匹配`deleteTask()`。

更新文件中的`deleteTask()`函数`App.js`，如下所示：

```
function deleteTask(id) {
  const remainingTasks = tasks.filter(task => id !== task.id);
  setTasks(remainingTasks);
}
```

复制到剪贴板

再次试用您的应用。现在您应该可以从您的应用程序中删除任务了！

## [概括](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_events_state#summary)

一篇文章就够了。在这里，我们向您介绍了 React 如何处理事件和处理状态，并实现了添加任务、删除任务和切换任务完成的功能。我们快到了。在下一篇文章中，我们将实现编辑现有任务的功能，并在所有任务、已完成任务和未完成任务之间过滤任务列表。我们将在此过程中查看条件 UI 渲染。

# React 交互性：编辑、过滤、条件渲染

当我们的 React 旅程接近尾声时（至少现在是这样），我们将为我们的待办事项列表应用程序中的主要功能区域添加最后的润色。这包括允许您编辑现有任务，以及在所有任务、已完成任务和未完成任务之间过滤任务列表。我们将在此过程中查看条件 UI 渲染。

## [编辑任务名称](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#editing_the_name_of_a_task)

我们还没有用于编辑任务名称的用户界面。我们稍后会讲到。首先，我们至少可以`editTask()`在`App.js`. 它将类似于`deleteTask()`因为它需要一个`id`来找到它的目标对象，但它也需要一个`newName`包含名称的属性来更新任务。我们将使用[`Array.prototype.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)而不是[`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)因为我们想要返回一个带有一些更改的新数组，而不是从数组中删除某些内容。

`editTask()`在您的 App 组件中添加该函数，与其他函数位于同一位置：

```
function editTask(id, newName) {
  const editedTaskList = tasks.map(task => {
  // if this task has the same ID as the edited task
    if (id === task.id) {
      //
      return {...task, name: newName}
    }
    return task;
  });
  setTasks(editedTaskList);
}
```

复制到剪贴板

以与我们相同的方式作为道具传递`editTask`到我们的`<Todo />`组件中`deleteTask`：

```
const taskList = tasks.map(task => (
  <Todo
    id={task.id}
    name={task.name}
    completed={task.completed}
    key={task.id}
    toggleTaskCompleted={toggleTaskCompleted}
    deleteTask={deleteTask}
    editTask={editTask}
  />
));
```

复制到剪贴板

现在打开`Todo.js`。我们将进行一些重构。

## [用于编辑的 UI](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#a_ui_for_editing)

为了允许用户编辑任务，我们必须为他们提供一个用户界面。首先，像我们之前对组件所做的那样导入`useState`到组件中，将第一个 import 语句更新为：`Todo``App`

```
import React, { useState } from "react";
```

复制到剪贴板

我们现在将使用它来设置一个`isEditing`状态，其默认状态应该是`false`. 在`Todo(props) { … }`组件定义的顶部添加以下行：

```
const [isEditing, setEditing] = useState(false);
```

复制到剪贴板

接下来，我们将重新考虑`<Todo />`组件——从现在开始，我们希望它显示两个可能的“模板”之一，而不是目前使用的单个模板：

- “视图”模板，当我们只是查看一个待办事项时；这是我们迄今为止在教程中使用的内容。
- “编辑”模板，当我们编辑待办事项时。我们即将创建这个。

将此代码块复制到`Todo()`函数中，位于`useState()`钩子下方但`return`语句上方：

```
const editingTemplate = (
  <form className="stack-small">
    <div className="form-group">
      <label className="todo-label" htmlFor={props.id}>
        New name for {props.name}
      </label>
      <input id={props.id} className="todo-text" type="text" />
    </div>
    <div className="btn-group">
      <button type="button" className="btn todo-cancel">
        Cancel
        <span className="visually-hidden">renaming {props.name}</span>
      </button>
      <button type="submit" className="btn btn__primary todo-edit">
        Save
        <span className="visually-hidden">new name for {props.name}</span>
      </button>
    </div>
  </form>
);
const viewTemplate = (
  <div className="stack-small">
    <div className="c-cb">
        <input
          id={props.id}
          type="checkbox"
          defaultChecked={props.completed}
          onChange={() => props.toggleTaskCompleted(props.id)}
        />
        <label className="todo-label" htmlFor={props.id}>
          {props.name}
        </label>
      </div>
      <div className="btn-group">
        <button type="button" className="btn">
          Edit <span className="visually-hidden">{props.name}</span>
        </button>
        <button
          type="button"
          className="btn btn__danger"
          onClick={() => props.deleteTask(props.id)}
        >
          Delete <span className="visually-hidden">{props.name}</span>
        </button>
      </div>
  </div>
);
```

复制到剪贴板

我们现在已经在两个单独的常量中定义了两种不同的模板结构——“edit”和“view”。这意味着现在的`return`语句`<Todo />`是重复的——它还包含“视图”模板的定义。我们可以通过使用**条件渲染**来确定组件返回哪个模板并因此在 UI 中**渲染**来清理它。

## [条件渲染](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#conditional_rendering)

在 JSX 中，我们可以使用条件来更改浏览器呈现的内容。要在 JSX 中编写条件，我们可以使用[三元运算符](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)。

对于我们的`<Todo />`组件，我们的条件是“此任务是否正在编辑？” 更改`return`里面的语句`Todo()`，使其看起来像这样：

```
return <li className="todo">{isEditing ? editingTemplate : viewTemplate}</li>;
```

复制到剪贴板

您的浏览器应该像以前一样呈现您的所有任务。要查看编辑模板，您现在必须将代码中的默认`isEditing`状态从更改为；我们将在下一节中研究如何使编辑按钮切换它！`false``true`

## [切换``模板](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#toggling_the_todo__templates)

终于，我们准备好让我们的最终核心功能具有交互性。首先，我们希望在用户按下我们的 中的“编辑”按钮时调用`setEditing()`一个值，以便我们可以切换模板。`true``viewTemplate`

`viewTemplate`像这样更新“编辑”按钮：

```
<button type="button" className="btn" onClick={() => setEditing(true)}>
  Edit <span className="visually-hidden">{props.name}</span>
</button>
```

复制到剪贴板

现在我们将向`onClick`中的“取消”按钮添加相同的处理程序`editingTemplate`，但这次我们将设置`isEditing`为 ，`false`以便它将我们切换回视图模板。

`editingTemplate`像这样更新“取消”按钮：

```
<button
  type="button"
  className="btn todo-cancel"
  onClick={() => setEditing(false)}
>
  Cancel
  <span className="visually-hidden">renaming {props.name}</span>
</button>
```

复制到剪贴板

有了这段代码，您应该能够在待办事项中按“编辑”和“取消”按钮在模板之间切换。

![显示视图模板的吃待办事项，编辑和删除按钮可用](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering/view.png)

![显示编辑模板的吃待办事项项目，带有用于输入新名称的输入字段，以及可用的取消和保存按钮](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering/edit.png)

下一步是使编辑功能真正起作用。

## [从用户界面编辑](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#editing_from_the_ui)

我们将要做的大部分工作将反映我们所做的工作`Form.js`：当用户在我们的新输入字段中输入时，我们需要跟踪他们输入的文本；一旦他们提交了表单，我们就需要使用回调道具用任务的新名称更新我们的状态。

我们将首先创建一个用于存储和设置新名称的新钩子。仍在 中`Todo.js`，将以下内容放在现有钩子下方：

```
const [newName, setNewName] = useState('');
```

复制到剪贴板

接下来，创建一个`handleChange()`将设置新名称的函数；把它放在钩子下面但在模板之前：

```
function handleChange(e) {
  setNewName(e.target.value);
}
```

复制到剪贴板

现在我们将更新我们`editingTemplate`的`<input />`字段，设置一个`value`属性`newName`，并将我们的`handleChange()`函数绑定到它的`onChange`事件。更新如下：

```
<input
  id={props.id}
  className="todo-text"
  type="text"
  value={newName}
  onChange={handleChange}
/>
```

复制到剪贴板

最后，我们需要创建一个函数来处理编辑表单的`onSubmit`事件；在您添加的上一个函数下方添加以下内容：

```
function handleSubmit(e) {
  e.preventDefault();
  props.editTask(props.id, newName);
  setNewName("");
  setEditing(false);
}
```

复制到剪贴板

请记住，我们的`editTask()`回调道具需要我们正在编辑的任务的 ID 及其新名称。

`submit`通过将以下`onSubmit`处理程序添加到`editingTemplate`'s ，将此函数绑定到表单的事件`<form>`：

```
<form className="stack-small" onSubmit={handleSubmit}>
```

复制到剪贴板

您现在应该可以在浏览器中编辑任务了！

## [返回过滤器按钮](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#back_to_the_filter_buttons)

现在我们的主要功能已经完成，我们可以考虑我们的过滤器按钮。目前，它们重复“全部”标签，并且没有任何功能！我们将重新应用我们在`<Todo />`组件中使用的一些技能：

- 创建一个用于存储有源滤波器的钩子。
- 渲染一组`<FilterButton />`元素，允许用户在全部、已完成和未完成之间更改活动过滤器。

### [添加过滤器钩子](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#adding_a_filter_hook)

向您的`App()`函数添加一个新挂钩，用于读取和设置过滤器。我们希望使用默认过滤器，`All`因为我们所有的任务都应该在最初显示：

```
const [filter, setFilter] = useState('All');
```

复制到剪贴板

### [定义我们的过滤器](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#defining_our_filters)

我们现在的目标有两个：

- 每个过滤器都应该有一个唯一的名称。
- 每个过滤器都应该有一个独特的行为。

JavaScript 对象是将名称与行为相关联的好方法：每个键都是过滤器的名称；每个属性都是与该名称相关联的行为。

在 的顶部`App.js`，在我们的导入之下但在我们的`App()`函数之上，让我们添加一个名为 的对象`FILTER_MAP`：

```
const FILTER_MAP = {
  All: () => true,
  Active: task => !task.completed,
  Completed: task => task.completed
};
```

复制到剪贴板

的值`FILTER_MAP`是我们将用来过滤`tasks`数据数组的函数：

- 该`All`过滤器将显示所有的任务，所以我们返回`true`的所有任务。
- 该`Active`过滤器显示的任务，其`completed`道具`false`。
- 该`Completed`过滤器显示的任务，其`completed`道具`true`。

在我们之前添加的下面，添加以下内容——这里我们使用该[`Object.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)方法来收集 的数组`FILTER_NAMES`：

```
const FILTER_NAMES = Object.keys(FILTER_MAP);
```

复制到剪贴板

**注意：**我们在`App()`函数外部定义这些常量，因为如果它们在函数内部定义，则每次`<App />`组件重新渲染时都会重新计算它们，我们不希望那样。无论我们的应用程序做什么，这些信息都不会改变。

### [渲染过滤器](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#rendering_the_filters)

现在我们有了`FILTER_NAMES`数组，我们可以用它来渲染我们所有的三个过滤器。在`App()`函数内部，我们可以创建一个名为 的常量`filterList`，我们将使用它来映射我们的名称数组并返回一个`<FilterButton />`组件。记住，我们这里也需要钥匙。

在`taskList`常量声明下添加以下内容：

```
const filterList = FILTER_NAMES.map(name => (
  <FilterButton key={name} name={name}/>
));
```

复制到剪贴板

现在我们将用 this替换三个重复的`<FilterButton />`s 。替换以下内容：`App.js``filterList`

```
<FilterButton />
<FilterButton />
<FilterButton />
```

复制到剪贴板

有了这个：

```
{filterList}
```

复制到剪贴板

这还不行。我们还有一些工作要做。

### [交互式过滤器](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#interactive_filters)

为了使我们的过滤器按钮具有交互性，我们应该考虑它们需要使用哪些道具。

- 我们知道`<FilterButton />`应该报告它当前是否被按下，如果它的名称与我们过滤器状态的当前值匹配就应该被按下。
- 我们知道`<FilterButton />`需要回调来设置活动过滤器。我们可以直接使用我们的`setFilter`钩子。

更新您的`filterList`常量如下：

```
const filterList = FILTER_NAMES.map(name => (
  <FilterButton
    key={name}
    name={name}
    isPressed={name === filter}
    setFilter={setFilter}
  />
));
```

复制到剪贴板

就像我们之前对`<Todo />`组件所做的一样，我们现在必须更新`FilterButton.js`以利用我们提供的道具。执行以下每项操作，并记住使用花括号读取这些变量！

- 替换`all`为`{props.name}`。
- 将 的值设置`aria-pressed`为`{props.isPressed}`。
- 添加一个使用过滤器名称`onClick`调用的处理程序`props.setFilter()`。

完成所有这些后，您的`FilterButton()`函数应如下所示：

```
function FilterButton(props) {
  return (
    <button
      type="button"
      className="btn toggle-btn"
      aria-pressed={props.isPressed}
      onClick={() => props.setFilter(props.name)}
    >
      <span className="visually-hidden">Show </span>
      <span>{props.name}</span>
      <span className="visually-hidden"> tasks</span>
    </button>
  );
}
```

复制到剪贴板

再次访问您的浏览器。您应该看到不同的按钮已被赋予各自的名称。当您按下过滤器按钮时，您应该会看到其文本呈现出新的轮廓——这表明它已被选中。如果您在单击按钮时查看 DevTool 的页面检查器，您将看到`aria-pressed`属性值相应地发生变化。

![应用程序的三个过滤器按钮 - 全部、活动和已完成 - 围绕已完成的焦点突出显示](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering/filter-buttons.png)

然而，我们的按钮实际上仍然没有过滤 UI 中的待办事项！让我们结束这一切。

### [在 UI 中过滤任务](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#filtering_tasks_in_the_ui)

现在，我们`taskList`在`App()`任务状态映射中的常量状态并`<Todo />`为所有任务返回一个新组件。这不是我们想要的！仅当任务包含在应用所选过滤器的结果中时才应呈现。在我们映射任务状态之前，我们应该对其进行过滤（使用[`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)）以消除我们不想渲染的对象。

`taskList`像这样更新：

```
const taskList = tasks
.filter(FILTER_MAP[filter])
.map(task => (
  <Todo
    id={task.id}
    name={task.name}
    completed={task.completed}
    key={task.id}
    toggleTaskCompleted={toggleTaskCompleted}
    deleteTask={deleteTask}
    editTask={editTask}
  />
));
```

复制到剪贴板

为了决定在 中使用哪个回调函数`Array.prototype.filter()`，我们访问与`FILTER_MAP`过滤器状态的键对应的值。`All`例如，当 filter 为 时，`FILTER_MAP[filter]`将评估为`() => true`。

在浏览器中选择过滤器现在将删除不符合其标准的任务。列表上方标题中的计数也将更改以反映列表！

![带有过滤器按钮的应用程序。 活动被突出显示，因此只显示活动的待办事项。](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering/filtered-todo-list.png)

## [概括](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_interactivity_filtering_conditional_rendering#summary)

就是这样 - 我们的应用程序现在功能完整。但是，既然我们已经实现了所有功能，我们可以进行一些改进以确保更广泛的用户可以使用我们的应用程序。我们的下一篇文章通过在 React 中包含焦点管理来完善我们的 React 教程，这可以提高可用性并减少纯键盘和屏幕阅读器用户的混淆。

# React 中的可访问性

在我们的最后一篇教程文章中，我们将重点关注（双关语）可访问性，包括 React 中的焦点管理，它可以提高可用性并减少纯键盘和屏幕阅读器用户的混淆。

| 先决条件： | 熟悉核心[HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML)、 [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)和 [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript)语言，了解 [终端/命令行](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)。 |
| :--------- | ------------------------------------------------------------ |
| 客观的：   | 了解如何在 React 中实现键盘可访问性。                        |

## [包括键盘用户](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#including_keyboard_users)

在这一点上，我们已经完成了我们打算实现的所有功能。用户可以添加新任务、选中和取消选中任务、删除任务或编辑任务名称。他们可以按所有、活动或已完成的任务过滤他们的任务列表。

或者，至少：他们可以用鼠标完成所有这些事情。不幸的是，仅使用键盘的用户不太容易访问这些功能。现在让我们来探讨一下。

## [探索键盘可用性问题](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#exploring_the_keyboard_usability_problem)

首先单击我们应用程序顶部的输入，就像您要添加新任务一样。您会在该输入周围看到一个粗虚线轮廓。此轮廓是浏览器当前关注此元素的视觉指示器。按Tab键，您将看到在输入下方的“添加”按钮周围出现轮廓。这表明浏览器的焦点已经移动。

再按Tab几次，您将看到这个虚线焦点指示器在每个过滤器按钮之间移动。继续前进，直到焦点指示器位于第一个“编辑”按钮周围。按Enter。

该`<Todo />`组件将按照我们的设计切换模板，您将看到一个表单，让我们可以编辑任务的名称。

但是我们的焦点指示器去哪儿了？

当我们在`<Todo />`组件中的模板之间切换时，我们完全删除了之前存在的元素，用其他东西替换它们。这意味着我们关注的元素消失了，没有任何东西在焦点上。这可能会使各种用户感到困惑，尤其是依赖键盘的用户或使用屏幕阅读器的用户。

为了改善键盘和屏幕阅读器用户的体验，我们应该自己管理浏览器的焦点。

## [在模板之间聚焦](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#focusing_between_templates)

当用户将`<Todo/>`模板从查看切换到编辑时，我们应该关注`<input>`用于重命名它的；当他们从编辑切换回查看时，我们应该将焦点移回“编辑”按钮。

### [针对我们的元素](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#targeting_our_elements)

为了关注 DOM 中的元素，我们需要告诉 React 我们想要关注哪个元素以及如何找到它。反应的[`useRef`](https://reactjs.org/docs/hooks-reference.html#useref)hook 创建一个具有单个属性的对象：`current`。此属性可以是对我们想要的任何内容的引用，稍后再查找该引用。它对于引用 DOM 元素特别有用。

更改`import`顶部的语句`Todo.js`，使其包括`useRef`：

```
import React, { useRef, useState } from "react";
```

复制到剪贴板

然后，在`Todo()`函数中的钩子下方创建两个新常量。每个都应该是一个引用——一个用于视图模板中的“编辑”按钮，一个用于编辑模板中的编辑字段。

```
const editFieldRef = useRef(null);
const editButtonRef = useRef(null);
```

复制到剪贴板

这些 refs 有一个默认值，`null`因为在我们将它们附加到它们各自的元素之前它们将没有值。为此，我们将为`ref`每个元素添加一个属性，并将它们的值设置为适当命名的`ref`对象。

`<input>`编辑模板中的文本框应该像这样更新：

```
<input
  id={props.id}
  className="todo-text"
  type="text"
  value={newName}
  onChange={handleChange}
  ref={editFieldRef}
/>
```

复制到剪贴板

视图模板中的“编辑”按钮应如下所示：

```
<button
  type="button"
  className="btn"
  onClick={() => setEditing(true)}
  ref={editButtonRef}
>
  Edit <span className="visually-hidden">{props.name}</span>
</button>
```

复制到剪贴板

### [使用 useEffect 关注我们的 refs](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#focusing_on_our_refs_with_useeffect)

为了将我们的 refs 用于预期目的，我们需要导入另一个 React 钩子： [`useEffect()`](https://reactjs.org/docs/hooks-reference.html#useeffect). `useEffect()`之所以如此命名是因为它在 React 渲染给定组件之后运行，并且会运行我们想要添加到渲染过程中的任何副作用，我们不能在主函数体内运行。`useEffect()`在当前情况下很有用，因为在`<Todo />`组件渲染并且 React 知道我们的 refs 在哪里之前，我们无法专注于元素。

`Todo.js`再次更改 import 语句以添加`useEffect`：

```
import React, { useEffect, useRef, useState } from "react";
```

复制到剪贴板

`useEffect()`将函数作为参数；该函数在组件渲染后执行。让我们看看它的实际效果；将以下`useEffect()`调用放在`return`主体中语句的正上方`Todo()`，并将一个函数传递给它，该函数将“副作用”一词记录到您的控制台：

```
useEffect(() => {
  console.log("side effect");
});
```

复制到剪贴板

为了说明主渲染进程和内部运行的代码之间的区别`useEffect()`，添加另一个日志——将这个日志放在之前添加的下面：

```
console.log("main render");
```

复制到剪贴板

现在，在浏览器中打开该应用程序。您应该在控制台中看到两条消息，每一条都重复三遍。注意“主渲染”是如何首先记录的，“副作用”是如何记录的，即使“副作用”日志首先出现在代码中。

```
main render (3)                                     Todo.js:100
side effect (3)                                     Todo.js:98
```

这就是我们现在的实验。`console.log("main render")`现在删除，让我们继续实施我们的焦点管理。

### [专注于我们的编辑领域](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#focusing_on_our_editing_field)

现在我们知道我们的`useEffect()`钩子工作了，我们可以用它来管理焦点。提醒一下，当我们切换到编辑模板时，我们要专注于编辑字段。

更新您现有的`useEffect()`钩子，使其看起来像这样：

```
useEffect(() => {
  if (isEditing) {
    editFieldRef.current.focus();
  }
}, [isEditing]);
```

复制到剪贴板

这些更改使得如果`isEditing`为 true，React 会读取 的当前值`editFieldRef`并将浏览器焦点移动到它。我们还将一个数组`useEffect()`作为第二个参数传入。这个数组是一个`useEffect()`应该依赖的值列表。包含这些值后，`useEffect()`将仅在这些值之一更改时运行。我们只想在值改变时改变焦点`isEditing`。

现在尝试一下，您会看到当您单击“编辑”按钮时，焦点会移动到相应的编辑上`<input>`！

### [将焦点移回编辑按钮](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#moving_focus_back_to_the_edit_button)

乍一看，当编辑被保存或取消时，让 React 将焦点移回我们的“编辑”按钮似乎很容易。当然，我们可以向我们添加一个条件以`useEffect`专注于编辑按钮，如果`isEditing`是`false`？让我们现在试试——`useEffect()`像这样更新你的电话：

```
useEffect(() => {
  if (isEditing) {
    editFieldRef.current.focus();
  } else {
    editButtonRef.current.focus();
  }
}, [isEditing]);
```

复制到剪贴板

这种大多有效。返回浏览器，您会看到在`<input>`开始和结束编辑时焦点在“编辑”和“编辑”按钮之间移动。但是，您可能已经注意到一个新问题——`<Todo />`在我们与应用程序交互之前，最终组件中的“编辑”按钮会立即集中在页面加载上！

我们的`useEffect()`钩子表现完全按照我们设计了它：它只要组件呈现运行时，看到那`isEditing`是`false`，重点在“编辑”按钮。因为有三个 实例`<Todo />`，我们看到焦点在最后一个“编辑”按钮上。

我们需要重构我们的方法，以便焦点仅在`isEditing`从一个值更改为另一个值时发生变化。

## [更强大的焦点管理](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#more_robust_focus_management)

为了满足我们改进的标准，我们不仅需要知道 的值`isEditing`，还需要知道该值*何时发生变化*。为此，我们需要能够读取`isEditing`常量的先前值。使用伪代码，我们的逻辑应该是这样的：

```
if (wasNotEditingBefore && isEditingNow) {
  focusOnEditField()
}
if (wasEditingBefore && isNotEditingNow) {
  focusOnEditButton()
}
```

React 团队已经讨论过 [获取组件先前状态的方法](https://reactjs.org/docs/hooks-faq.html#how-to-get-the-previous-props-or-state)，并提供了一个示例自定义钩子，我们可以用于这项工作。

将以下代码粘贴到 的顶部附近`Todo.js`，在您的`Todo()`函数上方。

```
function usePrevious(value) {
  const ref = useRef();
  useEffect(() => {
    ref.current = value;
  });
  return ref.current;
}
```

复制到剪贴板

现在我们将`wasEditing`在顶部的钩子下方定义一个常量`Todo()`。我们希望这个常量跟踪 的先前值`isEditing`，因此我们调用`usePrevious`with`isEditing`作为参数：

```
const wasEditing = usePrevious(isEditing);
```

复制到剪贴板

有了这个常量，我们可以更新我们的`useEffect()`钩子来实现我们之前讨论过的伪代码——更新如下：

```
useEffect(() => {
  if (!wasEditing && isEditing) {
    editFieldRef.current.focus();
  }
  if (wasEditing && !isEditing) {
    editButtonRef.current.focus();
  }
}, [wasEditing, isEditing]);
```

复制到剪贴板

请注意，`useEffect()`now的逻辑取决于`wasEditing`，因此我们在依赖项数组中提供它。

再次尝试使用“编辑”和“取消”按钮在`<Todo />`组件的模板之间切换；您将看到浏览器焦点指示器适当移动，而没有我们在本节开头讨论的问题。

## [当用户删除任务时聚焦](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#focusing_when_the_user_deletes_a_task)

最后一个键盘体验差距：当用户从列表中删除任务时，焦点消失。我们将遵循与之前更改类似的模式：我们将创建一个新的 ref，并利用我们的`usePrevious()`钩子，以便在用户删除任务时我们可以专注于列表标题。

### [为什么是列表标题？](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#why_the_list_heading)

有时，我们想要将焦点发送到的位置很明显：当我们切换`<Todo />`模板时，我们有一个“返回”原点——“编辑”按钮。然而，在这种情况下，由于我们从 DOM 中完全删除了元素，因此我们无处可去。下一个最好的事情是附近某处的直观位置。列表标题是我们最好的选择，因为它靠近用户将删除的列表项，关注它会告诉用户还剩下多少任务。

### [创建我们的参考](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#creating_our_ref)

将`useRef()`和`useEffect()`挂钩导入`App.js`- 您将在下面需要它们：

```
import React, { useState, useRef, useEffect } from "react";
```

复制到剪贴板

然后在`App()`函数内部声明一个新的 ref 。`return`声明正上方是一个好地方：

```
const listHeadingRef = useRef(null);
```

复制到剪贴板

### [准备标题](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#prepare_the_heading)

像我们这样的标题元素`<h2>`通常是不可聚焦的。这不是问题——我们可以通过向任何元素添加属性[`tabindex="-1"`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex)来以编程方式使其成为焦点。这意味着*只能使用 JavaScript 聚焦*。您不能按与使用 a或元素相同的方式Tab将焦点放在具有 tabindex 的元素上（这可以使用 来完成，但在这种情况下这并不合适）。`-1`[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)`tabindex="0"`

让我们将`tabindex`属性（`tabIndex`以 JSX编写）添加到任务列表上方的标题中，以及我们的`headingRef`：

```
<h2 id="list-heading" tabIndex="-1" ref={listHeadingRef}>
  {headingText}
</h2>
```

复制到剪贴板

**注意：**该`tabindex`属性非常适合可访问性边缘情况，但您应该**非常小心**不要过度使用它。仅`tabindex`当您绝对确定使其可聚焦会以某种方式使您的用户受益时，才将 a应用于元素。在大多数情况下，您应该使用可以自然吸引焦点的元素，例如按钮、锚点和输入。不负责任的使用`tabindex`可能会对键盘和屏幕阅读器用户产生深远的负面影响！

### [获取之前的状态](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#getting_previous_state)

`ref`只有当我们的用户从他们的列表中删除一个任务时，我们才希望关注与我们的 ref 关联的元素（通过属性）。这将需要`usePrevious()`我们之前已经使用过的钩子。将它添加到`App.js`文件的顶部，就在导入的下方：

```
function usePrevious(value) {
  const ref = useRef();
  useEffect(() => {
    ref.current = value;
  });
  return ref.current;
}
```

复制到剪贴板

现在`return`在`App()`函数内的语句上方添加以下内容：

```
const prevTaskLength = usePrevious(tasks.length);
```

复制到剪贴板

这里我们调用`usePrevious()`来跟踪任务状态的长度，如下所示：

**注意：**由于我们现在`usePrevious()`在两个文件中使用，一个好的效率重构是将`usePrevious()`函数移动到它自己的文件中，从那个文件中导出它，然后将它导入到你需要的地方。完成后尝试将此作为练习。

### [使用`useEffect()`控制我们的标题重点](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#using_useeffect_to_control_our_heading_focus)

现在我们已经存储了我们之前有多少个任务，我们可以设置一个`useEffect()`钩子在我们的任务数量发生变化时运行，如果我们现在拥有的任务数量少于之前的数量，它将聚焦标题——即我们删除了一个任务！

将以下内容添加到您的`App()`函数正文中，就在您之前添加的内容下方：

```
useEffect(() => {
  if (tasks.length - prevTaskLength === -1) {
    listHeadingRef.current.focus();
  }
}, [tasks.length, prevTaskLength]);
```

复制到剪贴板

如果我们现在的任务比以前少，我们只会尝试专注于我们的列表标题。传递到此钩子的依赖项确保它仅在这些值（当前任务的数量或先前任务的数量）中的任何一个发生变化时才尝试重新运行。

现在，当您在浏览器中删除任务时，您将看到我们的虚线焦点轮廓出现在列表上方的标题周围。

## [完成的！](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility#finished!)

你刚刚从头开始构建了一个 React 应用程序！恭喜！您在此处学到的技能将成为您继续使用 React 的良好基础。

大多数时候，即使您所做的只是仔细考虑组件及其状态和道具，您也可以成为 React 项目的有效贡献者。请记住始终编写最好的 HTML。

`useRef()`并且`useEffect()`是一些高级功能，您应该为使用它们感到自豪！寻找更多实践它们的机会，因为这样做可以让您为用户创造包容性的体验。请记住：如果没有键盘用户，我们的应用程序将无法访问！

**注意：**如果您需要根据我们的版本检查您的代码，您可以在我们的[待办事项反应库](https://github.com/mdn/todo-react). 有关正在运行的实时版本，请参阅https://mdn.github.io/todo-react-build/.

# React resources

Our final article provides you with a list of React resources that you can use to go further in your learning.

## [Component-level styles](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources#component-level_styles)

Although this tutorial doesn't use this approach, many React applications define their styles on a per-component basis, rather than in a single, monolithic stylesheet.

`create-react-app` makes it possible to import CSS files into JavaScript modules, so that CSS is only sent to your user when the corresponding component is rendered. For this app, we could have for example written a dedicated `Form.css` file to house the styles of those respective components, then imported the styles into their respective modules like this:

```
import Form from './Form';
import './Form.css'
```

This approach makes it easy to identify and manage the CSS that belongs to a specific component. However, it also fragments your stylesheet across your codebase, and this fragmentation might not be worthwhile. For larger applications with hundreds of unique views and lots of moving parts, it makes sense to limit the amount of irrelevant code that's sent to your user. You'll likely have app-wide styles and specific component styles that built on top of those.

You can [read more about component stylesheets in the create-react-app docs](https://create-react-app.dev/docs/adding-a-stylesheet/).

## [React DevTools](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources#react_devtools)

We used `console.log()` to check on the state and props of our application in this tutorial, and you'll also have seen some of the useful warnings and error message that react gives you both in the CLI and your browser's JavaScript console. But there's more we can do here.

The React DevTools utility allows you to inspect the internals of your React application directly in the browser. It adds a new panel to your browser's developer tools, and with it you can inspect the state and props of various components, and even edit state and props to make immediate changes to your application.

This screenshot shows our finished application as it appears in React DevTools:

![Our project being shown in React devtools](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources/react-devtools.png)

On the left, we see all of the components that make up our application, including some unique keys for the things that are rendered from arrays. On the right, we see the props and hooks that our App component utilizes. Notice, too, that the `Form`, `FilterButton`, and `Todo` components are indented to the right – this indicates that `App` is their parent. In more complex apps, this view is great for understanding parent/child relationships at a glance.

React DevTools is available in a number of forms:

- A [Chrome browser extension](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en).
- A [Firefox browser extension](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/).
- A Chromium Edge browser extension (available soon).
- A [stand-alone application you can install with NPM or Yarn](https://www.npmjs.com/package/react-devtools).

Try installing one of these, then using it to inspect the app you’ve just built!

You can [read more about React DevTools on the React blog](https://reactjs.org/blog/2019/08/15/new-react-devtools.html).

## [The Context API](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources#the_context_api)

The application that we built in this tutorial utilized component props to pass data from its `App` component to the child components that needed it. Most of the time, props are an appropriate method for sharing data; for complex, deeply nested applications, however, they're not always best.

React provides the [Context API](https://reactjs.org/docs/context.html) as a way to provide data to components that need it *without* passing props down the component tree. There's also [a useContext hook](https://reactjs.org/docs/hooks-reference.html#usecontext) that facilitates this.

If you'd like to try this API for yourself, Smashing Magazine has written an [introductory article about React context](https://www.smashingmagazine.com/2020/01/introduction-react-context-api/).

## [Class components](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources#class_components)

Although this tutorial doesn’t mention them, it is possible to build React components using ES6 classes – these are called class components. Until the arrival of hooks, ES6 classes were the only way to bring state into components or manage rendering side effects. They're still the only way to handle certain other, more edge-case features, and they’re very common in legacy React projects. The official React docs are a great place to start learning about them.

- [State and Lifecycle in the React Docs](https://reactjs.org/docs/state-and-lifecycle.html)
- [Intro To React in the React Docs](https://reactjs.org/tutorial/tutorial.html)
- [Read about JavaScript classes at MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

## [Testing](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources#testing)

`create-react-app` provides some tools for testing your application out of the box — you may have deleted the relevant files earlier in the tutorial. The documentation for `create-react-app` [covers some basics for testing](https://create-react-app.dev/docs/running-tests/).

## [Routing](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_resources#routing)

While routing is traditionally handled by a server and not an application on the user's computer, it is possible to configure a web application to read and update the browser's location, and render certain user interfaces. This is called client-side routing. It's possible to create many unique routes for your application (such as `/home`, `/dashboard`, or `login/`).

The React community has produced two major libraries for client-side routing: [React Router](https://reacttraining.com/react-router/) and [Reach Router](https://reach.tech/router).

- React Router is well-suited to applications with complex routing needs, and it meets some edge cases better than Reach Router. React Router is a larger library, however.
- Reach Router is well-suited to simpler applications, and automatically manages focus as the user navigates from page to page.

Focus management is essential in client-side routing — without it, keyboard users can be trapped in focus limbo, and screen-reader users may have no idea that they have moved to a new page. Because Reach Router is better for accessibility, it's a good place to start.

There's one caveat, however: these projects will be [merging in the near future](https://reacttraining.com/blog/reach-react-router-future/). When this merge happens, React Router will be the surviving project (with the addition of the focus management features of Reach).



