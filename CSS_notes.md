# CSS 介绍

### CSS语法

selector {
    property: value;
    property: value;
}

例如：

h1 {
    color: red;
    font-size: 5em;
}

### 外部样式表

#### 通过\<head>标签引入外部样式表

```
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <link rel="stylesheet" href="styles.css">
  </head>
```

### 内部样式表

#### 直接在\<head>标签插入\<style>标签编写样式表

```
<head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
    </style>
  </head>
```

### 内联样式

#### 直接在HTML元素的style属性中设置样式，特点是每个样式只能影响一个元素

```
<body>
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">Hello World!</h1>
    <p style="color:red;">This is my first CSS example</p>
  </body>
```

### @规则

#### @rules:一些特殊的规则，为 CSS提供了一些关于如何表现的指导。 有些`@rules` 规则很简单，有规则名和值。例如，要将额外的样式表导入主CSS样式表，可以使用`@import`:

`@import 'styles2.css';`

### 注释

#### 行注释

```
/* Handle basic element styling */
```

#### 块注释

```
/* Let's special case the global font size. On large screen or window,
     we increase the font size for better readability */
```

# CSS如何运行的

### CSS运行流程

当浏览器展示一个文件的时候，它必须兼顾文件的内容和文件的样式信息，下面我们会了解到它处理文件的标准的流程。需要知道的是，下面的步骤是浏览加载网页的简化版本，而且不同的浏览器在处理文件的时候会有不同的方式，但是下面的步骤基本都会出现

1. 浏览器载入HTML文件（比如从网络上获取）。

2. 将HTML文件转化成一个DOM（Document Object Model），DOM是文件在计算机内存中的表现形式，下一节将更加详细的解释DOM。

3. 接下来，浏览器会拉取该HTML相关的大部分资源，比如嵌入到页面的图片、视频和CSS样式。JavaScript则会稍后进行处理，简单起见，同时此节主讲CSS，所以这里对如何加载JavaScript不会展开叙述。

4. 浏览器拉取到CSS之后会进行解析，根据选择器的不同类型（比如element、class、id等等）把他们分到不同的“桶”中。浏览器基于它找到的不同的选择器，将不同的规则（基于选择器的规则，如元素选择器、类选择器、id选择器等）应用在对应的DOM的节点中，并添加节点依赖的样式（这个中间步骤称为渲染树）。

5. 上述的规则应用于渲染树之后，渲染树会依照应该出现的结构进行布局。

6. 网页展示在屏幕上（这一步被称为着色）

![img](https://mdn.mozillademos.org/files/11781/rendering.svg)

### DOM（Document Object Model）

一个DOM有一个树形结构，标记语言中的每一个元素、属性以及每一段文字都对应着结构树中的一个节点（Node/DOM或DOM node）。节点由节点本身和其他DOM节点的关系定义，有些节点有父节点，有些节点有兄弟节点（同级节点）。

#### DOM案例

<p>
  Let's use:
  <span>Cascading</span>
  <span>Style</span>
  <span>Sheets</span>
</p>

```
P
├─ "Let's use:"
├─ SPAN
|  └─ "Cascading"
├─ SPAN
|  └─ "Style"
└─ SPAN
   └─ "Sheets
```

# CSS 基础知识

### 层叠

#### 层叠位置的影响

同样优先级的规则，最后一条覆盖前面的，起作用。

相互冲突的声明将按以下顺序适用，后一种声明将覆盖前一种声明：

1. 用户代理样式表中的声明(例如，浏览器的默认样式，在没有设置其他样式时使用)。
2. 用户样式表中的常规声明(由用户设置的自定义样式)。
3. 作者样式表中的常规声明(这些是我们web开发人员设置的样式)。
4. 作者样式表中的`!important`声明
5. 用户样式表中的`!important` 声明

#### 优先级

选择器越具体，优先级越高。

一个选择器的优先级可以说是由四个部分相加 (分量)，可以认为是个十百千 — 四位数的四个位数：

1. **千位**： 如果声明在 [`style`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes#attr-style) 的属性（内联样式）则该位得一分。这样的声明没有选择器，所以它得分总是1000。
2. **百位**： 选择器中包含ID选择器则该位得一分。
3. **十位**： 选择器中包含类选择器、属性选择器或者伪类则该位得一分。
4. **个位**：选择器中包含元素、伪元素选择器则该位得一分。

*注：通用选择器 (`*`)，组合符 (`+`, `>`, `~`, ' ')，和否定伪类 (`:not`) 不会影响优先级。*

### 继承

某些父元素上的CSS属性会被子元素继承

比如嵌套的列表：

<ul class="main">
    <li>Item One</li>
    <li>Item Two
        <ul>
            <li>2.1</li>
            <li>2.2</li>
        </ul>
    </li>
    <li>Item Three
        <ul class="special">
            <li>3.1
                <ul>
                    <li>3.1.1</li>
                    <li>3.1.2</li>
                </ul>
            </li>
            <li>3.2</li>
        </ul>
    </li>
</ul>

#### 控制属性继承

##### inherit

强制开启继承，不管默认是否可以继承。

##### initial

设置属性值与浏览器默认样式相同，浏览器默认继承则继承。

##### unset

将属性重置为自然值，如果自然值是继承则继承，否则为浏览器默认样式。

#### 重设所有属性

##### 将所有属性值统一设置，这是一种撤销对样式所做更改的简便方法。

all：inherit/initial/unset

```
p {
    all: unset;
}
```

### CSS选择器

#### 选择器列表

通过逗号可以用选择器列表选择多个元素

```
h1, .special {
  color: blue;
} 
```

#### 选择器种类

##### 全局选择器

全局选择器的一种用法是让选择器更易读，更明显地表明它们的作用。例如，如果我想选中任何`<article>`元素的第一子元素，不论它是什么元素，都给它加粗，我可以将[`:first-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-child)选择器（我们将会在[伪类和伪元素](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)课中进一步了解）用作`<article>`元素选择器的一个兄弟选择器：

```
article :first-child {

}
```

但是这会和`article:first-child`混淆，而后者选择了作为其他元素的第一子元素的`<article>`元素。

为了避免这种混淆，我们可以向`:first-child`选择器加入全局选择器，这样选择器所做的事情很容易就能看懂。选择器正选中`<article>`元素的*任何*第一子元素：

```
article *:first-child {

} 
```

##### 类型（标签名、元素）选择器

```
h1 { }
```

##### 类选择器

```
.box { }
```

##### id选择器

```
#unique { }
```

##### 属性选择器

###### 存否和值选择器

|     选择器      | 示例                            | 描述                                                         |
| :-------------: | ------------------------------- | ------------------------------------------------------------ |
|    `[attr]`     | `a[title]`                      | 匹配带有一个名为*attr*的属性的元素——方括号里的值。           |
| `[attr=value]`  | `a[href="https://example.com"]` | 匹配带有一个名为*attr*的属性的元素，其值正为*value*——引号中的字符串。 |
| `[attr~=value]` | `p[class~="special"]`           | 匹配带有一个名为*attr*的属性的元素 ，其值正为*value*，或者匹配带有一个*attr*属性的元素，其值有一个或者更多，至少有一个和*value*匹配。     注意，在一列中的好几个值，是用空格隔开的。 |
| `[attr|=value]` | `div[lang|="zh"]`               | 匹配带有一个名为*attr*的属性的元素，其值可正为*value*，或者开始为*value*，后面紧随着一个连字符。 |

###### 字符串匹配选择器

| 选择器          | 示例                | 描述                                                         |
| --------------- | ------------------- | ------------------------------------------------------------ |
| `[attr^=value]` | `li[class^="box-"]` | 匹配带有一个名为*attr*的属性的元素，其值开头为*value*子字符串。 |
| `[attr$=value]` | `li[class$="-box"]` | 匹配带有一个名为*attr*的属性的元素，其值结尾为*value*子字符串 |
| `[attr*=value]` | `li[class*="box"]`  | 匹配带有一个名为*attr*的属性的元素，其值的字符串中的任何地方，至少出现了一次*value*子字符串。 |

##### 伪类(状态)选择器

| 选择器                                                       | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`:active`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:active) | 在用户激活（例如点击）元素的时候匹配。                       |
| [`:any-link`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:any-link) | 匹配一个链接的`:link`和`:visited`状态。                      |
| [`:blank`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:blank) | 匹配空输入值的[``元素](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)。 |
| [`:checked`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:checked) | 匹配处于选中状态的单选或者复选框。                           |
| [`:current` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/:current) | 匹配正在展示的元素，或者其上级元素。                         |
| [`:default`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:default) | 匹配一组相似的元素中默认的一个或者更多的UI元素。             |
| [`:dir`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:dir) | 基于其方向性（HTML`dir`属性或者CSS`direction`属性的值）匹配一个元素。 |
| [`:disabled`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:disabled) | 匹配处于关闭状态的用户界面元素                               |
| [`:empty`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:empty) | 匹配除了可能存在的空格外，没有子元素的元素。                 |
| [`:enabled`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:enabled) | 匹配处于开启状态的用户界面元素。                             |
| [`:first`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first) | 匹配[分页媒体](https://developer.mozilla.org/en-US/docs/Web/CSS/Paged_Media)的第一页。 |
| [`:first-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-child) | 匹配兄弟元素中的第一个元素。                                 |
| [`:first-of-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:first-of-type) | 匹配兄弟元素中第一个某种类型的元素。                         |
| [`:focus`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus) | 当一个元素有焦点的时候匹配。                                 |
| [`:focus-visible`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus-visible) | 当元素有焦点，且焦点对用户可见的时候匹配。                   |
| [`:focus-within`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus-within) | 匹配有焦点的元素，以及子代元素有焦点的元素。                 |
| [`:future` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/:future) | 匹配当前元素之后的元素。                                     |
| [`:hover`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:hover) | 当用户悬浮到一个元素之上的时候匹配。                         |
| [`:indeterminate`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:indeterminate) | 匹配未定态值的UI元素，通常为[复选框](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)。 |
| [`:in-range`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:in-range) | 用一个区间匹配元素，当值处于区间之内时匹配。                 |
| [`:invalid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:invalid) | 匹配诸如`<input>`的位于不可用状态的元素。                    |
| [`:lang`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:lang) | 基于语言（HTML[lang](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/lang)属性的值）匹配元素。 |
| [`:last-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:last-child) | 匹配兄弟元素中最末的那个元素。                               |
| [`:last-of-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:last-of-type) | 匹配兄弟元素中最后一个某种类型的元素。                       |
| [`:left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:left) | 在[分页媒体 (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Pages)中，匹配左手边的页。 |
| [`:link`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:link) | 匹配未曾访问的链接。                                         |
| [`:local-link` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/:local-link) | 匹配指向和当前文档同一网站页面的链接。                       |
| [`:is()`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:is) | 匹配传入的选择器列表中的任何选择器。                         |
| [`:not`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:not) | 匹配作为值传入自身的选择器未匹配的物件。                     |
| [`:nth-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-child) | 匹配一列兄弟元素中的元素——兄弟元素按照an+b形式的式子进行匹配（比如2n+1匹配元素1、3、5、7等。即所有的奇数个）。 |
| [`:nth-of-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-of-type) | 匹配某种类型的一列兄弟元素（比如，`<p>`元素）——兄弟元素按照an+b形式的式子进行匹配（比如2n+1匹配元素1、3、5、7等。即所有的奇数个）。 |
| [`:nth-last-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-last-child) | 匹配一列兄弟元素，从后往前倒数。兄弟元素按照an+b形式的式子进行匹配（比如2n+1匹配按照顺序来的最后一个元素，然后往前两个，再往前两个，诸如此类。从后往前数的所有奇数个）。 |
| [`:nth-last-of-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-last-of-type) | 匹配某种类型的一列兄弟元素（比如，`<p>`元素），从后往前倒数。兄弟元素按照an+b形式的式子进行匹配（比如2n+1匹配按照顺序来的最后一个元素，然后往前两个，再往前两个，诸如此类。从后往前数的所有奇数个）。 |
| [`:only-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:only-child) | 匹配没有兄弟元素的元素。                                     |
| [`:only-of-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:only-of-type) | 匹配兄弟元素中某类型仅有的元素。                             |
| [`:optional`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:optional) | 匹配不是必填的form元素。                                     |
| [`:out-of-range`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:out-of-range) | 按区间匹配元素，当值不在区间内的的时候匹配。                 |
| [`:past` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/:past) | 匹配当前元素之前的元素。                                     |
| [`:placeholder-shown`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:placeholder-shown) | 匹配显示占位文字的input元素。                                |
| [`:playing` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/:playing) | 匹配代表音频、视频或者相似的能“播放”或者“暂停”的资源的，且正在“播放”的元素。 |
| [`:paused` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/:paused) | 匹配代表音频、视频或者相似的能“播放”或者“暂停”的资源的，且正在“暂停”的元素。 |
| [`:read-only`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:read-only) | 匹配用户不可更改的元素。                                     |
| [`:read-write`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:read-write) | 匹配用户可更改的元素。                                       |
| [`:required`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:required) | 匹配必填的form元素。                                         |
| [`:right`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:right) | 在[分页媒体 (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Pages)中，匹配右手边的页。 |
| [`:root`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:root) | 匹配文档的根元素。                                           |
| [`:scope`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:scope) | 匹配任何为参考点元素的的元素。                               |
| [`:valid`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:valid) | 匹配诸如`<input>`元素的处于可用状态的元素。                  |
| [`:target`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:target) | 匹配当前URL目标的元素（例如如果它有一个匹配当前[URL分段](https://en.wikipedia.org/wiki/Fragment_identifier)的元素）。 |
| [`:visited`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:visited) | 匹配已访问链接。                                             |

##### 伪元素（内容）选择器

| 选择器                                                       | 描述                                                 |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| [`::after`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::after) | 匹配出现在原有元素的实际内容之后的一个可样式化元素。 |
| [`::before`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::before) | 匹配出现在原有元素的实际内容之前的一个可样式化元素。 |
| [`::first-letter`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::first-letter) | 匹配元素的第一个字母。                               |
| [`::first-line`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::first-line) | 匹配包含此伪元素的元素的第一行。                     |
| [`::grammar-error`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::grammar-error) | 匹配文档中包含了浏览器标记的语法错误的那部分。       |
| [`::selection`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::selection) | 匹配文档中被选择的那部分。                           |
| [`::spelling-error`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::spelling-error) | 匹配文档中包含了浏览器标记的拼写错误的那部分。       |

##### 关系选择器

###### 后代关系选择器（空格）

```
body article p
```

###### 子代关系选择器

```
article > p
```

###### 邻接兄弟关系选择器

```
p + img
```

###### 通用兄弟关系选择器

```
p ~ img
```

### 盒模型

##### 块级盒子

一个被定义成块级的（block）盒子会表现出以下行为:

- 盒子会在内联的方向上扩展并占据父容器在该方向上的所有可用空间，在绝大数情况下意味着盒子会和父容器一样宽
- 每个盒子都会换行
- [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width) 和 [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height) 属性可以发挥作用
- 内边距（padding）, 外边距（margin） 和 边框（border） 会将其他元素从当前盒子周围“推开”

##### 内联盒子

如果一个盒子对外显示为 `inline`，那么他的行为如下:

- 盒子不会产生换行。
-  [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width) 和 [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height) 属性将不起作用。
- 垂直方向的内边距、外边距以及边框会被应用但是不会把其他处于 `inline` 状态的盒子推开。
- 水平方向的内边距、外边距以及边框会被应用且会把其他处于 `inline` 状态的盒子推开。

注：<u>*我们通过对盒子[`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display) 属性的设置，比如 `inline` 或者 `block` ，来控制盒子的外部显示类型。*</u>

##### 盒模型

CSS中组成一个块级盒子需要:

- **Content box**: 这个区域是用来显示内容，大小可以通过设置 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width) 和 [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height).
- **Padding box**: 包围在内容区域外部的空白区域； 大小通过 [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding) 相关属性设置。
- **Border box**: 边框盒包裹内容和内边距。大小通过 [`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border) 相关属性设置。
- **Margin box**: 这是最外面的区域，是盒子和其他元素之间的空白区域。大小通过 [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin) 相关属性设置。

![Diagram of the box model](https://mdn.mozillademos.org/files/16558/box-model.png)

```CSS
.box {
  width: 350px;
  height: 150px;
  margin: 25px;
  padding: 25px;
  border: 5px solid black;
}
```

###### 标准盒模型

如果使用标准模型宽度 = 410px (350 + 25 + 25 + 5 + 5)，高度 = 210px (150 + 25 + 25 + 5 + 5)，padding 加 border 再加 content box

![Showing the size of the box when the standard box model is being used.](https://mdn.mozillademos.org/files/16559/standard-box-model.png)

###### 替代（IE）盒模型

你可能会认为盒子的大小还要加上边框和内边距，这样很麻烦，而且你的想法是对的! 因为这个原因，css还有一个替代盒模型。使用这个模型，所有宽度都是可见宽度，所以内容宽度是该宽度减去边框和填充部分。使用上面相同的样式得到 (width = 350px, height = 150px).

![Showing the size of the box when the alternate box model is being used.](https://mdn.mozillademos.org/files/16557/alternate-box-model.png)

*注：默认浏览器会使用标准模型。如果需要使用替代模型，您可以通过为其设置 `box-sizing: border-box` 来实现。 这样就可以告诉浏览器使用 `border-box` 来定义区域，从而设定您想要的大小*

```
.box {
  box-sizing: border-box;
} 
```

*如果你希望所有元素都使用替代模式，而且确实很常用，设置 `box-sizing` 在 `<html>` 元素上，然后设置所有元素继承该属性，正如下面的例子。如果想要深入理解，请看 [the CSS Tricks article on box-sizing](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/)。*

```
html {
  box-sizing: border-box;
}
*, *::before, *::after {
  box-sizing: inherit;
}
```

##### 使用display：inline-block

display有一个特殊的值，它在内联和块之间提供了一个中间状态。这对于以下情况非常有用:您不希望一个项切换到新行，但希望它可以设定宽度和高度，并避免上面看到的重叠。

一个元素使用 `display: inline-block`，实现我们需要的块级的部分效果：

- 设置`width` 和`height` 属性会生效。
- `padding`, `margin`, 以及`border` 会推开其他元素。

但是，它不会跳转到新行，如果显式添加`width` 和`height` 属性，它只会变得比其内容更大。

![image-20211021153748237](.\images\image-20211021153748237.png)

### 背景和边框

#### 背景颜色

```
background-color: #567895;

background-color: black;

background-color: rgba(255,255,255,.5);
```



#### 背景图片

##### 默认大图不会缩小以适应反馈，小图则平铺填充方框

```
background-image: url(balloons.jpg);
```

##### 控制背景平铺

[`background-repeat`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-repeat)属性用于控制图像的平铺行为。可用的值是:

- `no-repeat` — 不重复。
- `repeat-x` —水平重复。
- `repeat-y` —垂直重复。
- `repeat` — 在两个方向重复

##### 调整背景大小

 [`background-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size)属性，它可以设置长度或百分比值，来调整图像的大小以适应背景。

你也可以使用关键字:

- `cover` —浏览器将使图像足够大，使它完全覆盖了盒子区，同时仍然保持其高宽比。在这种情况下，有些图像可能会跳出盒子外
- `contain` — 浏览器将使图像的大小适合盒子内。在这种情况下，如果图像的长宽比与盒子的长宽比不同，则可能在图像的任何一边或顶部和底部出现间隙。

##### 背景图像定位

[`background-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position)属性允许您选择背景图像显示在其应用到的盒子中的位置。它使用的坐标系中，框的左上角是(0,0)，框沿着水平(x)和垂直(y)轴定位。也可以用关键字，长度值，百分比

*注：默认位置(0,0)*，`background-position`是[`background-position-x`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position-x)和[`background-position-y`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position-y)的简写，它们允许您分别设置不同的坐标轴的值。

```
background-position: top center;
background-position: 20px 10%;
background-position: top 20px;
```

还可以用您还可以使用4-value语法来指示到盒子的某些边的距离

```
background-position: top 20px right 10px;
```

##### 多个背景图片

背景将与最后列出的背景图像层在堆栈的底部，背景图像在代码列表中最先出现的在顶端。

```
background-image: url(image1.png), url(image2.png), url(image3.png), url(image1.png);
background-repeat: no-repeat, repeat-x, repeat;
background-position: 10px 20px,  top right
```

不同属性的每个值，将与其他属性中相同位置的值匹配。例如，上面的image1的background-repeat值将是no-repeat。但是，当不同的属性具有不同数量的值时，会发生什么情况呢？答案是较小数量的值会循环—在上面的例子中有四个背景图像，但是只有两个背景位置值。前两个位置值将应用于前两个图像，然后它们将再次循环—image3将被赋予第一个位置值，image4将被赋予第二个位置值

#### 渐变背景

##### 水平渐变

```
background-image: linear-gradient(105deg, rgba(0,249,255,1) 39%, rgba(51,56,57,1) 96%);
```

linear-gradient() 函数用于创建一个线性渐变的 "图像"

它的语法是

　　background: linear-gradient(direction, color-stop1, color-stop2, ...);

**direction**

　　用角度值指定渐变的方向

　　　　方向值：常用的是to top，to bottom，to left，to right,to right top等等

　　　　角度值：常用的是0deg、180deg等等

**color-stop1**

　　color

　　　　使用关键字red、rgba等颜色值（透明也可以设置）

　　stop

　　　　是这个颜色块终止位置，换句话说就是这块颜色占的区域

　　ps：颜色值至少两个

 

角度值

　　　先来看看文档的图画

　　　　　![img](https://img2018.cnblogs.com/i-beta/1019775/201912/1019775-20191212214056147-3382218.png)

 

　　　　0deg不是按我们数学的角度向右定义的，默认方向是向上的，是从方向北开始的，所以北才是0deg，

　　　　

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
　　.back{
        width: 300px;
        height: 300px;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%,-50%);
        background: linear-gradient(90deg,#02a0ff,red);
    }
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

 

 

 

　　　　当为90deg时，渐变线的方向相当于to right，从左指向右

　　　　　　![img](https://img2018.cnblogs.com/i-beta/1019775/201912/1019775-20191212215125994-264685043.png)

 

 

 

 

　　　　当为135deg时，渐变线的方向相当于to right bottom，从左上指向右下，相反为-135时，就从右上指向左下

　　　　　　![img](https://img2018.cnblogs.com/i-beta/1019775/201912/1019775-20191212215425908-305438838.png)

 

 

 颜色-终止位置

　　该值由一个<color>值组成，后跟一个可选的停止位置

 

 

 　

　　以上两种情形是颜色渐变，占的区域非常均匀，相当于background: linear-gradient(-135deg,#02a0ff 0%,red 100%)，都是从0-100%的比例结束的

　　 所以这个区域是可以修改的

　　　　　　![img](https://img2018.cnblogs.com/i-beta/1019775/201912/1019775-20191212220801737-341593991.png)

 

 

 　如上图，修改了参数

```
background: linear-gradient(180deg,#02a0ff 20%,red 80%);
```

　　20%相当于第一个颜色的区域，第一个白色箭头就是颜色1与颜色2初始渐变，最后一个白色箭头就表示完成渐变

　　我们会发现，顶部的20%和底部的20%并没有渐变，所以我们可以理解颜色1的20%为开始位置，颜色2的80%为结束位置。

　　

　　我们将颜色1的值改成大于后面颜色的值，得到以下结果

```
background: linear-gradient(180deg,#02a0ff 60%,red 20%);
```

 

　　　　　　![img](https://img2018.cnblogs.com/i-beta/1019775/201912/1019775-20191212222339474-771314096.png)

 

 　颜色1和颜色2直接就没有产生阴影了，所以阴影产生是在区间里面的

　　

做一个三角形覆盖图片

　　![img](https://img2018.cnblogs.com/i-beta/1019775/201912/1019775-20191212223555949-1958107228.png)

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
.box{
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%,-50%);
    }

    .box img{
        display: block;
    }

    .back{
        width: 330px;
        height: 100%;
        position: absolute;
        right: 0;
        top: 0;
        background: linear-gradient(135deg,transparent 50%,red 50%);
    }

　　<div class="box">
        <div class="back"></div>
        <img src="./img/dflmg.jpg">
    </div>
```

##### 圆形渐变

```
background-image: radial-gradient(circle, rgba(0,249,255,1) 39%, rgba(51,56,57,1) 96%);
```

#### 背景滚动

内容滚动。这是由[`background-attachment`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-attachment)属性控制的，它可以接受以下值:

- `scroll`: 使元素的背景在页面滚动时滚动。如果滚动了元素内容，则背景不会移动。实际上，背景被固定在页面的相同位置，所以它会随着页面的滚动而滚动。
- `fixed`: 使元素的背景固定在视图端口上，这样当页面或元素内容滚动时，它就不会滚动。它将始终保持在屏幕上相同的位置。
- `local`: 这个值是后来添加的(它只在Internet Explorer 9+中受支持，而其他的在IE4+中受支持)，因为滚动值相当混乱，在很多情况下并不能真正实现您想要的功能。局部值将背景固定在设置的元素上，因此当您滚动元素时，背景也随之滚动。

例子https://mdn.github.io/learning-area/css/styling-boxes/backgrounds/background-attachment.html

### 边框

#### 同时设置四条边

```
.box {
  border: 1px solid black;
} 
```

#### 单独设置一条

```
.box {
  border-top: 1px solid black;
}
```

一次写多个属性（顺序不固定）等价于分开写。

```
.box {
  border-width: 1px;
  border-style: solid;
  border-color: black;
}
```

### 圆角

通过使用[`border-radius`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-radius)属性和与方框的每个角相关的长边来实现方框的圆角。可以使用两个长度或百分比作为值，第一个值定义水平半径，第二个值定义垂直半径。在很多情况下，您将只传递一个值，这两个值都将使用。

例如，要使一个盒子的四个角都有10px的圆角半径：

```
.box {
  border-radius: 10px;
} 
```

或使右上角的水平半径为1em，垂直半径为10％：

```
.box {
  border-top-right-radius: 1em 10%;
} 
```

### 书写模式

CSS中的书写模式是指文本的排列方向是横向还是纵向的。[`writing-mode`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/writing-mode) 属性使我们从一种模式切换到另一种模式。为此，你不必使用一种竖向的语言——你还可以更改部分文字的方向以实现创新性的布局。

`writing-mode`的三个值分别是：

- `horizontal-tb`: 块流向从上至下。对应的文本方向是横向的。
- `vertical-rl`: 块流向从右向左。对应的文本方向是纵向的。
- `vertical-lr`: 块流向从左向右。对应的文本方向是纵向的。

因此，`writing-mode`属性实际上设定的是页面上块级元素的显示方向——要么是从上到下，要么是从右到左，要么是从左到右。而这决定了文本的方向。

用一个例子可以更清楚地说明这一点。下一个例子中有两个盒子，分别包含一个标题和一个段落。第一个盒子应用的是`writing-mode: horizontal-tb`，这是一个从上到下的横向的书写模式。第二个盒子应用的是`writing-mode: vertical-rl`，这是一个从右到左的纵向的书写模式。

![image-20211021204032018](.\images\image-20211021204032018.png)

不同书写模式下布局也不同

![img](https://mdn.mozillademos.org/files/17148/horizontal-tb-zh.png)

![img](https://mdn.mozillademos.org/files/17149/vertical-zh.png)

### 逻辑属性与逻辑值

#### 逻辑长和逻辑宽

我们想要的实际上是使宽和高随着书写模式一起变化。当处于纵向书写模式之下时，我们希望盒子可以向横向模式下一样得到拓宽。

为了更容易实现这样的转变，CSS最近开发了一系列映射属性。这些属性用逻辑（**logical**）和相对变化（**flow relative**）代替了像宽`width`和高`height`一样的物理属性。

横向书写模式下，映射到`width`的属性被称作内联尺寸（[`inline-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/inline-size)）——内联维度的尺寸。而映射`height`的属性被称为块级尺寸（[`block-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/block-size)），这是块级维度的尺寸。下面的例子展示了替换掉`width`的`inline-size`是如何生效的。

#### 逻辑外边距、边框和内边距

- `top`属性映射为`block-start`
- `bottom`属性映射为`block-end`
- `left`属性映射为`inline-start`
- `right`属性映射为`inline-end`

*注：用逻辑属性和逻辑值时，改变书写模式后原来的各个属性（边框、边距）随着书写方向改变，不影响阅读*

将原来属性的方位改成相应的逻辑方位就是逻辑属性了。

### 溢出

当模块中的内容超过模块边界是就是溢出

#### overflow属性

- [`overflow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow)属性是你控制一个元素溢出的方式，它告诉浏览器你想怎样处理溢出。`overflow`的默认值为`visible`，这就是我们的内容溢出的时候，我们在默认情况下看到它们的原因。
- 如果你想在内容溢出的时候把它裁剪掉，你可以在你的盒子上设置`overflow: hidden`。
- 如果你用了`overflow: scroll`，那么你的浏览器总会显示滚动条，即使没有足够多引起溢出的内容。（overflow-x、overflow-y设置不同方向的滚动条）
- 如果你只是想让滚动条在有比盒子所能装下更多的内容的时候才显示，那么使用`overflow: auto`。此时由浏览器决定是否显示滚动条。桌面浏览器一般仅仅会在有足以引起溢出的内容的时候这么做。

**注意：** 你可以用`overflow`属性指定x轴和y轴方向的滚动，同时使用两个值进行传递。如果指定了两个关键字，第一个对`overflow-x`生效而第二个对`overflow-y`生效。否则，`overflow-x`和`overflow-y`将会被设置成同样的值。例如，`overflow: scroll hidden`会把`overflow-x`设置成`scroll`，而`overflow-y`则为`hidden`

### CSS的值与单位

#### 数值

| 数值类型       | 描述                                                         |
| -------------- | ------------------------------------------------------------ |
| `<integer>`    | `<integer>`是一个整数，比如1024或-55。                       |
| `<number>`     | `<number>`表示一个小数——它可能有小数点后面的部分，也可能没有，例如0.255、128或-1.2。 |
| `<dimension>`  | `<dimension>`是一个`<number>`，它有一个附加的单位，例如45deg、5s或10px。`<dimension>`是一个伞形类别，包括`<length>`、`<angle>`、`<time>`和`<resolution>`类型。 |
| `<percentage>` | `<percentage>`表示一些其他值的一部分，例如50%。百分比值总是相对于另一个量，例如，一个元素的长度相对于其父元素的长度。 |

#### 绝对长度

| 单位 | 名称         | 等价换算            |
| ---- | ------------ | ------------------- |
| `cm` | 厘米         | 1cm = 96px/2.54     |
| `mm` | 毫米         | 1mm = 1/10th of 1cm |
| `Q`  | 四分之一毫米 | 1Q = 1/40th of 1cm  |
| `in` | 英寸         | 1in = 2.54cm = 96px |
| `pc` | 十二点活字   | 1pc = 1/16th of 1in |
| `pt` | 点           | 1pt = 1/72th of 1in |
| `px` | 像素         | 1px = 1/96th of 1in |

#### 相对长度

| 单位   | 相对于                                                       |
| ------ | ------------------------------------------------------------ |
| `em`   | 在 font-size 中使用是相对于父元素的字体大小，在其他属性中使用是相对于自身的字体大小，如 width |
| `ex`   | 字符“x”的高度                                                |
| `ch`   | 数字“0”的宽度                                                |
| `rem`  | 根元素的字体大小                                             |
| `lh`   | 元素的line-height                                            |
| `vw`   | 视窗宽度的1%                                                 |
| `vh`   | 视窗高度的1%                                                 |
| `vmin` | 视窗较小尺寸的1%                                             |
| `vmax` | 视图大尺寸的1%                                               |

##### em和rem(root element)

- 概括地说，在排版属性中 em 单位的意思是“父元素的字体大小”。

  父元素大小变，则其变。

- 概括地说，rem单位的意思是“根元素的字体大小”.

​        根元素大小变，则代代递进变。

##### 百分比（代代递进变）

在许多情况下，百分比与长度的处理方法是一样的。百分比的问题在于，它们总是相对于其他值设置的。例如，如果将元素的字体大小设置为百分比，那么它将是元素父元素字体大小的百分比。如果使用百分比作为宽度值，那么它将是父值宽度的百分比。

##### 数字

有些值接受数字，不添加任何单位。接受无单位数字的属性的一个例子是不透明度属性（`opacity` ），它控制元素的不透明度(它的透明程度)。此属性接受0(完全透明)和1(完全不透明)之间的数字。

```
.box {
  opacity: 0.6;
}
```

### 颜色

#### 十六进制RGB值

您可能遇到的下一种颜色值类型是十六进制代码。每个十六进制值由一个散列/磅符号(#)和六个十六进制数字组成，每个十六进制数字都可以取0到f(代表15)之间的16个值中的一个——所以是0123456789abcdef。每对值表示一个通道—红色、绿色和蓝色—并允许我们为每个通道指定256个可用值中的任意一个(16 x 16 = 256)。

```
.one {
  background-color: #02798b;
}

.two {
  background-color: #c55da1;
}

.three {
  background-color: #128a7d;
}
```

#### RGB和RGBA值

我们将在这里讨论的第三种方案是RGB。RGB值是一个函数—RGB()—它有三个参数，表示颜色的红色、绿色和蓝色通道值，与十六进制值的方法非常相似。RGB的不同之处在于，每个通道不是由两个十六进制数字表示的，而是由一个介于0到255之间的十进制数字表示的——这有点容易理解。

```
.one {
  background-color: rgb(2, 121, 139);
}

.two {
  background-color: rgb(197, 93, 161);
}

.three {
  background-color: rgb(18, 138, 125);
}
```

您还可以使用RGBA颜色——它们的工作方式与RGB颜色完全相同，因此您可以使用任何RGB值，但是有第四个值表示颜色的alpha通道，它控制不透明度。如果将这个值设置为`0`，它将使颜色完全透明，而设置为`1`将使颜色完全不透明。介于两者之间的值提供了不同级别的透明度。

```
.one {
  background-color: rgba(2, 121, 139, .3);
}

.two {
  background-color: rgba(197, 93, 161, .7);
}

.three {
  background-color: rgba(18, 138, 125, .9);
}
```

**注意：**在某种程度上，现代浏览器得到了更新，从而让`rgba()` 和`rgb()` （以及 `hsl()`和 `hsla()`;见下文）成为彼此的纯别名并开始表现完全相同，因此`rgba()` 和`rgb()` 接受带有和不带有alpha通道值的颜色。 尝试将上面示例的`rgba()` 函数更改为`rgb()` ，看看颜色是否仍然有效！ 使用哪种样式由您决定，但是将非透明和透明的颜色定义分开使用不同的功能可以（非常）更好地支持浏览器，并且可以直观地指示代码中定义透明颜色的位置。

#### HSL和HSLA值

与RGB相比，HSL颜色模型的支持稍差一些(在旧版本的IE中不支持)，它是在设计师们感兴趣之后实现的。`hsl()` 函数接受色调、饱和度和亮度值作为参数，而不是红色、绿色和蓝色值，这些值的不同方式组合，可以区分1670万种颜色：

- **色调**： 颜色的底色。这个值在0和360之间，表示色轮周围的角度。
- **饱和度**： 颜色有多饱和？ 它的值为0 - 100%，其中0为无颜色(它将显示为灰色阴影)，100%为全色饱和度
- **亮度**：颜色有多亮？ 它从0 - 100%中获取一个值，其中0表示没有光(它将完全显示为黑色)，100%表示完全亮(它将完全显示为白色

```
.one {
  background-color: hsl(188, 97%, 28%);
}

.two {
  background-color: hsl(321, 47%, 57%);
}

.three {
  background-color: hsl(174, 77%, 31%);
}
```

    .one {
      background-color: hsla(188, 97%, 28%, .3);
    }
    
    .two {
      background-color: hsla(321, 47%, 57%, .7);
    }
    
    .three {
      background-color: hsla(174, 77%, 31%, .9);
    }
### 图片

`<image>` 数据类型用于图像为有效值的任何地方。它可以是一个通过 `url()`函数指向的实际图像文件，也可以是一个渐变。

在下面的例子中，我们演示了一个图像和一个渐变作为CSS `background-image`属性的值。

```
.image {
  background-image: url(star.png);
}

.image {
  background-image: linear-gradient(90deg, rgba(119,0,255,1) 39%, rgba(0,212,255,1) 100%);
}
```

### 位置

`<position>` 数据类型表示一组2D坐标，用于定位一个元素，如背景图像(通过 `background-position`)。它可以使用关键字(如 `top`, `left`, `bottom`, `right`, 以及`center` )将元素与2D框的特定边界对齐，以及表示框的顶部和左侧边缘偏移量的长度

一个典型的位置值由两个值组成——第一个值水平地设置位置，第二个值垂直地设置位置。如果只指定一个轴的值，另一个轴将默认为 `center`。

### 字符串

插入字符串

```
.box {
  width:400px;
  padding: 1em;
  border-radius: .5em;
  border: 5px solid rebeccapurple;
  background-color: lightblue;
}

.box::after {
  content: "This is a string. I know because it is quoted in the CSS."
}
```

​    

```
<div class="box"></div> 
```

### 函数

`rgb()`、`hsl()`、`calc()`等。用于从文件返回图像的值——`url()`——也是一个函数。

```
.wrapper {
  width: 400px;
}

.box {
  width: calc(20% + 100px);
}
```

### mini-和max-尺寸

[`min-height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/min-height)属性。盒子就会一直保持大于这个最小高度，但是如果有比这个盒子在最小高度状态下所能容纳的更多内容，那么盒子就会变大。

```
.box {
  border: 5px solid darkblue;
  min-height: 150px;
  width: 200px;
}
```

 [`max-width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/max-width)的常见用法为，在没有足够空间以原有宽度展示图像时，让图像缩小，同时确保它们不会比这一宽度大

### 视窗单位

视口，即你在浏览器中看到的部分页面，也是有尺寸的。在CSS中，我们有与视口尺寸相关的度量单位，即意为视口宽度的`vw`单位，以及意为视口高度的 `vh`单位。使用这些单位，你可以把一些东西做得随用户的视口改变大小。

`1vh`等于视口高度的1%，`1vw`则为视口宽度的1%.你可以用这些单位约束盒子的大小，还有文字的大小。在下面的示例里，我们有一个大小被设为20vh和20vw的盒子。这个盒子里面有一个字母`A`，其[`font-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size)属性被设成了10vh

```
.box {
  border: 5px solid darkblue;
  width: 20vw;
  height: 20vh;
  font-size: 10vh;
}
```

### 图像展示方式

**先设置图片小于等于边框的情况下才能设置展示方式，否则溢出后展示方式无效。**

**object-fit:**

- cover覆盖全部

- contain包含其中

- fill变形填充

  ![image-20211026213747863](.\images\image-20211026213747863.png)

```
.box {
  width: 200px;
  height: 200px;
}

img {
  height: 100%;
  width: 100%;
}

.cover {
  object-fit: cover;
}

.contain {
  object-fit: contain;
}
.cn{
  object-fit:fill;
}
```

    <div class="wrapper">
      <div class="box"><img src="balloons.jpg" alt="balloons" class="cover"></div>
      <div class="box"><img src="balloons.jpg" alt="balloons" class="contain">
    </div>
       <div class="box"><img src="balloons.jpg" alt="balloons" class="cn"> </div>
    </div>

### 样式化form元素（统一）

**通过以下代码可以重置表示样式，方便后单独设置。**

```
button,
input,
select,
textarea {
  font-family: inherit;
  font-size: 100%;
  box-sizing: border-box;
  padding: 0; margin: 0;
}

textarea {
  overflow: auto;
} 
```

### 样式化表格

#### [一个典型的HTML表格](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#一个典型的html表格)

让我们从一个典型的HTML表格开始。恩，我说典型——大多数HTML表格都是关于鞋子，天气，或者员工的。我们决定通过制作英国著名的朋克乐队来让事情变得更有趣。标记看起来是这样的

```
<table>
  <caption>A summary of the UK's most famous punk bands</caption>
  <thead>
    <tr>
      <th scope="col">Band</th>
      <th scope="col">Year formed</th>
      <th scope="col">No. of Albums</th>
      <th scope="col">Most famous song</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Buzzcocks</th>
      <td>1976</td>
      <td>9</td>
      <td>Ever fallen in love (with someone you shouldn't've)</td>
    </tr>
    <tr>
      <th scope="row">The Clash</th>
      <td>1976</td>
      <td>6</td>
      <td>London Calling</td>
    </tr>

      ... some rows removed for brevity

    <tr>
      <th scope="row">The Stranglers</th>
      <td>1974</td>
      <td>17</td>
      <td>No More Heroes</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row" colspan="2">Total albums</th>
      <td colspan="2">77</td>
    </tr>
  </tfoot>
</table>
```

由于[`scope`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th#attr-scope)、`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption)、、等特性，表格被很好地标记了，易于使用，并且易于访问，不幸的是，它在屏幕上呈现时看起来不太好（见它的预览版 [punk-bands-unstyled.html](https://mdn.github.io/learning-area/css/styling-boxes/styling-tables/punk-bands-unstyled.html)）：

![img](https://mdn.mozillademos.org/files/13064/table-unstyled.png)

它看起来很拥挤，很难阅读，也很无聊。我们需要使用一些CSS来解决这个问题。

#### [自主学习：样式化我们的表格](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#自主学习：样式化我们的表格)

在这个自主学习部分中，我们将一起来样式化我们的表格。

1. 首先，复制[实例标记](https://github.com/mdn/learning-area/blob/master/css/styling-boxes/styling-tables/punk-bands-unstyled.html)到本地，下载这两个图像([noise](https://github.com/mdn/learning-area/blob/master/css/styling-boxes/styling-tables/noise.png)和 [leopardskin](https://github.com/mdn/learning-area/blob/master/css/styling-boxes/styling-tables/leopardskin.jpg))，然后将三个结果文件放在本地计算机的某个工作目录中。
2. 接下来，创建一个名为`style.css`的新文件并将其保存在与其他文件相同的目录中。
3. 将CSS链接到HTML中，将下面的HTML代码放到HTML的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/head)中：

```
<link href="style.css" rel="stylesheet" type="text/css">
```

#### [间距和布局](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#间距和布局)

我们需要做的第一件事是整理出空间/布局——默认的表格样式是如此的拥挤！要做到这一点，请将以下CSS添加到您的 `style.css` 文件：

```
/* spacing */

table {
  table-layout: fixed;
  width: 100%;
  border-collapse: collapse;
  border: 3px solid purple;
}

thead th:nth-child(1) {
  width: 30%;
}

thead th:nth-child(2) {
  width: 20%;
}

thead th:nth-child(3) {
  width: 15%;
}

thead th:nth-child(4) {
  width: 35%;
}

th, td {
  padding: 20px;
}
```

需要注意的最重要的部分如下：

- 在你的表上，给[`table-layout`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/table-layout)属性设置一个为`fixed`的值通常是一个好主意，因为它使表的行为在默认情况下更可预测。通常情况下，表列的尺寸会根据所包含的内容大小而变化，这会产生一些奇怪的结果。通过 `table-layout: fixed`，您可以根据列标题的宽度来规定列的宽度，然后适当地处理它们的内容。这就是为什么我们使用了`thead th:nth-child(*n*)` 选择了四个不同的标题([`:nth-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-child))选择器（“选择第n个子元素，它是一个顺序排列的`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th)元素，且其父元素是元素”）并给定了它们的百分比宽度。整个列宽度与列标题的宽度是一样的，这是一种很好的设定表列尺寸的方式。Chris Coyier在[Fixed Table Layouts](https://css-tricks.com/fixing-tables-long-strings/)中更详细地讨论了这一技术。
  
    我们将它与一个100%的[`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width)组合在一起，这意味着该表将填充它放入的任何容器，并且能很好的响应（虽然它仍然需要更多的工作来让它在窄屏宽度上看起来很好）。
- 一个[`border-collapse`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-collapse)属性的`collapse`值对于任何表样式的工作来说都是一个标准的最佳实践。默认情况下，当您在表元素上设置边框时，它们之间将会有间隔，如下图所示：![img](https://mdn.mozillademos.org/files/13068/no-border-collapse.png)这看起来不太好(虽然可能是你想要的样子，谁知道呢?)。使用 `border-collapse: collapse;` ，让边框合为一条，现在看起来好多了：![img](https://mdn.mozillademos.org/files/13066/border-collapse.png)
- 我们在整个表设置了一个[`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border)，这是必要的，因为我们将在表页眉和页脚后面设置一些边框——当你在表格外面没有一个边界而且以空隙结尾的时候，它看起来很奇怪，而且是不连贯的。
- 我们在`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th)和`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td)元素上设置了一些[`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding)——这些元素使数据项有了一些空间，使表看起来更加清晰。

此刻，我们的表看起来好多了：

![img](https://mdn.mozillademos.org/files/13070/table-with-spacing.png)

#### [一些简单的排版：](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#一些简单的排版：)

现在我们把类型整理一下。

首先，我们在[Google Fonts](https://www.google.com/fonts)上找到了一种适合于朋克乐队的字体的字体。如果你愿意，你可以去那里找一个不同的。现在，您只需替换我们提供的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link)元素和定制的[`font-family`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-family)声明，并使用Google字体提供给您的内容。

首先，将下面的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link)元素添加到您的HTML头部，就在您现有的 `<link>` 元素之上：

```
<link href='https://fonts.googleapis.com/css?family=Rock+Salt' rel='stylesheet' type='text/css'>
```

现在将下面的CSS添加到您的`style.css`文件，在之前内容后面添加：

```
/* typography */

html {
  font-family: 'helvetica neue', helvetica, arial, sans-serif;
}

thead th, tfoot th {
  font-family: 'Rock Salt', cursive;
}

th {
  letter-spacing: 2px;
}

td {
  letter-spacing: 1px;
}

tbody td {
  text-align: center;
}

tfoot th {
  text-align: right;
}
```

这里没有什么特别的东西。我们通常会对字体样式进行调整，使其更易于阅读：

- 我们已经设置了一个全局无衬线字体;这纯粹是一种风格上的选择。我们还在和元素的标题上设置了自定义字体，这是一种很不错的、很有朋克风格的外观。
- 我们在标题和单元格上设置了一些[`letter-spacing`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/letter-spacing)，因为我们觉得它有助于提高可读性。再次强调，这主要是一种风格上的选择。
- 我们在中的表格单元中对文本进行了居中对齐，使它们与标题对齐。默认情况下，单元格被赋予了一个[`text-align`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-align)的`left`值，并且标题被赋予了一个`center`值，但是通常情况下，让两者对齐看起来更好。标题字体的默认粗体值足以区分它们的外观。
- 我们在中对标题进行了右对齐，以便与它的数据点更好地关联。

结果看起来更整洁一些：

![img](https://mdn.mozillademos.org/files/13072/table-with-typography.png)

#### [图形和颜色](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#图形和颜色)

现在轮到图形和颜色了！因为表格上充满“朋克“和“个性”，我们需要给它再搭配一些鲜艳的造型。别担心，你不必让你的表格”燥起来“，你可以选择一些更巧妙、更有品位的东西。

首先将下面的CSS添加到`style.css`文件中，在底部添加:

```
thead, tfoot {
  background: url(leopardskin.jpg);
  color: white;
  text-shadow: 1px 1px 1px black;
}

thead th, tfoot th, tfoot td {
  background: linear-gradient(to bottom, rgba(0,0,0,0.1), rgba(0,0,0,0.5));
  border: 3px solid purple;
}
```

同样，对于表格这里没有什么特别的，但有几件事值得注意。

我们已经将一个[`background-image`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-image)添加到和，并将页眉和页脚的所有文本颜色[`color`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/color)更改为白色(并给它一个[`text-shadow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-shadow))，这样它的可读性就更好了。你应该确保你的文字与你的背景形成鲜明的对比，使得它是可读的。

我们还为`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th)和 `](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td)添加了一个线性渐变，在页眉和页脚中添加了一个漂亮的纹理，同时也为这些元素提供了一个明亮的紫色边框。有多个嵌套的元素是很有用的，这样您就可以将样式层叠在一起。是的，我们可以通过设置多组背景图像属性值来在和 元素上同时使用背景图像和线性渐变，但是我们决定分开使用，因为考虑到不支持多个背景图像或线性渐变的老浏览器。

#### 斑马条纹图案

我们想用一个单独的部分来展示如何实现斑马条纹（**zebra stripes**）——通过改变不同数据行的颜色，使表中交替行不同的数据行可以更容易地进行解析和读取。将下面的CSS添加到您的 `style.css` 文件底部：

```
tbody tr:nth-child(odd) {
  background-color: #ff33cc;
}

tbody tr:nth-child(even) {
  background-color: #e495e4;
}

tbody tr {
  background-image: url(noise.png);
}

table {
  background-color: #ff33cc;
}
```

- 您在前面看到了[`:nth-child`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:nth-child)选择器用于选择特定的子元素。它也可以用一个公式作为参数，来选择一个元素序列。公式`2n-1`会选择所有奇数的子元素(1、3、5等)，而公式`2n`会选择所有偶数的子元素(2、4、6等等)。我们在代码中使用了`odd`和`even`的关键字，这与前面提到的公式作用完全相同。在这里，我们给奇数行和偶数行不同的(醒目的)颜色。
- 我们还为所有的行添加了一个重复的噪点背景色块（一个半透明的`.png`，有一点视觉上的扭曲）来提供一些纹理。
- 最后，我们给整个表格提供了一个纯的背景颜色，这样浏览器不支持`:nth-child`选择器仍然有它们的正文行的背景。

这种颜色爆炸的结果如下：

![img](https://mdn.mozillademos.org/files/13074/table-with-color.png)

现在，这可能有点过头不符合你的品味，但我们在这里想要指出的一点是，表格并非只能是枯燥无味的，学术性的。

#### [样式化标题](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#样式化标题)

对我们的表格还有最后一点处理——样式化标题。要做到这一点，请将以下内容添加到您的`style.css` 文件底部：

```
caption {
  font-family: 'Rock Salt', cursive;
  padding: 20px;
  font-style: italic;
  caption-side: bottom;
  color: #666;
  text-align: right;
  letter-spacing: 1px;
}
```

这里没有什么值得注意的地方，除了[`caption-side`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/caption-side)属性，它被赋予了一个`bottom`的值。这就导致标题被放置在表格的底部，与其他声明一起提供了最后的外观（见预览版[punk-bands-complete.html](https://mdn.github.io/learning-area/css/styling-boxes/styling-tables/punk-bands-complete.html)）：

![img](https://mdn.mozillademos.org/files/13076/table-with-caption.png)

#### [自主学习：样式化你自己的表格](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#自主学习：样式化你自己的表格)

现在，我们希望您可以使用我们的示例表格HTML(或者使用您自己的一些！)，并将其样式设计成比我们的表更好的设计和不那么花哨的东西。

#### [表格样式小贴士](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Styling_tables#表格样式小贴士)

在继续之前，我们认为我们将为您提供一个快速列表，列出了上面提到的最有用的点：

- 使您的表格标记尽可能简单，并且保持灵活性，例如使用百分比，这样设计就更有响应性。
- 使用 [`table-layout`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/table-layout)`: fixed` 创建更可控的表布局，可以通过在标题[`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width)中设置[`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width)来轻松设置列的宽度。
- 使用 [`border-collapse`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-collapse)`: collapse` 使表元素边框合并，生成一个更整洁、更易于控制的外观。
- 使用, 和 将表格分割成逻辑块，并提供额外的应用CSS的地方，因此如果需要的话，可以更容易地将样式层叠在一起。
- 使用斑马线来让其他行更容易阅读。
- 使用 [`text-align`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-align)直线对齐您的`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/th)和`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/td)文本，使内容更整洁、更易于跟随。

### 调试CSS

介绍调试CSS的browser工具

https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Debugging_CSS

### 组织CSS

介绍规范化，工程化的CSS组织方式

https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Organizing

# 样式化文字

## 基本文本和字体样式

### [字体种类](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#字体种类)

要在你的文本上设置一个不同的字体，你可以使用 [`font-family`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-family) 属性，这个允许你为浏览器指定一个字体 (或者一个字体的列表)，然后浏览器可以将这种字体应用到选中的元素上。浏览器只会把在当前机器上可用的字体应用到当前正在访问的网站上；如果字体不可用，那么就会用浏览器默认的字体代替 [default font](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#default_fonts). 下面是一个简单的例子:

```
p {
  font-family: arial;
}
```

这段语句使所有在页面上的段落都采用 arial 字体，这个字体可在任何电脑上找到。

#### 网页安全字体

说到字体可用性，只有某几个字体通常可以应用到所有系统，因此可以毫无顾忌地使用。这些都是所谓的 **网页安全字体**。

大多数时候，作为网页开发者，我们希望对用于显示我们的文本内容的字体有更具体的控制。问题在于，需要一个方法来知道当前正在浏览我们的网站网页的电脑，它有哪些可用字体。我们并不是总能在每种情况下都知道这一点，但是网络安全字体在几乎所有最常用的操作系统（Windows，Mac，最常见的Linux发行版，Android和iOS版本）中都可用。

实际的Web安全字体列表将随着操作系统的发展而改变，但是可以认为下面的字体是网页安全的，至少对于现在来说 (它们中的许多都非常流行，这要感谢微软在90年代末和21世纪初期的倡议*[Core fonts for the Web](https://en.wikipedia.org/wiki/Core_fonts_for_the_Web)* )：

| 字体名称        | 泛型       | 注意                                                         |
| --------------- | ---------- | ------------------------------------------------------------ |
| Arial           | sans-serif | 通常认为最佳做法还是添加 Helvetica 作为 Arial 的首选替代品，尽管它们的字体面几乎相同，但 Helvetica 被认为具有更好的形状，即使Arial更广泛地可用。 |
| Courier New     | monospace  | 某些操作系统有一个 Courier New 字体的替代（可能较旧的）版本叫Courier。使用Courier New作为Courier的首选替代方案，被认为是最佳做法。 |
| Georgia         | serif      |                                                              |
| Times New Roman | serif      | 某些操作系统有一个 Times New Roman 字体的替代（可能较旧的）版本叫 Times。使用Times作为Times New Roman的首选替代方案，被认为是最佳做法。 |
| Trebuchet MS    | sans-serif | 您应该小心使用这种字体——它在移动操作系统上并不广泛。         |
| Verdana         | sans-serif |                                                              |

**注意**: 在各种资源中，[cssfontstack.com](http://www.cssfontstack.com/) 网站维护了一个可用在 Windows 和 Mac 操作系统上使用的网页安全字体的列表，这可以帮助决策网站的安全性。

**注意**: 有一个可以下载来自一个网页的自定义字体的方法，允许你通过任何你想要的方法来定制你使用的字体：**网页字体**。这个有一点复杂，我们将在这个模块中的另一篇文章中讨论这一点。

#### 默认字体

CSS 定义了 5 个常用的字体名称: `serif, ``sans-serif, ``monospace`, `cursive,`和 `fantasy. `这些都是非常通用的，当使用这些通用名称时，使用的字体完全取决于每个浏览器，而且它们所运行的每个操作系统也会有所不同。这是一种糟糕的情况，浏览器会尽力提供一个看上去合适的字体。 `serif`, `sans-serif` 和 `monospace` 是比较好预测的，默认的情况应该比较合理，另一方面，`cursive` 和 `fantasy` 是不太好预测的，我们建议使用它们的时候应该稍微注意一些，多多测试。

五个名称定义如下：

| 名称         | 定义                                                         | 示例                |
| ------------ | ------------------------------------------------------------ | ------------------- |
| `serif`      | 有衬线的字体 （衬线一词是指字体笔画尾端的小装饰，存在于某些印刷体字体中） | My big red elephant |
| `sans-serif` | 没有衬线的字体。                                             | My big red elephant |
| `monospace`  | 每个字符具有相同宽度的字体，通常用于代码列表。               | My big red elephant |
| `cursive`    | 用于模拟笔迹的字体，具有流动的连接笔画。                     | My big red elephant |
| `fantasy`    | 用来装饰的字体                                               | My big red elephant |

#### 字体栈

由于你无法保证你想在你的网页上使用的字体的可用性 (甚至一个网络字体可能由于某些原因而出错), 你可以提供一个**字体栈** (**font stack**)，这样的话，浏览器就有多种字体可以选择了。只需包含一个`font-family属性`，其值由几个用逗号分离的字体名称组成。比如

```
p {
  font-family: "Trebuchet MS", Verdana, sans-serif;
}
```

在这种情况下，浏览器从列表的第一个开始，然后查看在当前机器中，这个字体是否可用。如果可用，就把这个字体应用到选中的元素中。如果不可用，它就移到列表中的下一个字体，然后再检查。

在字体栈的最后提供一个合适的通用的字体名称是个不错的办法，这样的话，即使列出的字体都无法使用，浏览器至少可以提供一个还算合适的选择。为了强调这一点，如果没有其他选项可用，那么段落将被赋予浏览器的默认衬线字体 - 通常是Time New Roman - 这对于 sans-serif 字体是不利的！

**注意**: 有一些字体名称不止一个单词，比如`Trebuchet MS` ，那么就需要用引号包裹。

### [字体大小](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#字体大小)

在我们之前的模块中的[CSS values and units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units) 文章，我们回顾了[length and size units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#length_and_size). 字体大小 (通过 [`font-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size) 属性设置) 可以取大多数这些单位的值 (以及其他，比如百分比 [percentages](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#percentages))，然而你在调整字体大小时，最常用的单位是：

- `px` (像素): 将像素的值赋予给你的文本。这是一个绝对单位， 它导致了在任何情况下，页面上的文本所计算出来的像素值都是一样的。
- `em`: 1em 等于我们设计的当前元素的父元素上设置的字体大小 (更加具体的话，比如包含在父元素中的大写字母 M 的宽度) 如果你有大量设置了不同字体大小的嵌套元素，这可能会变得棘手, 但它是可行的，如下图所示。为什么要使用这个麻烦的单位呢?  当你习惯这样做时，那么就会变得很自然，你可以使用`em`调整任何东西的大小，不只是文本。你可以有一个单位全部都使用 em 的网站，这样维护起来会很简单。
- `rem`: 这个单位的效果和 `em` 差不多，除了 1`rem` 等于 HTML 中的根元素的字体大小， (i.e. [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/html)) ，而不是父元素。这可以让你更容易计算字体大小，但是遗憾的是， `rem` 不支持 Internet Explorer 8 和以下的版本。如果你的项目需要支持较老的浏览器，你可以坚持使用`em` 或 `px`, 或者是 [polyfill](https://developer.mozilla.org/zh-CN/docs/Glossary/Polyfill) 就像 [REM-unit-polyfill](https://github.com/chuckcarpenter/REM-unit-polyfill). （这个单位在“CSS的值和单位”一节也有讲解）

元素的 `font-size` 属性是从该元素的父元素继承的。所以这一切都是从整个文档的根元素——[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/html)开始，浏览器的 `font-size` 标准设置的值为 16px。在根元素中的任何段落 (或者那些浏览器没有设置默认大小的元素)，会有一个最终的大小值：16px。其他元素也许有默认的大小，比如 [ (en-US)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) 元素有一个 2em 的默认值，所以它的最终大小值为 32px。当你开始更改嵌套元素的字体大小时，事情会变得棘手。比如，如果你有一个 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/article) 元素在你的页面上，然后设置它的 font-size 为 `1.5em` (通过计算，可以得到大小为 24px)，然后想让 `<article>` 元素中的段落获得一个计算值为 20px 的大小，那么你应该使用多少 em。

```
<!-- document base font-size is 16px -->
<article> <!-- If my font-size is 1.5em -->
  <p>My paragraph</p> <!-- How do I compute to 20px font-size? -->
</article>
```

你需要将 em 的值设置为 20/24, 或者 `0.83333333em`. 这个计算可能比较复杂，所以当你设置的时候，你需要仔细一些。如果可以使用 rem 的话，那实现起来就变得简单不少，避免在可能的情况下设置容器元素的字体大小。

#### 一个简单的 size 示例

当调整你的文本大小时，将文档(document)的基础 `font-size` 设置为10px往往是个不错的主意，这样之后的计算会变得简单，所需要的 (r)em 值就是想得到的像素的值除以 10，而不是 16。做完这个之后，你可以简单地调整在你的 HTML 中你想调整的不同类型文本的字体大小。在样式表的指定区域列出所有`font-size`的规则集是一个好主意，这样它们就可以很容易被找到。

我们的新结果是这样的:

```
html {
  font-size: 10px;
}

h1 {
  font-size: 2.6rem;
}

p {
  font-size: 1.4rem;
  color: red;
  font-family: Helvetica, Arial, sans-serif;
}
```

### [字体样式，字体粗细，文本转换和文本装饰](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#font_style_font_weight_text_transform_and_text_decoration)

CSS 提供了 4 种常用的属性来改变文本的样子：

- `font-style`

  : 用来打开和关闭文本 italic (斜体)。 可能的值如下 (你很少会用到这个属性，除非你因为一些理由想将斜体文字关闭斜体状态)：  

  - `normal`: 将文本设置为普通字体 (将存在的斜体关闭)
  - `italic`: 如果当前字体的斜体版本可用，那么文本设置为斜体版本；如果不可用，那么会利用 oblique 状态来模拟 italics。
  - `oblique`: 将文本设置为斜体字体的模拟版本，也就是将普通文本倾斜的样式应用到文本中。

- `font-weight`

  : 设置文字的粗体大小。这里有很多值可选 (比如 

  -light

  , 

  -normal

  , 

  -bold

  , 

  -extrabold

  , 

  -black

  , 等等), 不过事实上你很少会用到 

  ```
  normal
  ```

   和 

  ```
  bold
  ```

  以外的值：  

  - `normal`, `bold`: 普通或者**加粗**的字体粗细
  - `lighter`, `bolder`: 将当前元素的粗体设置为比其父元素粗体更细或更粗一步。`100`–`900`: 数值粗体值，如果需要，可提供比上述关键字更精细的粒度控制。

- `text-transform`

  : 允许你设置要转换的字体。值包括：  

  - `none`: 防止任何转型。
  - `uppercase`: 将所有文本转为大写。
  - `lowercase`: 将所有文本转为小写。
  - `capitalize`: 转换所有单词让其首字母大写。
  - `full-width`: 将所有字形转换成全角，即固定宽度的正方形，类似于等宽字体，允许拉丁字符和亚洲语言字形（如中文，日文，韩文）对齐。

- `text-decoration`

  : 设置/取消字体上的文本装饰 (你将主要使用此方法在设置链接时取消设置链接上的默认下划线。) 可用值为：  

  - `none`: 取消已经存在的任何文本装饰。
  - `underline`: 文本下划线.
  - `overline`: 文本上划线
  - `line-through`: 穿过文本的线 strikethrough over the text.

    你应该注意到 

  `text-decoration`

   可以一次接受多个值，如果你想要同时添加多个装饰值， 比如 

  `text-decoration: underline overline`

  .。同时注意 

  `text-decoration`

   是一个缩写形式，它由 

  `text-decoration-line`

  , 

  `text-decoration-style`

   和 

  `text-decoration-color`

   构成。你可以使用这些属性值的组合来创建有趣的效果，比如 

  `text-decoration: line-through red wavy`.

我们来看一下这几个属性添加到我们的例子中：

我们的新结果是这样的：

```
html {
  font-size: 10px;
}

h1 {
  font-size: 2.6rem;
  text-transform: capitalize;
}

h1 + p {
  font-weight: bold;
}

p {
  font-size: 1.4rem;
  color: red;
  font-family: Helvetica, Arial, sans-serif;
}
```

### [文字阴影](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#文字阴影)

你可以为你的文本应用阴影，使用 [`text-shadow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-shadow) 属性。这最多需要 4 个值，如下例所示：

```
text-shadow: 4px 4px 5px red;
```

4 个属性如下:

1. 阴影与原始文本的水平偏移，可以使用大多数的 CSS 单位 [length and size units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#length_and_size), 但是 px 是比较合适的。这个值必须指定。
2. 阴影与原始文本的垂直偏移;效果基本上就像水平偏移，除了它向上/向下移动阴影，而不是左/右。这个值必须指定。
3. 模糊半径 - 更高的值意味着阴影分散得更广泛。如果不包含此值，则默认为0，这意味着没有模糊。可以使用大多数的 CSS 单位 [length and size units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#length_and_size).
4. 阴影的基础颜色，可以使用大多数的 CSS 颜色单位 [CSS color unit](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#colors). 如果没有指定，默认为 `black`.

**注意**: 正偏移值可以向右移动阴影，但也可以使用负偏移值来左右移动阴影，例如 `-1px -1px`.

#### 多种阴影

您可以通过包含以逗号分隔的多个阴影值，将多个阴影应用于同一文本，例如：

```
text-shadow: -1px -1px 1px #aaa,
             0px 4px 1px rgba(0,0,0,0.5),
             4px 4px 5px rgba(0,0,0,0.7),
             0px 0px 7px rgba(0,0,0,0.4);
```

## [文本布局](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#文本布局)

有了基本的字体属性，我们来看看我们可以用来影响文本布局的属性。

### [文本对齐](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#text_alignment)

 [`text-align`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-align) 属性用来控制文本如何和它所在的内容盒子对齐。可用值如下，并且在与常规文字处理器应用程序中的工作方式几乎相同：

- `left`: 左对齐文本。
- `right`: 右对齐文本。
- `center`: 居中文字
- `justify`: 使文本展开，改变单词之间的差距，使所有文本行的宽度相同。你需要仔细使用，它可以看起来很可怕。特别是当应用于其中有很多长单词的段落时。如果你要使用这个，你也应该考虑一起使用别的东西，比如 [`hyphens`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/hyphens)，打破一些更长的词语。

如果我们应用 `text-align: center;` 到我们例子中的 [ (en-US)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) 元素中，结果如下：



### [行高](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#hidden_example2)

 [`line-height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/line-height) 属性设置文本每行之间的高，可以接受大多数单位 [length and size units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#length_and_size)，不过也可以设置一个无单位的值，作为乘数，通常这种是比较好的做法。无单位的值乘以 [`font-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size) 来获得 `line-height`。当行与行之间拉开空间，正文文本通常看起来更好更容易阅读。推荐的行高大约是 1.5–2 (双倍间距。) 所以要把我们的文本行高设置为字体高度的1.5倍，你可以使用这个:

```
line-height: 1.5;
```

### [字母和单词间距](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#letter_and_word_spacing)

[`letter-spacing`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/letter-spacing) 和 [`word-spacing`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/word-spacing) 属性允许你设置你的文本中的字母与字母之间的间距、或是单词与单词之间的间距。你不会经常使用它们，但是可能可以通过它们，来获得一个特定的外观，或者让较为密集的文字更加可读。它们可以接受大多数单位 [length and size units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#length_and_size).

所以作为例子，如果我们把这个样式应用到我们的示例中的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p) 段落的第一行：

```
p::first-line {
  letter-spacing: 2px;
  word-spacing: 4px;
}
```

我们会得到下面的结果：



### [其他一些值得看一下的属性](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#其他一些值得看一下的属性)

以上属性让你了解如何开始在网页上设置文本， 但是你可以使用更多的属性。我们只是想介绍最重要的。一旦你习惯使用上面的内容，你还应该探索以下几点：

Font 样式:

- [`font-variant`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant): 在小型大写字母和普通文本选项之间切换。
- [`font-kerning`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-kerning): 开启或关闭字体间距选项。
- [`font-feature-settings`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-feature-settings): 开启或关闭不同的 [OpenType](https://en.wikipedia.org/wiki/OpenType) 字体特性。
- [`font-variant-alternates`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant-alternates): 控制给定的自定义字体的替代字形的使用。
- [`font-variant-caps`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant-caps): 控制大写字母替代字形的使用。
- [`font-variant-east-asian` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian): 控制东亚文字替代字形的使用, 像日语和汉语。
- [`font-variant-ligatures`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant-ligatures): 控制文本中使用的连写和上下文形式。
- [`font-variant-numeric`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant-numeric): 控制数字，分式和序标的替代字形的使用。
- [`font-variant-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant-position): 控制位于上标或下标处，字号更小的替代字形的使用。
- [`font-size-adjust`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size-adjust): 独立于字体的实际大小尺寸，调整其可视大小尺寸。
- [`font-stretch`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-stretch): 在给定字体的可选拉伸版本中切换。
- [`text-underline-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-underline-position): 指定下划线的排版位置，通过使用 `text-decoration-line` 属性的`underline` 值。
- [`text-rendering`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-rendering): 尝试执行一些文本渲染优化。

文本布局样式：

- [`text-indent`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-indent): 指定文本内容的第一行前面应该留出多少的水平空间。
- [`text-overflow`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-overflow): 定义如何向用户表示存在被隐藏的溢出内容。
- [`white-space`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/white-space): 定义如何处理元素内部的空白和换行。
- [`word-break`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/word-break): 指定是否能在单词内部换行。
- [`direction`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/direction): 定义文本的方向 (这取决于语言，并且通常最好让HTML来处理这部分，因为它是和文本内容相关联的。)
- [`hyphens`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/hyphens): 为支持的语言开启或关闭连字符。
- [`line-break`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/line-break): 对东亚语言采用更强或更弱的换行规则。
- [`text-align-last`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-align-last): 定义一个块或行的最后一行，恰好位于一个强制换行前时，如何对齐。
- [`text-orientation`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-orientation): 定义行内文本的方向。
- [`word-wrap`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow-wrap): 指定浏览器是否可以在单词内换行以避免超出范围。
- [`writing-mode`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/writing-mode): 定义文本行布局为水平还是垂直，以及后继文本流的方向。

## [Font 简写](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Fundamentals#font_简写)

许多字体的属性也可以通过 [`font`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font) 的简写方式来设置 . 这些是按照以下顺序来写的： [`font-style`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-style), [`font-variant`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant), [`font-weight`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-weight), [`font-stretch`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-stretch), [`font-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size), [`line-height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/line-height), and [`font-family`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-family).

如果你想要使用 `font` 的简写形式，在所有这些属性中，只有 `font-size` 和 `font-family` 是一定要指定的。

[`font-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-size) 和 [`line-height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/line-height) 属性之间必须放一个正斜杠。

一个完整的例子如下所示：

```
font: italic normal bold normal 3em/1.5 Helvetica, Arial, sans-serif;
```

# 样式化列表

## [一个简单的例子](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#一个简单的例子)

首先，让我们看一个简单的例子。文章中我们将看到无序，有序和描述列表——它们都具有相似的样式特性，而某些特性却又各不相同。[Github](https://mdn.github.io/learning-area/css/styling-text/styling-lists/unstyled-list.html)上有未加载样式的例子（也可以查看[源码](https://github.com/mdn/learning-area/blob/master/css/styling-text/styling-lists/unstyled-list.html)。）

例子中列表的HTML代码如下：

```
<h2>Shopping (unordered) list</h2>

<p>Paragraph for reference, paragraph for reference, paragraph for reference,
paragraph for reference, paragraph for reference, paragraph for reference.</p>

<ul>
  <li>Humous</li>
  <li>Pitta</li>
  <li>Green salad</li>
  <li>Halloumi</li>
</ul>

<h2>Recipe (ordered) list</h2>

<p>Paragraph for reference, paragraph for reference, paragraph for reference,
paragraph for reference, paragraph for reference, paragraph for reference.</p>

<ol>
  <li>Toast pitta, leave to cool, then slice down the edge.</li>
  <li>Fry the halloumi in a shallow, non-stick pan, until browned on both sides.</li>
  <li>Wash and chop the salad.</li>
  <li>Fill pitta with salad, humous, and fried halloumi.</li>
</ol>

<h2>Ingredient description list</h2>

<p>Paragraph for reference, paragraph for reference, paragraph for reference,
paragraph for reference, paragraph for reference, paragraph for reference.</p>

<dl>
  <dt>Humous</dt>
  <dd>A thick dip/sauce generally made from chick peas blended with tahini, lemon juice, salt, garlic, and other ingredients.</dd>
  <dt>Pitta</dt>
  <dd>A soft, slightly leavened flatbread.</dd>
  <dt>Halloumi</dt>
  <dd>A semi-hard, unripened, brined cheese with a higher-than-usual melting point, usually made from goat/sheep milk.</dd>
  <dt>Green salad</dt>
  <dd>That green healthy stuff that many of us just use to garnish kebabs.</dd>
</dl>
```

现在，如果你去到例子的展示页面，并使用[浏览器开发者工具](https://developer.mozilla.org/zh-CN/docs/Learn/Common_questions/What_are_browser_developer_tools)查看那些列表元素，你会注意到若干个默认的样式预设值：

- ul和ol 元素设置[`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin)的顶部和底部: 16px(1em) 0;和 padding-left: 40px(2.5em); （在这里注意的是浏览器默认字体大小为16px）。
- li默认是没有设置间距的。
- dl 元素设置 margin的顶部和底部: 16px(1em) ，无内边距设定。
- dd 元素设置为： [`margin-left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin-left)  `40px` (`2.5em`)。
- 在参考中提到的 [`p`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p) 元素设置 margin的顶部和底部: 16px(1em)，和其他的列表类型相同。

## [处理列表间距](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#处理列表间距)

当您创建样式列表时，您需要调整样式，使其保持与周围元素相同的垂直间距（例如段落和图片，有时称为垂直节奏））和相互间的水平间距（您可以在 Github 上参考[完成的样式示例](https://mdn.github.io/learning-area/css/styling-text/styling-lists/) ，也可以找到[源代码](https://github.com/mdn/learning-area/blob/master/css/styling-text/styling-lists/index.html)。）

用于文本样式和间距的CSS如下所示：

```
/* General styles */

html {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 10px;
}

h2 {
  font-size: 2rem;
}

ul,ol,dl,p {
  font-size: 1.5rem;
}

li, p {
  line-height: 1.5;
}

/* Description list styles */


dd, dt {
  line-height: 1.5;
}

dt {
  font-weight: bold;
}

dd {
  margin-bottom: 1.5rem;
}
```

- 第一条规则集设置一个网站字体，基准字体大小为10px。 页面上的所有内容都将继承该规则集。
- 规则集2和3为标题、不同的列表类型和段落以及设置了相对字体大小（这些列表的子元素将会继承该规则集），这就意味着每个段落和列表都将拥有相同的字体大小和上下间距,有助于保持垂直间距一致。
- 规则集4在段落和列表项目上设置相同的 [`line-height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/line-height) ，因此段落和每个单独的列表项目将在行之间具有相同的间距。 这也将有助于保持垂直间距一致。
- 规则集5-7适用于描述列表 - 我们在描述列表的术语和其描述上设置与段落和列表项相同的行高，以及 [`margin-bottom`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin-bottom) 为1.5 rem（与段落（p）和列表项目（li））相同。 再次强调一遍，这里很好地实现了一致性！ 我们还使描述术语具有粗体字体，因此它们在视觉上脱颖而出。

## [列表特定样式](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#列表特定样式)

现在我们来看一下列表的一般间距，我们来研究一些列表具有的特定属性。 我们从三个属性开始了解，这三个属性可以在 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ul) 或  [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ol) 元素上设置：

- [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type) ：设置用于列表的项目符号的类型，例如无序列表的方形或圆形项目符号，或有序列表的数字，字母或罗马数字。
- [`list-style-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-position) ：设置在每个项目开始之前，项目符号是出现在列表项内，还是出现在其外。
- [`list-style-image`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-image) ：允许您为项目符号使用自定义图片，而不是简单的方形或圆形。

### [符号样式](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#符号样式)

像上面所提及的， [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type)  属性允许你设置项目符号点的类型，在我们的例子中，我们在有序列表上设置了大写罗马数字：

```
ol {
  list-style-type: upper-roman;
}
```

效果显示如下：

![an ordered list with the bullet points set to appear outside the list item text.](https://mdn.mozillademos.org/files/12962/outer-bullets.png)

您可以通过 [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type)  参考页面查找到更多选项。

### [项目符号位置](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#项目符号位置)

[`list-style-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-position) 设置在每个项目开始之前，项目符号是出现在列表项内，还是出现在其外。 如上所示，默认值为 outside，这使项目符号位于列表项之外。

如果值设置为 inside，项目条目则位于行内。

```
ol {
  list-style-type: upper-roman;
  list-style-position: inside;
}
```

![an ordered list with the bullet points set to appear inside the list item text.](https://mdn.mozillademos.org/files/12958/inner-bullets.png)

### [使用自定义的项目符号图片](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#使用自定义的项目符号图片)

[`list-style-image`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-image) 属性允许对于项目符号使用自定义图片。其语法相当简单：

```
ul {
  list-style-image: url(star.svg);
}
```

然而，这个属性在控制项目符号的位置，大小等方面是有限的。 您最好使用[`background`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background) 系列属性，您将在 [Styling boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks) 模块中了解更多信息。在这里我们仅做一点尝试！

结束我们的例子，我们样式化无序列表像这样（放到您之前所见的顶部）：

```
ul {
  padding-left: 2rem;
  list-style-type: none;
}

ul li {
  padding-left: 2rem;
  background-image: url(star.svg);
  background-position: 0 0;
  background-size: 1.6rem 1.6rem;
  background-repeat: no-repeat;
}
```

我们的所做如下：

- 将 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ul) 的 [`padding-left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding-left) 从默认的 `40px`设置为 `20px`，然后在列表项上设置相同的数值。 这就是说，整个列表项仍然排列在列表中，但是列表项产生了一些用于背景图像的填充。 如果我们没有设置填充，背景图像将与列表项文本重叠，这看起来会很乱。
- 将 [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type) 设置为none，以便默认情况下不会显示项目符号。 我们将使用 [`background`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background) 属性来代替项目符号。
- 为每个无序列表项插入项目符号，其相应的属性如下：  
  - [`background-image`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-image): 充当项目符号的图片文件的参考路径
  - [`background-position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position): 这定义了所选元素背景中的图像将出现在哪里 - 在我们的示例中设置 `0 0`，这意味着项目符号将出现在每个列表项的最左上侧。
  - [`background-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size): 设置背景图片的大小。 理想条件下，我们想要项目符号与列表项的大小相同（比列表项稍大或稍小亦可）。  我们使用的尺寸为1.6rem（16px），它非常吻合我们为项目符号设置的 20px 的填充， 16px 加上 4px  的空格间距，可以使项目符号和列表项文本效果更好。
  - [`background-repeat`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-repeat)：默认条件下，背景图片不断复制直到填满整个背景空间，在我们的例子中，背景图片只需复制一次，所以我们设置值为 `no-repeat`。

效果显示如下：

![an unordered list with the bullet points set as little star images](https://mdn.mozillademos.org/files/12956/image-bullets.png)

### [list-style 速记](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#list-style_速记)

上述提到的三种属性可以用一个单独的速记属性 [`list-style`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style) 来设置。例如：

```
ul {
  list-style-type: square;
  list-style-image: url(example.png);
  list-style-position: inside;
}
```

可以被如下方式代替：

```
ul {
  list-style: square url(example.png) inside;
}
```

属性值可以任意顺序排列，你可以设置一个，两个或者三个值（该属性的默认值为 disc, none, outside），如果指定了 type 和 image，如果由于某种原因导致图像无法加载，则 type 将用作回退。

## [管理列表计数](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#管理列表计数)

有时，您可能想在有序列表上进行不同的计数方式。例如： 从1以外的数字开始，或向后倒数，或者按步或多于1计数。HTML和CSS有一些工具可以帮助您

### [start](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#start)

[`start`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ol#attr-start) 属性允许你从1 以外的数字开始计数。示例如下：

```
<ol start="4">
  <li>Toast pitta, leave to cool, then slice down the edge.</li>
  <li>Fry the halloumi in a shallow, non-stick pan, until browned on both sides.</li>
  <li>Wash and chop the salad.</li>
  <li>Fill pitta with salad, humous, and fried halloumi.</li>
</ol>
```

输出的结果如下：



### [reversed](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#reversed)

[`reversed`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ol#attr-reversed) 属性将启动列表倒计数。示例如下：

```
<ol start="4" reversed>
  <li>Toast pitta, leave to cool, then slice down the edge.</li>
  <li>Fry the halloumi in a shallow, non-stick pan, until browned on both sides.</li>
  <li>Wash and chop the salad.</li>
  <li>Fill pitta with salad, humous, and fried halloumi.</li>
</ol>
```

输出的结果如下：



### [value](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#value)

[`value`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ol#attr-value) 属性允许设置列表项指定数值，示例如下:

```
<ol>
  <li value="2">Toast pitta, leave to cool, then slice down the edge.</li>
  <li value="4">Fry the halloumi in a shallow, non-stick pan, until browned on both sides.</li>
  <li value="6">Wash and chop the salad.</li>
  <li value="8">Fill pitta with salad, humous, and fried halloumi.</li>
</ol>
```

输出的结果如下：

![image-20211128161132654](.\images\image-20211128161132654.png)

**注意**: 纵然你使用非数字的 [`list-style-type`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/list-style-type), 你仍需要使用与数值同等意义的值作为 value 的属性。

# 样式化链接

### [链接状态](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_links#链接状态)

第一件需要理解的事情是链接状态的概念，链接存在时处于不同的状态，每一个状态都可以用对应的 [伪类](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors#pseudo-classes) 来应用样式:

- **Link (没有访问过的)**: 这是链接的默认状态，当它没有处在其他状态的时候，它可以使用[`:link`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:link) 伪类来应用样式。
- **Visited**: 这个链接已经被访问过了(存在于浏览器的历史纪录), 它可以使用 [`:visited`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:visited) 伪类来应用样式。
- **Hover**: 当用户的鼠标光标刚好停留在这个链接，它可以使用 [`:hover`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:hover) 伪类来应用样式。
- **Focus**: 一个链接当它被选中的时候 (比如通过键盘的 Tab  移动到这个链接的时候，或者使用编程的方法来选中这个链接 [`HTMLElement.focus()` (en-US)](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus)) 它可以使用 [`:focus`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:focus) 伪类来应用样式。
- **Active**: 一个链接当它被激活的时候 (比如被点击的时候)，它可以使用 [`:active`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/:active) 伪类来应用样式。

### [默认的样式](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_links#默认的样式)

下面的例子说明了一个链接的默认行为表现 (这里的 CSS 仅仅是为了放大和居中文本，使内容更加突出)

```
<p><a href="https://mozilla.org">A link to the Mozilla homepage</a></p>
p {
  font-size: 2rem;
  text-align: center;
}
```

![image-20211128205151397](.\images\image-20211128205151397.png)

当你观察默认样式的时候，你也许会注意到一些东西:

- 链接具有下划线。
- 未访问过的 (Unvisited) 的链接是蓝色的。
- 访问过的 (Visited) 的链接是紫色的.
- 悬停 (Hover) 在一个链接的时候鼠标的光标会变成一个小手的图标。
- 选中 (Focus) 链接的时候，链接周围会有一个轮廓，你应该可以按 tab 来选中这个页面的链接 (在 Mac 上, 你可能需要使用*Full Keyboard Access: All controls* 选项，然后再按下 Ctrl + F7 ，这样就可以起作用)
- 激活 (Active) 链接的时候会变成红色 (当你点击链接时，请尝试按住鼠标按钮。)

有趣的是，这些默认的样式与20世纪90年代中期浏览器早期的风格几乎相同。这是因为用户知道以及期待链接就是这样变化的，如果链接的样式不同，就会让一些人感到奇怪。不过这不意味着你不应该为链接添加任何样式，只是你的样式不应该与用户预期的相差太大，你应该至少：

- 为链接使用下划线，但是不要在其他内容上也用下划线，以作区分。如果你不想要带有下划线的链接，那你至少要用其他方法来高亮突出链接。
- 当用户悬停或选择 (hover 或者 focused) 的时候，使链接有相应的变化，并且在链接被激活(active) 的时候，变化会有一些不同。可以使用以下CSS属性关闭/更改默认样式：
- [`color`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/color) 文字的颜色
- [`cursor`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/cursor) 鼠标光标的样式，你不应该把这个关掉，除非你有非常好的理由。
- [`outline`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/outline) 文字的轮廓 (轮廓有点像边框，唯一的区别是边框占用了盒模型的空间，而轮廓没有； 它只是设置在背景图片的顶部)。outline  是一个有用的辅助功能，所以在把它关掉之前考虑清楚；你至少应该将悬停 (hover) 状态的样式同时应用到选中 (focus) 状态上。

**注意**: 你不仅仅只限于上述属性来把样式应用到你的链接上，你可以用任何你喜欢的属性，就是不要搞得太疯狂！

### [将样式应用到一些链接](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_links#将样式应用到一些链接)

现在我们已经详细地看了默认的状态，让我们看一下典型的链接样式的设置。

开始之前，我们先写出我们的空规则集：

```
a {

}


a:link {

}

a:visited {

}

a:focus {

}

a:hover {

}

a:active {

}
```

这几个规则的顺序是有意义的，因为链接的样式是建立在另一个样式之上的，比如，第一个规则的样式也会在后面的规则中生效，一个链接被激活  (activated) 的时候，它也是处于悬停 (hover)  状态的。如果你搞错了顺序，那么就可能不会产生正确的效果。要记住这个顺序，你可以尝试这样帮助记忆：**L**o**V**e **F**ears **HA**te.

现在让我们再添加一些信息，得到正确的样式：

```
body {
  width: 300px;
  margin: 0 auto;
  font-size: 1.2rem;
  font-family: sans-serif;
}

p {
  line-height: 1.4;
}

a {
  outline: none;
  text-decoration: none;
  padding: 2px 1px 0;
}

a:link {
  color: #265301;
}

a:visited {
  color: #437A16;
}

a:focus {
  border-bottom: 1px solid;
  background: #BAE498;
}

a:hover {
  border-bottom: 1px solid;
  background: #CDFEAA;
}

a:active {
  background: #265301;
  color: #CDFEAA;
}
```

这里还提供了一些示例HTML，供你应用CSS：

```
<p>There are several browsers available, such as <a href="https://www.mozilla.org/zh-CN/firefox/">Mozilla
Firefox</a>, <a href="https://www.google.com/chrome/index.html">Google Chrome</a>, and
<a href="https://www.microsoft.com/zh-CN/windows/microsoft-edge">Microsoft Edge</a>.</p>
```

把这两个放在一起，我们得到这样的结果：

![image-20211128205215425](.\images\image-20211128205215425.png)

那么我们在这里做了什么? 这个看起来肯定和默认的样式不同，但仍然提供了一个熟悉的体验，好让用户知道发生了什么：

- 第一和第二条规则和本次讨论关系不大。

- 第三个规则使用了 `a` 选择器，取消了默认的文本下划线和链接被选中（focus）时的轮廓 （outline）（不同浏览器的默认行为可能不同），并为每个链接添加了少量的内边距（padding），所有这一切将在之后变得明确。

- 接着，我们使用`a:link`和`a:visited`选择器来设置未访问（unvisited）链接和访问过（visited）的链接的一点颜色上的变化，然后就能分辨开来了。

- 下面两条规则使用 

  ```
  a:focus
  ```

   和 

  ```
  a:hover
  ```

   来设置选中（focus）和悬停（hover）的链接为不同的背景颜色，再加上一个下划线，使链接更加突出。这里有两点需要注意：  

  - 下划线是使用 [`border-bottom`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-bottom) 创造的, 而不是 [`text-decoration`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-decoration)，有一些人喜欢这样，因为前者比后者有更好的样式选项， 并且绘制的位置会稍微低一点，所以不会穿过字母 (比如 字母 g 和 y 底部).
  - [`border-bottom`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-bottom)的值被设置为`1px solid`，没有指定颜色。这样做可以使边框采用和元素文本一样的颜色，这在这样的情况下是很有用的，因为链接的每种状态下，文本是不同的颜色。

- 最后, `a:active` 用来给链接一个不同的配色方案，当链接被激活 (activated) 时，让链接被激活的时候更加明显。

## [在链接中包含图标](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_links#在链接中包含图标)

常见的做法是在链接中包含图标，使链接提供更多关于链接指向的内容的信息。让我们来看一个简单的例子，例子中为一个外部链接 (链接指向的不是本站，而是外部站点)。这样的图标通常看起来像一个指向盒子的小箭头，比如, 我们会使用[icons8.com上的这个优秀的范例](https://icons8.com/web-app/741/external-link)。

让我们来看一些能给我们这个效果的 HTML 和 CSS。先是一些简单的等待你样式化的 HTML ：

```
<p>For more information on the weather, visit our <a href="weather.html">weather page</a>,
look at <a href="https://en.wikipedia.org/wiki/Weather">weather on Wikipedia</a>, or check
out <a href="http://www.extremescience.com/weather.htm">weather on Extreme Science</a>.</p>
```

接着是 CSS:

```
body {
  width: 300px;
  margin: 0 auto;
  font-family: sans-serif;
}

p {
  line-height: 1.4;
}

a {
  outline: none;
  text-decoration: none;
  padding: 2px 1px 0;
}

a:link {
  color: blue;
}

a:visited {
  color: purple;
}

a:focus, a:hover {
  border-bottom: 1px solid;
}

a:active {
  color: red;
}

a[href*="http"] {
  background: url('https://mdn.mozillademos.org/files/12982/external-link-52.png') no-repeat 100% 0;
  background-size: 16px 16px;
  padding-right: 19px;
}
```

![image-20211128205247585](.\images\image-20211128205247585.png)

那么这里发生了什么? 我们将跳过大部分的 CSS，因为那些只是你之前看过的相同的信息。最后一条规则很有趣，这里，我们在外部链接上插入了一个自定义背景图片，这和上篇[自定义列表项目符号](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_lists#using_a_custom_bullet_image)文章的做法很像。这次，我们使用了 [`background`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background) 简写，而不是分别使用多个属性。我们设置了我们想要插入的图片的路径，指定了 `no-repeat` ，这样我们只插入了一次图片，然后指定位置为100%，使其出现在内容的右边，距离上方是0px。

我们也使用 [`background-size`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size) 来指定要显示的背景图像的大小，为了满足响应式网站设计的需要，在图标更大，需要再重新调整它的大小的时候，这样做是很有帮助的。但是，这仅适用于IE 9及更高版本。所以你如果需要支持那些老的浏览器，只能调整图像的原始大小，然后插入。

最后，我们在链接上设置 [`padding-right`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding-right) ，为背景图片留出空间，这样就不会让它和文本重叠了。

最后的问题，我们是如何只选中了外部链接的？如果你正确编写你的[HTML链接](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks) ，你应该只会在外部链接上使用绝对 URL，如果链接是链接你的站点的其他部分，那么使用相对链接是更加高效的。因此“http”文本应该只出现在外部链接上，为此我们可以使用一个[属性选择器](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors#attribute_selectors)——`a[href*="http"]` ——选中 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a) 元素，但是这样只会选中那些拥有 [`href`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a#attr-href) 属性，且属性的值包含 "http" 的 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a)的元素。

就这样啦，尝试重新审视上面的动手练习部分，尝试这种新技术！

**注意**: 不要担心，如果你目前不熟悉 [backgrounds](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks) 和 [responsive web design (en-US)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Responsive/responsive_design_building_blocks) ; 这些会在其他地方解释。

## [样式化链接为按钮](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Styling_links#样式化链接为按钮)

目前在本文中探索的用法也可以用在其他方面。比如，悬停 (hover) 的状态可以为不同的元素应用样式，不只是链接，你也许会想添加悬停状态的样式到段落、列表项、或者是其他东西。

此外，在某些情况下，链接通常会应用样式，使它看上去的效果和按钮差不多，一个网站导航菜单通常是标记为一个列表，列表中包含链接，这可以很容易地被设计为看起来像一组控制按钮或是选项卡，主要是用于让用户可以访问站点的其他部分，现在让我们来看一看。

首先，一些 HTML:

```
<ul>
  <li><a href="#">Home</a></li><li><a href="#">Pizza</a></li><li><a href="#">Music</a></li><li><a href="#">Wombats</a></li><li><a href="#">Finland</a></li>
</ul>
```

接着，是我们的 CSS:

```
body,html {
  margin: 0;
  font-family: sans-serif;
}

ul {
  padding: 0;
  width: 100%;
}

li {
  display: inline;
}

a {
  outline: none;
  text-decoration: none;
  display: inline-block;
  width: 19.5%;
  margin-right: 0.625%;
  text-align: center;
  line-height: 3;
  color: black;
}

li:last-child a {
  margin-right: 0;
}

a:link, a:visited, a:focus {
  background: yellow;
}

a:hover {
  background: orange;
}

a:active {
  background: red;
  color: white;
}
```

这给我们以下结果：![image-20211128205345086](.\images\image-20211128205345086.png)

让我们来解释一下这里发生了什么，主要是几个有趣的部分:

- 我们的第二条规则删除了 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ul) 元素的默认的 [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding)，然后设置了它的宽度是外部容器 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/body) (在这次条件下) 的 100% 。

- [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/li) 元素通常默认是块元素 (可见 [types of CSS boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#types_of_css_boxes) 回顾)，意味着它们各自会占用一行。在这个例子中，我们创建了一组水平列表的链接，所以在第三条规则中，我们设置了 [`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display) 属性为 inline，这会导致列表中的每项内容都会一起出现在同一行，它们现在表现得就像内联元素。

- 第四条规则，主要是 

   元素的样式，这里比较复杂; 让我们一步一步来看：  

  - 和前面的例子一样，我们首先关掉了 [`text-decoration`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-decoration) 和 [`outline`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/outline)，我们不希望这些破坏我们链接的样子。
  - 接着，我们设置 [`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display) 为 `inline-block` ，[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a) 元素默认为内联元素，而且我们不希望它们像值为 `block` 时一样，线条超出自己的内容，我们确实想要控制它们的大小`inline-block` 允许我们这样做。
  - 接着是尺寸的设置! 我们要填满整个 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/ul) 的宽度，为按钮之间留一些间距 (margin)  (但不是右边边缘的间距)，我们有 5 个按钮需要容纳，所以它们的大小应该一样。为了做到这一点，我们设置 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width) 为 19.5%，然后 [`margin-right`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin-right) 为 0.625%. 你会注意到所有宽度加起来是 100.625%, 这样会让最后一个按钮溢出 `<ul>` ，然后显示到下一行中。但是，我们使用了下一条规则让它恢复到了 100%，这条规则选中了列表中的最后一个 `<a>`元素，然后删除了它的间距 (margin)。完成!
  - 最后三条声明就比较简单了，主要是为链接各个状态添加了颜色。我们居中了每个链接中的文本，设置 [`line-height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/line-height) 为 3， 让按钮有一些高度 (这也具有垂直居中文本的优点)，并设置文本的颜色为黑色。

# web字体

## [字体种类回顾](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#字体种类回顾)

正如我们在[基本文本和字体样式](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)中所看到的那样，应用到您的HTML的字体可以使用 [`font-family`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-family)属性来控制。您需要提供一个或多个字体种类名称，浏览器会在列表中搜寻，直到找到它所运行的系统上可用的字体。

```
p {
  font-family: Helvetica, "Trebuchet MS", Verdana, sans-serif;
}
```

这个系统运行良好，但是对于传统的web开发人员来说，字体选择是有限的。只有少数几种字体可以保证兼容所有流行的操作系统——这就是所谓的 [Web-safe 字体](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals#web_safe_fonts)。您可以使用字体堆栈来指定可选择的字体，后面是Web-safe的替代选项，然后是默认的系统字体，但是为了确保您的设计在每种字体中都显示正常，这样增加了测试的开销。

## [Web 字体](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#web_字体)

但是还有一种选择，它非常有效，回到IE版本6。Web字体是一种CSS特性，允许您指定在访问时随您的网站一起下载的字体文件，这意味着任何支持Web字体的浏览器都可以使用您指定的字体。太酷啦！所需的语法如下所示：

首先，在CSS的开始处有一个[`@font-face`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/@font-face)块，它指定要下载的字体文件：

```
@font-face {
  font-family: "myFont";
  src: url("myFont.ttf");
}
```

在这个下面，你可以使用@font-face中指定的字体种类名称来将你的定制字体应用到你喜欢的任何东西上，比如说：

```
html {
  font-family: "myFont", "Bitstream Vera Serif", serif;
}
```

语法确实比这更复杂，下面我们将详细介绍。

关于网页字体有两件重要的事情要记住：

1. 浏览器支持不同的字体格式，因此您需要多种字体格式以获得良好的跨浏览器支持。例如,大多数现代浏览器都支持WOFF / WOFF2(Web Open Font Format versions 1 and  2，Web开放字体格式版本1和2)，它是最有效的格式，但是旧版本IE只支持EOT (Embedded Open  Type，嵌入式开放类型)的字体,你可能需要包括一个SVG版本的字体支持旧版本的iPhone和Android浏览器。我们将向您展示如何生成所需的代码。
2. 字体一般都不能自由使用。您必须为他们付费，或者遵循其他许可条件，比如在代码中(或者在您的站点上)提供字体创建者。你不应该在没有适当的授权的情况下偷窃字体。

**注意：** Web字体作为一种技术从 Internet Explorer 4 开始就得到了的支持！

## [自主学习:web字体示例](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#自主学习web字体示例)

记住这一点，让我们从最初的原则构建一个基本的web字体示例。使用嵌入的live示例很难演示这一点，因此，我们希望您按照下面几节中详细介绍的步骤来了解这个过程。

你应该使用 [web-font-start.html](https://github.com/mdn/learning-area/blob/master/css/styling-text/web-fonts/web-font-start.html) 和 [web-font-start.css](https://github.com/mdn/learning-area/blob/master/css/styling-text/web-fonts/web-font-start.css) 文件作为开始添加到你的代码中（又见[预览版](https://mdn.github.io/learning-area/css/styling-text/web-fonts/web-font-start.html)。）现在，在你的电脑上的一个新目录中复制这些文件。在 `web-font-start.css`文件中，您将找到一些最小的CSS来处理这个示例的基本布局和排版。

### [查找字体](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#查找字体)

对于本例，我们将使用两种web字体，一种用于标题，另一种用于正文文本。首先，我们需要找到包含字体的字体文件。字体是由字体铸造厂创建的，并且存储在不同的文件格式中。
 通常有三种类型的网站可以获得字体：

- 免费的字体经销商：这是一个可以下载免费字体的网站(可能还有一些许可条件，比如对字体创建者的信赖)。比如： [Font Squirre](https://www.fontsquirrel.com/)，[dafont](http://www.dafont.com/) 和 [Everything Fonts](https://everythingfonts.com/)。
- 收费的字体经销商：这是一个收费则字体可用的网站，例如[fonts.com](http://www.fonts.com/)或[myfonts.com](http://www.myfonts.com/)。您也可以直接从字体铸造厂中购买字体，例如[Linotype](https://www.linotype.com/)，[Monotype](http://www.monotype.com) 或 [Exljbris](http://www.exljbris.com/)。
- 在线字体服务：这是一个存储和为你提供字体的网站，它使整个过程更容易。更多细节见[Using an online font service](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#using_an_online_font_service)。

让我们找到一些字体！前往[Font Squirrel](https://www.fontsquirrel.com/)  并选择两种字体——一种用于标题的有趣的字体(可能是一种不错的显示字体或无衬线字体)，和一种用于段落，稍微不那么华丽，更易于阅读的字体。当您找到每种字体时，按下下载按钮，并将该文件保存在与您先前保存的HTML和CSS文件相同的目录中。无论它们是TTF(True Type Fonts))还是OTF(Open Type字体)都不重要。

在每种情况下，都要解压字体包(Web字体通常分布在包含字体文件和许可信息的ZIP文件中。)您可能会在包中发现多个字体文件，一些字体是作为一个具有不同变体的家庭分布的，例如，瘦、中、粗体、斜体、斜体等等。对于这个例子，我们只是想让您自己考虑一个单一的字体文件。

**注意：** 在右边栏的“查找字体”部分中，您可以单击不同的标记和分类来筛选显示的选项。

### [生成所需代码](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#生成所需代码)

现在您需要生成所需的代码(以及字体格式)。对于每种字体，遵循以下步骤：

1. 确保您已经满足了任何许可证的要求，如果您打算在一个商业和/或Web项目中使用它。
2. 前往 Fontsquirrel [Webfont Generator](https://www.fontsquirrel.com/tools/webfont-generator).
3. 使用上传字体按钮上传你的两个字体文件。
4. 勾选复选框，“是的，我上传的字体符合网络嵌入的合法条件。
5. 点击下载你的套件（kit）。

在生成器完成处理之后，您应该得到一个ZIP文件，将它保存在与HTML和CSS相同的目录中。

### [在演示中实现代码](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#在演示中实现代码)

在这一点上解压您刚刚生成的webfont套件。在解压的目录中，您将看到三个有用的条目：

- 每个字体的多个版本：（比如 `.ttf`, `.woff`, `.woff2`…… 随着浏览器支持需求的改变，提供的字体将随着时间的推移而不断更新。） 正如上面提到的，跨浏览器支持需要使用多种字体——这是Fontsquirrel的方法，确保你得到了你需要的一切。
- 每个字体的一个演示HTML文件在你的浏览器中加载，看看在不同的使用环境下字体会是什么样子。
- 一个 `stylesheet.css` 文件，它包含了你需要的生成好的 @font-face 代码。

要在演示中实现这些字体，请遵循以下步骤：

1. 将解压缩的目录重命名为简易的目录，比如`fonts`

2. 打开 `stylesheet.css` 文件，把包含在你的网页中的 `@font-face`块复制到你的 `web-font-start.css` 文件—— 你需要把它们放在最上面，在你的CSS之前，因为字体需要导入才能在你的网站上使用。

3. 每个`url()`函数指向一个我们想要导入到我们的CSS中的字体文件——我们需要确保文件的路径是正确的，因此，在每个路径的开头添加`fonts/` （必要时进行调整）。

4. 现在，您可以在字体栈中使用这些字体，就像任何web安全或默认的系统字体一样。

     例如：  

   ```
   font-family: 'zantrokeregular', serif;
   ```

你应该得到一个演示页面，上面有一些漂亮的字体。因为不同字体的字体大小不同，你可能需要调整大小、间距等，以区分外观和感觉。

![img](https://mdn.mozillademos.org/files/12984/web-font-example.png)

**注意：**如果对于要让它正常工作您有任何问题，可以自由地将您的版本与我们完成的文件进行比较——见 [web-font-finished.html](https://github.com/mdn/learning-area/blob/master/css/styling-text/web-fonts/web-font-finished.html) 和 [web-font-finished.css](https://github.com/mdn/learning-area/blob/master/css/styling-text/web-fonts/web-font-finished.css) ([运行完成的示例](https://mdn.github.io/learning-area/css/styling-text/web-fonts/web-font-finished.html))。

## [使用在线字体服务](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#使用在线字体服务)

在线字体服务通常会为你存储和服务字体，这样你就不用担心写`@font-face`代码了，通常只需要在你的网站上插入一两行代码就可以让一切都运行。例子包括[Typekit](https://typekit.com/) 和[Cloud.typography](http://www.typography.com/cloud/welcome/)。大多数这些服务都是基于订阅的，除了[Google Fonts](https://www.google.com/fonts)，这是一个有用的免费服务，特别是对于快速的测试工作和编写演示。

大多数这些服务都很容易使用，所以我们不会详细地介绍它们。让我们快速浏览一下Google Fonts，这样你就能明白它的意思了。再次的，使用`web-font-start.html` 和 `web-font-start.css` a的副本作为你的开始。

1. 前往 [Google Fonts](https://www.google.com/fonts).
2. 使用左边的过滤器来显示你想要选择的字体类型，并选择一些你喜欢的字体。
3. 要选择字体种类，按下按钮旁边的 ⊕ 按钮。
4. 当您选择好字体种类时，按下页面底部的*[Number]* 种类选择。
5. 在生成的屏幕中，首先需要复制所显示的HTML代码行，并将其粘贴到HTML文件的头部。将其置于现有的[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link)元素之上，使得字体是导入的，然后在你的CSS中使用它。
6. 然后，您需要将CSS声明复制到您的CSS中，以便将自定义字体应用到您的HTML。

**注意：**如果你需要对比我们的，你可以在 [google-font.html](https://github.com/mdn/learning-area/blob/master/css/styling-text/web-fonts/google-font.html)和[google-font.css](https://github.com/mdn/learning-area/blob/master/css/styling-text/web-fonts/google-font.css)找到完整版本的。（[见预览版](https://mdn.github.io/learning-area/css/styling-text/web-fonts/google-font.html)）

## [关于@font-face的更多细节](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Styling_text/Web_fonts#关于font-face的更多细节)

让我们来探索由fontsquirrel为您生成的`@font-face`语法。这是其中一个块的样子：

```
@font-face {
  font-family: 'ciclefina';
  src: url('fonts/cicle_fina-webfont.eot');
  src: url('fonts/cicle_fina-webfont.eot?#iefix') format('embedded-opentype'),
         url('fonts/cicle_fina-webfont.woff2') format('woff2'),
         url('fonts/cicle_fina-webfont.woff') format('woff'),
         url('fonts/cicle_fina-webfont.ttf') format('truetype'),
         url('fonts/cicle_fina-webfont.svg#ciclefina') format('svg');
  font-weight: normal;
  font-style: normal;
}
```

这被称为"bulletproof @font-face syntax（刀枪不入的@font-face语法）", 这是 Paul Irish早期的一篇文章提及后@font-face开始流行起来 ([Bulletproof @font-face Syntax](https://www.paulirish.com/2009/bulletproof-font-face-implementation-syntax/)。让我们来看看它是怎么做的：

- `font-family`：这一行指定了您想要引用的字体的名称。你可以把它作为你喜欢的任何东西，只要你在你的CSS中始终如一地使用它。
- `src`：这些行指定要导入到您的CSS(`url`部分)的字体文件的路径，以及每种字体文件的格式(`format`部分)。后面的部分不是必要的，但是声明它是很有用的，因为它允许浏览器更快地找到可以使用的字体。可以列出多个声明，用逗号分隔——浏览器会搜索并使用它能找到的第一个——因此，最好是把新的、更好的格式比如WOFF2放在前面，把偏老的，不是那么好的格式像TTF这样的放在后面。唯一的例外是EOT字体——他们首先在旧版本的IE中修复了几个bug，这样它就会尝试使用它找到的第一件东西，即使它不能真正使用字体。
- [`font-weight`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-weight)/[`font-style`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-style): 这些行指定字体的粗细，以及它是否斜体。如果您正在导入相同字体的多个粗细，您可以指定它们的粗细/样式，然后使用不同的[`font-weight`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-weight)/[`font-style`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-style)来选择它们之间的不同值，而不必调用字体种类不同名称的所有不同成员。Roger Johansson写的 [@font-face tip: define font-weight and font-style to keep your CSS simple](http://www.456bereastreet.com/archive/201012/font-face_tip_define_font-weight_and_font-style_to_keep_your_css_simple/) 更详细地说明了该做些什么。

**注意：**您还可以为您的web字体指定特定的[`font-variant`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-variant) 和 [`font-stretch`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font-stretch) )值。在较新的浏览器中，您还可以指定一个[`unicode-range` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range)值，这是一个您需要使用什么web字体的特定范围的字符——在支持浏览器中，只有指定的字符才会被下载，省去了不必要的下载。Drew McLellan写的[Creating Custom Font Stacks with Unicode-Range](https://24ways.org/2011/creating-custom-font-stacks-with-unicode-range/)在如何利用这个问题上提供了一些有用的建议。



# css布局

CSS页面布局技术允许我们拾取网页中的元素，并且控制它们相对正常布局流、周边元素、父容器或者主视口/窗口的位置。在这个模块中将涉及更多关于页面[布局技术](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Layout_mode)的细节：

- 正常布局流
- [`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display)属性
- 弹性盒子
- 网格
- 浮动
- 定位
- CSS 表格布局
- 多列布局

每种技术都有它们的用途，各有优缺点，相互辅助。通过理解各个布局方法的设计理念，你能够找到构建你想要的网页需要的布局方案。

## [正常布局流(Normal flow)](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#normal_flow)

正常布局流(normal flow)是指在不对页面进行任何布局控制时，浏览器默认的HTML布局方式。让我们快速地看一个HTML的例子：

```
<p>I love my cat.</p>

<ul>
  <li>Buy cat food</li>
  <li>Exercise</li>
  <li>Cheer up friend</li>
</ul>

<p>The end!</p>
```

默认情况下，浏览器的显示如下:![image-20211129212307627](.\images\image-20211129212307627.png)

注意，HTML元素完全按照源码中出现的先后次序显示——第一个段落、无序列表、第二个段落。

出现在另一个元素下面的元素被描述为**块**元素，与出现在另一个元素旁边的**内联元素**不同，内联元素就像段落中的单个单词一样。

注意：块元素内容的布局方向被描述为**块方向**。块方向在英语等具有水平**书写模式**(`writing mode`)的语言中垂直运行。它可以在任何垂直书写模式的语言中水平运行。对应的**内联方向**是内联内容（如句子）的运行方向。

当你使用css创建一个布局时，你正在离开**正常布局流**，但是对于页面上的多数元素，**正常布局流**将完全可以创建你所需要的布局。从一个结构良好的Html文档开始是非常重要，因为你可以按照默认的方式来搭建页面，而不是自造车轮。

下列布局技术会覆盖默认的布局行为：

-  **[`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display)** 属性 — 标准的value,比如`block`, `inline` 或者 `inline-block` 元素在正常布局流中的表现形式 (见 [Types of CSS boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model#Types_of_CSS_boxes)). 接着是全新的布局方式，通过设置`display`的值, 比如 [CSS Grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids) 和 [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox).
- **浮动**——应用 **[`float`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/float)** 值，诸如 `left` 能够让块级元素互相并排成一行，而不是一个堆叠在另一个上面。
- **[`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position)** 属性 — 允许你精准设置盒子中的盒子的位置，正常布局流中，默认为 `static` ，使用其它值会引起元素不同的布局方式，例如将元素固定到浏览器视口的左上角。
- **表格布局**— 表格的布局方式可以用在非表格内容上，可以使用`display: table`和相关属性在非表元素上使用。
- **多列布局**— 这个 [Multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns) 属性 可以让块按列布局，比如报纸的内容就是一列一列排布的。

## [display属性](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#display属性)

在css中实现页面布局的主要方法是设定`display`属性的值。此属性允许我们更改默认的显示方式。正常流中的所有内容都有一个`display`的值，用作元素的默认行为方式。例如，英文段落显示在一个段落的下面，这是因为它们的样式是`display:block`。如果在段落中的某个文本周围创建链接，则该链接将与文本的其余部分保持内联，并且不会打断到新行。这是因为a元素默认为`display:inline`。

您可以更改此默认显示行为。例如，li元素默认为`display:block`，这意味着在我们的英文文档中，列表项显示为一个在另一个之下。如果我们将显示值更改为`inline`，它们现在将显示在彼此旁边，就像单词在句子中所做的那样。事实上，您可以更改任何元素的`display`值，这意味着您可以根据它们的语义选择html元素，而不必关心它们的外观。他们的样子是你可以改变的。

除了可以通过将一些内容从`block`转换为`inline`（反之亦然）来更改默认表示形式之外，还有一些更大的布局方法以`display`值开始。但是，在使用这些属性时，通常需要调用其他属性。在讨论布局时，对我们来说最重要的两个值是`display`:`flex`和`display`:`grid`。

## [弹性盒子(Flexbox)](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#弹性盒子flexbox)

Flexbox 是CSS 弹性盒子布局模块（[Flexible Box Layout](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Flexible_Box_Layout) Module）的缩写，它被专门设计出来用于创建横向或是纵向的一维页面布局。要使用flexbox，你只需要在想要进行flex布局的父元素上应用`display: flex` ，所有直接子元素都将会按照flex进行布局。我们来看一个例子。

下面这些HTML标记描述了一个class为`wrapper`的容器元素，它的内部有三个`<div>`元素。它们在我们的英文文档当中，会默认地作为块元素从上到下进行显示。

现在，当我们把`display: flex`添加到它的父元素时，这三个元素就自动按列进行排列。这是由于它们变成了*flex项(flex items)*，按照flex容器（也就是它们的父元素）的一些flex相关的初值进行flex布局：它们整整齐齐排成一行，是因为父元素上`flex-direction`的初值是`row`。它们全都被拉伸至和最高的元素高度相同，是因为父元素上`align-items`属性的初值是`stretch`。这就意味着所有的子元素都会被拉伸到它们的flex容器的高度，在这个案例里就是所有flex项中最高的一项。所有项目都从容器的开始位置进行排列，排列成一行后，在尾部留下一片空白。

```
.wrapper {
  display: flex;
}
<div class="wrapper">
  <div class="box1">One</div>
  <div class="box2">Two</div>
  <div class="box3">Three</div>
</div>
```

![image-20211129212340880](.\images\image-20211129212340880.png)

除了上述可以被应用到flex容器的属性以外，还有很多属性可以被应用到flex项(flex items)上面。这些属性可以改变flex项在flex布局中占用宽/高的方式，允许它们通过伸缩来适应可用空间。

作为一个简单的例子，我们可以在我们的所有子元素上添加[`flex`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/flex) 属性，并赋值为`1`，这会使得所有的子元素都伸展并填充容器，而不是在尾部留下空白，如果有更多空间，那么子元素们就会变得更宽，反之，他们就会变得更窄。除此之外，如果你在HTML标记中添加了一个新元素，那么它们也会变得更小，来为新元素创造空间——不管怎样，最终它们会调整自己直到占用相同宽度的空间。

```
.wrapper {
    display: flex;
}

.wrapper > div {
    flex: 1;
}
<div class="wrapper">
    <div class="box1">One</div>
    <div class="box2">Two</div>
    <div class="box3">Three</div>
</div>
```

![image-20211129212357966](.\images\image-20211129212357966.png)

**注意：**为了找到更多关于Flexbox的信息，看看我们的 [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox) 的文章。

## [Grid布局](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#grid布局)

Flexbox用于设计横向或纵向的布局，而Grid布局则被设计用于同时在两个维度上把元素按行和列排列整齐。

同flex一样，你可以通过指定display的值来转到grid布局：`display: grid`。下面的例子使用了与flex例子类似的HTML标记，描述了一个容器和若干子元素。除了使用`display:grid`，我们还分别使用 [`grid-template-rows`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/grid-template-rows) 和 [`grid-template-columns`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/grid-template-columns) 两个属性定义了一些行和列的轨道。定义了三个`1fr`的列，还有两个`100px`的行之后，无需再在子元素上指定任何规则，它们自动地排列到了我们创建的格子当中。

```
.wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 100px 100px;
    grid-gap: 10px;
}
<div class="wrapper">
    <div class="box1">One</div>
    <div class="box2">Two</div>
    <div class="box3">Three</div>
    <div class="box4">Four</div>
    <div class="box5">Five</div>
    <div class="box6">Six</div>
</div>
```

![image-20211129212414932](.\images\image-20211129212414932.png)

一旦你拥有了一个grid，你也可以显式地将元素摆放在里面，而不是依赖于浏览器进行自动排列。在下面的第二个例子里，我们定义了一个和上面一样的grid，但是这一次我们只有三个子元素。我们利用 [`grid-column`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/grid-column) 和 [`grid-row`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/grid-row) 两个属性来指定每一个子元素应该从哪一行/列开始，并在哪一行/列结束。这就能够让子元素在多个行/列上展开。

```
.wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 100px 100px;
    grid-gap: 10px;
}

.box1 {
    grid-column: 2 / 4;
    grid-row: 1;
}

.box2 {
    grid-column: 1;
    grid-row: 1 / 3;
}

.box3 {
    grid-row: 2;
    grid-column: 3;
}
<div class="wrapper">
    <div class="box1">One</div>
    <div class="box2">Two</div>
    <div class="box3">Three</div>
</div>
```

![image-20211129212440583](.\images\image-20211129212440583.png)

**注意**: 这两个例子只是展示了grid布局的冰山一角，要深入了解grid布局，请参阅我们的文章[Grid Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids)。

这篇指南的其余部分介绍了其他的布局方式，它们与你的页面的主要布局结构关系不大，但是却能够帮助你实现特殊的操作。同时，只要你理解了每一个布局任务的初衷，你就能够马上意识到哪一种布局更适合你的组件。

## [浮动](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#浮动)

把一个元素“浮动”(float)起来，会改变该元素本身和在正常布局流（normal flow）中跟随它的其他元素的行为。这一元素会浮动到左侧或右侧，并且从正常布局流(normal flow)中移除，这时候其他的周围内容就会在这个被设置浮动([`float`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/float))的元素周围环绕。

[`float`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/float) 属性有四个可能的值：

- `left` — 将元素浮动到左侧。
- `right` — 将元素浮动到右侧。
- `none` — 默认值, 不浮动。
- `inherit` — 继承父元素的浮动属性。

在下面这个例子当中，我们把一个`<div>`元素浮动到左侧，并且给了他一个右侧的[`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin)，把文字推开。这给了我们文字环绕着这个`<div>`元素的效果，在现代网页设计当中，这是你唯一需要学会的事情。

```
<h1>Simple float example</h1>

<div class="box">Float</div>

<p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci vel, viverra egestas ligula. Curabitur vehicula tellus neque, ac ornare ex malesuada et. In vitae convallis lacus. Aliquam erat volutpat. Suspendisse ac imperdiet turpis. Aenean finibus sollicitudin eros pharetra congue. Duis ornare egestas augue ut luctus. Proin blandit quam nec lacus varius commodo et a urna. Ut id ornare felis, eget fermentum sapien.</p>
.box {
    float: left;
    width: 150px;
    height: 150px;
    margin-right: 30px;
}
```

![image-20211129212503226](.\images\image-20211129212503226.png)

**注意:** : CSS浮动的知识会在我们关于 [浮动](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats)的教程当中被详细地解释。除此之外，如果您想要了解在Flexbox和Grid布局出现之前我们是如何进行列布局的（仍然有可能碰到这种情形），请阅读我们关于[传统布局方式](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods)的文章.

## [定位技术](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#定位技术)

定位(positioning)能够让我们把一个元素从它原本在正常布局流(normal flow)中应该在的位置移动到另一个位置。定位(positioning)并不是一种用来给你做主要页面布局的方式，它更像是让你去管理和微调页面中的一个特殊项的位置。

有一些非常有用的技术在特定的布局下依赖于[`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position)属性。同时，理解定位(positioning)也能够帮助你理解正常布局流(normal flow)，理解把一个元素移出正常布局流(normal flow)是怎么一回事。

有五种主要的定位类型需要我们了解：

- **静态定位(Static positioning)**是每个元素默认的属性——它表示“将元素放在文档布局流的默认位置——没有什么特殊的地方”。
- **相对定位(Relative positioning)**允许我们相对于元素在正常的文档流中的位置移动它——包括将两个元素叠放在页面上。这对于微调和精准设计(design pinpointing)非常有用。
- **绝对定位(Absolute positioning)**将元素完全从页面的正常布局流(normal layout flow)中移出，类似将它单独放在一个图层中。我们可以将元素相对于页面的 `<html>` 元素边缘固定，或者相对于该元素的*最近被定位祖先元素(nearest positioned ancestor element)*。绝对定位在创建复杂布局效果时非常有用，例如通过标签显示和隐藏的内容面板或者通过按钮控制滑动到屏幕中的信息面板。
- **固定定位(Fixed positioning)**与绝对定位非常类似，但是它是将一个元素相对浏览器视口固定，而不是相对另外一个元素。 这在创建类似在整个页面滚动过程中总是处于屏幕的某个位置的导航菜单时非常有用。
- **粘性定位(Sticky positioning)**是一种新的定位方式，它会让元素先保持和`position: static`一样的定位，当它的相对视口位置(offset from the viewport)达到某一个预设值时，他就会像`position: fixed`一样定位。

### [简单定位示例](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#simple_positioning_example)

我们将展示一些示例代码来熟悉这些布局技术. 这些示例代码都作用在下面这一个相同的HTML上：

```
<h1>Positioning</h1>

<p>I am a basic block level element.</p>
<p class="positioned">I am a basic block level element.</p>
<p>I am a basic block level element.</p>
```

该HTML将使用以下CSS默认样式：

```
body {
  width: 500px;
  margin: 0 auto;
}

p {
    background-color: rgb(207,232,220);
    border: 2px solid rgb(79,185,227);
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
}
```

渲染效果如下:![image-20211129212523064](.\images\image-20211129212523064.png)

### [相对定位](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#相对定位)

相对定位(relative positioning)让你能够把一个正常布局流(normal flow)中的元素从它的默认位置按坐标进行相对移动。比如将一个图标往下调一点，以便放置文字. 我们可以通过下面的规则添加相对定位来实现效果: 

```
.positioned {
  position: relative;
  top: 30px;
  left: 30px;
}
```

这里我们给中间段落的[`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position) 一个 `relative`值——这属性本身不做任何事情，所以我们还添加了[`top`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/top)和[`left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/left)属性。这些可以将受影响的元素向下向右移——这可能看起来和你所期待的相反，但你需要把它看成是左边和顶部的元素被“推开”一定距离，这就导致了它的向下向右移动。

添加此代码将给出以下结果：

```
.positioned {
  position: relative;
  background: rgba(255,84,104,.3);
  border: 2px solid rgb(255,84,104);
  top: 30px;
  left: 30px;
}
```

![image-20211129212539368](.\images\image-20211129212539368.png)

### [绝对定位](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#绝对定位)

绝对定位用于将元素移出正常布局流(normal flow)，以坐标的形式相对于它的容器定位到web页面的任何位置，以创建复杂的布局。有趣的是，它经常被用于与相对定位和浮动的协同工作。

回到我们最初的非定位示例，我们可以添加以下的CSS规则来实现绝对定位：

```
.positioned {
  position: absolute;
  top: 30px;
  left: 30px;
}
```

这里我们给我们的中间段一个[`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position)的 `absolute`值，并且和前面一样加上 [`top`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/top) 和[`left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/left) 属性。但是，添加此代码将给出以下结果：

```
.positioned {
    position: absolute;
    background: rgba(255,84,104,.3);
    border: 2px solid rgb(255,84,104);
    top: 30px;
    left: 30px;
}
```

![image-20211129212601096](.\images\image-20211129212601096.png)

这和之前截然不同！定位元素现在已经与页面布局的其余部分完全分离，并位于页面的顶部。其他两段现在靠在一起，好像之前那个中间段落不存在一样。[`top`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/top)和[`left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/left)属性对绝对位置元素的影响不同于相对位置元素。在这一案例当中，他们没有指定元素相对于原始位置的移动程度。相反，在这一案例当中，它们指定元素应该从页面边界的顶部和左边的距离(确切地说，是 `<html>`元素的距离)。我们也可以修改作为容器的那个元素（在这里是`<html>`元素），要了解这方面的知识，参见关于[定位(positioning)](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)的课程

我们现在暂时不讨论固定定位（ fixed positioning ）——它基本上以相同的方式工作，除了它仍然固定在浏览器窗口的边缘，而不是它定位的父节点的边缘。

### [固定定位](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#固定定位)

固定定位(fixed positioning)同绝对定位(absolute positioning)一样，将元素从文档流(document  flow)当中移出了。但是，定位的坐标不会应用于"容器"边框来计算元素的位置，而是会应用于视口(viewport)边框。利用这一特性，我们可以轻松搞出一个固定位置的菜单，而不受底下的页面滚动的影响。

在这个例子里面，我们在HTML加了三段很长的文本来使得页面可滚动，又加了一个带有`position: fixed`的盒子。

```
<h1>Fixed positioning</h1>

<div class="positioned">Fixed</div>

<p>Paragraph 1.</p>
<p>Paragraph 2.</p>
<p>Paragraph 3.</p>
.positioned {
    position: fixed;
    top: 30px;
    left: 30px;
}
```

![image-20211129212622160](.\images\image-20211129212622160.png)

### [粘性定位](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#粘性定位)

粘性定位(sticky positioning)是最后一种我们能够使用的定位方式。它将默认的静态定位(static positioning)和固定定位(fixed positioning)相混合。当一个元素被指定了`position: sticky`时，它会在正常布局流中滚动，直到它出现在了我们给它设定的相对于容器的位置，这时候它就会停止随滚动移动，就像它被应用了`position: fixed`一样。

```
.positioned {
  position: sticky;
  top: 30px;
  left: 30px;
}
```

![image-20211129212642510](.\images\image-20211129212642510.png)

![image-20211129212651622](.\images\image-20211129212651622.png)

**注意**: 想要发现更多关于定位的信息，请参阅我们的[Positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)和[Practical positioning examples](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Practical_positioning_examples)文章。

## [表格布局](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#table_layout)

HTML表格对于显示表格数据是很好的，但是很多年前——在浏览器中支持基本的CSS之前——web开发人员过去也常常使用表格来完成整个网页布局——将它们的页眉、页脚、不同的列等等放在不同的表行和列中。这在当时是有效的，但它有很多问题——表布局是不灵活的，繁重的标记，难以调试和语义上的错误（比如，屏幕阅读器用户在导航表布局方面有问题）。

一个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table)标签之所以能够像表格那样展示，是由于css默认给[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table)标签设置了一组table布局属性。当这些属性被应用于排列非[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table)元素时，这种用法被称为“使用CSS表格”。

下面这个例子展示了一个这样的用法。使用CSS表格来进行布局，在现在这个时间点应该被认为是一种传统方法，它通常会被用于兼容一些不支持Flexbox和Grid的浏览器。

让我们来看一个例子。首先，创建HTML表单的一些简单标记。每个输入元素都有一个标签，我们还在一个段落中包含了一个标题。为了进行布局，每个标签/输入对都封装在[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/div)中。

```
<form>
  <p>First of all, tell us your name and age.</p>
  <div>
    <label for="fname">First name:</label>
    <input type="text" id="fname">
  </div>
  <div>
    <label for="lname">Last name:</label>
    <input type="text" id="lname">
  </div>
  <div>
    <label for="age">Age:</label>
    <input type="text" id="age">
  </div>
</form>
```

现在，我们例子中的CSS。除了使用 [`display`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display) 属性外，大多数CSS都是相当普通的。 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form), [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/div),  [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label)和[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input)被告知要分别显示表、表行和表单元——基本上，它们会像HTML表格标记一样，导致标签和输入在默认情况下排列整齐。我们所要做的就是添加一些大小、边缘等等，让一切看起来都好一点，我们就完成了。

你会注意到标题段落已经给出了 `display: table-caption;`——这使得它看起来就像一个表格`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/caption) ——同时出于设计需要，我们通过`caption-side: bottom;` 告诉标题应该展示在表格的底部，即使这个[``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p)标记在源码中是在`<input>`之前。这就能让你有一点灵活的弹性。

```
html {
  font-family: sans-serif;
}

form {
  display: table;
  margin: 0 auto;
}

form div {
  display: table-row;
}

form label, form input {
  display: table-cell;
  margin-bottom: 10px;
}

form label {
  width: 200px;
  padding-right: 5%;
  text-align: right;
}

form input {
  width: 300px;
}

form p {
  display: table-caption;
  caption-side: bottom;
  width: 300px;
  color: #999;
  font-style: italic;
}
```

结果如下：![image-20211129212710551](.\images\image-20211129212710551.png)

## [多列布局](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Introduction#多列布局)

多列布局模组给了我们 一种把内容按列排序的方式，就像文本在报纸上排列那样。由于在web内容里让你的用户在一个列上通过上下滚动来阅读两篇相关的文本是一种非常低效的方式，那么把内容排列成多列可能是一种有用的技术。

要把一个块转变成多列容器(multicol container)，我们可以使用 [`column-count`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/column-count)属性来告诉浏览器我们需要多少列，也可以使用[`column-width` (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width)来告诉浏览器以至少某个宽度的尽可能多的列来填充容器。

在下面这个例子中，我们从一个class为`container`的`<div>`容器元素里边的一块HTML开始。

```
<div class="container">
    <h1>Multi-column layout</h1>

    <p>Paragraph 1.</p>
    <p>Paragraph 2.</p>

</div>
```

我们指定了该容器的`column-width`为200像素，这让浏览器创建了尽可能多的200像素的列来填充这一容器。接着他们共同使用剩余的空间来伸展自己的宽度。

```
    .container {
        column-width: 200px;
    }
```

![image-20211129212731352](.\images\image-20211129212731352.png)

# 正常布局流

这篇文章介绍正常的流布局，或者说，在你没有改变默认布局规则情况下的页面元素布局方式。

如上小节对布局的介绍，如果你未曾应用任何CSS规则来改变它们的展现方式，网页上的元素将会按照正常布局流来组织。同样的，开始探索前，你可以通过调整元素位置，或者完全的移除元素来改变它们的表现效果。从一副简单的、结构良好并且在正常布局流下仍然易读的文档开始，是上手任何页面的最佳方式（译者注：几乎没有很简单的CSS，标签组织符合一般用法）。这样确保了你的内容的易读性，即便用户使用受限的浏览器或者屏幕阅读设备（译者注：比如有些老旧浏览器对某些CSS特性的支持不理想，或者有用户自定义CSS样式）。此外，由于正常布局流的设计初衷在于构建易读、合理的文档，遵循这样的指引原则，你在对布局做出改动时应该是与文档协同，而不是与之对抗。

在深入探索不同的布局方式之前， 你最好回顾下在之前模块学习到的关于正常布局流的知识点（译者注：比如position display float table flex-box grid-layout）.

## [默认情况下，元素是如何布局的？](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/CSS_layout/Normal_Flow#默认情况下，元素是如何布局的？)

首先，取得元素的内容来放在一个独立的元素盒子中，然后在其周边加上内边距、边框和外边距 --- 就是我们之前看到的盒子模型。

默认的，一个[块级元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Block-level_elements)的内容宽度是其父元素的100%，其高度与其内容高度一致。[内联元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Inline_elements)的height width与内容一致。你无法设置内联元素的height width --- 它们就那样置于块级元素的内容里。 如果你想控制内联元素的尺寸，你需要为元素设置`display: block;` （或者，`display: inline-block;` inline-block 混合了inline 和 block的特性。)

这样解释了独立元素的布局，但是元素之间又是如何相互影响的呢？ 正常布局流（在布局介绍里提到过）是一套在浏览器视口内放置、组织元素的系统。默认的，块级元素按照基于其父元素的[书写顺序](https://developer.mozilla.org/zh-CN/docs/Web/CSS/writing-mode)(*默认值:* horizontal-tb)的*块流动方向(block flow direction)*放置 --- 每个块级元素会在上一个元素下面另起一行，它们会被设置好的margin 分隔。在英语，或者其他水平书写、自上而下模式里，块级元素是垂直组织的。

内联元素的表现有所不同 --- 它们不会另起一行；只要在其父级块级元素的宽度内有足够的空间，它们与其他内联元素、相邻的文本内容（或者被包裹的）被安排在同一行。如果空间不够，溢出的文本或元素将移到新的一行。

如果两个相邻的元素都设置了margin 并且两个margin有重叠，那么更大的设置会被保留，小的则会消失 --- 这被称为外边距叠加，我们之前见到过。

我们来看一个对全部这些做出解释的简单例子：

```html
<h1>Basic document flow</h1>

<p>I am a basic block level element. My adjacent block level elements sit on new lines below me.</p>

<p>By default we span 100% of the width of our parent element, and we are as tall as our child content. Our total width and height is our content + padding + border width/height.</p>

<p>We are separated by our margins. Because of margin collapsing, we are separated by the width of one of our margins, not both.</p>

<p>inline elements <span>like this one</span> and <span>this one</span> sit on the same line as one another, and adjacent text nodes, if there is space on the same line. Overflowing inline elements will <span>wrap onto a new line if possible (like this one containing text)</span>, or just go on to a new line if not, much like this image will do: <img src="https://mdn.mozillademos.org/files/13360/long.jpg"></p>
```

```css
body {
  width: 500px;
  margin: 0 auto;
}

p {
  background: rgba(255,84,104,0.3);
  border: 2px solid rgb(255,84,104);
  padding: 10px;
  margin: 10px;
}

span {
  background: white;
  border: 1px solid black;
}
```

![image-20211203114323072](.\images\image-20211203114323072.png)

# 弹性盒子(Flexbox)

[Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout) is a one-dimensional layout method for arranging items in rows or columns. Items *flex* (expand) to fill additional space or shrink to fit into smaller spaces. This article explains all the fundamentals.

## [Why Flexbox?](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#why_flexbox)

For a long time, the only reliable cross-browser compatible tools available for creating CSS layouts were features like [floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats) and [positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning). These work, but in some ways they're also limiting and frustrating.

The following simple layout designs are either difficult or  impossible to achieve with such tools in any kind of convenient,  flexible way:

- Vertically centering a block of content inside its parent.
- Making all the children of a container take up an equal amount of  the available width/height, regardless of how much width/height is  available.
- Making all columns in a multiple-column layout adopt the same height even if they contain a different amount of content.

As you'll see in subsequent sections, flexbox makes a lot of layout tasks much easier. Let's dig in!

## [Introducing a simple example](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#introducing_a_simple_example)

In this article, you'll work through a series of exercises to help you  understand how flexbox works. To get started, you should make a local  copy of the first starter file — [flexbox0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox0.html) from our github repo. Load it in a modern browser (like Firefox or  Chrome) and have a look at the code in your code editor. You can also [see it live here](https://mdn.github.io/learning-area/css/css-layout/flexbox/flexbox0.html).

  ![Image showing the starting point of Flexbox tutorial](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/bih741v.png)

You'll see that we have a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header) element with a top level heading inside it and a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) element containing three [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)s. We're going to use these to create a fairly standard three column layout.

## [Specifying what elements to lay out as flexible boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#specifying_what_elements_to_lay_out_as_flexible_boxes)

To start with, we need to select which elements are to be laid out as flexible boxes. To do this, we set a special value of [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) on the parent element of the elements you want to affect. In this case we want to lay out the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) elements, so we set this on the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section):

```
section {
  display: flex;
}
```

This causes the <section> element to become a **flex container** and its children to become **flex items**. The result of this should be something like so:

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example2.png)

So, this single declaration gives us everything we need. Incredible,  right? We have our multiple column layout with equal-sized columns, and  the columns are all the same height. This is because the default values  given to flex items (the children of the flex container) are set up to  solve common problems such as this.

To be clear, let's reiterate what is happening here. The element we've given a [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) value of `flex` to is acting like a block-level element in terms of how it interacts  with the rest of the page, but its children are laid out as flex items.  The next section will explain in more detail what this means. Note also  that you can use a `display` value of `inline-flex` if you wish to lay out an element's children as flex items, but have that element behave like an inline element.

## [The flex model](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#the_flex_model)

When elements are laid out as flex items, they are laid out along two axes:

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flex_terms.png)

- The **main axis** is the axis running in the  direction the flex items are laid out in (for example, as rows across  the page, or columns down the page.) The start and end of this axis are  called the **main start** and **main end**.
- The **cross axis** is the axis running perpendicular  to the direction the flex items are laid out in. The start and end of  this axis are called the **cross start** and **cross end**.
- The parent element that has `display: flex` set on it (the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) in our example) is called the **flex container**.
- The items laid out as flexible boxes inside the flex container are called **flex items** (the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) elements in our example).

Bear this terminology in mind as you go through subsequent sections.  You can always refer back to it if you get confused about any of the  terms being used.

## [Columns or rows?](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#columns_or_rows)

Flexbox provides a property called [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) that specifies which direction the main axis runs (which direction the  flexbox children are laid out in). By default this is set to `row`, which causes them to be laid out in a row in the direction your  browser's default language works in (left to right, in the case of an  English browser).

Try adding the following declaration to your [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) rule:

```
flex-direction: column;
```

You'll see that this puts the items  back in a column layout, much like they were before we added any CSS.  Before you move on, delete this declaration from your example.

**Note:** You can also lay out flex items in a reverse direction using the `row-reverse` and `column-reverse` values. Experiment with these values too!

## [Wrapping](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#wrapping)

One issue that arises when you have a fixed width or height in your layout  is that eventually your flexbox children will overflow their container,  breaking the layout. Have a look at our [flexbox-wrap0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox-wrap0.html) example and try [viewing it live](https://mdn.github.io/learning-area/css/css-layout/flexbox/flexbox-wrap0.html) (take a local copy of this file now if you want to follow along with this example):

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example3.png)

Here we see that the children are indeed breaking out of their  container. One way in which you can fix this is to add the following  declaration to your [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) rule:

```
flex-wrap: wrap;
```

Also, add the following declaration to your [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) rule:

```
flex: 200px;
```

Try this now. You'll see that the layout looks much better with this included:

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example4.png)We now have multiple rows. Each row has as many flexbox children fitted  into it as is sensible. Any overflow is moved down to the next line. The `flex: 200px` declaration set on the articles means that  each will be at least 200px wide. We'll discuss this property in more  detail later on. You might also notice that the last few children on the last row are each made wider so that the entire row is still filled.

But there's more we can do here. First of all, try changing your [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) property value to `row-reverse`. Now you'll see that you still have your multiple row layout, but it  starts from the opposite corner of the browser window and flows in  reverse.

## [flex-flow shorthand](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#flex-flow_shorthand)

At this point it's worth noting that a shorthand exists for [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) and [`flex-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap): [`flex-flow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-flow). So, for example, you can replace

```
flex-direction: row;
flex-wrap: wrap;
```

with

```
flex-flow: row wrap;
```

## [Flexible sizing of flex items](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#flexible_sizing_of_flex_items)

Let's now return to our first example and look at how we can control what  proportion of space flex items take up compared to the other flex items. Fire up your local copy of [flexbox0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox0.html), or take a copy of [flexbox1.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flexbox1.html) as a new starting point ([see it live](https://mdn.github.io/learning-area/css/css-layout/flexbox/flexbox1.html)).

First, add the following rule to the bottom of your CSS:

```
article {
  flex: 1;
}
```

This is a unitless proportion value that  dictates how much available space along the main axis each flex item  will take up compared to other flex items. In this case, we're giving  each [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) element the same value (a value of 1), which means they'll all take up  an equal amount of the spare space left after properties like padding  and margin have been set. This value is proportionally shared among the  flex items: giving each flex item a value of 400000 would have exactly  the same effect.

Now add the following rule below the previous one:

```
article:nth-of-type(3) {
  flex: 2;
}
```

Now when you refresh, you'll see that the third [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) takes up twice as much of the available width as the other two. There  are now four proportion units available in total (since 1 + 1 + 2 = 4).  The first two flex items have one unit each, so they each take 1/4 of  the available space. The third one has two units, so it takes up 2/4 of  the available space (or one-half).

You can also specify a minimum size value within the flex value. Try updating your existing article rules like so:

```
article {
  flex: 1 200px;
}

article:nth-of-type(3) {
  flex: 2 200px;
}
```

This basically states, "Each flex item will  first be given 200px of the available space. After that, the rest of the available space will be shared according to the proportion units." Try  refreshing and you'll see a difference in how the space is shared.

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example1.png)

The real value of flexbox can be seen in its flexibility/responsiveness. If you resize the browser window or add another [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) element, the layout continues to work just fine.

## [flex: shorthand versus longhand](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#flex_shorthand_versus_longhand)

[`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) is a shorthand property that can specify up to three different values:

- The unitless proportion value we discussed above. This can be specified separately using the [`flex-grow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow) longhand property.
- A second unitless proportion value, [`flex-shrink`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink), which comes into play when the flex items are overflowing their  container. This value specifies how much an item will shrink in order to prevent overflow. This is quite an advanced flexbox feature and we  won't be covering it any further in this article.
- The minimum size value we discussed above. This can be specified separately using the [`flex-basis`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis) longhand value.

We'd advise against using the longhand flex properties unless you  really have to (for example, to override something previously set). They lead to a lot of extra code being written, and they can be somewhat  confusing.

## [Horizontal and vertical alignment](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#horizontal_and_vertical_alignment)

You can also use flexbox features to align flex items along the main or  cross axis. Let's explore this by looking at a new example: [flex-align0.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/flex-align0.html) ([see it live also](https://mdn.github.io/learning-area/css/css-layout/flexbox/flex-align0.html)). We're going to turn this into a neat, flexible button/toolbar. At the  moment you'll see a horizontal menu bar with some buttons jammed into  the top left-hand corner.

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example5.png)

First, take a local copy of this example.

Now, add the following to the bottom of the example's CSS:

```
div {
  display: flex;
  align-items: center;
  justify-content: space-around;
}
```

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox_center_space-around.png)

Refresh the page and you'll see that the buttons are now nicely  centered horizontally and vertically. We've done this via two new  properties.

[`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items) controls where the flex items sit on the cross axis.

- By default, the value is `stretch`, which stretches all flex items to fill the parent in the direction of the cross axis. If  the parent doesn't have a fixed width in the cross axis direction, then  all flex items will become as long as the longest flex item. This is how our first example had columns of equal height by default.
- The `center` value that we used in our above code  causes the items to maintain their intrinsic dimensions, but be centered along the cross axis. This is why our current example's buttons are  centered vertically.
- You can also have values like `flex-start` and `flex-end`, which will align all items at the start and end of the cross axis respectively. See [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items) for the full details.

You can override the [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items) behavior for individual flex items by applying the [`align-self`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-self) property to them. For example, try adding the following to your CSS:

```
button:first-child {
  align-self: flex-end;
}
```

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox_first-child_flex-end.png)

Have a look at what effect this has and remove it again when you've finished.

[`justify-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content) controls where the flex items sit on the main axis.

- The default value is `flex-start`, which makes all the items sit at the start of the main axis.
- You can use `flex-end` to make them sit at the end.
- `center` is also a value for `justify-content`. It'll make the flex items sit in the center of the main axis.
- The value we've used above, `space-around`, is useful — it distributes all the items evenly along the main axis with a bit of space left at either end.
- There is another value, `space-between`, which is very similar to `space-around` except that it doesn't leave any space at either end.

We'd like to encourage you to play with these values to see how they work before you continue.

## [Ordering flex items](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#ordering_flex_items)

Flexbox also has a feature for changing the layout order of flex items without  affecting the source order. This is another thing that is impossible to  do with traditional layout methods.

The code for this is simple. Try adding the following CSS to your button bar example code:

```
button:first-child {
  order: 1;
}
```

Refresh and you'll see that the "Smile" button has moved to the end  of the main axis. Let's talk about how this works in a bit more detail:

- By default, all flex items have an [`order`](https://developer.mozilla.org/en-US/docs/Web/CSS/order) value of 0.
- Flex items with higher specified order values will appear later in the display order than items with lower order values.
- Flex items with the same order value will appear in their source  order. So if you have four items whose order values have been set as 2,  1, 1, and 0 respectively, their display order would be 4th, 2nd, 3rd,  then 1st.
- The 3rd item appears after the 2nd because it has the same order value and is after it in the source order.

You can set negative order values to make items appear earlier than  items whose value is 0. For example, you could make the "Blush" button  appear at the start of the main axis using the following rule:

```
button:last-child {
  order: -1;
}
```

## [Nested flex boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#nested_flex_boxes)

It's possible to create some pretty complex layouts with flexbox. It's  perfectly OK to set a flex item to also be a flex container, so that its children are also laid out like flexible boxes. Have a look at [complex-flexbox.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/flexbox/complex-flexbox.html) ([see it live also](https://mdn.github.io/learning-area/css/css-layout/flexbox/complex-flexbox.html)).

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox/flexbox-example7.png)

The HTML for this is fairly simple. We've got a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) element containing three [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)s. The third [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) contains three [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s. :

```
section - article
          article
          article - div - button
                    div   button
                    div   button
                          button
                          button
```

Let's look at the code we've used for the layout.

First of all, we set the children of the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) to be laid out as flexible boxes.

```
section {
  display: flex;
}
```

Next, we set some flex values on the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)s themselves. Take special note of the 2nd rule here: we're setting the third [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) to have its children laid out like flex items too, but this time we're laying them out like a column.

```
article {
  flex: 1 200px;
}

article:nth-of-type(3) {
  flex: 3 200px;
  display: flex;
  flex-flow: column;
}
```

Next, we select the first [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div). We first use `flex:1 100px;` to effectively give it a minimum height of 100px, then we set its children (the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) elements) to also be laid out like flex items. Here we lay them out in a wrapping row and align them in the center of the available space as we  did with the individual button example we saw earlier.

```
article:nth-of-type(3) div:first-child {
  flex:1 100px;
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: space-around;
}
```

Finally, we set some sizing on the button. This  time by giving it a flex value of 1 auto. This has a very interesting  effect, which you'll see if you try resizing your browser window width.  The buttons will take up as much space as they can. As many will fit on a line as is comfortable; beyond that, they'll drop to a new line.

```
button {
  flex: 1 auto;
  margin: 5px;
  font-size: 18px;
  line-height: 1.5;
}
```

## [Cross-browser compatibility](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#cross-browser_compatibility)

Flexbox support is available in most new browsers: Firefox, Chrome, Opera,  Microsoft Edge, and IE 11, newer versions of Android/iOS, etc. However,  you should be aware that there are still older browsers in use that  don't support Flexbox (or do, but support a really old, out-of-date  version of it.)

While you're just learning and experimenting, this doesn't matter too much; however, if you're considering using flexbox in a real website,  you need to do testing and make sure that your user experience is still  acceptable in as many browsers as possible.

Flexbox is a bit trickier than some CSS features. For example, if a  browser is missing a CSS drop shadow, then the site will likely still be usable. Not supporting flexbox features, however, will probably break a layout completely, making it unusable.

We discuss strategies for overcoming cross-browser support issues in our [Cross browser testing](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing) module.

# 网格布局（Grids)

## [What is grid layout?](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#what_is_grid_layout)

A grid is a collection of horizontal and vertical lines creating a  pattern against which we can line up our design elements. They help us  to create layouts in which our elements won't jump around or change  width as we move from page to page, providing greater consistency on our websites.

A grid will typically have **columns**, **rows**, and then gaps between each row and column. The gaps are commonly referred to as **gutters**.

  ![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids/grid.png)

## [Creating your grid in CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#creating_your_grid_in_css)

Having decided on the grid that your design needs, you can use CSS Grid Layout to create it. We'll look at the basic features of Grid Layout first and then explore how to create a simple grid system for your project.

The following video provides a nice visual explanation of using CSS Grid:

<iframe src="https://www.youtube-nocookie.com/embed/KOvGeFUHAC0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="" loading="lazy" width="560" height="315"></iframe>

### [Defining a grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#defining_a_grid)

As a starting point, download and open [the starting point file](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/0-starting-point.html) in your text editor and browser (you can also[ see it live here](https://mdn.github.io/learning-area/css/css-layout/grids/0-starting-point.html)). You will see an example with a container, which has some child items.  By default these display in normal flow, so the boxes display one below  the other. We'll be working with this file for the first part of this  lesson, making changes to see how its grid behaves.

To define a grid we use the `grid` value of the [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property. As with Flexbox, this enables Grid Layout; all of the direct  children of the container become grid items. Add this to the CSS inside  your file:

```
.container {
    display: grid;
}
```

Unlike flexbox, the items will not immediately look any different. Declaring `display: grid` gives you a one column grid, so your items will continue to display one below the other as they do in normal flow.

To see something that looks more grid-like, we'll need to add some  columns to the grid. Let's add three 200-pixel columns. You can use any  length unit or percentage to create these column tracks.

```
.container {
    display: grid;
    grid-template-columns: 200px 200px 200px;
}
```

Add the 2nd declaration to your CSS rule,  then reload the page. You should see that the items have rearranged  themselves such that there's one in each cell of the grid.

<iframe class="sample-code-frame" title="Defining a grid sample" id="frame_Defining_a_grid" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.Defining_a_grid.html" loading="lazy" width="100%" height="400"></iframe>

### [Flexible grids with the **fr** unit](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#flexible_grids_with_the_fr_unit)

In addition to creating grids using lengths and percentages, we can use the `fr` unit to flexibly size grid rows and columns. This unit represents one fraction of the available space in the grid container.

Change your track listing to the following definition, creating three `1fr` tracks.

```
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

You should now see that you have flexible tracks. The `fr` unit distributes space proportionally. So if you specify different positive values for your tracks like so:

```
.container {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
}
```

The first track now gets `2fr` of the available space and the other two tracks get `1fr`, making the first track larger. You can mix `fr` units with fixed length units — in such a case the space needed for the fixed tracks is used up first; the remaining space is then distributed  to the other tracks.

<iframe class="sample-code-frame" title="Flexible grids with the fr unit sample" id="frame_Flexible_grids_with_the_fr_unit" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.Flexible_grids_with_the_fr_unit.html" loading="lazy" width="100%" height="400"></iframe>

**Note:** The `fr` unit distributes *available* space, not *all* space. Therefore, if one of your tracks has something large inside it, there will be less free space to share.

### [Gaps between tracks](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#gaps_between_tracks)

To create gaps between tracks we use the properties [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap) for gaps between columns, [`row-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap) for gaps between rows, and [`gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/gap) as a shorthand for both.

```
.container {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr;
    gap: 20px;
}
```

These gaps can be any length unit or percentage, but not an `fr` unit.

<iframe class="sample-code-frame" title="Gaps between tracks sample" id="frame_Gaps_between_tracks" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.Gaps_between_tracks.html" loading="lazy" width="100%" height="400"></iframe>

**Note:** The `*gap` properties used to be prefixed by `grid-`, but this has been changed in the spec in order to make them usable in  multiple layout methods. The prefixed versions will be maintained as an  alias, so they'll be safe to use for some time. To be on the safe side,  you could double up and add both properties to make your code more  bulletproof.

```
.container {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  grid-gap: 20px;
  gap: 20px;
}
```

### [Repeating track listings](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#repeating_track_listings)

You can repeat all or merely a section of your track listing using the CSS `repeat` function. Change your track listing to the following:

```
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

You'll now get three `1fr`  tracks just as before. The first value passed to the repeat function  specifies the number of times you want the listing to repeat, while the  second value is a track listing, which may be one or more tracks that  you want to repeat.

### [The implicit and explicit grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#the_implicit_and_explicit_grid)

We've only specified column tracks so far, yet rows are being created to hold our content. This is an example of the *explicit* versus the *implicit* grid. The explicit grid is the one that you create using `grid-template-columns` or `grid-template-rows`. The implicit grid is created when content is placed outside of that grid, such as into our rows.

By default, tracks created in the implicit grid are `auto` sized, which in general means that they're large enough to accomodate  their content. If you wish to give implicit grid tracks a size, you can  use the [`grid-auto-rows`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows) and [`grid-auto-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-columns) properties. If you add `grid-auto-rows` with a value of `100px` to your CSS, you'll see that those created rows are now 100 pixels tall.

```
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 100px;
  grid-gap: 20px;
}
```

<iframe class="sample-code-frame" title="The implicit and explicit grid sample" id="frame_The_implicit_and_explicit_grid" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.The_implicit_and_explicit_grid.html" loading="lazy" width="100%" height="400"></iframe>

### [The minmax() function](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#the_minmax_function)

Our 100-pixel tall tracks won’t be very useful if we add content into those tracks that is taller than 100 pixels, in which case it would cause an  overflow. It might be better to have tracks that are *at least*  100 pixels tall and can still expand if more content becomes added. A  fairly basic fact about the web is that you never really know how tall  something is going to be — additional content or larger font sizes can  cause problems with designs that attempt to be pixel perfect in every  dimension.

The [`minmax()`](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax()) function lets us set a minimum and maximum size for a track, for example, `minmax(100px, auto)`. The minimum size is 100 pixels, but the maximum is `auto`, which will expand to accomodate more content. Try changing `grid-auto-rows` to use a minmax value:

```
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: minmax(100px, auto);
    gap: 20px;
}
```

If you add extra content, you'll see  that the track expands to allow it to fit. Note that the expansion  happens right along the row.

### [As many columns as will fit](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#as_many_columns_as_will_fit)

We can combine some of the lessons we've learned about track listing, repeat notation, and [`minmax()`](https://developer.mozilla.org/en-US/docs/Web/CSS/minmax()) to create a useful pattern. Sometimes it's helpful to be able to ask  grid to create as many columns as will fit into the container. We do  this by setting the value of `grid-template-columns` using the [`repeat()`](https://developer.mozilla.org/en-US/docs/Web/CSS/repeat()) function, but instead of passing in a number, pass in the keyword `auto-fill`. For the second parameter of the function we use `minmax()` with a minimum value equal to the minimum track size that we would like to have and a maximum of `1fr`.

Try this in your file now using the CSS below:

```
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  grid-auto-rows: minmax(100px, auto);
  gap: 20px;
}
```

<iframe class="sample-code-frame" title="As many columns as will fit sample" id="frame_As_many_columns_as_will_fit" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.As_many_columns_as_will_fit.html" loading="lazy" width="100%" height="400"></iframe>

This works because grid is creating as many 200 pixel columns as will fit into the container, then sharing whatever space is leftover among  all the columns. The maximum is 1fr which, as we already know,  distributes space evenly between tracks.

## [Line-based placement](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#line-based_placement)

We now move on from creating a grid to placing things on the grid. Our  grid always has lines. These lines are numbered, beginning with 1. They  relate to the Writing Mode of the document. Therefore, in English column line 1 is on the left hand side of the grid and row line 1 at the top.  In Arabic column line 1 would be on the right hand side since Arabic is  written right to left.

We can arrange things in accordance with these lines by specifying  the start and end line. We do this using the following properties:

- [`grid-column-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-start)
- [`grid-column-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column-end)
- [`grid-row-start`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-start)
- [`grid-row-end`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-end)

These properties can all have a line number as their value. You can also use the shorthand properties:

- [`grid-column`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-column)
- [`grid-row`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row)

These let you specify the start and end lines at once, separated by a forward slash `/`.

[Download this file as a starting point](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/8-placement-starting-point.html) or [see it live here](https://mdn.github.io/learning-area/css/css-layout/grids/8-placement-starting-point.html). It has a defined grid and a simple article outlined. You can see that *auto-placement* is placing each item into its own cell on the grid.

Let's instead arrange all of the elements for our site by using the  grid lines. Add the following rules to the bottom of your CSS:

```
header {
  grid-column: 1 / 3;
  grid-row: 1;
}

article {
  grid-column: 2;
  grid-row: 2;
}

aside {
  grid-column: 1;
  grid-row: 2;
}

footer {
  grid-column: 1 / 3;
  grid-row: 3;
}
```

<iframe class="sample-code-frame" title="Line-based placement sample" id="frame_Line-based_placement" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.Line-based_placement.html" loading="lazy" width="100%" height="600"></iframe>

**Note:** you can also use the value `-1`  to target the end column or row line, then count inwards from the end  using negative values. Note also that lines count always from the edges  of the explicit grid, not the [implicit grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid).

## [Positioning with grid-template-areas](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#positioning_with_grid-template-areas)

An alternative way to arrange items on your grid is to use the [`grid-template-areas`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) property and give the various elements of your design a name.

Remove the line-based positioning from the last example (or  re-download the file to have a fresh starting point) and add the  following CSS.

```
.container {
  display: grid;
  grid-template-areas:
      "header header"
      "sidebar content"
      "footer footer";
  grid-template-columns: 1fr 3fr;
  gap: 20px;
}

header {
  grid-area: header;
}

article {
  grid-area: content;
}

aside {
  grid-area: sidebar;
}

footer {
  grid-area: footer;
}
```

Reload the page and you will see that your items have been placed just as before without us needing to use any line numbers!

<iframe class="sample-code-frame" title="Positioning with grid-template-areas sample" id="frame_Positioning_with_grid-template-areas" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.Positioning_with_grid-template-areas.html" loading="lazy" width="100%" height="600"></iframe>

The rules for `grid-template-areas` are as follows:

- You need to have every cell of the grid filled.
- To span across two cells, repeat the name.
- To leave a cell empty, use a `.` (period).
- Areas must be rectangular — you can’t have an L-shaped area for example.
- Areas can't be repeated in different locations.

You can play around with our layout, changing the footer to only sit  underneath the article and the sidebar to span all the way down. This is a very nice way to describe a layout because it's clear just from  looking at the CSS to know exactly what's happening.

## [A CSS Grid, grid framework](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#a_css_grid_grid_framework)

Grid "frameworks" tend to be based around 12 or 16 column grids. With CSS  Grid, you don’t need any third party tool to give you such a framework — it's already there in the spec.

[Download the starting point file](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/11-grid-system-starting-point.html). This has a container with a 12 column grid defined and the same markup  we used in the previous two examples. We can now use line-based  placement to place our content on the 12 column grid.

```
header {
  grid-column: 1 / 13;
  grid-row: 1;
}

article {
  grid-column: 4 / 13;
  grid-row: 2;
}

aside {
  grid-column: 1 / 4;
  grid-row: 2;
}

footer {
  grid-column: 1 / 13;
  grid-row: 3;
}
```

<iframe class="sample-code-frame" title="A CSS Grid grid framework sample" id="frame_A_CSS_Grid_grid_framework" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Grids/_sample_.A_CSS_Grid_grid_framework.html" loading="lazy" width="100%" height="600"></iframe>

If you use the [Firefox Grid Inspector](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_grid_layouts) to overlay the grid lines on your design, you can see how our 12 column grid works.

  ![A 12 column grid overlaid on our design.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids/learn-grids-inspector.png)



# 浮动布局（Floats）

## [The background of floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#the_background_of_floats)

The [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) property was introduced to allow web developers to implement simple  layouts involving an image floating inside a column of text, with the  text wrapping around the left or right of it. The kind of thing you  might get in a newspaper layout.

But web developers quickly realized that you can float anything, not  just images, so the use of float broadened, for example, to fun layout  effects such as [drop-caps](https://css-tricks.com/snippets/css/drop-caps/).

Floats have commonly been used to create entire web site layouts  featuring multiple columns of information floated so they sit alongside  one another (the default behavior would be for the columns to sit below  one another in the same order as they appear in the source). There are  newer, better layout techniques available. Using floats in this way  should be regarded as a [legacy technique](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods).

In this article we'll just concentrate on the proper uses of floats.

## [A simple float example](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#a_simple_float_example)

Let's explore the use of floats. We'll start with a really simple example  involving floating a block of text around an element. You can follow  along by creating a new `index.html` file on your computer, filling it with a [simple HTML template](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/getting-started/index.html), and inserting the below code into it at the appropriate places. At the  bottom of the section, you can see a live example of what the final code should look like.

First, we'll start off with some simple HTML. Add the following to  your HTML body, removing anything that was inside there before:

```
<h1>Simple float example</h1>

<div class="box">Float</div>

<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies tellus laoreet sit amet. </p>

<p>Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci vel, viverra egestas ligula. Curabitur vehicula tellus neque, ac ornare ex malesuada et. In vitae convallis lacus. Aliquam erat volutpat. Suspendisse ac imperdiet turpis. Aenean finibus sollicitudin eros pharetra congue. Duis ornare egestas augue ut luctus. Proin blandit quam nec lacus varius commodo et a urna. Ut id ornare felis, eget fermentum sapien.</p>

<p>Nam vulputate diam nec tempor bibendum. Donec luctus augue eget malesuada ultrices. Phasellus turpis est, posuere sit amet dapibus ut, facilisis sed est. Nam id risus quis ante semper consectetur eget aliquam lorem. Vivamus tristique elit dolor, sed pretium metus suscipit vel. Mauris ultricies lectus sed lobortis finibus. Vivamus eu urna eget velit cursus viverra quis vestibulum sem. Aliquam tincidunt eget purus in interdum. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
```

Now apply the following CSS to your HTML (using a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element or a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) to a separate `.css` file — your choice):

```
body {
  width: 90%;
  max-width: 900px;
  margin: 0 auto;
  font: .9em/1.2 Arial, Helvetica, sans-serif
}

.box {
  width: 150px;
  height: 100px;
  border-radius: 5px;
  background-color: rgb(207,232,220);
  padding: 1em;
}
```

If you save and refresh, you'll see something much like what you'd expect: the box is sitting above the text, in normal flow.

### [Floating the box](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#floating_the_box)

To float the box, add the [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) and [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right) properties to the `.box` rule:

```
.box {
  float: left;
  margin-right: 15px;
  width: 150px;
  height: 100px;
  border-radius: 5px;
  background-color: rgb(207,232,220);
  padding: 1em;
}
```

Now if you save and refresh you'll see something like the following:

<iframe class="sample-code-frame" title="Floating the box sample" id="frame_Floating_the_box" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Floats/_sample_.Floating_the_box.html" loading="lazy" width="100%" height="500"></iframe>

Let's think about how the float works. The element with the float set on it (the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element in this case) is taken out of the normal layout flow of the  document and stuck to the left-hand side of its parent container ([``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body), in this case). Any content that would come below the floated element in the normal layout flow will now wrap around it instead, filling up the  space to the right-hand side of it as far up as the top of the floated  element. There, it will stop.

Floating the content to the right has exactly the same effect, but in reverse: the floated element will stick to the right, and the content  will wrap around it to the left. Try changing the float value to `right` and replace [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right) with [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left) in the last ruleset to see what the result is.

### [Visualising the float](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#visualising_the_float)

While we can add a margin to the float to push the text away, we can't add a  margin to the text to move it away from the float. This is because a  floated element is taken out of normal flow and the boxes of the  following items actually run behind the float. You can see this by  making some changes to your example.

Add a class of `special` to the first paragraph of text,  the one immediately following the floated box, then in your CSS add the  following rules. These will give our following paragraph a background  color.

```
.special {
  background-color: rgb(79,185,227);
  padding: 10px;
  color: #fff;
}
```

To make the effect easier to see, change the `margin-left` on your float to `margin` so you get space all around the float. You'll be able to see the  background on the paragraph running right underneath the floated box, as in the example below.

<iframe class="sample-code-frame" title="Visualising the float sample" id="frame_Visualising_the_float" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Floats/_sample_.Visualising_the_float.html" loading="lazy" width="100%" height="500"></iframe>

The [line boxes](https://developer.mozilla.org/en-US/docs/Web/CSS/Visual_formatting_model#line_boxes) of our following element have been shortened so the text runs around  the float, but due to the float being removed from normal flow the box  around the paragraph still remains full width.

## [Clearing floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#clearing_floats)

We've seen that a float is removed from normal flow and that other elements  will display beside it. If we want to stop the following element from  moving up, we need to *clear* it; this is achieved with the [`clear`](https://developer.mozilla.org/en-US/docs/Web/CSS/clear) property.

In your HTML from the previous example, add a class of `cleared` to the second paragraph below the floated item. Then add the following to your CSS:

```
.cleared {
  clear: left;
}
```

<iframe class="sample-code-frame" title="Clearing floats sample" id="frame_Clearing_floats" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Floats/_sample_.Clearing_floats.html" loading="lazy" width="100%" height="600"></iframe>

You should see that the second paragraph now clears the floated element and no longer comes up alongside it. The `clear` property accepts the following values:

- `left`: Clear items floated to the left.
- `right`: Clear items floated to the right.
- `both`: Clear any floated items, left or right.

## [Clearing boxes wrapped around a float](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#clearing_boxes_wrapped_around_a_float)

You now know how to clear something following a floated element, but let's  see what happens if you have a tall float and a short paragraph, with a  box wrapped around *both* elements.

### [The problem](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#the_problem)

Change your document so that the first paragraph and the floated box are jointly wrapped with a [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div), which has a class of `wrapper`.

```
<div class="wrapper">
  <div class="box">Float</div>

  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat vulputate.</p>
</div>
```

In your CSS, add the following rule for the `.wrapper` class and then reload the page:

```
.wrapper {
  background-color: rgb(79,185,227);
  padding: 10px;
  color: #fff;
}
```

In addition, remove the original `.cleared` class:

```
.cleared {
    clear: left;
}
```

You'll see that, just like in the example  where we put a background color on the paragraph, the background color  runs behind the float.

<iframe class="sample-code-frame" title="The problem sample" id="frame_The_problem" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Floats/_sample_.The_problem.html" loading="lazy" width="100%" height="600"></iframe>

Once again, this is because the float has been taken out of normal  flow. Clearing the following element won't work as it did before. This  is a problem if you want the box to wrap jointly around the floated item as well as the text of the first paragraph that wraps around the float, while also having the following content cleared of the box. There are  three potential ways to deal with this, two of which work in all  browsers — yet are slightly hacky — and a third, newer way that deals  with this situation properly.

### [The clearfix hack](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#the_clearfix_hack)

The way that this situation has traditionally been dealt with is to use  something known as a "clearfix hack". This involves first inserting some generated content after the box that contains both the float and  content wrapped around it, then setting that generated content to clear  both.

Add the following CSS to our example:

```
.wrapper::after {
  content: "";
  clear: both;
  display: block;
}
```

Now reload the page and the box should clear. This is essentially the same as if you had added an HTML element such as a `<div>` below the items and set it to `clear: both`.

<iframe class="sample-code-frame" title="The clearfix hack sample" id="frame_The_clearfix_hack" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Floats/_sample_.The_clearfix_hack.html" loading="lazy" width="100%" height="600"></iframe>

### [Using overflow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#using_overflow)

An alternative method is to set the [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) property of the wrapper to a value other than `visible`.

Remove the clearfix CSS you added in the last section; instead add `overflow: auto` to the rules for wrapper. Once again, the box should clear.

```
.wrapper {
  background-color: rgb(79,185,227);
  padding: 10px;
  color: #fff;
  overflow: auto;
}
```

<iframe class="sample-code-frame" title="Using overflow sample" id="frame_Using_overflow" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Floats/_sample_.Using_overflow.html" loading="lazy" width="100%" height="600"></iframe>

This example works by creating what's known as a **block formatting context** (BFC). This is like a mini layout inside your page, inside of which  everything is contained. This means our floated element is contained  inside the BFC, and the background runs behind both items. This will  usually work; however, in certain cases you might find unwanted  scrollbars or clipped shadows due to unintended consequences of using  overflow.

### [display: flow-root](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats#display_flow-root)

The modern way of solving this problem is to use the value `flow-root` of the `display` property. This exists only to create a BFC without using hacks — there  will be no unintended consequences when you use it. Remove `overflow: auto` from your `.wrapper` rule and add `display: flow-root`. Assuming you have a [supporting browser](https://developer.mozilla.org/en-US/docs/Web/CSS/display#browser_compatibility), the box will clear.

```
.wrapper {
  background-color: rgb(79,185,227);
  padding: 10px;
  color: #fff;
  display: flow-root;
}
```

<iframe class="sample-code-frame" title="display flow-root sample" id="frame_display_flow-root" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Floats/_sample_.display_flow-root.html" loading="lazy" width="100%" height="600"></iframe>

# 定位布局（Positioning）

## [Introducing positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#introducing_positioning)

Positioning allows us to produce interesting results by overriding normal document  flow. What if you want to slightly alter the position of some boxes from their default flow position to give a slightly quirky, distressed feel? Positioning is your tool. Or what if you want to create a UI element  that floats over the top of other parts of the page and/or always sits  in the same place inside the browser window no matter how much the page  is scrolled? Positioning makes such layout work possible.

There are a number of different types of positioning that you can put into effect on HTML elements. To make a specific type of positioning  active on an element, we use the [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) property.

## [Static positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#static_positioning)

Static positioning is the default that every element gets. It just means "put  the element into its normal position in the document flow — nothing  special to see here."

To see this (and get your example set up for future sections) first add a `class` of `positioned` to the second [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) in the HTML:

```
<p class="positioned"> ... </p>
```

Now add the following rule to the bottom of your CSS:

```
.positioned {
  position: static;
  background: yellow;
}
```

If you save and refresh, you'll see no difference at all, except for  the updated background color of the 2nd paragraph. This is fine — as we  said before, static positioning is the default behavior!

**Note:** You can see the example at this point live at [`1_static-positioning.html`](https://mdn.github.io/learning-area/css/css-layout/positioning/1_static-positioning.html) ([see source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/positioning/1_static-positioning.html)).

## [Relative positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#relative_positioning)

Relative positioning is the first position type we'll take a look at. This is  very similar to static positioning, except that once the positioned  element has taken its place in the normal flow, you can then modify its  final position, including making it overlap other elements on the page.  Go ahead and update the `position` declaration in your code:

```
position: relative;
```

If you save and refresh at this stage,  you won't see a change in the result at all. So how do you modify the  element's position? You need to use the [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [`bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom), [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left), and [`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/right) properties, which we'll explain in the next section.

### [Introducing top, bottom, left, and right](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#introducing_top_bottom_left_and_right)

[`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [`bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom), [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left), and [`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/right) are used alongside [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position) to specify exactly where to move the positioned element to. To try this out, add the following declarations to the `.positioned` rule in your CSS:

```
top: 30px;
left: 30px;
```

**Note:** The values of these properties can take any [units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units) you'd reasonably expect: pixels, mm, rems, %, etc.

If you now save and refresh, you'll get a result something like this:

<iframe class="sample-code-frame" title="Introducing top bottom left and right sample" id="frame_Introducing_top_bottom_left_and_right" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Positioning/_sample_.Introducing_top_bottom_left_and_right.html" loading="lazy" width="100%" height="500"></iframe>

Cool, huh? Ok, so this probably wasn't what you were expecting. Why has it moved to the bottom and to the right if we specified *top* and *left*? This may seem counterintuitive. You need to think of it as if there's  an invisible force that pushes the specified side of the positioned box, moving it in the opposite direction. So, for example, if you specify `top: 30px;`, it's as if a force will push the top of the box, causing it to move downwards by 30px.

**Note:** You can see the example at this point live at [`2_relative-positioning.html`](https://mdn.github.io/learning-area/css/css-layout/positioning/2_relative-positioning.html) ([see source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/positioning/2_relative-positioning.html)).

## [Absolute positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#absolute_positioning)

Absolute positioning brings very different results.

### [Setting position: absolute](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#setting_position_absolute)

Let's try changing the position declaration in your code as follows:

```
position: absolute;
```

If you now save and refresh, you should see something like so:

<iframe class="sample-code-frame" title="Setting position absolute sample" id="frame_Setting_position_absolute" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Positioning/_sample_.Setting_position_absolute.html" loading="lazy" width="100%" height="450"></iframe>

First of all, note that the gap where the positioned element should  be in the document flow is no longer there — the first and third  elements have closed together like it no longer exists! Well, in a way,  this is true. An absolutely positioned element no longer exists in the  normal document flow. Instead, it sits on its own layer separate from  everything else. This is very useful: it means that we can create  isolated UI features that don't interfere with the layout of other  elements on the page. For example, popup information boxes, control  menus, rollover panels, UI features that can be dragged and dropped  anywhere on the page, and so on.

Second, notice that the position of the element has changed. This is because [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [`bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom), [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left), and [`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/right) behave in a different way with absolute positioning. Rather than  positioning the element based on its relative position within the normal document flow, they specify the distance the element should be from  each of the containing element's sides. So in this case, we are saying  that the absolutely positioned element should sit 30px from the top of  the "containing element" and 30px from the left. (In this case, the  "containing element" is the **initial containing block**. See the section below for more information)

**Note:** You can use [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top), [`bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/bottom), [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left), and [`right`](https://developer.mozilla.org/en-US/docs/Web/CSS/right) to resize elements if you need to. Try setting `top: 0; bottom: 0; left: 0; right: 0;` and `margin: 0;` on your positioned elements and see what happens! Put it back again afterwards...

**Note:** Yes, margins still affect positioned elements. Margin collapsing doesn't, however.

**Note:** You can see the example at this point live at [`3_absolute-positioning.html`](https://mdn.github.io/learning-area/css/css-layout/positioning/3_absolute-positioning.html) ([see source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/positioning/3_absolute-positioning.html)).

### [Positioning contexts](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#positioning_contexts)

Which element is the "containing element" of an absolutely positioned  element? This is very much dependent on the position property of the  ancestors of the positioned element (See [Identifying the containing block](https://developer.mozilla.org/en-US/docs/Web/CSS/Containing_block#identifying_the_containing_block)).

If no ancestor elements have their position property explicitly  defined, then by default all ancestor elements will have a static  position. The result of this is the absolutely positioned element will  be contained in the **initial containing block**. The initial containing block has the dimensions of the viewport and is also the block that contains the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element. In other words, the absolutely positioned element will be displayed outside of the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element and be positioned relative to the initial viewport.

The positioned element is nested inside the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) in the HTML source, but in the final layout it's 30px away from the top and the left edges of the page. We can change the **positioning context**, that is, which element the absolutely positioned element is positioned  relative to. This is done by setting positioning on one of the  element's ancestors: to one of the elements it's nested inside of (you  can't position it relative to an element it's not nested inside of). To  see this, add the following declaration to your `body` rule:

```
position: relative;
```

This should give the following result:

<iframe class="sample-code-frame" title="Positioning contexts sample" id="frame_Positioning_contexts" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Positioning/_sample_.Positioning_contexts.html" loading="lazy" width="100%" height="420"></iframe>

The positioned element now sits relative to the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element.

**Note:** You can see the example at this point live at [`4_positioning-context.html`](https://mdn.github.io/learning-area/css/css-layout/positioning/4_positioning-context.html) ([see source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/positioning/4_positioning-context.html)).



### [Introducing z-index](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#introducing_z-index)

All this absolute positioning is good fun, but there's another feature we  haven't considered yet. When elements start to overlap, what determines  which elements appear over others and which elements appear under  others? In the example we've seen so far, we only have one positioned  element in the positioning context, and it appears on the top since  positioned elements win over non-positioned elements. What about when we have more than one?

Try adding the following to your CSS to make the first paragraph absolutely positioned too:

```
p:nth-of-type(1) {
  position: absolute;
  background: lime;
  top: 10px;
  right: 30px;
}
```

At this point you'll see the first paragraph colored lime, moved out  of the document flow, and positioned a bit above from where it  originally was. It's also stacked below the original `.positioned` paragraph where the two overlap. This is because the `.positioned` paragraph is the second paragraph in the source order, and positioned  elements later in the source order win over positioned elements earlier  in the source order.

Can you change the stacking order? Yes, you can, by using the [`z-index`](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index) property. "z-index" is a reference to the z-axis. You may recall from  previous points in the course where we discussed web pages using  horizontal (x-axis) and vertical (y-axis) coordinates to work out  positioning for things like background images and drop shadow offsets.  For languages that run left to right, (0,0) is at the top left of the  page (or element), and the x- and y-axes run across to the right and  down the page.

Web pages also have a z-axis: an imaginary line that runs from the  surface of your screen towards your face (or whatever else you like to  have in front of the screen). [`z-index`](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index) values affect where positioned elements sit on that axis; positive  values move them higher up the stack, negative values move them lower  down the stack. By default, positioned elements all have a `z-index` of `auto`, which is effectively 0.

To change the stacking order, try adding the following declaration to your `p:nth-of-type(1)` rule:

```
z-index: 1;
```

You should now see the lime paragraph on top:

<iframe class="sample-code-frame" title="Introducing z-index sample" id="frame_Introducing_z-index" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Positioning/_sample_.Introducing_z-index.html" loading="lazy" width="100%" height="400"></iframe>

Note that `z-index` only accepts unitless index values;  you can't specify that you want one element to be 23 pixels up the  Z-axis — it doesn't work like that. Higher values will go above lower  values and it's up to you what values you use. Using values of 2 or 3  would give the same effect as values of 300 or 40000.

**Note:** You can see an example for this live at [`5_z-index.html`](https://mdn.github.io/learning-area/css/css-layout/positioning/5_z-index.html) ([see source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/positioning/5_z-index.html)).

## [Fixed positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#fixed_positioning)

Let's now look at fixed positioning. This works in exactly the same way as  absolute positioning, with one key difference: whereas absolute  positioning fixes an element in place relative to its nearest positioned ancestor (the initial containing block if there isn't one), **fixed positioning** *usually* fixes an element in place relative to the visible portion of the  viewport. (An exception to this occurs if one of the element's ancestors is a fixed containing block because its [transform property](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) has a value other than *none*.) This means that you can create useful UI items that are fixed in place, like persistent navigation menus that are always visible no matter how  much the page scrolls.

Let's put together a simple example to show what we mean. First of all, delete the existing `p:nth-of-type(1)` and `.positioned` rules from your CSS.

Now update the `body` rule to remove the `position: relative;` declaration and add a fixed height, like so:

```
body {
  width: 500px;
  height: 1400px;
  margin: 0 auto;
}
```

Now we're going to give the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) element `position: fixed;` and have it sit at the top of the viewport. Add the following rule to your CSS:

```
h1 {
  position: fixed;
  top: 0;
  width: 500px;
  margin-top: 0;
  background: white;
  padding: 10px;
}
```

The `top: 0;` is required to make it stick to the top of  the screen. We give the heading the same width as the content column and then a white background and some padding and margin so the content  won't be visible underneath it.

If you save and refresh, you'll see a fun little effect of the  heading staying fixed — the content appears to scroll up and disappear  underneath it. But notice how some of the content is initially clipped  under the heading. This is because the positioned heading no longer  appears in the document flow, so the rest of the content moves up to the top. We could improve this by moving the paragraphs all down a bit. We  can do this by setting some top margin on the first paragraph. Add this  now:

```
p:nth-of-type(1) {
  margin-top: 60px;
}
```

You should now see the finished example:

<iframe class="sample-code-frame" title="Fixed positioning sample" id="frame_Fixed_positioning" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Positioning/_sample_.Fixed_positioning.html" loading="lazy" width="100%" height="400"></iframe>

**Note:** You can see an example for this live at [`6_fixed-positioning.html`](https://mdn.github.io/learning-area/css/css-layout/positioning/6_fixed-positioning.html) ([see source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/positioning/6_fixed-positioning.html)).

## [Sticky positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#sticky_positioning)

There is another position value available called `position: sticky`, which is somewhat newer than the others. This is basically a hybrid  between relative and fixed position. It allows a positioned element to  act like it's relatively positioned until it's scrolled to a certain  threshold (e.g., 10px from the top of the viewport), after which it  becomes fixed.

### [Basic example](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#basic_example)

Sticky positioning can be used, for example, to cause a navigation bar to  scroll with the page until a certain point and then stick to the top of  the page.

```
.positioned {
  position: sticky;
  top: 30px;
  left: 30px;
}
```

<iframe class="sample-code-frame" title="Basic example sample" id="frame_Basic_example" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Positioning/_sample_.Basic_example.html" loading="lazy" width="100%" height="200"></iframe>

### [Scrolling index](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning#scrolling_index)

An interesting and common use of `position: sticky` is to create a scrolling index page where different headings stick to  the top of the page as they reach it. The markup for such an example  might look like so:

```
<h1>Sticky positioning</h1>

<dl>
    <dt>A</dt>
    <dd>Apple</dd>
    <dd>Ant</dd>
    <dd>Altimeter</dd>
    <dd>Airplane</dd>
    <dt>B</dt>
    <dd>Bird</dd>
    <dd>Buzzard</dd>
    <dd>Bee</dd>
    <dd>Banana</dd>
    <dd>Beanstalk</dd>
    <dt>C</dt>
    <dd>Calculator</dd>
    <dd>Cane</dd>
    <dd>Camera</dd>
    <dd>Camel</dd>
    <dt>D</dt>
    <dd>Duck</dd>
    <dd>Dime</dd>
    <dd>Dipstick</dd>
    <dd>Drone</dd>
    <dt>E</dt>
    <dd>Egg</dd>
    <dd>Elephant</dd>
    <dd>Egret</dd>
</dl>
```

The CSS might look as follows. In normal flow the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt) elements will scroll with the content. When we add `position: sticky` to the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt) element, along with a [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top) value of 0, supporting browsers will stick the headings to the top of  the viewport as they reach that position. Each subsequent header will  then replace the previous one as it scrolls up to that position.

```
dt {
  background-color: black;
  color: white;
  padding: 10px;
  position: sticky;
  top: 0;
  left: 0;
  margin: 1em 0;
}
```

<iframe class="sample-code-frame" title="Scrolling index sample" id="frame_Scrolling_index" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Positioning/_sample_.Scrolling_index.html" loading="lazy" width="100%" height="200"></iframe>

Sticky elements are "sticky" relative to the nearest ancestor with a  "scrolling mechanism", which is determined by its ancestors' [position](https://developer.mozilla.org/en-US/docs/Web/CSS/position) property.

**Note:** You can see this example live at [`7_sticky-positioning.html`](https://mdn.github.io/learning-area/css/css-layout/positioning/7_sticky-positioning.html) ([see source code](https://github.com/mdn/learning-area/blob/master/css/css-layout/positioning/7_sticky-positioning.html)).

# 布局和包含块

一个元素的尺寸和位置经常受其**包含块(containing block)**的影响。大多数情况下，包含块就是这个元素最近的祖先[块元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Block-level_elements)的[内容区](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model#content-area)，但也不是总是这样。在本文中，我们来过一遍确定包含块的所有因素。

当一个客户端代理（比如说浏览器）展示一个文档的时候，对于每一个元素，它都产生了一个盒子。每一个盒子都被划分为四个区域：

1. 内容区
2. 内边距区
3. 边框区
4. 外边距区

![Diagram of the box model](https://mdn.mozillademos.org/files/16558/box-model.png)

许多开发者认为一个元素的包含块就是他的父元素的内容区。但事实并非如此。接下来让我们来看看，确定元素包含块的因素都有哪些。

## [包含块的影响](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#包含块的影响)

在学习如何确定元素包含块之前，先了解一下它的重要性。

元素的尺寸及位置，常常会受它的包含块所影响。对于一些属性，例如 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width), [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height), [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding), [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin)，绝对定位元素的偏移值 （比如 [`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position) 被设置为 `absolute` 或 `fixed`），当我们对其赋予百分比值时，这些值的计算值，就是通过元素的包含块计算得来。

## [确定包含块](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#确定包含块)

确定一个元素的包含块的过程完全依赖于这个元素的 [`position`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/position) 属性：

1. 如果 position 属性为 `**static**` 、 `**relative**` **或 `sticky`**，包含块可能由它的最近的祖先**块元素**（比如说inline-block, block 或 list-item元素）的内容区的边缘组成，也可能会建立格式化上下文(比如说 a table container, flex  container, grid container, 或者是 the block container 自身)。

2. 如果 position 属性为 `**absolute**` ，包含块就是由它的最近的 position 的值不是 `static` （也就是值为`fixed`, `absolute`, `relative` 或 `sticky`）的祖先元素的内边距区的边缘组成。

3. 如果 position 属性是 **`fixed`**，在连续媒体的情况下(continuous media)包含块是 [viewport](https://developer.mozilla.org/zh-CN/docs/Glossary/Viewport) ,在分页媒体(paged media)下的情况下包含块是分页区域(page area)。

4. 如果 position 属性是 

   ```
   absolute
   ```

    或 

   ```
   fixed
   ```

   ，包含块也可能是由满足以下条件的最近父级元素的内边距区的边缘组成的：  

   1.  [`transform`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform) 或 [`perspective`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/perspective) 的值不是 `none`
   2.  [`will-change`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/will-change) 的值是 `transform` 或 `perspective`
   3.  [`filter`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter) 的值不是 `none` 或 `will-change` 的值是 `filter`(只在 Firefox 下生效).
   4.  [`contain`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/contain) 的值是 `paint` (例如: `contain: paint;`)

**注意:** 根元素(<html>)所在的包含块是一个被称为**初始包含块**的矩形。他的尺寸是视口 viewport (for continuous media) 或分页媒体 page media (for paged media).

## [根据包含块计算百分值](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#根据包含块计算百分值)

如上所述，如果某些属性被赋予一个百分值的话，它的计算值是由这个元素的包含块计算而来的。这些属性包括盒模型属性和偏移属性：

1. 要计算 [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height) [`top`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/top) 及 [`bottom`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/bottom) 中的百分值，是通过包含块的 `height` 的值。如果包含块的 `height` 值会根据它的内容变化，而且包含块的 `position` 属性的值被赋予 `relative` 或 `static` ，那么，这些值的计算值为 auto。
2. 要计算 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width), [`left`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/left), [`right`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/right), [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding), [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin) 这些属性由包含块的 `width` 属性的值来计算它的百分值。

## [示例](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#示例)

接下来的示例，都使用如下 HTML 代码:

```
<body>
  <section>
    <p>This is a paragraph!</p>
  </section>
</body>
```

下面的示例，只有 CSS 不同。

### [Example 1](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#example_1)

这个示例中，P 标签设置为静态定位，所以它的包含块为 `<section>` ，因为距离最近的父节点即是她的包含块。

```
body {
  background: beige;
}

section {
  display: block;
  width: 400px;
  height: 160px;
  background: lightgray;
}

p {
  width: 50%;   /* == 400px * .5 = 200px */
  height: 25%;  /* == 160px * .25 = 40px */
  margin: 5%;   /* == 400px * .05 = 20px */
  padding: 5%;  /* == 400px * .05 = 20px */
  background: cyan;
}
```



### [Example 2](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#example_2)

在这个示例中，P 标签的包含块为 `<body>` **元素，**因为 `<section>` 不再是一个块容器，所以并没有形成一个格式上下文。

```
body {
  background: beige;
}

section {
  display: inline;
  background: lightgray;
}

p {
  width: 50%;     /* == half the body's width */
  height: 200px;  /* Note: a percentage would be 0 */
  background: cyan;
}
```



### [Example 3](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#example_3)

这个示例中，P 元素的包含块是 `<section`>，因为 `<section>` 的 `position` 为 `absolute` 。P 元素的百分值会受其包含块的 `padding` 所影响。不过，如果包含块的 [`box-sizing`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/box-sizing) 值设置为 `border-box` ，就没有这个问题。

```
body {
  background: beige;
}

section {
  position: absolute;
  left: 30px;
  top: 30px;
  width: 400px;
  height: 160px;
  padding: 30px 20px;
  background: lightgray;
}

p {
  position: absolute;
  width: 50%;   /* == (400px + 20px + 20px) * .5 = 220px */
  height: 25%;  /* == (160px + 30px + 30px) * .25 = 55px */
  margin: 5%;   /* == (400px + 20px + 20px) * .05 = 22px */
  padding: 5%;  /* == (400px + 20px + 20px) * .05 = 22px */
  background: cyan;
}
```



### [Example 4](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#example_4)

这个示例中，P 元素的 `position` 为 `fixed`，所以它的包含块就是初始包含块（在屏幕上，也就是 viewport）。这样的话，P 元素的尺寸大小，将会随着浏览器窗框大小的变化，而变化。

```
body {
  background: beige;
}

section {
  width: 400px;
  height: 480px;
  margin: 30px;
  padding: 15px;
  background: lightgray;
}

p {
  position: fixed;
  width: 50%;   /* == (50vw - (width of vertical scrollbar)) */
  height: 50%;  /* == (50vh - (height of horizontal scrollbar)) */
  margin: 5%;   /* == (5vw - (width of vertical scrollbar)) */
  padding: 5%;  /* == (5vw - (width of vertical scrollbar)) */
  background: cyan;
}
```



### [Example 5](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Containing_block#example_5)

这个示例中，P 元素的 `position` 为 `absolute`，所以它的包含块是 `<section>`，也就是距离它最近的一个 `transform` 值不为 none 的父元素。

```
body {
  background: beige;
}

section {
  transform: rotate(0deg);
  width: 400px;
  height: 160px;
  background: lightgray;
}

p {
  position: absolute;
  left: 80px;
  top: 30px;
  width: 50%;   /* == 200px */
  height: 25%;  /* == 40px */
  margin: 5%;   /* == 20px */
  padding: 5%;  /* == 20px */
  background: cyan;
}
```

# （多列排版Multiple-column）

## [A basic example](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#a_basic_example)

Let's explore how to use multiple-column layout — often referred to as *multicol*. You can follow along by [downloading the multicol starting point file](https://github.com/mdn/learning-area/blob/master/css/css-layout/multicol/0-starting-point.html) and adding the CSS into the appropriate places. At the bottom of the  section you can see an example of what the final code should look like.

### [A three-column layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#a_three-column_layout)

Our starting point file contains some very simple HTML: a wrapper with a class of `container`, inside of which is a heading and some paragraphs.

The [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) with a class of container will become our multicol container. We enable multicol by using one of two properties: [`column-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count) or [`column-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-width). The `column-count` property takes a number as its value and creates that number of  columns. If you add the following CSS to your stylesheet and reload the  page, you'll get three columns:

```
.container {
  column-count: 3;
}
```

The columns that you create have flexible widths — the browser works out how much space to assign each column.

<iframe class="sample-code-frame" title="A three-column layout sample" id="frame_A_three-column_layout" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout/_sample_.A_three-column_layout.html" loading="lazy" width="100%" height="400"></iframe>

### [Setting column-width](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#setting_column-width)

Change your CSS to use `column-width` as follows:

```
.container {
  column-width: 200px;
}
```

The browser will now give you as many  columns as it can of the size that you specify; any remaining space is  then shared between the existing columns. This means that you won't get  exactly the width that you specify unless your container is exactly  divisible by that width.

<iframe class="sample-code-frame" title="Setting column-width sample" id="frame_Setting_column-width" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout/_sample_.Setting_column-width.html" loading="lazy" width="100%" height="400"></iframe>

## [Styling the columns](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#styling_the_columns)

The columns created by multicol cannot be styled individually. There's no  way to make one column bigger than other columns or to change the  background or text color of a single column. You have two opportunities  to change the way that columns display:

- Changing the size of the gap between columns using the [`column-gap`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap).
- Adding a rule between columns with [`column-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule).

Using your example above, change the size of the gap by adding a `column-gap` property. You can play around with different values — the property accepts any length unit.

Now add a rule between the columns with `column-rule`. In a similar way to the [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) property that you encountered in previous lessons, `column-rule` is a shorthand for [`column-rule-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color), [`column-rule-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-style), and [`column-rule-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-width), and accepts the same values as `border`.

```
.container {
  column-count: 3;
  column-gap: 20px;
  column-rule: 4px dotted rgb(79, 185, 227);
}
```

Try adding rules of different styles and colors.

<iframe class="sample-code-frame" title="Styling the columns sample" id="frame_Styling_the_columns" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout/_sample_.Styling_the_columns.html" loading="lazy" width="100%" height="400"></iframe>

Something to take note of is that the rule doesn't take up any width of its own. It lies across the gap you created with `column-gap`. To make more space on either side of the rule, you'll need to increase the `column-gap` size.

## [Spanning columns](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#spanning_columns)

You can cause an element to span across all the columns. In this case, the  content breaks where the spanning element's introduced and then  continues below the element, creating a new set of columns. To cause an  element to span all the columns, specify the value of `all` for the [`column-span`](https://developer.mozilla.org/en-US/docs/Web/CSS/column-span) property.

**Note:** It isn't possible to cause an element to span just *some* columns. The property can only have the values of `none` (which is the default) or `all`.

<iframe class="sample-code-frame" title="Spanning columns sample" id="frame_Spanning_columns" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout/_sample_.Spanning_columns.html" loading="lazy" width="100%" height="550"></iframe>

## [Columns and fragmentation](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#columns_and_fragmentation)

The content of a multi-column layout is fragmented. It essentially behaves  the same way as content behaves in paged media, such as when you print a webpage. When you turn your content into a multicol container, it  fragments into columns. In order for the content to do this, it must *break*.

### [Fragmented boxes](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#fragmented_boxes)

Sometimes, this breaking will happen in places that lead to a poor reading  experience. In the example below, I have used multicol to lay out a  series of boxes, each of which has a heading and some text inside. The  heading becomes separated from the text if the columns fragment between  the two.

```
<div class="container">
    <div class="card">
      <h2>I am the heading</h2>
      <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat
                vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies
                tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci
                vel, viverra egestas ligula.</p>
    </div>

    <div class="card">
      <h2>I am the heading</h2>
      <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat
                vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies
                tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci
                vel, viverra egestas ligula.</p>
    </div>

    <div class="card">
      <h2>I am the heading</h2>
      <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat
                vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies
                tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci
                vel, viverra egestas ligula.</p>
    </div>
    <div class="card">
      <h2>I am the heading</h2>
      <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat
                vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies
                tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci
                vel, viverra egestas ligula.</p>
    </div>

    <div class="card">
      <h2>I am the heading</h2>
      <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat
                vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies
                tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci
                vel, viverra egestas ligula.</p>
    </div>

    <div class="card">
      <h2>I am the heading</h2>
      <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat
                vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies
                tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci
                vel, viverra egestas ligula.</p>
    </div>

    <div class="card">
      <h2>I am the heading</h2>
      <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat
                vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies
                tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci
                vel, viverra egestas ligula.</p>
    </div>

</div>
.container {
  column-width: 250px;
  column-gap: 20px;
}

.card {
  background-color: rgb(207, 232, 220);
  border: 2px solid rgb(79, 185, 227);
  padding: 10px;
  margin: 0 0 1em 0;
}
```

<iframe class="sample-code-frame" title="Fragmented boxes sample" id="frame_Fragmented_boxes" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout/_sample_.Fragmented_boxes.html" loading="lazy" width="100%" height="1000"></iframe>

### [Setting break-inside](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout#setting_break-inside)

To control this behavior, we can use properties from the [CSS Fragmentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fragmentation) specification. This specification gives us properties to control the  breaking of content in multicol and in paged media. For example, by  adding the property [`break-inside`](https://developer.mozilla.org/en-US/docs/Web/CSS/break-inside) with a value of `avoid` to the rules for `.card`. This is the container of the heading and text, so we don't want it fragmented.

```
.card {
  break-inside: avoid;
  page-break-inside: avoid;
  background-color: rgb(207, 232, 220);
  border: 2px solid rgb(79, 185, 227);
  padding: 10px;
  margin: 0 0 1em 0;
}
```

The addition of this property causes the boxes to stay in one piece—they now do not *fragment* across the columns.

<iframe class="sample-code-frame" title="Setting break-inside sample" id="frame_Setting_break-inside" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout/_sample_.Setting_break-inside.html" loading="lazy" width="100%" height="1100"></iframe>

# 响应式设计（Responsive design）

## [Historic website layouts](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#historic_website_layouts)

At one point in history you had two options when designing a website:

- You could create a *liquid* site, which would stretch to fill the browser window
- or a *fixed width* site, which would be a fixed size in pixels.

These two approaches tended to result in a website that looked its  best on the screen of the person designing the site! The liquid site  resulted in a squashed design on smaller screens (as seen below) and  unreadably long line lengths on larger ones.

  ![A layout with two columns squashed into a mobile size viewport.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-liquid.png)

**Note:** See this simple liquid layout: [example](https://mdn.github.io/css-examples/learn/rwd/liquid-width.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/liquid-width.html). When viewing the example, drag your browser window in and out to see how this looks at different sizes.

The fixed-width site risked a horizontal scrollbar on screens smaller than the site width (as seen below), and lots of white space at the  edges of the design on larger screens.

  ![A layout with a horizontal scrollbar in a mobile viewport.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-fixed.png)

**Note:** See this simple fixed-width layout: [example](https://mdn.github.io/css-examples/learn/rwd/fixed-width.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/fixed-width.html). Again, observe the result as you change the browser window size.

**Note:** The screenshots above are taken using the [Responsive Design Mode](https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode) in Firefox DevTools.

As the mobile web started to become a reality with the first feature  phones, companies who wished to embrace mobile would generally create a  special mobile version of their site, with a different URL (often  something like *m.example.com*, or *example.mobi*). This meant that two separate versions of the site had to be developed and kept up-to-date.

In addition, these mobile sites often offered a very cut down  experience. As mobile devices became more powerful and able to display  full websites, this was frustrating to mobile users who found themselves trapped in the site's mobile version and unable to access information  they knew was on the full-featured desktop version of the site.

## [Flexible layout before responsive design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#flexible_layout_before_responsive_design)

A number of approaches were developed to try to solve the downsides of  the liquid or fixed-width methods of building websites. In 2004 Cameron  Adams wrote a post entitled [Resolution dependent layout](https://www.themaninblue.com/writing/perspective/2004/09/21/), describing a method of creating a design that could adapt to different  screen resolutions. This approach required JavaScript to detect the  screen resolution and load the correct CSS.

Zoe Mickley Gillenwater was instrumental in [her work](https://zomigi.com/blog/voices-that-matter-slides-available/) to describe and formalize the different ways in which flexible sites  could be created, attempting to find a happy medium between filling the  screen or being completely fixed in size.

## [Responsive design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#responsive_design)

The term responsive design was [coined by Ethan Marcotte in 2010](https://alistapart.com/article/responsive-web-design/) and described the use of three techniques in combination.

1. The first was the idea of fluid grids, something which was already being explored by Gillenwater, and can be read up on in Marcotte's  article, [Fluid Grids](https://alistapart.com/article/fluidgrids/) (published in 2009 on A List Apart).
2. The second technique was the idea of [fluid images](https://unstoppablerobotninja.com/entry/fluid-images). Using a very simple technique of setting the `max-width` property to `100%`, images would scale down smaller if their containing column became  narrower than the image's intrinsic size, but never grow larger. This  enables an image to scale down to fit in a flexibly-sized column, rather than overflow it, but not grow larger and become pixelated if the  column becomes wider than the image.
3. The third key component was the [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries). Media Queries enable the type of layout switch that Cameron Adams had  previously explored using JavaScript, using only CSS. Rather than having one layout for all screen sizes, the layout could be changed. Sidebars  could be repositioned for the smaller screen, or alternate navigation  could be displayed.

It is important to understand that **responsive web design isn't a separate technology** — it is a term used to describe an approach to web design or a set of best practices, used to create a layout that can *respond* to the device being used to view the content. In Marcotte's original  exploration this meant flexible grids (using floats) and media queries,  however in the almost 10 years since that article was written, working  responsively has become the default. Modern CSS layout methods are  inherently responsive, and we have new things built into the web  platform to make designing responsive sites easier.

The rest of this article will point you to the various web platform  features you might want to use when creating a responsive site.

## [Media Queries](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#media_queries)

Responsive design was only able to emerge due to the media query. The Media  Queries Level 3 specification became a Candidate Recommendation in 2009, meaning that it was deemed ready for implementation in browsers. Media  Queries allow us to run a series of tests (e.g. whether the user's  screen is greater than a certain width, or a certain resolution) and  apply CSS selectively to style the page appropriately for the user's  needs.

For example, the following media query tests to see if the current  web page is being displayed as screen media (therefore not a printed  document) and the viewport is at least 800 pixels wide. The CSS for the `.container` selector will only be applied if these two things are true.

```
@media screen and (min-width: 800px) {
  .container {
    margin: 1em 2em;
  }
}
```

You can add multiple media queries  within a stylesheet, tweaking your whole layout or parts of it to best  suit the various screen sizes. The points at which a media query is  introduced, and the layout changed, are known as *breakpoints*.

A common approach when using Media Queries is to create a simple  single-column layout for narrow-screen devices (e.g mobile phones), then check for larger screens and implement a multiple-column layout when  you know that you have enough screen width to handle it. This is often  described as **mobile first** design.

Find out more in the MDN documentation for [Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries).

## [Flexible grids](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#flexible_grids)

Responsive sites don't just change their layout between breakpoints, they are  built on flexible grids. A flexible grid means that you don't need to  target every possible device size that there is, and build a pixel  perfect layout for it. That approach would be impossible given the vast  number of differently-sized devices that exist, and the fact that on  desktop at least, people do not always have their browser window  maximized.

By using a flexible grid, you only need to add in a breakpoint and  change the design at the point where the content starts to look bad. For example, if the line lengths become unreadably long as the screen size  increases, or a box becomes squashed with two words on each line as it  narrows.

In the early days of responsive design, our only option for performing layout was to use [floats](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats). Flexible floated layouts were achieved by giving each element a  percentage width, and ensuring that across the layout the totals were  not more than 100%. In his original piece on fluid grids, Marcotte  detailed a formula for taking a layout designed using pixels and  converting it into percentages.

```
target / context = result
```

For example, if our target column size is 60 pixels, and the context  (or container) it is in is 960 pixels, we divide 60 by 960 to get a  value we can use in our CSS, after moving the decimal point two places  to the right.

```
.col {
  width: 6.25%; /* 60 / 960 = 0.0625 */
}
```

This approach will be found in many places across the web today, and it is documented here in the layout section of our [Legacy layout methods](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods) article. It is likely that you will come across websites using this  approach in your work, so it is worth understanding it, even though you  would not build a modern site using a float-based flexible grid.

The following example demonstrates a simple responsive design using  Media Queries and a flexible grid. On narrow screens the layout displays the boxes stacked on top of one another:

  ![A mobile view of the layout with boxes stacked on top of each other vertically.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-mobile.png)

On wider screens they move to two columns:

  ![A desktop view of a layout with two columns.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-desktop.png)

**Note:** You can find the [live example](https://mdn.github.io/css-examples/learn/rwd/float-based-rwd.html) and [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/float-based-rwd.html) for this example on GitHub.

## [Modern layout technologies](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#modern_layout_technologies)

Modern layout methods such as [Multiple-column layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout), [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox), and [Grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids) are responsive by default. They all assume that you are trying to create a flexible grid and give you easier ways to do so.

### [Multicol](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#multicol)

The oldest of these layout methods is multicol — when you specify a `column-count`, this indicates how many columns you want your content to be split into. The browser then works out the size of these, a size that will change  according to the screen size.

```
.container {
  column-count: 3;
}
```

If you instead specify a `column-width`, you are specifying a *minimum* width. The browser will create as many columns of that width as will  comfortably fit into the container, then share out the remaining space  between all the columns. Therefore the number of columns will change  according to how much space there is.

```
.container {
  column-width: 10em;
}
```

### [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#flexbox)

In Flexbox, flex items will shrink and distribute space between the items  according to the space in their container, as their initial behavior. By changing the values for `flex-grow` and `flex-shrink` you can indicate how you want the items to behave when they encounter more or less space around them.

In the example below the flex items will each take an equal amount of space in the flex container, using the shorthand of `flex: 1` as described in the layout topic [Flexbox: Flexible sizing of flex items](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox#flexible_sizing_of_flex_items).

```
.container {
  display: flex;
}

.item {
  flex: 1;
}
```

**Note:** As an example, we have rebuilt the simple  responsive layout above, this time using flexbox. You can see how we no  longer need to use strange percentage values to calculate the size of  the columns: [example](https://mdn.github.io/css-examples/learn/rwd/flex-based-rwd.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/flex-based-rwd.html).

### [CSS grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#css_grid)

In CSS Grid Layout the `fr` unit allows the distribution of available space across grid tracks. The next example creates a grid container with three tracks sized at `1fr`. This will create three column tracks, each taking one part of the  available space in the container. You can find out more about this  approach to create a grid in the Learn Layout Grids topic, under [Flexible grids with the fr unit](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids#flexible_grids_with_the_fr_unit).

```
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

**Note:** The grid layout version is even simpler as we can define the columns on the .wrapper: [example](https://mdn.github.io/css-examples/learn/rwd/grid-based-rwd.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/grid-based-rwd.html).

## [Responsive images](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#responsive_images)

The simplest approach to responsive images was as described in Marcotte's  early articles on responsive design. Basically, you would take an image  that was at the largest size that might be needed, and scale it down.  This is still an approach used today, and in most stylesheets, you will  find the following CSS somewhere:

```
img {
  max-width: 100%;
}
```

There are obvious downsides to this  approach. The image might be displayed a lot smaller than its intrinsic  size, which is a waste of bandwidth — a mobile user may be downloading  an image several times the size of what they actually see in the browser window. In addition, you may not want the same image aspect ratio on  mobile as on desktop. For example, it might be nice to have a square  image for mobile, but show the same scene as a landscape image on  desktop. Or, acknowledging the smaller size of an image on mobile you  might want to show a different image altogether, one which is more  easily understood at a small screen size. These things can't be achieved by scaling down an image.

Responsive Images, using the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture) element and the [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) `srcset` and `sizes` attributes solve both of these problems. You can provide multiple sizes along with "hints" (meta data that describes the screen size and  resolution the image is best suited for), and the browser will choose  the most appropriate image for each device, ensuring that a user will  download an image size appropriate for the device they are using.

You can also *art direct* images used at different sizes, thus providing a different crop or completely different image to different screen sizes.

You can find a detailed [guide to Responsive Images in the Learn HTML section](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images) here on MDN.

## [Responsive typography](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#responsive_typography)

An element of responsive design not covered in earlier work was the idea  of responsive typography. Essentially, this describes changing font  sizes within media queries to reflect lesser or greater amounts of  screen real estate.

In this example, we want to set our level 1 heading to be `4rem`, meaning it will be four times our base font size. That's a really large heading! We only want this jumbo heading on larger screen sizes,  therefore we first create a smaller heading then use media queries to  overwrite it with the larger size if we know that the user has a screen  size of at least `1200px`.

```
html {
  font-size: 1em;
}

h1 {
  font-size: 2rem;
}

@media (min-width: 1200px) {
  h1 {
    font-size: 4rem;
  }
}
```

We have edited our responsive grid  example above to also include responsive type using the method outlined. You can see how the heading switches sizes as the layout goes to the  two column version.

On mobile the heading is smaller:

  ![A stacked layout with a small heading size.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-font-mobile.png)

On desktop, however, we see the larger heading size:

  ![A two column layout with a large heading.](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design/mdn-rwd-font-desktop.png)

**Note:** See this example in action: [example](https://mdn.github.io/css-examples/learn/rwd/type-rwd.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/type-rwd.html).

As this approach to typography shows, you do not need to restrict  media queries to only changing the layout of the page. They can be used  to tweak any element to make it more usable or attractive at alternate  screen sizes.

### [Using viewport units for responsive typography](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#using_viewport_units_for_responsive_typography)

An interesting approach is to use the viewport unit `vw` to enable responsive typography. `1vw` is equal to one percent of the viewport width, meaning that if you set your font size using `vw`, it will always relate to the size of the viewport.

```
h1 {
  font-size: 6vw;
}
```

The problem with doing the above is that the user loses the ability to zoom any text set using the `vw` unit, as that text is always related to the size of the viewport. **Therefore you should never set text using viewport units alone**.

There is a solution, and it involves using [`calc()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc()). If you add the `vw` unit to a value set using a fixed size such as `em`s or `rem`s then the text will still be zoomable. Essentially, the `vw` unit adds on top of that zoomed value:

```
h1 {
  font-size: calc(1.5rem + 3vw);
}
```

This means that we only need to specify the  font size for the heading once, rather than set it up for mobile and  redefine it in the media queries. The font then gradually increases as  you increase the size of the viewport.

**Note:** See an example of this in action: [example](https://mdn.github.io/css-examples/learn/rwd/type-vw.html), [source code](https://github.com/mdn/css-examples/blob/master/learn/rwd/type-vw.html).

## [The viewport meta tag](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design#the_viewport_meta_tag)

If you look at the HTML source of a responsive page, you will usually see the following [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) tag in the `<head>` of the document.

```
<meta name="viewport" content="width=device-width,initial-scale=1">
```

This meta tag tells mobile browsers that  they should set the width of the viewport to the device width, and scale the document to 100% of its intended size, which shows the document at  the mobile-optimized size that you intended.

Why is this needed? Because mobile browsers tend to lie about their viewport width.

This meta tag exists because when the original iPhone launched and  people started to view websites on a small phone screen, most sites were not mobile optimized. The mobile browser would, therefore, set the  viewport width to 960 pixels, render the page at that width, and show  the result as a zoomed-out version of the desktop layout. Other mobile  browsers (e.g. on Google Android) did the same thing. Users could zoom  in and pan around the website to view the bits they were interested in,  but it looked bad. You will still see this today if you have the  misfortune to come across a site that does not have a responsive design.

The trouble is that your responsive design with breakpoints and media queries won't work as intended on mobile browsers. If you've got a  narrow screen layout that kicks in at 480px viewport width or less, and  the viewport is set at 960px, you'll never see your narrow screen layout on mobile. By setting `width=device-width` you are overriding Apple's default `width=960px` with the actual width of the device, so your media queries will work as intended.

**So you should \*always\* include the above line of HTML in the head of your documents.**

There are other settings you can use with the viewport meta tag, however in general the above line is what you will want to use.

- `initial-scale`: Sets the initial zoom of the page, which we set to 1.
- `height`: Sets a specific height for the viewport.
- `minimum-scale`: Sets the minimum zoom level.
- `maximum-scale`: Sets the maximum zoom level.
- `user-scalable`: Prevents zooming if set to `no`.

You should avoid using `minimum-scale`, `maximum-scale`, and in particular setting `user-scalable` to `no`. Users should be allowed to zoom as much or as little as they need to; preventing this causes accessibility problems.

**Note:** There was a CSS @ rule designed to replace the viewport meta tag — [@viewport](https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport) — however, the rule failed to gain traction and has been deprecated. @viewport should not be used.

# 媒体查询（Media Queries）

## [媒体查询基础](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#media_query_basics)

最简单的媒体查询语法如下所示：

```
@media media-type and (media-feature-rule) {
  /* CSS rules go here */
}
```

复制到剪贴板

它包括：

- 一种媒体类型，它告诉浏览器此代码用于哪种媒体（例如打印或屏幕）。
- 一个媒体表达式，它是一个规则或测试，必须通过它才能应用所包含的 CSS。
- 如果测试通过并且媒体类型正确，将应用一组 CSS 规则。

### [媒体类型](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#media_types)

您可以指定的可能的媒体类型有：

- `all`
- `print`
- `screen`
- `speech`

如果打印页面，以下媒体查询只会将正文设置为 12pt。当页面在浏览器中加载时，它将不适用。

```
@media print {
    body {
        font-size: 12pt;
    }
}
```

复制到剪贴板

**注意：**这里的媒体类型不同于所谓的[MIME 类型](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type)。

**注意：** Level 3 Media Queries 规范中定义了许多其他媒体类型；这些已被弃用，应避免使用。

**注意：**媒体类型是可选的；如果您没有在媒体查询中指明媒体类型，则媒体查询将默认为所有媒体类型。

### [媒体功能规则](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#media_feature_rules)

指定类型后，您可以使用规则定位媒体功能。

#### 宽度和高度

为了创建响应式设计（并且具有广泛的浏览器支持），我们最常检测到的功能是视口宽度，如果视口高于或低于特定宽度（或精确宽度），我们可以应用 CSS `min-width`，使用, `max-width`, 和`width`媒体功能。

这些功能用于创建响应不同屏幕尺寸的布局。例如，如果视口正好是 600 像素，要将正文颜色更改为红色，您可以使用以下媒体查询。

```
@media screen and (width: 600px) {
    body {
        color: red;
    }
}
```

复制到剪贴板

[打开这个例子](https://mdn.github.io/css-examples/learn/media-queries/width.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/width.html).

的`width`（和`height`特征可以用作范围，因此）介质与作为前缀`min-`或`max-`以指示所述给定值是最小值，或最大值。例如，如果视口小于 600 像素，要使颜色为蓝色，请使用`max-width`：

```
@media screen and (max-width: 600px) {
    body {
        color: blue;
    }
}
```

复制到剪贴板

[打开这个例子](https://mdn.github.io/css-examples/learn/media-queries/max-width.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/max-width.html).

在实践中，使用最小值或最大值对于响应式设计更有用，因此您很少会看到`width`或`height`单独使用。

您可以测试许多其他媒体功能，尽管媒体查询规范的第 4 级和第 5 级中引入的一些较新的功能对浏览器的支持有限。MDN 上记录了每个功能以及浏览器支持信息，您可以在[使用媒体查询：媒体功能中](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#media_features)找到完整列表。

#### 方向

一项受到良好支持的媒体功能是`orientation`，它允许我们测试纵向或横向模式。如果设备处于横向，要更改正文文本颜色，请使用以下媒体查询。

```
@media (orientation: landscape) {
    body {
        color: rebeccapurple;
    }
}
```

复制到剪贴板

[打开这个例子](https://mdn.github.io/css-examples/learn/media-queries/orientation.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/orientation.html).

标准桌面视图具有横向方向，在此方向上运行良好的设计在手机或平板电脑上以纵向模式查看时可能效果不佳。方向测试可以帮助您创建针对纵向模式设备优化的布局。

#### 指点设备的使用

作为第 4 级规范的一部分，`hover`引入了媒体功能。此功能意味着您可以测试用户是否能够将鼠标悬停在某个元素上，这实质上意味着他们正在使用某种指点设备；触摸屏和键盘导航不悬停。

```
@media (hover: hover) {
    body {
        color: rebeccapurple;
    }
}
```

复制到剪贴板

[打开这个例子](https://mdn.github.io/css-examples/learn/media-queries/hover.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/hover.html).

如果我们知道用户无法悬停，我们可以默认显示一些交互功能。对于可以悬停的用户，我们可能会选择在悬停链接时使他们可用。

级别 4 中还有`pointer`媒体功能。这需要三个可能的值`none`，`fine`和`coarse`。一个`fine`指针是像一个鼠标或触控板。它使用户能够精确定位一个小区域。一个`coarse`指针是在触摸屏上手指。该值`none`表示用户没有指针设备；也许他们仅使用键盘或语音命令进行导航。

使用`pointer`可以帮助您设计更好的界面，以响应用户与屏幕的交互类型。例如，如果您知道用户将设备作为触摸屏进行交互，则可以创建更大的点击区域。

## [更复杂的媒体查询](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#more_complex_media_queries)

对于所有不同的可能的媒体查询，您可能希望将它们组合起来，或者创建查询列表——其中任何一个都可以匹配。

### [媒体查询中的“和”逻辑](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#and_logic_in_media_queries)

要组合媒体功能，您可以使用`and`与我们`and`上面使用的组合媒体类型和功能大致相同的方式。例如，我们可能想要测试 a`min-width`和`orientation`。仅当视口宽度至少为 600 像素且设备处于横向模式时，正文文本才会为蓝色。

```
@media screen and (min-width: 600px) and (orientation: landscape) {
    body {
        color: blue;
    }
}
```

复制到剪贴板

[打开这个例子](https://mdn.github.io/css-examples/learn/media-queries/and.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/and.html).

### [媒体查询中的“或”逻辑](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#or_logic_in_media_queries)

如果您有一组查询，其中任何一个都可以匹配，那么您可以用逗号分隔这些查询。在下面的示例中，如果视口宽度至少为 600 像素或设备处于横向，则文本将为蓝色。如果其中任何一项为真，则查询匹配。

```
@media screen and (min-width: 600px), screen and (orientation: landscape) {
    body {
        color: blue;
    }
}
```

复制到剪贴板

[打开这个例子](https://mdn.github.io/css-examples/learn/media-queries/or.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/or.html).

### [媒体查询中的“非”逻辑](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#not_logic_in_media_queries)

您可以使用`not`运算符否定整个媒体查询。这颠倒了整个媒体查询的含义。因此，在下一个示例中，如果方向为纵向，则文本只会是蓝色的。

```
@media not all and (orientation: landscape) {
    body {
        color: blue;
    }
}
```

复制到剪贴板

[打开这个例子](https://mdn.github.io/css-examples/learn/media-queries/not.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/not.html).

## [如何选择断点](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#how_to_choose_breakpoints)

在响应式设计的早期，许多设计师会尝试针对非常特定的屏幕尺寸。发布了流行手机和平板电脑屏幕尺寸的列表，以便可以创建与这些视口完美匹配的设计。

现在有太多的设备，具有各种各样的尺寸，使之成为可能。这意味着不是针对所有设计针对特定尺寸，更好的方法是在内容开始以某种方式中断的尺寸更改设计。也许行的长度变得太长，或者盒装的侧边栏被压扁且难以阅读。这就是您想要使用媒体查询将设计更改为适合您可用空间的更好设计的点。这种方法意味着所用设备的确切尺寸无关紧要，每个范围都可以满足。引入媒体查询的点称为**断点**。

 Firefox DevTools 中的[响应式设计模式](https://developer.mozilla.org/en-US/docs/Tools/Responsive_Design_Mode)对于确定这些断点应该去哪里非常有用。通过添加媒体查询和调整设计，您可以轻松地使视口越来越小，以查看可以改进内容的位置。

![Firefox DevTools 中移动视图中布局的屏幕截图。](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries/rwd-mode.png)

## [主动学习：移动优先响应式设计](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#active_learning_mobile_first_responsive_design)

从广义上讲，您可以采用两种方法来进行响应式设计。您可以从桌面或最宽的视图开始，然后添加断点以随着视口变小移动事物，或者您可以从最小的视图开始并随着视口变大添加布局。第二种方法被描述为**移动优先**响应式设计，并且通常是最好的方法。

最小设备的视图通常是一个简单的单列内容，就像它在正常流程中出现的一样。这意味着您可能不需要为小型设备做很多布局——好好订购你的源代码，默认情况下你会有一个可读的布局。

下面的演练通过一个非常简单的布局带你了解这种方法。在生产站点中，您可能需要在媒体查询中调整更多内容，但方法是完全相同的。

### [演练：一个简单的移动优先布局](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#walkthrough_a_simple_mobile-first_layout)

我们的起点是一个 HTML 文档，其中应用了一些 CSS 来为布局的各个部分添加背景颜色。

```
* {
    box-sizing: border-box;
}

body {
    width: 90%;
    margin: 2em auto;
    font: 1em/1.3 Arial, Helvetica, sans-serif;
}

a:link,
a:visited {
    color: #333;
}

nav ul,
aside ul {
    list-style: none;
    padding: 0;
}

nav a:link,
nav a:visited {
    background-color: rgba(207, 232, 220, 0.2);
    border: 2px solid rgb(79, 185, 227);
    text-decoration: none;
    display: block;
    padding: 10px;
    color: #333;
    font-weight: bold;
}

nav a:hover {
    background-color: rgba(207, 232, 220, 0.7);
}

.related {
    background-color: rgba(79, 185, 227, 0.3);
    border: 1px solid rgb(79, 185, 227);
    padding: 10px;
}

.sidebar {
    background-color: rgba(207, 232, 220, 0.5);
    padding: 10px;
}

article {
    margin-bottom: 1em;
}
```

复制到剪贴板

我们没有对布局进行任何更改，但是文档源的排序方式使内容可读。这是重要的第一步，它确保如果内容被屏幕阅读器读出，它是可以理解的。

```
<body>
    <div class="wrapper">
      <header>
        <nav>
          <ul>
            <li><a href="">About</a></li>
            <li><a href="">Contact</a></li>
            <li><a href="">Meet the team</a></li>
            <li><a href="">Blog</a></li>
          </ul>
        </nav>
      </header>
      <main>
        <article>
          <div class="content">
            <h1>Veggies!</h1>
            <p>
              ...
            </p>
          </div>
          <aside class="related">
            <p>
              ...
            </p>
          </aside>
        </article>

        <aside class="sidebar">
          <h2>External vegetable-based links</h2>
          <ul>
            <li>
              ...
            </li>
          </ul>
        </aside>
      </main>

      <footer><p>&copy;2019</p></footer>
    </div>
  </body>
```

复制到剪贴板

这种简单的布局也适用于移动设备。如果我们在 DevTools 中查看响应式设计模式中的布局，我们可以看到它作为网站的简单移动视图工作得非常好。

[打开步骤 1](https://mdn.github.io/css-examples/learn/media-queries/step1.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/step1.html).

**如果您想继续执行此示例，请制作本地副本 [步骤1.html](https://github.com/mdn/css-examples/blob/master/learn/media-queries/step1.html) 在你的电脑。**

从这一点开始，开始将响应式设计模式视图拖得更宽，直到您可以看到线条长度变得很长，并且我们有空间让导航显示在水平线上。这是我们将添加第一个媒体查询的地方。我们将使用 em，因为这意味着如果用户增加了他们的文本大小，断点将发生在与文本大小较小的用户相似但更宽的视口处。

**将以下代码添加到 step1.html CSS 的底部。**

```
@media screen and (min-width: 40em) {
    article {
        display: grid;
        grid-template-columns: 3fr 1fr;
        column-gap: 20px;
    }

    nav ul {
        display: flex;
    }

    nav li {
        flex: 1;
    }
}
```

复制到剪贴板

这个 CSS 为我们提供了文章内部的两列布局，文章内容和相关信息在 aside 元素中。我们还使用了 flexbox 将导航放在一行中。

[打开第 2 步](https://mdn.github.io/css-examples/learn/media-queries/step2.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/step2.html).

让我们继续扩大宽度，直到我们觉得侧边栏有足够的空间来形成一个新的列。在媒体查询中，我们将主要元素变成两列网格。然后我们需要删除[`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom)文章上的 以使两个侧边栏彼此对齐，我们将[`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border)在页脚的顶部添加一个。通常，这些小的调整是为了使设计在每个断点处看起来都很好。

**再次，将以下代码添加到 step1.html CSS 的底部。**

```
@media screen and (min-width: 70em) {
    main {
        display: grid;
        grid-template-columns: 3fr 1fr;
        column-gap: 20px;
    }

    article {
        margin-bottom: 0;
    }

    footer {
        border-top: 1px solid #ccc;
        margin-top: 2em;
    }
}
```

复制到剪贴板

[打开第 3 步](https://mdn.github.io/css-examples/learn/media-queries/step3.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/step3.html).

如果您查看不同宽度的最终示例，您可以看到设计如何响应并作为单列、两列或三列工作，具体取决于可用宽度。这是一个非常简单的移动优先响应式设计示例。

## [视口元标记](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#the_viewport_meta_tag)

如果您查看上面示例中的 HTML 源代码，您将看到文档头部包含以下元素：

```
<meta name="viewport" content="width=device-width,initial-scale=1">
```

复制到剪贴板

这是[视口元标记](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)——它作为一种控制移动浏览器如何呈现内容的方式存在。这是必需的，因为默认情况下，大多数移动浏览器都会对其视口宽度撒谎。在窄视口中渲染时，无响应的网站通常看起来很糟糕，因此移动浏览器通常会默认以比实际设备宽度更宽的视口宽度（通常为 960 像素）渲染网站，然后缩小渲染结果以使其适合在显示器中。

这一切都很好，但这意味着响应式网站不会按预期工作。如果视口宽度报告为 960 像素，则移动布局（例如使用 的媒体查询创建`@media screen and (max-width: 600px) { ... }`）将不会按预期呈现。

为了解决这个问题，在你的页面上包含一个像上面那样的视口元标记告诉浏览器“不要用 960 像素的视口呈现内容——而是使用真实的设备宽度来呈现它，并设置一个默认的初始缩放级别以获得更好的效果一致性。” 然后媒体查询将按预期启动。

您可以将许多其他选项放入`content`视口元标记的属性中 - 请参阅[使用视口元标记来控制移动浏览器上的布局以](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag)获取更多详细信息。

## [您真的需要媒体查询吗？](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries#do_you_really_need_a_media_query)

Flexbox、Grid 和多列布局都为您提供了无需媒体查询即可创建灵活甚至响应式组件的方法。总是值得考虑这些布局方法是否可以在不添加媒体查询的情况下实现您想要的。例如，您可能需要一组宽度至少为 200 像素的卡片，并且这 200 像素中的数量要适合主要文章。这可以通过网格布局来实现，完全不使用媒体查询。

这可以使用以下方法实现：

```
<ul class="grid">
    <li>
        <h2>Card 1</h2>
        <p>...</p>
    </li>
    <li>
        <h2>Card 2</h2>
        <p>...</p>
    </li>
    <li>
        <h2>Card 3</h2>
        <p>...</p>
    </li>
    <li>
        <h2>Card 4</h2>
        <p>...</p>
    </li>
    <li>
        <h2>Card 5</h2>
        <p>...</p>
    </li>
</ul>
```

复制到剪贴板

```
.grid {
    list-style: none;
    margin: 0;
    padding: 0;
    display: grid;
    gap: 20px;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
}

.grid li {
    border: 1px solid #666;
    padding: 10px;
}
```

复制到剪贴板

[打开网格布局示例](https://mdn.github.io/css-examples/learn/media-queries/grid.html) 在浏览器中，或 [查看来源](https://github.com/mdn/css-examples/blob/master/learn/media-queries/grid.html).

在浏览器中打开示例后，使屏幕变宽和变窄以查看列轨道数量的变化。这种方法的好处是网格不查看视口宽度，而是查看它对该组件可用的宽度。用您可能根本不需要媒体查询的建议来结束有关媒体查询的部分似乎很奇怪！但是，在实践中，您会发现充分利用现代布局方法，并通过媒体查询进行增强，将获得最佳结果。

# 传统布局方法

## [CSS Grid Layout 之前的布局和网格系统](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#layout_and_grid_systems_before_css_grid_layout)

对于具有设计背景的任何人来说，CSS 直到最近才具有内置网格系统，这似乎令人惊讶，相反，我们似乎正在使用各种次优方法来创建类似网格的设计。我们现在将这些称为“遗留”方法。

对于新项目，在大多数情况下，CSS 网格布局将与一种或多种其他现代布局方法结合使用，以形成任何布局的基础。然而，您会不时遇到使用这些传统方法的“网格系统”。了解它们的工作原理以及为什么它们与 CSS 网格布局不同是值得的。

本课将解释基于浮动和弹性盒的网格系统和网格框架是如何工作的。学习了网格布局后，您可能会惊讶于这一切看起来多么复杂！如果您需要为不支持较新方法的浏览器创建回退代码，除了允许您处理使用这些类型系统的现有项目之外，这些知识将对您有所帮助。

值得记住的是，当我们探索这些系统时，它们实际上都没有像 CSS Grid Layout 创建网格那样创建网格。它们的工作方式是给项目一个大小，然后推动它们以*看起来*像网格的方式排列它们。

## [两列布局](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#a_two_column_layout)

让我们从最简单的示例开始——两列布局。您可以`index.html`在计算机上创建一个新文件，并在其中填充[简单的 HTML 模板](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/getting-started/index.html), 并将以下代码插入其中的适当位置。在该部分的底部，您可以看到最终代码应该是什么样子的现场示例。

首先，我们需要一些内容放入我们的专栏。用以下内容替换当前体内的任何内容：

```
<h1>2 column layout example</h1>
<div>
  <h2>First column</h2>
  <p> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla luctus aliquam dolor, eu lacinia lorem placerat vulputate. Duis felis orci, pulvinar id metus ut, rutrum luctus orci. Cras porttitor imperdiet nunc, at ultricies tellus laoreet sit amet. Sed auctor cursus massa at porta. Integer ligula ipsum, tristique sit amet orci vel, viverra egestas ligula. Curabitur vehicula tellus neque, ac ornare ex malesuada et. In vitae convallis lacus. Aliquam erat volutpat. Suspendisse ac imperdiet turpis. Aenean finibus sollicitudin eros pharetra congue. Duis ornare egestas augue ut luctus. Proin blandit quam nec lacus varius commodo et a urna. Ut id ornare felis, eget fermentum sapien.</p>
</div>

<div>
  <h2>Second column</h2>
  <p>Nam vulputate diam nec tempor bibendum. Donec luctus augue eget malesuada ultrices. Phasellus turpis est, posuere sit amet dapibus ut, facilisis sed est. Nam id risus quis ante semper consectetur eget aliquam lorem. Vivamus tristique elit dolor, sed pretium metus suscipit vel. Mauris ultricies lectus sed lobortis finibus. Vivamus eu urna eget velit cursus viverra quis vestibulum sem. Aliquam tincidunt eget purus in interdum. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
</div>
```

复制到剪贴板

每一列都需要一个外部元素来包含其内容，并让我们一次操作所有内容。在此示例中，我们选择了[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s，但您可以选择更符合语义[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)的内容，例如s、 [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)s 和 [``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)，或其他任何内容。

现在是 CSS。首先，将以下内容应用到您的 HTML 以提供一些基本设置：

```
body {
  width: 90%;
  max-width: 900px;
  margin: 0 auto;
}
```

复制到剪贴板

身体将是视口的 90% 宽，直到它达到 900 像素宽，在这种情况下，它会保持固定在这个宽度并在视口中居中。默认情况下，它的子元素（the[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)和两个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s）将跨越 body 宽度的 100%。如果我们希望两个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)s 并排浮动，我们需要将它们的宽度设置为其父元素宽度的 100% 或更小，以便它们可以并排放置。将以下内容添加到 CSS 的底部：

```
div:nth-of-type(1) {
  width: 48%;
}

div:nth-of-type(2) {
  width: 48%;
}
```

复制到剪贴板

在这里，我们将两者都设置为父级宽度的 48% — 总计 96%，让我们有 4% 的时间可以作为两列之间的排水沟，给内容一些喘息的空间。现在我们只需要浮动列，如下所示：

```
div:nth-of-type(1) {
  width: 48%;
  float: left;
}

div:nth-of-type(2) {
  width: 48%;
  float: right;
}
```

复制到剪贴板

把这一切放在一起应该会给我们这样的结果：

<iframe class="sample-code-frame" title="两列布局示例" id="frame_A_two_column_layout" width="100%" height="520" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods/_sample_.A_two_column_layout.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

您会在此处注意到，我们对所有宽度都使用了百分比——这是一个很好的策略，因为它创建了一种**流动布局**，可以根据不同的屏幕尺寸进行调整，并在较小的屏幕尺寸下保持列宽的相同比例。尝试调整浏览器窗口的宽度以亲自查看。这是响应式网页设计的宝贵工具。

**注意：**你可以看到这个例子在运行[0_two-column-layout.html](https://mdn.github.io/learning-area/css/css-layout/floats/0_two-column-layout.html) （也可以看看 [源代码](https://github.com/mdn/learning-area/blob/master/css/css-layout/floats/0_two-column-layout.html)）。

## [创建简单的遗留网格框架](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#creating_simple_legacy_grid_frameworks)

大多数遗留框架使用[`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float)属性的行为将一列浮动到另一列旁边，以创建看起来像网格的东西。通过创建带有浮点数的网格的过程向您展示了它是如何工作的，并且还介绍了一些更高级的概念，以建立在您在[浮点数和清除](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Floats)课程中学到的东西的基础上。

最容易创建的网格框架类型是固定宽度的——我们只需要计算出我们希望我们的设计有多少总宽度，我们想要多少列，以及装订线和列应该有多宽。如果我们决定将我们的设计布置在一个网格上，其中列根据浏览器宽度增长和缩小，我们需要计算列和它们之间的间距的百分比宽度。

在接下来的部分中，我们将看看如何创建两者。我们将创建一个 12 列网格——这是一个非常常见的选择，鉴于 12 可以被 6、4、3 和 2 整除，因此它被认为非常适合不同的情况。

### [一个简单的固定宽度网格](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#a_simple_fixed_width_grid)

让我们首先创建一个使用固定宽度列的网格系统。

首先制作我们样本的本地副本 [简单的grid.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/simple-grid.html) 文件，其正文中包含以下标记。

```
<div class="wrapper">
  <div class="row">
    <div class="col">1</div>
    <div class="col">2</div>
    <div class="col">3</div>
    <div class="col">4</div>
    <div class="col">5</div>
    <div class="col">6</div>
    <div class="col">7</div>
    <div class="col">8</div>
    <div class="col">9</div>
    <div class="col">10</div>
    <div class="col">11</div>
    <div class="col">12</div>
  </div>
  <div class="row">
    <div class="col span1">13</div>
    <div class="col span6">14</div>
    <div class="col span3">15</div>
    <div class="col span2">16</div>
  </div>
</div>
```

复制到剪贴板

目的是将其变成一个在 12 列网格上的两行演示网格——顶行展示各个列的大小，第二行展示网格上一些不同大小的区域。

![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods/simple-grid-finished.png)

在该[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)元素中，添加以下代码，这使包装容器的宽度为 980 像素，右侧的填充为 20 像素。这为我们的总列/装订线宽度留下了 960 像素——在这种情况下，从总内容宽度中减去了内边距，因为我们在网站上的所有元素上都设置[`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)了`border-box`。（请参阅[完全更改框模型](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model#changing_the_box_model_completely)以获取更多解释）。

```
* {
  box-sizing: border-box;
}

body {
  width: 980px;
  margin: 0 auto;
}

.wrapper {
  padding-right: 20px;
}
```

复制到剪贴板

现在使用环绕网格每一行的行容器从另一行清除一行。在之前的规则下方添加以下规则：

```
.row {
  clear: both;
}
```

复制到剪贴板

应用此清除意味着我们不需要用构成完整十二列的元素完全填充每一行。行将保持分开，不会相互干扰。

列之间的间距为 20 像素宽。我们将这些装订线创建为每列左侧的边距 - 包括第一列，以平衡容器右侧的 20 像素内边距。所以我们总共有 12 个排水沟——12 x 20 = 240。

我们需要从 960 像素的总宽度中减去它，为我们的列提供 720 像素。如果我们现在将其除以 12，我们知道每列应该是 60 像素宽。

我们的下一步是为 class 创建一个规则，将`.col`其向左浮动，使其 a[`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)为 20 像素以形成装订线，a[`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)为 60 像素。将以下规则添加到 CSS 的底部：

```
.col {
  float: left;
  margin-left: 20px;
  width: 60px;
  background: rgb(255, 150, 150);
}
```

复制到剪贴板

单列的顶行现在将整齐地布置为网格。

**注意：**我们还为每一列指定了浅红色，这样您就可以准确地看到每一列占用了多少空间。

我们想要跨越多列的布局容器需要被赋予特殊的类，以将它们的[`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)值调整为所需的列数（加上它们之间的间距）。我们需要创建一个额外的类来允许容器跨越 2 到 12 列。每个宽度都是该列数的列宽加上装订线宽度的结果，装订线宽度总是比列数少一。

在 CSS 底部添加以下内容：

```
/* Two column widths (120px) plus one gutter width (20px) */
.col.span2 { width: 140px; }
/* Three column widths (180px) plus two gutter widths (40px) */
.col.span3 { width: 220px; }
/* And so on... */
.col.span4 { width: 300px; }
.col.span5 { width: 380px; }
.col.span6 { width: 460px; }
.col.span7 { width: 540px; }
.col.span8 { width: 620px; }
.col.span9 { width: 700px; }
.col.span10 { width: 780px; }
.col.span11 { width: 860px; }
.col.span12 { width: 940px; }
```

复制到剪贴板

创建这些类后，我们现在可以在网格上布置不同宽度的列。尝试在浏览器中保存和加载页面以查看效果。

**注意：**如果您在使用上述示例时遇到问题，请尝试将其与我们的[完成版](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/simple-grid-finished.html) 在 GitHub ([现场直播](https://mdn.github.io/learning-area/css/css-layout/grids/simple-grid-finished.html) 还）。

尝试修改元素上的类，甚至添加和删除一些容器，看看如何改变布局。例如，您可以使第二行看起来像这样：

```
<div class="row">
  <div class="col span8">13</div>
  <div class="col span4">14</div>
</div>
```

复制到剪贴板

现在您已经有了一个可以工作的网格系统，您可以定义每行的行数和列数，然后用您需要的内容填充每个容器。伟大的！

### [创建流体网格](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#creating_a_fluid_grid)

我们的网格工作得很好，但它有一个固定的宽度。我们真的想要一个灵活的（流动的）网格，它会随着浏览器[视口中](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)的可用空间而增长和缩小。为了实现这一点，我们可以将参考像素宽度转换为百分比。

将固定宽度转换为基于百分比的灵活宽度的等式如下。

```
target / context = result
```

对于我们的列宽，我们的**目标宽度**是 60 像素，我们的**上下文**是 960 像素的包装器。我们可以使用以下方法来计算百分比。

```
60 / 960 = 0.0625
```

然后我们将小数点移动 2 位，得到 6.25% 的百分比。所以，在我们的 CSS 中，我们可以用 6.25% 替换 60 像素的列宽。

我们需要对我们的装订线宽度做同样的事情：

```
20 / 960 = 0.02083333333
```

因此，我们需要更换20像素[`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)上我们的`.col`规则和20像素[`padding-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding-right)上`.wrapper`与2.08333333％。

#### 更新我们的网格

要开始本部分，请制作您之前示例页面的新副本，或制作我们的本地副本 [简单网格完成.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/simple-grid-finished.html) 用作起点的代码。

更新第二个 CSS 规则（使用`.wrapper`选择器），如下所示：

```
body {
  width: 90%;
  max-width: 980px;
  margin: 0 auto;
}

.wrapper {
  padding-right: 2.08333333%;
}
```

复制到剪贴板

我们不仅给了它一个百分比[`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)，我们还添加了一个[`max-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width)属性来阻止布局变得太宽。

接下来，更新第四条 CSS 规则（使用`.col`选择器），如下所示：

```
.col {
  float: left;
  margin-left: 2.08333333%;
  width: 6.25%;
  background: rgb(255, 150, 150);
}
```

复制到剪贴板

现在是稍微费力的部分——我们需要更新所有`.col.span`规则以使用百分比而不是像素宽度。使用计算器需要一些时间；为了节省您的精力，我们在下面为您完成了。

使用以下内容更新 CSS 规则的底部块：

```
/* Two column widths (12.5%) plus one gutter width (2.08333333%) */
.col.span2 { width: 14.58333333%; }
/* Three column widths (18.75%) plus two gutter widths (4.1666666) */
.col.span3 { width: 22.91666666%; }
/* And so on... */
.col.span4 { width: 31.24999999%; }
.col.span5 { width: 39.58333332%; }
.col.span6 { width: 47.91666665%; }
.col.span7 { width: 56.24999998%; }
.col.span8 { width: 64.58333331%; }
.col.span9 { width: 72.91666664%; }
.col.span10 { width: 81.24999997%; }
.col.span11 { width: 89.5833333%; }
.col.span12 { width: 97.91666663%; }
```

复制到剪贴板

现在保存你的代码，在浏览器中加载它，然后尝试改变视口宽度——你应该看到列宽很好地适应了。

**注意：**如果您在使用上述示例时遇到问题，请尝试将其与我们的[GitHub 上的完成版本](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/fluid-grid.html) ([现场直播](https://mdn.github.io/learning-area/css/css-layout/grids/fluid-grid.html) 还）。

### [使用 calc() 函数更容易计算](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#easier_calculations_using_the_calc_function)

您可以使用该[`calc()`](https://developer.mozilla.org/en-US/docs/Web/CSS/calc())函数直接在 CSS 中进行数学运算——这允许您将简单的数学方程插入到 CSS 值中，以计算一个值应该是什么。当需要完成复杂的数学运算时，它特别有用，您甚至可以计算使用不同单位的计算，例如“我希望此元素的高度始终为其父元素高度的 100%，减去 50px”。请参阅[MediaRecorder API 教程中的此示例](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API/Using_the_MediaStream_Recording_API#keeping_the_interface_constrained_to_the_viewport_regardless_of_device_height_with_calc())。

无论如何，回到我们的网格！跨越我们网格的一列以上的任何列的总宽度为 6.25% 乘以跨越的列数加上 2.08333333% 乘以间距数（总是列数减 1）。该`calc()`函数允许我们在宽度值内部进行计算，因此对于跨越 4 列的任何项目，我们都可以这样做，例如：

```
.col.span4 {
  width: calc((6.25%*4) + (2.08333333%*3));
}
```

复制到剪贴板

尝试用以下内容替换底部的规则块，然后在浏览器中重新加载它以查看是否得到相同的结果：

```
.col.span2 { width: calc((6.25%*2) + 2.08333333%); }
.col.span3 { width: calc((6.25%*3) + (2.08333333%*2)); }
.col.span4 { width: calc((6.25%*4) + (2.08333333%*3)); }
.col.span5 { width: calc((6.25%*5) + (2.08333333%*4)); }
.col.span6 { width: calc((6.25%*6) + (2.08333333%*5)); }
.col.span7 { width: calc((6.25%*7) + (2.08333333%*6)); }
.col.span8 { width: calc((6.25%*8) + (2.08333333%*7)); }
.col.span9 { width: calc((6.25%*9) + (2.08333333%*8)); }
.col.span10 { width: calc((6.25%*10) + (2.08333333%*9)); }
.col.span11 { width: calc((6.25%*11) + (2.08333333%*10)); }
.col.span12 { width: calc((6.25%*12) + (2.08333333%*11)); }
```

复制到剪贴板

**注意：**您可以在[流体网格calc.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/fluid-grid-calc.html) （还 [现场观看](https://mdn.github.io/learning-area/css/css-layout/grids/fluid-grid-calc.html)）。

**注意：**如果你不能让它工作，那可能是因为你的浏览器不支持该`calc()`功能，尽管它在浏览器中得到了很好的支持 - 早在 IE9。

### [语义与“非语义”网格系统](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#semantic_versus_“unsemantic”_grid_systems)

将类添加到您的标记以定义布局意味着您的内容和标记将与您的视觉呈现相关联。有时您会听到这种 CSS 类的使用被描述为“非语义”——描述内容的外观——而不是描述内容的类的语义使用。这与我们的情况下`span2`，`span3`等类。

这些不是唯一的方法。您可以改为决定您的网格，然后将大小信息添加到现有语义类的规则中。例如，如果你有一个[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)类`content`，你想跨越 8 列，你可以从`span8`类的宽度复制，给你一个这样的规则：

```
.content {
  width: calc((6.25%*8) + (2.08333333%*7));
}
```

复制到剪贴板

**注意：**如果您要使用预处理器，例如[萨斯](https://sass-lang.com/)，您可以创建一个简单的 mixin 来为您插入该值。

### [在我们的网格中启用偏移容器](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#enabling_offset_containers_in_our_grid)

只要我们想要启动与网格左侧齐平的所有容器，我们创建的网格就可以很好地工作。如果我们想在第一个容器之前——或容器之间——留下一个空的列空间，我们需要创建一个偏移类来为我们的站点添加一个左边距，以便在视觉上将其推过网格。更多数学！

让我们试试这个。

从您之前的代码开始，或使用我们的 [流体网格.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/fluid-grid.html) 文件作为起点。

让我们在 CSS 中创建一个类，它将容器元素偏移一列宽度。将以下内容添加到 CSS 的底部：

```
.offset-by-one {
  margin-left: calc(6.25% + (2.08333333%*2));
}
```

复制到剪贴板

或者，如果您更喜欢自己计算百分比，请使用以下方法：

```
.offset-by-one {
  margin-left: 10.41666666%;
}
```

复制到剪贴板

您现在可以将此类添加到任何要在其左侧留下一列宽的空白空间的容器。例如，如果你的 HTML 中有这个：

```
<div class="col span6">14</div>
```

复制到剪贴板

尝试将其替换为

```
<div class="col span5 offset-by-one">14</div>
```

复制到剪贴板

**注意：**请注意，您需要减少跨越的列数，以便为偏移腾出空间！

尝试加载和刷新以查看差异，或查看我们的 [流体网格偏移量.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/fluid-grid-offset.html) 例子（见 [直播](https://mdn.github.io/learning-area/css/css-layout/grids/fluid-grid-offset.html)还）。完成的示例应如下所示：

![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods/offset-grid-finished.png)

**注意：**作为一个额外的练习，你能实现一个`offset-by-two`类吗？

### [浮动网格限制](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#floated_grid_limitations)

使用这样的系统时，您确实需要注意您的总宽度是否正确累加，并且行中不包含跨越多列的元素，而不是该行可以包含的列数。由于浮动的工作方式，如果网格列的数量对于网格来说太宽了，最后的元素将下降到下一行，破坏网格。

还要记住，如果元素的内容比它们占据的行宽，它会溢出并看起来一团糟。

这个系统的最大限制是它本质上是一维的。我们正在处理列，并跨越列而不是行跨越元素。使用这些较旧的布局方法很难在不明确设置高度的情况下控制元素的高度，而且这也是一种非常不灵活的方法——它只有在您可以保证您的内容为特定高度时才有效。

## [弹性盒网格？](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#flexbox_grids)

如果您阅读了我们之前关于[flexbox 的](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)文章，您可能会认为 flexbox 是创建网格系统的理想解决方案。有许多基于 flexbox 的网格系统可用，flexbox 可以解决我们在上面创建网格时已经发现的许多问题。

然而，flexbox 从来没有被设计成一个网格系统，当它作为一个网格系统使用时会带来一系列新的挑战。作为一个简单的例子，我们可以把我们上面使用同样的例子标记和使用以下CSS来风格`wrapper`，`row`和`col`类：

```
body {
  width: 90%;
  max-width: 980px;
  margin: 0 auto;
}

.wrapper {
  padding-right: 2.08333333%;
}

.row {
  display: flex;
}

.col {
  margin-left: 2.08333333%;
  margin-bottom: 1em;
  width: 6.25%;
  flex: 1 1 auto;
  background: rgb(255,150,150);
}
```

复制到剪贴板

您可以尝试在您自己的示例中进行这些替换，或者查看我们的 [flexbox-grid.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/flexbox-grid.html) 示例代码（见 [直播](https://mdn.github.io/learning-area/css/css-layout/grids/flexbox-grid.html) 还）。

在这里，我们将每一行变成了一个 flex 容器。对于基于 flexbox 的网格，我们仍然需要行以允许我们拥有加起来小于 100% 的元素。我们将该容器设置为`display: flex`.

在`.col`我们设定的[`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)属性的第一个值（[`flex-grow`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow)）1，因此我们的项目可以增长，第二个值（[`flex-shrink`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink)），以1这样的项目可以缩小，第三个值（[`flex-basis`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis)）来`auto`。由于我们的元素有一个[`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width)集合，`auto`将使用该宽度作为`flex-basis`值。

在最上面一行，我们在网格上得到了 12 个整齐的盒子，它们随着我们改变视口宽度而均匀地增长和收缩。然而，在下一行，我们只有四个项目，而且这些项目也在 60 像素的基础上增长和缩小。仅使用其中的四个，它们就可以比上面一行中的项目增长得更多，结果是它们在第二行中都占据相同的宽度。

![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods/flexbox-grid-incomplete.png)

为了解决这个问题，我们仍然需要包含我们的`span`类来提供一个宽度来替换该`flex-basis`元素使用的值。

他们也不尊重上述项目使用的网格，因为他们对此一无所知。

Flexbox在设计上是**一维**的。它处理单个维度，即行或列的维度。我们不能为列和行创建严格的网格，这意味着如果我们要为我们的网格使用 flexbox，我们仍然需要像浮动布局一样计算百分比。

在您的项目中，由于 flexbox 在浮动上提供了额外的对齐和空间分布功能，您可能仍然选择使用 flexbox 'grid'。但是，您应该注意，您仍在使用工具用于其设计用途之外的其他用途。所以你可能会觉得它让你跳过额外的箍以获得你想要的最终结果。

## [第三方网格系统](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#third_party_grid_systems)

现在我们了解了网格计算背后的数学原理，现在我们可以看看一些常用的第三方网格系统了。如果您在 Web 上搜索“CSS 网格框架”，您会找到大量可供选择的选项。流行的框架，例如[引导程序](https://getbootstrap.com/) 和 [基础](https://foundation.zurb.com/)包括网格系统。还有独立的网格系统，要么使用 CSS 开发，要么使用预处理器。

让我们看一看这些独立系统之一，因为它展示了使用网格框架的常用技术。我们将使用的网格是 Skeleton（一个简单的 CSS 框架）的一部分。

要开始访问 [骷髅网站](http://getskeleton.com/)，然后选择“下载”以下载 ZIP 文件。解压缩并将 skeleton.css 和 normalize.css 文件复制到新目录中。

复制我们的 [html-骨架.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/html-skeleton.html) 文件并将其保存在与骨架相同的目录中并规范化 CSS。

通过在其头部添加以下内容，在 HTML 页面中包含骨架和规范化 CSS：

```
<link href="normalize.css" rel="stylesheet">
<link href="skeleton.css" rel="stylesheet">
```

复制到剪贴板

Skeleton 不仅仅包含一个网格系统——它还包含用于排版和其他页面元素的 CSS，您可以将其用作起点。但是，我们暂时将这些保留为默认值——这是我们在这里真正感兴趣的网格。

**笔记：** [归一化](https://necolas.github.io/normalize.css/) 是一个非常有用的小 CSS 库，由 Nicolas Gallagher 编写，它会自动进行一些有用的基本布局修复，并使默认元素样式在浏览器之间更加一致。

我们将使用与前面示例类似的 HTML。将以下内容添加到您的 HTML 正文中：

```
<div class="container">
  <div class="row">
    <div class="col">1</div>
    <div class="col">2</div>
    <div class="col">3</div>
    <div class="col">4</div>
    <div class="col">5</div>
    <div class="col">6</div>
    <div class="col">7</div>
    <div class="col">8</div>
    <div class="col">9</div>
    <div class="col">10</div>
    <div class="col">11</div>
    <div class="col">12</div>
  </div>
  <div class="row">
    <div class="col">13</div>
    <div class="col">14</div>
    <div class="col">15</div>
    <div class="col">16</div>
  </div>
</div>
```

复制到剪贴板

要开始使用 Skeleton，我们需要给包装器[``](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)一个类`container`——这已经包含在我们的 HTML 中。这使内容居中，最大宽度为 960 像素。您可以看到这些框现在的宽度永远不会超过 960 像素。

您可以在 skeleton.css 文件中查看我们应用此类时使用的 CSS。在`<div>`使用中心`auto`左，右边界，并且20个像素的施加填充左和右。Skeleton 也像我们之前一样设置了[`box-sizing`](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)属性`border-box`，所以这个元素的内边距和边框将包含在总宽度中。

```
.container {
  position: relative;
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 20px;
  box-sizing: border-box;
}
```

复制到剪贴板

如果元素在一行中，则它们只能是网格的一部分，因此在我们之前的示例中，我们需要一个附加的`<div>`或其他元素，其类`row`嵌套在s`content` `<div>`和我们的实际内容容器`<div>`s 之间。我们也已经这样做了。

现在让我们布置容器盒。骨架基于 12 列网格。顶行框都需要的类`one column`使它们跨越一列。

现在添加这些，如以下代码段所示：

```
<div class="container">
  <div class="row">
    <div class="one column">1</div>
    <div class="one column">2</div>
    <div class="one column">3</div>
    /* and so on */
  </div>
</div>
```

复制到剪贴板

接下来，给第二行类上的容器解释它们应该跨越的列数，如下所示：

```
<div class="row">
  <div class="one column">13</div>
  <div class="six columns">14</div>
  <div class="three columns">15</div>
  <div class="two columns">16</div>
</div>
```

复制到剪贴板

尝试保存您的 HTML 文件并将其加载到浏览器中以查看效果。

**注意：**如果您在使用此示例时遇到问题，请尝试将其与我们的[html-骨架-finished.html](https://github.com/mdn/learning-area/blob/master/css/css-layout/grids/html-skeleton-finished.html) 文件（见 [直播](https://mdn.github.io/learning-area/css/css-layout/grids/html-skeleton-finished.html) 还）。

如果您查看 skeleton.css 文件，您会看到它是如何工作的。例如，Skeleton 定义了以下内容来为元素添加“三列”类。

```
.three.columns { width: 22%; }
```

复制到剪贴板

Skeleton（或任何其他网格框架）所做的就是设置预定义的类，您可以通过将它们添加到标记中来使用这些类。这与您自己计算这些百分比的工作完全相同。

如您所见，使用 Skeleton 时我们只需要编写很少的 CSS。当我们向标记中添加类时，它会为我们处理所有的浮动。正是这种将布局责任移交给其他事物的能力，使得使用网格系统框架成为一个引人注目的选择！然而，如今，随着 CSS Grid Layout 的出现，许多开发人员正在远离这些框架，转而使用 CSS 提供的内置原生网格。

## [概括](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods#summary)

您现在了解了各种网格系统是如何创建的，这对于处理旧站点以及理解 CSS 网格布局的原生网格与这些旧系统之间的区别非常有用。

# 支持旧浏览器

- [以前的](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods)
- [概述：CSS 布局](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout)
- [下一个](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Fundamental_Layout_Comprehension)

在本模块中，我们建议使用 Flexbox 和 Grid 作为您设计的主要布局方法。但是，您网站的访问者将使用旧版浏览器或不支持您使用的方法的浏览器。在网络上总是如此——随着新功能的开发，不同的浏览器会优先考虑不同的事情。本文解释了如何使用现代 Web 技术而不会将旧技术的用户拒之门外。

| 先决条件： | HTML 基础知识（学习 [HTML 简介](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)），以及 CSS 工作原理的想法（学习 [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)和 [样式框](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks)[简介](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps)。） |
| :--------- | ------------------------------------------------------------ |
| 客观的：   | 了解如何在可能不支持您想要使用的功能的旧浏览器上为您的布局提供支持。 |

## [您网站的浏览器环境如何？](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#what_is_the_browser_landscape_for_your_site)

每个网站的目标受众都不同。在决定采取何种方法之前，先了解使用旧浏览器访问您网站的访问者数量。如果您有要添加或替换的现有网站，这很简单，因为您可能有可用的分析，可以告诉您人们正在使用的技术。如果您没有分析或这是一个全新的网站，那么有一些网站，例如[统计计数器](https://gs.statcounter.com/) 可以提供按位置过滤的统计信息。

您还应该考虑设备类型和人们使用您网站的方式，例如，您可能期望移动设备的数量高于平均水平。应始终考虑可访问性和使用辅助技术的人员，但对于某些可能更为关键的站点。以我的经验，开发人员通常非常担心 1% 的用户在旧版本的 Internet Explorer 中的体验，而根本没有考虑到更多的具有可访问性需求的用户。

## [对您要使用的功能的支持是什么？](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#what_is_the_support_for_the_features_you_want_to_use)

一旦您知道访问您网站的浏览器，您就可以评估您想要使用的任何技术，以及它的支持程度以及为没有该技术的访问者提供替代方案的难易程度。在 MDN，我们试图通过在详细介绍 CSS 属性的每个页面上提供浏览器兼容性信息来让您轻松完成这项工作。例如，查看 的页面[`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)。此页面底部有一个表格，其中列出了主要浏览器以及它们开始支持此属性的版本。

![img](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers/browser-table.png)

另一种了解功能支持情况的流行方法是 [我可以用吗](https://caniuse.com/)网站。此站点列出了大多数 Web 平台功能以及有关其浏览器支持状态的信息。您可以按位置查看使用情况统计信息——如果您在一个用户主要来自世界特定地区的网站上工作，这将非常有用。您甚至可以关联您的 Google Analytics 帐户以根据您的用户数据进行分析。

了解您的用户拥有的技术，以及对您可能想要使用的事物的支持，使您能够做出所有决定并了解如何最好地支持所有用户。

## [支持并不意味着“看起来一样”](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#support_doesnt_mean_looks_the_same)

一个网站不可能在所有浏览器中看起来都一样，因为您的一些用户将在手机上查看网站，而其他用户则在大桌面屏幕上查看。同样，您的一些用户将使用旧版浏览器，而其他用户将使用最新浏览器。您的一些用户可能会听到屏幕阅读器向他们朗读您的内容，或者已放大页面以便能够阅读。支持所有人意味着提供一个防御性设计的内容版本，这样它在现代浏览器上看起来会很棒，但对于旧浏览器的用户来说仍然可以在基本级别使用。

基本级别的支持来自于很好地构建您的内容，以便您的页面的正常流动有意义。使用非常有限的功能手机的用户可能不会获得太多的 CSS，但内容会以一种易于阅读的方式流动。因此，结构良好的 HTML 文档应该始终是您的起点。*如果您删除样式表，您的内容是否有意义？*

一种选择是将这个网站的简单视图作为使用非常旧或有限浏览器的人的后备。如果您只有少数人使用这些浏览器访问该站点，那么花时间尝试为他们提供与使用现代浏览器的人类似的体验可能没有商业意义。最好将时间花在使网站更易于访问的事情上，从而为更多用户提供服务。在纯 HTML 页面和所有花里胡哨之间有一个中间立场，而 CSS 实际上使创建这些回退变得非常简单。

## [在 CSS 中创建回退](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#creating_fallbacks_in_css)

CSS 规范包含解释当两种布局方法应用于同一项目时浏览器会做什么的信息。这意味着如果浮动项目也是使用 CSS 网格布局的网格项目，则会发生什么情况有一个定义。将此信息与浏览器忽略它们不理解的 CSS 的知识结合起来，您就可以使用我们已经介绍过的[遗留技术](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Legacy_Layout_Methods)创建简单的布局，然后在理解它的现代浏览器中被您的 Grid 布局覆盖。

### [从网格回落到浮动](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#falling_back_from_grid_to_float)

在下面的示例中，我们浮动了三个 `<div>`s，以便它们连续显示。任何不支持[CSS 网格布局的](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids)浏览器都会将这行框视为浮动布局。成为网格项目的浮动项目失去了浮动行为，这意味着通过将包装器转换为网格容器，浮动项目将成为网格项目。如果浏览器支持网格布局，它将显示网格视图，否则它会忽略`display: grid`和相关属性并使用浮动布局。

```
* {box-sizing: border-box;}

.wrapper {
  background-color: rgb(79,185,227);
  padding: 10px;
  max-width: 400px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

.item {
  float: left;
  border-radius: 5px;
  background-color: rgb(207,232,220);
  padding: 1em;
}
```

复制到剪贴板

```
<div class="wrapper">
  <div class="item">Item One</div>
  <div class="item">Item Two</div>
  <div class="item">Item Three</div>
</div>
```

复制到剪贴板

<iframe class="sample-code-frame" title="从网格回落到浮动样本" id="frame_Falling_back_from_grid_to_float" width="100%" height="200" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers/_sample_.Falling_back_from_grid_to_float.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

**注意：**[`clear`](https://developer.mozilla.org/en-US/docs/Web/CSS/clear)一旦被清除的项变成网格项，该属性也没有任何影响，因此您可以拥有一个带有清除页脚的布局，然后将其转换为网格布局。

### [回退方法](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#fallback_methods)

有许多布局方法可以以与此浮动示例类似的方式使用。您可以选择对您需要创建的布局模式最有意义的一种。

- 漂浮和清晰

  如上所示，如果浮动或清除项目变为弹性或网格项目，则浮动和清除属性将不再影响布局。

- 显示：内联块

  此方法可用于创建列布局，如果项目已`display: inline-block`设置但随后变为 flex 或网格项目，则忽略内联块行为。

- 显示：表

  在这些课程的[介绍中](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction)描述的创建 CSS 表的方法可以用作后备。设置了 CSS 表格布局的项目如果变成 flex 或网格项目，将失去此行为。重要的是，为修复表结构而创建的匿名框并没有被创建。

- 多列布局

  对于某些布局，您可以使用[多列](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)作为后备，如果您的容器`column-*`定义了任何属性，然后成为网格容器，则多列行为将不会发生。

- Flexbox 作为 Grid 的后备

  由于 IE10 和 11 支持[Flexbox，](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)因此它比 Grid 具有比 Grid 更好的浏览器支持，尽管请查看本课后面的信息，解释旧浏览器对 Flexbox 的相当不完整和混乱的支持。如果将 flex 容器制作成网格容器，则任何`flex`应用于子项的属性都将被忽略。

对于旧浏览器中的许多布局调整，您可能会发现以这种方式使用 CSS 可以获得不错的体验。我们基于旧的和受广泛支持的技术添加了一个更简单的布局，然后使用新的 CSS 来创建超过 90% 的观众都会看到的布局。但是，在某些情况下，回退代码需要包含新浏览器也会解释的内容。一个很好的例子是，如果我们要为浮动项目添加百分比宽度，使列更像网格显示，拉伸以填充容器。

在浮动布局中，百分比是从容器计算的——33.333% 是容器宽度的三分之一。然而，在网格中，33.333% 是根据放置项目的网格区域计算的，因此一旦引入网格布局，它实际上变成了我们想要的尺寸的三分之一。

```
* {box-sizing: border-box;}

.wrapper {
  background-color: rgb(79,185,227);
  padding: 10px;
  max-width: 400px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

.item {
  float: left;
  border-radius: 5px;
  background-color: rgb(207,232,220);
  padding: 1em;
  width: 33.333%;
}
```

复制到剪贴板

```
<div class="wrapper">
  <div class="item">Item One</div>
  <div class="item">Item Two</div>
  <div class="item">Item Three</div>
</div>
```

复制到剪贴板

<iframe class="sample-code-frame" title="回退方法示例" id="frame_Fallback_methods" width="100%" height="200" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers/_sample_.Fallback_methods.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

为了解决这个问题，我们需要有一种方法来检测是否支持 Grid 以及它是否会覆盖宽度。CSS 在这里为我们提供了解决方案。

## [特征查询](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#feature_queries)

功能查询允许您测试浏览器是否支持任何特定的 CSS 功能。这意味着您可以为不支持某个功能的浏览器编写一些 CSS，然后检查浏览器是否支持，如果支持，请输入您喜欢的布局。

如果我们在上面的例子中添加一个特征查询，`auto` 如果我们知道我们有网格支持，我们可以使用它来设置我们项目的宽度。

```
* {box-sizing: border-box;}

.wrapper {
  background-color: rgb(79,185,227);
  padding: 10px;
  max-width: 400px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}

.item {
  float: left;
  border-radius: 5px;
  background-color: rgb(207,232,220);
  padding: 1em;
  width: 33.333%;
}

@supports (display: grid) {
  .item {
      width: auto;
  }
}
```

复制到剪贴板

```
<div class="wrapper">
  <div class="item">Item One</div>
  <div class="item">Item Two</div>
  <div class="item">Item Three</div>
</div>
```

复制到剪贴板

<iframe class="sample-code-frame" title="特征查询示例" id="frame_Feature_queries" width="100%" height="200" src="https://yari-demos.prod.mdn.mozit.cloud/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers/_sample_.Feature_queries.html" loading="lazy" style="box-sizing: border-box; border-width: 1px 1px 1px 6px; border-style: solid; border-color: rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 114, 179) rgb(0, 82, 130); border-image: initial; margin: 0px 0px 12px; padding: 12px; width: 1002px; max-width: 100%;"></iframe>

现代浏览器对特征查询的支持非常好。但是，您应该注意，不支持 CSS Grid 的浏览器也往往不支持功能查询。这意味着上面详述的方法将适用于这些浏览器。我们正在做的是首先编写我们的旧 CSS，在任何功能查询之外。不支持 Grid 和不支持功能查询的浏览器将使用他们可以理解的布局信息并完全忽略其他所有内容。支持特征查询的浏览器也支持 CSS Grid，因此将运行网格代码和特征查询内部的代码。

特性查询规范还包含测试浏览器是否不支持特性的能力——这只有在浏览器支持特性查询时才有用。将来，检查是否缺乏支持的方法将起作用，因为没有功能查询支持的浏览器将消失。但是，就目前而言，使用旧 CSS 的方法，然后覆盖它，以获得最佳支持。

## [旧版本的 Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#older_versions_of_flexbox)

在旧版本的浏览器中，您可以找到 Flexbox 规范的先前迭代。在撰写本文时，这主要是 Internet Explorer 10 的问题，它使用`-ms-` Flexbox 前缀。这也意味着存在一些过时的文章和教程；[这个有用的指南](https://css-tricks.com/old-flexbox-and-new-flexbox/) 帮助您检查您正在查看的内容，如果您在非常旧的浏览器中需要 flex 支持，也可以提供帮助。

## [带有 IE10 和 11 前缀的 Grid 版本](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#the_ie10_and_11_prefixed_version_of_grid)

CSS Grid 规范的原型最初是在 Internet Explorer 10 中；这意味着虽然 IE10 和 IE11 没有*现代*网格支持，但它们确实有一个非常有用的网格布局版本，尽管与本网站上记录的现代规范不同。IE10 和 11 实现 `-ms-`带有前缀，这意味着您可以将它用于这些浏览器，并且它将被非 Microsoft 浏览器忽略。然而，Edge 仍然理解旧的语法，因此请注意现代网格 CSS 中的所有内容都已被安全覆盖。

[Grid Layout 中的 Progressive Enhancement](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/CSS_Grid_and_Progressive_Enhancement)指南可以帮助您了解 IE 版本的网格，我们在本课末尾提供了一些额外的有用链接。但是，除非您在较旧的 IE 版本中拥有大量访问者，否则您可能会发现最好专注于创建适用于所有不支持浏览器的回退。

## [测试旧浏览器](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#testing_older_browsers)

由于大多数浏览器都支持 Flexbox 和 Grid，因此测试旧浏览器可能相当困难。一种方法是使用在线测试工具，例如 Sauce Labs，如[跨浏览器测试](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing)模块中所述。

您还可以下载并安装虚拟机，并在您自己的计算机上的包含环境中运行旧版本的浏览器。访问旧版本的 Internet Explorer 尤其有用，为此，Microsoft 已将[一系列可供免费下载的虚拟机](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/). 这些适用于 Mac、Windows 和 Linux 操作系统，因此即使您不使用 Windows 计算机，也是在旧的和现代的 Windows 浏览器中进行测试的好方法。

## [概括](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Supporting_Older_Browsers#summary)

您现在已经掌握了自信地使用 Grid 和 Flexbox 等技术、为旧浏览器创建回退以及利用未来可能出现的任何新技术的知识。

