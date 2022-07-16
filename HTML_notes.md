

# HTML 介绍

## HTML 概述

### HTML 元素结构

![img](https://mdn.mozillademos.org/files/16475/element.png)

### 块级元素和内联元素

#### 块级元素：纵向排列，像叠箱子一样，不同的块会换行，可以嵌套。

块级元素在页面中以块的形式展现 ——  相对于其前面的内容它会出现在新的一行，其后的内容也会被挤到下一行展现。块级元素通常用于展示页面上结构化的内容，例如段落、列表、导航菜单、页脚等等。一个以block形式展现的块级元素不会被嵌套进内联元素中，但可以嵌套在其它块级元素中。

#### 内联元素：横向排列，通常出现在块级元素内，不会换行。

内联元素通常出现在块级元素中并环绕文档内容的一小部分，而不是一整个段落或者一组内容。内联元素不会导致文本换行：它通常出现在一堆文字之间例如超链接元素<a>.

### 空元素

通常用于插入，嵌入一些东西，比如<img>，<link>。

### 属性

![&amp;amp;lt;p class="editor-note">我的猫咪脾气爆&amp;amp;lt;/p>](https://mdn.mozillademos.org/files/16476/attribute.png)

属性包含元素的额外信息，这些信息不会出现在实际的内容中。在上述例子中，这个class属性给元素赋了一个识别的名字（id），这个名字此后可以被用来识别此元素的样式信息和其他信息。

## 剖析HTML文档

```HTML
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>我的测试站点</title>
  </head>
  <body>
    <p>这是我的页面</p>
  </body>
</html>
```

1. `<!DOCTYPE html>`: 声明文档类型. 很久以前，早期的HTML(大约1991年2月)，文档类型声明类似于链接，规定了HTML页面必须遵从的良好规则，能自动检测错误和其他有用的东西。使用如下：   

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

  然而这种写法已经过时了，这些内容已成为历史。只需要知道 `<!DOCTYPE html>` 是最短有效的文档声明。

2. `<html></html>`: `<html>`元素。这个元素包裹了整个完整的页面，是一个根元素。

3. `<head></head>`: `<head>元素`. 这个元素是一个容器，它包含了所有你想包含在HTML页面中但不想在HTML页面中显示的内容。这些内容包括你想在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等。以后的章节能学到更多关于`<head>`元素的内容。

4. `<meta charset="utf-8">`: 这个元素设置文档使用utf-8字符集编码，utf-8字符集包含了人类大部分的文字。基本上他能识别你放上去的所有文本内容。毫无疑问要使用它，并且它能在以后避免很多其他问题。

   

5. `<title></title>`: 设置页面标题，出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面。

`<body></body>`: `<body>`元素。 包含了你访问页面时所有显示在页面上的内容，文本，图片，音频，游戏等等

### HTML 注释

<!-- <p>我在注释内！</p> -->

## \<head> 标签

### 相当于C语言中的头文件，包含的内容有：

#### 字符集

```
<meta charset="utf-8">
```

#### 作者和描述

<meta name="author" content="Chris Mills">
<meta name="description" content="The MDN Learning Area aims to provide
complete beginners to the Web with all they need to know to get
started with developing web sites and applications.">

#### 其它元数据

<meta name="twitter:title" content="Mozilla Developer Network">

#### 链接引入文件

##### 图标

```
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
```

##### CSS

`<link rel="stylesheet" href="my-css-file.css">`

##### scripts

<script src="my-js-file.js"></script>

## HTML 文字处理

### 基础文字处理标签

#### 标题

<p>我是一个段落，千真万确。</p>

#### 段落

```
<h1>这是一个顶级标题</h1>
```

#### 无序列表

<ul>
  <li>豆浆</li>
  <li>油条</li>
  <li>豆汁</li>
  <li>焦圈</li>
</ul>

#### 有序列表

<ol>
  <li>沿着条路走到头</li>
  <li>右转</li>
  <li>直行穿过第一个十字路口</li>
  <li>在第三个十字路口处左转</li>
  <li>继续走 300 米，学校就在你的右手边</li>
</ol>

#### 强调

<p>I am <em>glad</em> you weren't <em>late</em>.</p>

#### 非常重要

<p>This liquid is <strong>highly toxic</strong>.</p>

<p>I am counting on you. <strong>Do not</strong> be late!</p>

#### 斜体、粗体、下划线

`<b> 、<i>、<u>。`

<!-- 学名 -->

<p>
  红喉北蜂鸟（学名：<i>Archilocus colubris</i>）
  是北美东部最常见的蜂鸟品种。
</p>
<!-- 舶来词 -->

<p>
  菜单上有好多舶来词汇，比如 <i lang="uk-latn">vatrushka</i>（东欧乳酪面包）,
  <i lang="id">nasi goreng</i>（印尼炒饭）以及<i lang="fr">soupe à l'oignon</i>（法式洋葱汤）。
</p>

<!-- 已知的错误书写 -->
<p>
  总有一天我会改掉写<u style="text-decoration-line: underline; text-decoration-style: wavy;">措字</u>的毛病。
</p>

<!-- 在一组指令中突出显示关键字 -->
<ol>
  <li>
    <b>切</b>下两片面包，
  </li>
  <li>
    在两片面包中间<b>夹入</b>一片西红柿和一片生菜叶。
  </li>
</ol>

### 高级文字处理标签

#### 描述列表

<dl>
  <dt>内心独白</dt>
    <dd>戏剧中，某个角色对自己的内心活动或感受进行念白表演，这些台词只面向观众，而其他角色不会听到。</dd>
  <dt>语言独白</dt>
    <dd>戏剧中，某个角色把自己的想法直接进行念白表演，观众和其他角色都可以听到。</dd>
  <dt>旁白</dt>
    <dd>戏剧中，为渲染幽默或戏剧性效果而进行的场景之外的补充注释念白，只面向观众，内容一般都是角色的感受、想法、以及一些背景信息等。</dd>
</dl>

#### 引用

##### 块引用

<blockquote cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">
  <p>The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or <em>HTML Block
  Quotation Element</em>) indicates that the enclosed text is an extended quotation.</p>
</blockquote>

##### 行内引用

<p>The quote element — <code>&lt;q&gt;</code> — is <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q">intended
for short quotations that don't require paragraph breaks.</q></p>

##### 引文

<p>According to the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote">
<cite>MDN blockquote page</cite></a>:
</p>
##### 缩略语

<p>我们使用 <abbr title="超文本标记语言（Hyper text Markup Language）">HTML</abbr> 来组织网页文档。</p>

<p>第 33 届 <abbr title="夏季奥林匹克运动会">奥运会</abbr> 将于 2024 年 8 月在法国巴黎举行。</p>

##### 标记联系方式

<address>
  <p>Chris Mills, Manchester, The Grim North, UK</p>
</address>

##### 上标和下标

<p>咖啡因的化学方程式是 C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>。</p>
<p>如果 x<sup>2</sup> 的值为 9，那么 x 的值必为 3 或 -3。</p>

##### 代码标签

![image-20211021090719469](.\images\image-20211021090719469.png)

##### 标记日期和时间

<!-- 标准简单日期 -->
<time datetime="2016-01-20">20 January 2016</time>
<!-- 只包含年份和月份-->
<time datetime="2016-01">January 2016</time>
<!-- 只包含月份和日期 -->
<time datetime="01-20">20 January</time>
<!-- 只包含时间，小时和分钟数 -->
<time datetime="19:30">19:30</time>
<!-- 还可包含秒和毫秒 -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- 日期和时间 -->
<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
<!-- 含有时区偏移值的日期时间 -->
<time datetime="2016-01-20T19:30+01:00">7.30pm, 20 January 2016 is 8.30pm in France</time>
<!-- 调用特定的周 -->
<time datetime="2016-W04">The fourth week of 2016</time>

### 实体字符

&nbsp 表示non-breaking space 无间断空格

https://www.w3school.com.cn/charsets/ref_html_8859.asp

## 超链接

### 文字链接

<p>我创建了一个指向
<a href="https://www.mozilla.org/zh-CN/"
   title="了解 Mozilla 使命以及如何参与贡献的最佳站点。">Mozilla 主页</a>
的超链接。
</p>

### 块级链接

<a href="https://www.mozilla.org/zh-CN/">
  <img src="mozilla-image.png" alt="链接至 Mozilla 主页的 Mozilla 标志">
</a>

#### 下载链接

```html
<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=zh-CN"
   download="firefox-latest-64bit-installer.exe">
  下载最新的 Firefox 中文版 - Windows（64位）
</a>
```

## 文档结构

### 文档组成部分标签

#### 页眉

`<header>`

#### 导航栏

`<nav>`

#### 主内容

`<main>`

#### 侧边栏（经常嵌套在`<main>`中）

`<aside>`

#### 页脚

`<footer>`

![一个简单站点首页截图](https://mdn.mozillademos.org/files/16497/snapshot.png)

### 无语义元素

#### 内联无语义元素

<p>国王喝得酩酊大醉，在凌晨 1 点时才回到自己的房间，踉跄地走过门口。<span class="editor-note">[编辑批注：此刻舞台灯光应变暗]</span>.</p>

#### 块级无语义元素

<div class="shopping-cart">
  <h2>购物车</h2>
  <ul>
    <li>
      <p><a href=""><strong>银耳环</strong></a>：$99.95.</p>
      <img src="../products/3333-0985/" alt="Silver earrings">
    </li>
    <li>
      ...
    </li>
  </ul>
  <p>售价：$237.89</p>
</div>

### 换行与水平分割线

#### 换行

<p>从前有个人叫小高<br>
他说写 HTML 感觉最好<br>
但他写的代码结构语义一团糟<br>
他写的标签谁也懂不了。</p>

#### 水平分割线

```html
<p>原来这唐僧是个慈悯的圣僧。他见行者哀告，却也回心转意道：“既如此说，且饶你这一次。再休无礼。如若仍前作恶，这咒语颠倒就念二十遍！”行者道：“三十遍也由你，只是我不打人了。”却才伏侍唐僧上马，又将摘来桃子奉上。唐僧在马上也吃了几个，权且充饥。</p>
<hr>
<p>却说那妖精，脱命升空。原来行者那一棒不曾打杀妖精，妖精出神去了。他在那云端里，咬牙切齿，暗恨行者道：“几年只闻得讲他手段，今日果然话不虚传。那唐僧已此不认得我，将要吃饭。若低头闻一闻儿，我就一把捞住，却不是我的人了。不期被他走来，弄破我这勾当，又几乎被他打了一棒。若饶了这个和尚，诚然是劳而无功也。我还下去戏他一戏。”</p>
```

# 多媒体与嵌入

## HTML中的图片

```
<img src="images/dinosaur.jpg"
     alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
     width="400"
     height="341"
     title="A T-Rex on display in the Manchester University Museum">
```

图片包含源地址、替代文字、图片大小、图片标题。

```
<figure>
  <img src="https://raw.githubusercontent.com/mdn/learning-area/master/html/multimedia-and-embedding/images-in-html/dinosaur_small.jpg"
     alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
     width="400"
     height="341">
  <figcaption>曼彻斯特大学博物馆展出的一只霸王龙的化石</figcaption>
</figure>
```

还可以为图片提供语义容器figure。

## HTML中的视频

<video controls width="400" height="400"
       autoplay loop muted
       poster="poster.png">
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>你的浏览器不支持 HTML5 视频。可点击<a href="rabbit320.mp4">此链接</a>观看</p>
</video>

视频标签包括控制栏controls、大小、自动播放autoplay、循环loop、无声muted、封面poster、不同格式播放源、可替代播放链接。

## HTML中的音频

<audio controls>
  <source src="viper.mp3" type="audio/mp3">
  <source src="viper.ogg" type="audio/ogg">
  <p>你的浏览器不支持 HTML5 音频，可点击<a href="viper.mp3">此链接</a>收听。</p>
</audio>

使用方式与video标签几乎一样，只是播放框不一样

## HTML中的音轨

<video controls>
    <source src="example.mp4" type="video/mp4">
    <source src="example.webm" type="video/webm">
    <track kind="subtitles" src="subtitles_en.vtt" srclang="en">
</video>

音轨标签嵌入在video和audio中，文件为.vtt文件。使用kind表明是那种类型，srclang表明语言类型。

## iframe等嵌入技术

### \<iframe>标签嵌入

```
<iframe src="https://developer.mozilla.org/en-US/docs/Glossary"
        width="100%" height="500" frameborder="0"
        allowfullscreen sandbox>
  <p> <a href="https://developer.mozilla.org/en-US/docs/Glossary">
    Fallback link for browsers that don't support iframes
  </a> </p>
</iframe>
```

使用iframe可以嵌入各种插件，比如bilibili视频，谷歌地图等等。

### \<embed>和\<object>元素

\<embed>和\<object>元素功能不同于iframe，主要用于嵌入多种类型的外部内容，比如java程序、FLash、PDF，甚至像视频、SVG和图像。

#### \<embed>

<embed src="whoosh.swf" quality="medium"
       bgcolor="#ffffff" width="550" height="400"
       name="whoosh" align="middle" allowScriptAccess="sameDomain"
       allowFullScreen="false" type="application/x-shockwave-flash"
       pluginspage="http://www.macromedia.com/go/getflashplayer">

#### \<object>

<object data="mypdf.pdf" type="application/pdf"
        width="800" height="1200" typemustmatch>
  <p>You don't have a PDF plugin, but you can <a href="myfile.pdf">download the PDF file.</a></p>
</object>

## 矢量图形

位图使用像素网格定义，改变图像大小会影响画质。包括Bitmap (`.bmp`), PNG (`.png`), JPEG (`.jpg`), and GIF (`.gif`.)。

矢量图用算法定义，改变图像大小不会影响画质。包括SVG格式。

#### SVG

SVG是用于描述矢量图形的XML语言，一下代码创建一个圆和矩形。

<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">
  <rect width="100%" height="100%" fill="black" />
  <circle cx="150" cy="100" r="90" fill="blue" />
</svg>

#### 将SVG添加到页面

```
<img
    src="equilateral.svg"
    alt="triangle with all three sides equal"
    height="87px"
    width="100px" />
```

## 响应式图片

### 根据视窗大小改变图片尺寸

```
<img srcset="elva-fairy-320w.jpg 320w,
             elva-fairy-480w.jpg 480w,
             elva-fairy-800w.jpg 800w"
     sizes="(max-width: 320px) 280px,
            (max-width: 480px) 440px,
            800px"
     src="elva-fairy-800w.jpg" alt="Elva dressed as a fairy">
```

图像源集合用于不同尺寸的图片选择，与媒体条件一一对应。

### 根据视窗大小改变图片分辨率，不改变尺寸。

```
<img srcset="elva-fairy-320w.jpg,
             elva-fairy-480w.jpg 1.5x,
             elva-fairy-640w.jpg 2x"
     src="elva-fairy-640w.jpg" alt="Elva dressed as a fairy">
```

x语法与size类似，根据视窗大小倍数判定。

### 根据视窗大小改变图片，注重图片中的内容

<picture>
  <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg">
  <source media="(min-width: 800px)" srcset="elva-800w.jpg">
  <img src="elva-800w.jpg" alt="Chris standing up holding his daughter Elva">
</picture>

对于大块的图片作为页眉，需要突出图片中的信息时，可以将大图片重要信息截图作为小图片。用\<picture>标签嵌入。

# HTML表格

```html
   <table>
      <caption>太阳系中行星的一些数据。（资料取自<a href="http://nssdc.gsfc.nasa.gov/planetary/factsheet/">NASA 行星数据 - 公制</a>，图片取自<a href="https://www.nasa.gov/multimedia/imagegallery/">NASA 照片库</a>。）</caption>
      <colgroup>
        <col span="2">
        <col style="border: 2px solid black">
        <col span="10">
      </colgroup>
      <thead>
        <tr>
          <td colspan="2"></td>
          <th scope="col">名字</th>
          <th scope="col">图片</th>
          <th scope="col">质量 (10<sup>24</sup>kg)</th>
          <th scope="col">直径 (km)</th>
          <th scope="col">密度 (kg/m<sup>3</sup>)</th>
          <th scope="col">重力 (m/s<sup>2</sup>)</th>
          <th scope="col">天长 (小时)</th>
          <th scope="col">与太阳距离 (10<sup>6</sup>km)</th>
          <th scope="col">平均温度 (°C)</th>
          <th scope="col">卫星数量</th>
          <th scope="col">备注</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th rowspan="4" colspan="2" scope="rowgroup">类地行星</th>
          <th scope="row">水星</th>
          <td><img src="images/mercury.jpg" alt="水星"></td>
          <td>0.330</td>
          <td>4,879</td>
          <td>5427</td>
          <td>3.7</td>
          <td>4222.6</td>
          <td>57.9</td>
          <td>167</td>
          <td>0</td>
          <td>距太阳最近</td>
        </tr>
        <tr>
          <th scope="row">金星</th>
          <td><img src="images/venus.jpg" alt="金星"></td>
          <td>4.87</td>
          <td>12,104</td>
          <td>5243</td>
          <td>8.9</td>
          <td>2802.0</td>
          <td>108.2</td>
          <td>464</td>
          <td>0</td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">地球</th>
          <td><img src="images/earth.png" alt="地球"></td>
          <td>5.97</td>
          <td>12,756</td>
          <td>5514</td>
          <td>9.8</td>
          <td>24.0</td>
          <td>149.6</td>
          <td>15</td>
          <td>1</td>
          <td>我们的世界</td>
        </tr>
        <tr>
          <th scope="row">火星</th>
          <td><img src="images/mars.jpg" alt="火星"></td>
          <td>0.642</td>
          <td>6,792</td>
          <td>3933</td>
          <td>3.7</td>
          <td>24.7</td>
          <td>227.9</td>
          <td>-65</td>
          <td>2</td>
          <td>红色星球</td>
        </tr>
        <tr>
          <th rowspan="4" scope="rowgroup">类木行星</th>
          <th rowspan="2" scope="rowgroup">气巨星</th>
          <th scope="row">木星</th>
          <td><img src="images/jupiter.jpg" alt="木星"></td>
          <td>1898</td>
          <td>142,984</td>
          <td>1326</td>
          <td>23.1</td>
          <td>9.9</td>
          <td>778.6</td>
          <td>-110</td>
          <td>67</td>
          <td>太阳系最大</td>
        </tr>
        <tr>
          <th scope="row">土星</th>
          <td><img src="images/saturn.jpg" alt="土星"></td>
          <td>568</td>
          <td>120,536</td>
          <td>687</td>
          <td>9.0</td>
          <td>10.7</td>
          <td>1433.5</td>
          <td>-140</td>
          <td>62</td>
          <td></td>
        </tr>
        <tr>
          <th rowspan="2" scope="rowgroup">冰巨星</th>
          <th scope="row">天王星</th>
          <td><img src="images/uranus.jpg" alt="天王星"></td>
          <td>86.8</td>
          <td>51,118</td>
          <td>1271</td>
          <td>8.7</td>
          <td>17.2</td>
          <td>2872.5</td>
          <td>-195</td>
          <td>27</td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">海王星</th>
          <td><img src="images/neptune.jpg" alt="海王星"></td>
          <td>102</td>
          <td>49,528</td>
          <td>1638</td>
          <td>11.0</td>
          <td>16.1</td>
          <td>4495.1</td>
          <td>-200</td>
          <td>14</td>
          <td></td>
        </tr>
        <tr>
          <th colspan="2" scope="rowgroup">矮行星</th>
          <th scope="row">冥王星</th>
          <td><img src="images/pluto.jpg" alt="冥王星"></td>
          <td>0.0146</td>
          <td>2,370</td>
          <td>2095</td>
          <td>0.7</td>
          <td>153.3</td>
          <td>5906.4</td>
          <td>-225</td>
          <td>5</td>
          <td>2006年降格，但<a href="http://www.usatoday.com/story/tech/2014/10/02/pluto-planet-solar-system/16578959/">尚存争议</a>。</td>
        </tr>
      </tbody>
    </table>
```

![image-20211021105001415](.\images\image-20211021105001415.png)

# [浏览器的渲染原理简介](https://news.cnblogs.com/n/178402/)        

　　看到这个标题大家一定会想到这篇神文《[How Browsers Work](http://taligarsiel.com/Projects/howbrowserswork1.htm)》，这篇文章把浏览器的很多细节讲得很细，而且也被[翻译成了中文](http://ux.sohu.com/topics/50972d9ae7de3e752e0081ff)。为什么我还想写一篇呢？因为两个原因，

　　1）这篇文章太长了，阅读成本太大，不能一口气读完。

　　2）花了大力气读了这篇文章后可以了解很多，但似乎对工作没什么帮助。

　　所以，我准备写下这篇文章来解决上述两个问题。希望你能在上班途中，或是坐马桶时就能读完，并能从中学会一些能用在工作上的东西。

　　**浏览器工作大流程**

　　废话少说，先来看个图：

![img](https://images0.cnblogs.com/news/66372/201305/22110607-791cc828c8e64c18b0d86d573338a345.jpg)

　　从上面这个图中，我们可以看到那么几个事：

　　1）浏览器会解析三个东西：

- 一个是 HTML/SVG/XHTML，事实上，Webkit 有三个 C++ 的类对应这三类文档。解析这三种文件会产生一个 DOM Tree。
- CSS，解析 CSS 会产生 CSS 规则树。
- Javascript，脚本，主要是通过 DOM API 和 CSSOM API 来操作 DOM Tree 和 CSS Rule Tree.

　　2）解析完成后，浏览器引擎会通过 DOM Tree 和 CSS Rule Tree 来构造 Rendering Tree。注意：

- Rendering Tree 渲染树并不等同于 DOM 树，因为一些像 Header 或 display:none 的东西就没必要放在渲染树中了。
- CSS 的 Rule Tree 主要是为了完成匹配并把 CSS Rule 附加上 Rendering Tree 上的每个 Element。也就是 DOM 结点。也就是所谓的 Frame。
- 然后，计算每个 Frame（也就是每个 Element）的位置，这又叫 layout 和 reflow 过程。

　　3）最后通过调用操作系统 Native GUI 的 API 绘制。

　　**DOM 解析**

　　HTML 的 DOM Tree 解析如下：

```
<html>
<head>
　　<title>Web page parsing</title>
</head>
<body>
　　<div>
　　<h1>Web page parsing</h1>
　　<p>This is an example Web page.</p>
　　</div>
</body>
</html>
```

　　上面这段 HTML 会解析成这样：

![img](https://images0.cnblogs.com/news/66372/201305/22111701-b098b6bffadc42e484bf61e86380a580.jpg)

　　下面是另一个有 SVG 标签的情况。

![img](https://images0.cnblogs.com/news/66372/201305/22111700-847e3939e1674b48b56204a5411df7e0.jpg)

　　**CSS 解析**

　　CSS 的解析大概是下面这个样子（下面主要说的是 Gecko 也就是 Firefox 的玩法），假设我们有下面的 HTML 文档：

```
<doc>
<title>A few quotes</title>
<para>
Franklin said that <quote>"A penny saved is a penny earned."</quote>
</para>
<para>
FDR said <quote>"We have nothing to fear but <span>fear itself.</span>"</quote>
</para>
</doc>
```

　　于是 DOM Tree 是这个样子：

![img](https://images0.cnblogs.com/news/66372/201305/22111700-d94557d93d124c57973976bd4106c32f.jpg)

　　然后我们的 CSS 文档是这样的：

```
/* rule 1 */ doc { display: block; text-indent: 1em; }
/* rule 2 */ title { display: block; font-size: 3em; }
/* rule 3 */ para { display: block; }
/* rule 4 */ [] { font-style: italic; }
```

　　于是我们的 CSS Rule Tree 会是这个样子：

![img](https://images0.cnblogs.com/news/66372/201305/22111701-636fce0d8fba466ab5fa2a2c38c6abe3.jpg)

　　注意，图中的第 4 条规则出现了两次，一次是独立的，一次是在规则 3 的子结点。所以，我们可以知道，建立 CSS Rule Tree  是需要比照着 DOM Tree 来的。CSS 匹配 DOM Tree 主要是从右到左解析 CSS 的  Selector，好多人以为这个事会比较快，其实并不一定。关键还看我们的 CSS 的 Selector 怎么写了。

　　**注意：CSS 匹配 HTML 元素是一个相当复杂和有性能问题的事情。所以，你就会在N多地方看到很多人都告诉你，DOM 树要小，CSS 尽量用 id 和 class，千万不要过渡层叠下去，……**

　　通过这两个树，我们可以得到一个叫 Style Context Tree，也就是下面这样（把 CSS Rule 结点 Attach 到 DOM Tree 上）：

![img](https://images0.cnblogs.com/news/66372/201305/22111700-2d7e0bb4d7e54a9a8deb22c8394149a2.jpg)

　　所以，Firefox 基本上来说是通过 CSS 解析生成 CSS Rule Tree，然后，通过比对 DOM 生成 Style  Context Tree，然后 Firefox 通过把 Style Context Tree 和其 Render Tree（Frame  Tree）关联上，就完成了。注意：Render Tree 会把一些不可见的结点去除掉。而 **Firefox 中所谓的 Frame 就是一个 DOM 结点，不要被其名字所迷惑了**。

![img](https://images0.cnblogs.com/news/66372/201305/22111700-6096cefafee64f2d9f86e899c8bf79ca.png)

　　注：Webkit 不像 Firefox 要用两个树来干这个，Webkit 也有 Style 对象，它直接把这个 Style 对象存在了相应的 DOM 结点上了。

　　**渲染**

　　渲染的流程基本上如下（黄色的四个步骤）：

1. 计算 CSS 样式
2. 构建 Render Tree
3. Layout – 定位坐标和大小，是否换行，各种 position, overflow， z-index 属性 ……
4. 正式开画

![img](https://images0.cnblogs.com/news/66372/201305/22111701-578c65c6633246b2b6b35c4335bc7131.jpg)

　　注意：上图流程中有很多连接线，这表示了 Javascript 动态修改了 DOM 属性或是 CSS 属性会导致重新 Layout，有些改变不会，就是那些指到天上的箭头，比如，修改后的 CSS rule 没有被匹配到，等。

　　这里重要要说两个概念，一个是 Reflow，另一个是 Repaint。这两个不是一回事。

- Repaint——屏幕的一部分要重画，比如某个 CSS 的背景色变了。但是元素的几何尺寸没有变。
- Reflow——意味着元件的几何尺寸变了，我们需要重新验证并计算 Render Tree。是 Render Tree 的一部分或全部发生了变化。这就是 Reflow，或是 Layout。（**HTML 使用的是 flow based layout，也就是流式布局，所以，如果某元件的几何尺寸发生了变化，需要重新布局，也就叫 reflow**）reflow 会从 <html> 这个 root frame 开始递归往下，依次计算所有的结点几何尺寸和位置，在 reflow 过程中，可能会增加一些 frame，比如一个文本字符串必需被包装起来。

　　下面是一个打开 Wikipedia 时的 Layout/reflow 的视频（注：HTML 在初始化的时候也会做一次 reflow，叫 intial reflow），你可以感受一下：



　　Reflow 的成本比 Repaint 的成本高得多的多。DOM Tree 里的每个结点都会有 reflow 方法，一个结点的  reflow 很有可能导致子结点，甚至父点以及同级结点的 reflow。在一些高性能的电脑上也许还没什么，但是如果 reflow  发生在手机上，那么这个过程是非常痛苦和耗电的。

　　所以，下面这些动作有很大可能会是成本比较高的。

- 当你增加、删除、修改 DOM 结点时，会导致 Reflow 或 Repaint。
- 当你移动 DOM 的位置，或是搞个动画的时候。
- 当你修改 CSS 样式的时候。
- 当你 Resize 窗口的时候（移动端没有这个问题），或是滚动的时候。
- 当你修改网页的默认字体时。

　　注：display:none 会触发 reflow，而 visibility:hidden 只会触发 repaint，因为没有发现位置变化。

　　多说两句关于滚屏的事，通常来说，如果在滚屏的时候，我们的页面上的所有的像素都会跟着滚动，那么性能上没什么问题，因为我们的显卡对于这种把全屏像素往上往下移的算法是很快。但是如果你有一个 fixed 的背景图，或是有些 Element 不跟着滚动，有些 Elment  是动画，那么这个滚动的动作对于浏览器来说会是相当相当痛苦的一个过程。你可以看到很多这样的网页在滚动的时候性能有多差。因为滚屏也有可能会造成  reflow。

　　基本上来说，reflow 有如下的几个原因：

- Initial。网页初始化的时候。
- Incremental。一些 Javascript 在操作 DOM Tree 时。
- Resize。其些元件的尺寸变了。
- StyleChange。如果 CSS 的属性发生变化了。
- Dirty。几个 Incremental 的 reflow 发生在同一个 frame 的子树上。

　　好了，我们来看一个示例吧：

```
var bstyle = document.body.style; // cache
bstyle.padding = "20px"; // reflow， repaint
bstyle.border = "10px solid red"; //  再一次的 reflow 和 repaint
bstyle.color = "blue"; // repaint
bstyle.backgroundColor = "#fad"; // repaint
bstyle.fontSize = "2em"; // reflow， repaint
// new DOM element - reflow， repaint
document.body.appendChild (document.createTextNode ('dude!'));
```

　　当然，我们的浏览器是聪明的，它不会像上面那样，你每改一次样式，它就 reflow 或 repaint 一次。**一般来说，浏览器会把这样的操作积攒一批，然后做一次 reflow，这又叫异步 reflow 或增量异步 reflow**。但是有些情况浏览器是不会这么做的，比如：resize 窗口，改变了页面默认的字体，等。对于这些操作，浏览器会马上进行 reflow。

　　但是有些时候，我们的脚本会阻止浏览器这么干，比如：如果我们请求下面的一些 DOM 值：

1. offsetTop, offsetLeft, offsetWidth, offsetHeight
2. scrollTop/Left/Width/Height
3. clientTop/Left/Width/Height
4. IE 中的 getComputedStyle ()， 或 currentStyle

　　因为，如果我们的程序需要这些值，那么浏览器需要返回最新的值，而这样一样会 flush 出去一些样式的改变，从而造成频繁的 reflow/repaint。

　　**减少 reflow/repaint**

　　下面是一些 Best Practices：

　　**1）不要一条一条地修改 DOM 的样式。与其这样，还不如预先定义好 css 的 class，然后修改 DOM 的 className。**

```
// bad
var left = 10,
top = 10;
el.style.left = left + "px";
el.style.top  = top  + "px";

// Good
el.className += " theclassname";
// Good
el.style.cssText += "; left: " + left + "px; top: " + top + "px;";
```

　　**2）把 DOM 离线后修改。如：**

- 使用 documentFragment 对象在内存里操作 DOM。
- 先把 DOM 给 display:none (有一次 repaint)，然后你想怎么改就怎么改。比如修改 100 次，然后再把他显示出来。
- clone 一个 DOM 结点到内存里，然后想怎么改就怎么改，改完后，和在线的那个的交换一下。

　　3）**不要把 DOM 结点的属性值放在一个循环里当成循环里的变量。**不然这会导致大量地读写这个结点的属性。

　　4）**尽可能的修改层级比较低的 DOM**。当然，改变层级比较底的 DOM 有可能会造成大面积的 reflow，但是也可能影响范围很小。

　　5）**为动画的 HTML 元件使用 fixed 或 absoult 的 position**，那么修改他们的 CSS 是不会 reflow 的。

　　6）**千万不要使用 table 布局**。因为可能很小的一个小改动会造成整个 table 的重新布局。

> In this manner, the user agent can begin to lay out the table once  the entire first row has been received. Cells in subsequent rows do not  affect column widths. Any cell that has content that overflows uses the  ‘overflow’ property to determine whether to clip the overflow content.
>
> [Fixed layout, CSS 2.1 Specification](http://www.w3.org/TR/CSS21/tables.html#fixed-table-layout)
>
> This algorithm may be inefficient since it requires the user agent to have access to all the content in the table before determining the  final layout and may demand more than one pass.
>
> [Automatic layout, CSS 2.1 Specification](http://www.w3.org/TR/CSS21/tables.html#auto-table-layout)

　　**几个工具和几篇文章**

　　有时候，你会也许会发现在 IE 下，你不知道你修改了什么东西，结果 CPU 一下子就上去了到 100%，然后过了好几秒钟  repaint/reflow 才完成，这种事情以 IE 的年代时经常发生。所以，我们需要一些工具帮我们看看我们的代码里有没有什么不合适的东西。

- Chrome 下，Google 的 [SpeedTracer](http://code.google.com/webtoolkit/speedtracer/) 是个非常强悍的工作让你看看你的浏览渲染的成本有多大。其实 Safari 和 Chrome 都可以使用开发者工具里的一个 Timeline 的东东。
- Firefox 下这个基于 Firebug 的叫 [Firebug Paint Events](https://addons.mozilla.org/en-US/firefox/addon/firebug-paint-events/) 的插件也不错。
- IE 下你可以用一个叫 [dynaTrace](http://ajax.dynatrace.com/pages/) 的 IE 扩展。

　　最后，别忘了下面这几篇提高浏览器性能的文章：

- [Google – Web Performance Best Practices](http://code.google.com/speed/page-speed/docs/rules_intro.html)
- [Yahoo – Best Practices for Speeding Up Your Web Site](http://developer.yahoo.com/performance/rules.html)
- [Steve Souders – 14 Rules for Faster-Loading Web Sites](http://stevesouders.com/hpws/rules.php)

　　**参考**

- David Baron 的演讲：Fast CSS: How Browsers Lay Out Web Pages：[slideshow](http://dbaron.org/talks/2012-03-11-sxsw/slide-1.xhtml), [all slides](http://dbaron.org/talks/2012-03-11-sxsw/master.xhtml), [audio (MP3)](http://audio.sxsw.com/2012/podcasts/11-ACC-Fast_CSS_How_Browser_Layout.mp3), [Session page](http://schedule.sxsw.com/2012/events/event_IAP12909), [Lanyrd page](http://lanyrd.com/2012/sxsw-interactive/spmbt/)
- How Browsers Work: http://taligarsiel.com/Projects/howbrowserswork1.htm
- Mozilla 的 Style System Overview：https://developer.mozilla.org/en-US/docs/Style_System_Overview
- Mozilla 的 Note of reflow： http://www-archive.mozilla.org/newlayout/doc/reflow.html
- Rendering: repaint, reflow/relayout, restyle：http://www.phpied.com/rendering-repaint-reflowrelayout-restyle/
- Effective Rendering CSS：http://css-tricks.com/efficiently-rendering-css/
- Webkit Rendering 文档：http://trac.webkit.org/wiki/WebCoreRendering
