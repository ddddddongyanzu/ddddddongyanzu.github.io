---
Layout: post
desc: JavaScript基础
title:  JavaScript基础
tag:  study
---


## JavaScript基础

### <1> 走进JavaScript世界

#### 1.1 认识JavaScript

`JavaScript`简单来说，就是一种专为与网页交互而设计的脚本语言，这是官方的一种说法，作为初学者，我们更关注的应该是效果，即什么东西可以实现什么效果。

`JavaScript`主要由三部分组成：

1. 核心(ECMAScript)
2. 文档对象模型(DOM)
3. 浏览器对象模型(BOM)

我们可以将这三部分当作三个部门，每个部门都有自己的职责，首先我们来介绍核心(ECMAScript)。

##### 核心(ECMAScript)

`ECMAScript`规定了**这门语言的基本组成部分**，主要有以下几个部分组成：

- 语法
- 类型
- 语句
- 关键字
- 保留字
- 操作符
- 对象

在这里我们先不同去纠结这几部分到底是什么，在后面的课程中我们会逐一学习到，在这里我们只要知道它们是`JavaScript`**这门语言的基本组成部分**即可。

有了这些基本组成部分，`JavaScript`就可以完成基本的**逻辑以及数据处理**。

##### 文档对象模型(DOM)

`DOM`的功能简单来说呢就是可以获取到我们写的所有的`html`标签，并给标签添加或者删除样式，并可以给标签添加事件(例如点击、拖动等)。这些功能的实现是基于下面几种接口的：

- **DOM 遍历和范围**： 可以找到页面中所有的标签;
- **DOM 事件**： 例如给某个图片添加拖动事件，使图片可以随意拖动;
- **DOM 样式**： 可以更改页面中所有元素的样式，例如更改某一段文字的颜色。

再次重申，这一节的内容目前都是用来了解的，**不要深入研究**

##### 浏览器对象模型(BOM)

`BOM`只会处理跟浏览器相关的东西，比如：

- 弹出新窗口功能
- 移动、缩放、关闭浏览器窗口的功能
- 给用户提供显示器分辨率的功能
- 提供浏览器信息

在初学 JavaScript 的时候，我们可能只会跟前两种打交道

#### 1.2 在HTML中使用JavaScript

##### `JavaScript`的书写位置

`JavaScript`与`CSS`的书写位置非常相似，分为`HTML`内部和外部

##### `JavaScript`写在`HTML`内部

1. 使用`script`标签嵌入`JavaScript`

<script></script>标签可以将JavaScript代码嵌入到HTML内部，具体嵌入方式如下：

```js
// script标签嵌入JavaScript代码
<script>
    // JavaScript代码
    let name = "Bob";
    function(){
        console.log("我的名字叫："+name);
    }
</script>
```

> 上述代码中，`script`标签中间的代码大家不用去理解，后面我们会学到. 你或许会看到`<script type="text/javascript" charset="utf-8"></script>`这种类型的`script`标签，其实它跟`<script></script>`标签是一样的，其中`type="text/javascript"`代表> 文档类型是`javascript`类型，字符编解码方式是`utf-8`.这两个暂时都不用去理解

1. 注意`script`标签在`HTML`文件中的位置

这里我们强行规定一个位置或者说这就是一种规范，即`body`标签的内部，并保证是在末尾，如下面的代码所示：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Document</title>
  </head>
  <body>
    <!-- 正常的html标签一定要写在script标签的前面 -->
    <div></div>
    <!-- 在body标签的内部并在末尾 -->
    <script></script>
  </body>
</html>
```

> `script`标签在`HTML`文件中的位置很随意，可以说写在哪里都无所谓，但是在学习`JavaScript`的`DOM`的时候，如果不注意`script`标签的位置，会出现你意想不到的报错.

此时我们就可以在`script`标签中间书写`JavaScript`代码了.

下面我们通过代码演示来感受一下：

代码演示

##### `JavaScript`写在`HTML`外部

和`CSS`一样，在`JavaScript`中我们也是推崇代码分离的，即`JavaScript`代码写在`xxx.js`文件中，然后由引入标签去引入即可.

这里的引入标签即`script`标签，不一样的是，在标签上多了一个`src`参数，引入方式如下：

```js
<script src='index.js'></script>
```

代码演示如下：

代码演示



书写位置与内部的书写位置一致，即书写在`body`标签内，但是在末尾。

##### 1.3 JavaScript入门

##### JavaScript 注释

JavaScript 注释包括单行注释和块行注释

单行注释

单行注释以两个斜杠开头，如下所示：

```js
// 单行注释
```

**块级注释**

块级注释以一个斜杠和两个星号开头，以一个星号和一个斜杠结尾，如下所示：

```js
/*
 * 注释
 * 注释
 */
```

注释的内容少，可以用单行注释，内容多，就使用块级注释。

##### 字符串

什么事字符串呢？简单的说就是用引号印起来的就是字符串，这里的引号可以是单引号（‘’）也可以是双引号（“”）。

> 在输入引号的时候，一定要切换为英文输入法。

下面都是字符串：

```js
// 双引号
"字符串";
// 单引号
'字符串';

// 双引号
"Tom";
// 单引号
'Tom';

// 双引号
"T";
// 单引号
'T';

// 双引号，字符串
"12";
// 单引号，字符串
'1';
```

Console 访问控制台

JavaScript 与我们之前学习的`HTML/CSS`不同的是，它的输出结果不是在浏览器的页面中显示，而是在控制台中显示

`console`表示访问控制台,`log()`表示在控制台输出信息，中间用点（`.`）连接，完整的写法是：

```js
console.log("要输出的内容");
```

> 不用纠结`console.log()`是什么，因为这是浏览器内置对象，也就是浏览器自带的，我们只要记住这句话可以在控制台输出信息即可.

将输出语句写在`script`标签内，完整的写法如下：

```js
<script>console.log("Hello World");</script>
```

`JavaScript`代码写在`HTML`代码内部的写法如下：

代码演示



可以看出，在`index.js`文件中写`JavaScript`代码的时候，是不需要加`script`标签的，只有在`HTML`代码中才需要加`script`标签.

##### 模版字符串

在一般的字符串中，如果我们要将字符串和变量拼接起来，要用加号（+）去拼接，例如：

```js
let firstName = "胡";
let lastName = "雪岩";

let say = "大家好，我姓" + firstName + "，名" + lastName;

console.log(say);
```

可以看的出，这个写法非常的繁琐，模版字符串就可以简化书写，模版字符串的核心是反引号（``）和 占位符 `${expression}` ，反引号的作用是将字符串和变量包起来，占位符的作用就是在字符串中插入变量。

> 记住占位符的语法：`${变量名}`

比如上面的代码我们可以使用模版字符串来进行改造：

```js
let firstName = "胡";
let lastName = "雪岩";

let say = `大家好，我姓${firstName}，名${lastName}`;

console.log(say);
```

#### 转义符（\）

转义符在模版字符串和一般的字符串中都很常见，比如说我们要写下面这段代码：

```js
let str = "华为正式发布操作系统---"鸿蒙OS"";
console.log(str);
```

这样的写法是错误的，但是我们就想在双引号里面写双引号，怎么办呢？这里就要用到转义符（\），在前后双引号前面添加一个转义符（\），代码如下：

```js
let str = "华为正式发布操作系统---\"鸿蒙OS\"";
console.log(str);
```

这里因为文档格式化的原因，没办法写出转义符号，其实应该是这样的"华为正式发布操作系统---"鸿蒙 OS""

同样的，如果我们想要在模版字符串中使用反引号（``），也可以在模版字符串中的`前面添加一个转义符（\），如：

```js
let firstName = "胡";
let lastName = "雪岩";

let say = `大家好，我姓${firstName}，名${lastName}，喜欢\`看书\``;

console.log(say);
```

#### 多行字符串拼接

再比如我们要输出一首古诗，使用一般的字符串我们就要用到\n 来换行，代码如下：

```js
let str = "春眠不觉晓\n" + "处处闻啼鸟\n" + "夜来风雨声\n" + "花落知多少\n";
console.log(str);
```

但是使用模版字符串，只需要回车就好，代码如下：

```js
let str = `春眠不觉晓
处处闻啼鸟
夜来风雨声
花落知多少`;

console.log(str);
```

#### 在字符串中使用表达式

在以前我们要在一个字符串中使用表达式，我们要去拼接这个表达式，具体做法如下：

```js
let number1 = 20;
let number2 = 10;
console.log(
  "两个数的和是：" +
    (number1 + number2) +
    "\n两个数的差是：" +
    (number1 - number2) +
    "。"
);
```

同样，这种做法就很繁琐，首先加号和引号太多了，输入成本太高，这时候我们就可以充分利用占位符（${expression}）来做点文章，改写如下：

```js
let number1 = 20;
let number2 = 10;
console.log(`两个数的和是：${number1 + number2} 
两个数的差是：${number1 - number2} 。`);
```

#### 模版字符串中使用三元表达式

这里我们就不去管字符串拼接的表达式了，直接使用模版字符串来写三元表达式，先写一个最简单的:

```js
let str = `这里是${false ? "浙江" : "江苏"}`;

console.log(str); // 江苏
```

很容易可以看的出，输出结果是江苏，那么我们做更深一步的书写，加大难度：

```js
let str = `这里是${true ? "江苏" : "浙江"}-${true ? "南京" : "常州"}`;

console.log(str); // 这里是江苏-南京
```

#### 使用场景一

熟练了这种应用以后呢，我们要结合实际工作来做点文章，给个场景吧，大家知道，一个 class 后面是可以跟多个类名的，类名不同，样式不同，比如说 class = "base hover"，

当然我们这个场景不会这么简单，我们的场景是根据屏幕的宽度来动态的改样式，这里就可以用模版字符串：

```js
// 定义屏幕的宽度，当然这个宽度是根据window的api去获取的
let screen = 760;

// 判断屏幕是大屏还是小屏，这里我们认为大于760px的就是大屏
function isLargeScreen() {
  return screen > 800;
}

// 定义元素的排列方式，大屏row排列，小屏column排列
// 具体什么排列方式，是根据屏幕大小决定的
let item = {
  isCollapsed: screen > 800
};

// 这里我们就要根据上面的信息来动态的获取类名（多个）
const classes = `header ${
  isLargeScreen() ? "" : `icon-${item.isCollapsed ? "column" : "row"}`
}`;

console.log(classes);
```

#### 使用场景二

再比如我们后面会在 js 代码中组装 HTML 代码，然后显示在屏幕中：

```js
let htmlCode = `
    <img src='' />
    ${
      true
        ? `<img src='https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1906469856,4113625838&fm=26&gp=0.jpg' />`
        : `<img src='' />`
    }
`;
console.log(htmlCode);
// <img src='' />
//    <img src='https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1906469856,4113625838&fm=26&gp=0.jpg' />
```

这里注意，html 代码作为条件成功后要输出的内容，要用反引号扩起来，会跟之前的代码有点区别，要注意一下



### <2> 基础数据类型

#### 2.1 变量

变量就是保存值的占位符，它的作用与二元一次方程的未知数x或y一样，都是用来临时保存值的。

在`JavaScript`中定义变量的关键字（编程语言中特定的单词）有两个，即`let`和`const`

##### 使用 let 定义变量

定义变量的格式如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/1/2j/%E5%8F%98%E9%87%8F%E8%A7%A3%E9%87%8A.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

- 关键字：编程语言中特定的单词

- 变量名：用于保存值的占位符
- 赋值符号：将值符给变量的符号

下面来定义一个变量并在控制台输出，核心代码如下：

```js
let name = "Will Smith";
console.log(name);
```

其实上面的代码包含了两步：

1. 定义变量
2. 给变量赋值

##### 1. 定义变量

定义一个变量名为`name`的变量：

```js
// 定义一个变量名为name的变量
let name;
```

**注意：**`let`声明变量的时候，不能重复声明同名变量，例如：

```js
let number = 20;
let number = 30;
```

上面这段代码运行的时候会报如下错误：`Uncaught SyntaxError: Identifier 'number' has already been declared`，这句话的意思是`number`这个变量已经被声明过了.

> 当然如果是在不同的作用域内声明相同变量，是可以的，暂时我们还遇不到这种情况，遇到的时候会讲

##### 2给变量赋值

```js
// 定义变量
let name;

// 给变量赋值
name = "Will Smith";
```

**注意：**

1. 在使用`console.log()`输出变量的时候，并没有加引号("").
2. 使用变量一定要在定义变量之后，例如下面这种方式会报错：

```js
// name还未定义和赋值就使用，报错
console.log(name);
let name = "Will Smith";
```

正确的写法是：

```js
// 正确输出
let name = "Will Smith";
console.log(name);
```

> 或许你们会在其它资料中看到定义变量的关键字`var`，这是一种过时的定义变量的关键字，因为它会导致很多未知的错误，所以现在已经不常用了，大家可以忽略.

##### 使用 const 定义变量

const 定义变量的方式和 let 一样，如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/1/2j/const.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

const 的用法也和 let 是一样的，在这里我们就不做过多解释，下面我们主要讨论的是 const 和 let 在定义变量的时候，有什么不同.

##### `let`和`const`异同点一：

- `let`定义的变量可以被多次重新赋值

```js
let name = "Bob";
console.log(name); // Bob

name = "Tom";
console.log(name); // Tom
```

代码演示



- `const`定义的变量只能赋值一次

```js
const name = "Bob";
console.log(name); // Bob

name = "Tom"; // 报错
console.log(name); // 不执行
```

因为代码演示会导致我们的系统卡死，所以暂不做演示

代码演示

##### `let`和`const`异同点二：

- `let`定义变量的时候，可以不赋初始值

```js
let age;
console.log(age); // undefined
```

- `const`定义变量的时候，要赋初始值，否则会报错

```js
const age; // 报错
console.log(age);  // 不执行
```

#### 2.2 数值类型

常用的数值类型主要包括整数、浮点数（你可以理解为小数）和NaN（Not a Number 非数值），当然还有其他类型的一些数值



##### 整数

`JavaScript`中的整数和数学中的整数是一样的,是正整数、零、负整数的集合,一般来说,我们所接触的整数都是十进制的,例如：

```js
let number = 8;
console.log(number); // 8
```

除了十进制还有八进制,十六进制,所谓十进制就是逢 10 进 1,八进制就是逢 8 进 1,十六进制就是逢 16 进 1,我们用几张图来简单的理解一下进制问题,下面的途中,红色方格表示进位：

- 八进制

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/2/%E5%85%AB%E8%BF%9B%E5%88%B6.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

```js
let number1 = 010; // 八进制的8
let number2 = 011; // 八进制的9
let number3 = 012; // 八进制的10
```

- 十进制

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/2/%E5%8D%81%E8%BF%9B%E5%88%B6.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

```js
let number1 = 7; // 十进制的7
let number2 = 20; // 十进制的20
```

- 十六进制

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/2/%E5%8D%81%E5%85%AD%E8%BF%9B%E5%88%B6.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

```js
let number1 = 0x010; // 十六进制的16
let number2 = 0x11; // 十六进制的17
let number3 = 0x12; // 十六进制的18
```

**注意：**在编程中我们遇到的更多的是十进制的数值，大家大可不必把时间花费在不常用的知识点上，对于其它两种进制的要求是，见到能认识即可.

##### 浮点数

浮点数值必须包含一个小数点，并且小数点后面至少有一位数字.小数点前面可以没有数字，但是不推荐这种写法.

下面是几种常见的浮点数值：

```js
let floatNumber1 = 2.0;
let floatNumber2 = 0.4;
let floatNumber3 = .2; // 正确，但是不推荐
```

除此之外还有一些极大或者极小的数值，可以用科学计数法`e`来表示，例如：

```js
let bigNumber = 9.43e7; // 等于94300000
```

上面的数值表示 9.43 乘以 10 的 7 次方.

```js
let smallNumber = 3e-7; // 等于0.0000003
```

上面的数值表示 3 乘以 10 的-7 次方.

###### 浮点数的精度丢失现象

浮点数值的最高精度是 17 位小数，但是在算数运算当中其精度远不如整数.

例如，0.1 加 0.2 的结果不是 0.3：

```js
let number1 = 0.1;
let number2 = 0.2;
console.log(number1 + number2); // 0.30000000000000004
```

因此在后面我们学习到条件判断的时候，不要使用这种判断：

```js
if (a + b == 0.3) {
  console.log('输出成功');
}
```

这段代码的意思就是如果 a+b=0.3，那么就在控制台输出“输出成功”四个字.

因为 0.1+0.2 本来的确等于 0.3，因为精度丢失成了 0.30000000000000004，所以本来应该成立的判断条件却不成立了.

##### NaN

NaN(Not a Number)即非数值.

简单来说，就是两个变量执行了一个运算，例如`+`、`-`、`*`、`/`当中的一种，返回的结果仍然是数字类型，但是执行的数学运算没有成功.例如：

```js
let a = 'number';
let b = 10;
let c = a / b;
console.log(c); // NaN
console.log(typeof c); // number
```

> 上面的代码中`typeof`是用来判断变量类型的，最后返回的结果`number`表示是数字类型

我们再回过头来看一下最开始的定义

1. 执行了一个运算,这里执行了除法运算
2. 返回的结果仍然是数字类型,可以从输出结果看,是`number`类型
3. 执行的数学运算没有成功,本案例中一个字符串除以一个数字,的确是无法进行运算的.

通过这个定义我们还可以知道其他的一些出现`NaN`的情况,如：

1. 0/0
2. 字符串乘以数字
3. `NaN`和任何数进行运算,例如

```js
let a = 'number';
let b = 10;
let c = a / b;
// 此时`c`和任何数进行运算结果都是`NaN`
```

目前我们知道这几个就足够了

#### 2.3 类型转换/字符串拼接

类型转换主要包括两种，隐式转换和强制类型转换。

##### 隐式转换

- 数字字符串加数字，数字隐式转化为字符串

```js
console.log(20+"20");
//调换位置仍可
console.log("20"+20);
```

其结果不是40，而是2020，编译器会将20隐式转换为“20”，与后面的字符串拼接

- 数字字符与数字做非加法运算，字符串隐式转换为数字

```js
console.log("20" - 10); // 10
console.log(10 * "10"); // 100
console.log(10 / "2"); // 5
```

进行减法运算的时候,'20'会默认转换为 20,然后再进行运算

代码演示



- **数字字符串与数字字符串做非加法运算,隐式转换为数字**

```js
console.log("20" - "10"); // 10
console.log("20" / "10"); // 2
console.log("20" * "10"); // 200
```

代码演示

##### 强制类型转换

强制类型转换我们需要学习两个,parseInt(将小数字符串、整数字符串或者小数转换为整数)、parseFloat(将小数字符串转换为小数).

##### parseInt

- 整数字符串转换为整数

```js
let number = "20";
//  将number转换为整数类型
let converNumber = parseInt(number);
console.log(converNumber); // 20
// 判断转换后的数据类型
console.log(typeof converNumber); // number
```

- 小数字符串转换为整数

```js
let number = "20.5";
let converNumber = parseInt(number);
console.log(converNumber); // 20  不足21一律按照20算
console.log(typeof converNumber); // number
```

- 小数转换为整数

```js
let number = 20.5;
let converNumber = parseInt(number);
console.log(converNumber); // 20
```

代码演示如下：

代码演示

##### parseFloat

将小数字符串转换为小数

```js
let number = "20.9";
let converNumber = parseFloat(number);
console.log(converNumber); // 20.9
console.log(typeof converNumber); // number
```

##### 字符串拼接

字符串拼接主要是为了有格式的在控制台输出一些信息,比如我们之前写的代码：

```js
let number = "20.9";
let converNumber = parseFloat(number);
console.log(converNumber); // 20.9
console.log(typeof converNumber); // number
```

我们更希望输出的结果是这样：

```js
转换后的结果是： 20.9
转换后的数字类型是： number 类型
```

此时我们就需要字符串拼接技术来实现.

- 字符串拼接使用的符号是`+`(加号)
- 字符串用引号引起来,单双引不做要求,但是要对应,不能是前半部分单引号,后半部分双引号,如('").
- 变量名不能用引号,如果变量名在字符串中间,可以用加号和引号区分开,例如("我的名字："+name+",谢谢").

例如上面的输出代码可以改为：

```js
console.log("转换后的结果是：" + converNumber);
console.log("转换后的数字类型是：" + typeof converNumber + "类型");
```

字符串拼接不仅仅是在`console`中使用,也可以在变量中使用,例如：

```js
let age = 20;
let name = "小李子";
let output = "我叫：" + name + ",今年" + age + "岁了";
console.log(output);
```

#### 2.4 运算符

##### 相等/全等

在编程语言里，我们会经常去做值的判断，比如判断两个值是否相同，这时候就要用到相等（=）和全等（==）运算符，这两个运算符的区别是前者只判断是否相同，后者在此基础上还要判断类型是否相同。

举个例子说明一下：

```js
let number1 = 45;
let number2 = 45;
console.log(number1 == number2); // true
```



如我们所预料的一样,45 和 45 是相等的,所以最后输出了`true`,接下来我们使用全等(===)符号来做一次判断.

```js
let number1 = 45;
let number2 = 45;
console.log(number1 === number2); // true
```

全等符号的判断结果也是`true`,这里并没有什么不同,接下来就要展示不同之处了,代码如下：

```js
let number1 = "45";
let number2 = 45;
console.log(number1 == number2); // true
```



上述代码似乎开始不符合我们的常规思想了,一个是字符串,一个是数字,怎么会相等呢?

我们之前学习过**隐式类型转换**,在这里做比较的时候会首先将'45'转换为 45,然后再去跟`number2`比较,这就等同于下面的代码：

```js
let number1 = 45;
let number2 = 45;
console.log(number1 == number2);
```

同样的比较,如果做全等(===)比较,结果却不相同,代码如下：

```js
let number1 = "45";
let number2 = 45;
console.log(number1 === number2); // false
```

代码演示



可以看到最终输出了`false`,这是因为全等(===)符号不仅对值(45)进行了判断,还对类型进行了判断,因为'45'是字符串,45 是整数,两个值的类型不同,所以两个值不同.

由于相等错在类型转换问题,为了保持代码中数据类型的完整性,**推荐使用全等**

##### 自增/自减

什么是自增自减呢?举个例子,比如说我在卖气球,我本来有 10 个气球,手里有 0 元,每卖出去一个气球,手里就多 2 元,那么对于气球来说,就是自减,对于我手里的钱来说,就是自增.用代码表示就是：

```js
let balloon = 10;
let money = 0;
// 卖出去第一个
balloon = balloon - 1; // 9
money = money + 2; // 2

// 卖出去第二个
balloon = balloon - 1; // 8
money = money + 2; // 4

// .....
// 以此类推
```

很明显这种写法看起来非常繁琐,所以就有了自增(++)/自减(--)符号,上面的代码可以改写成如下代码：

```js
let balloon = 10;
let money = 0;
// 卖出去第一个
balloon--; // 9
money++; // 1

// 卖出去第二个
balloon--; // 8
money++; // 2

// .....
// 以此类推
```

下面我们添加`console`将结果输出：

```js
let balloon = 10;
let money = 0;

balloon--;
money++;
console.log("第一次递减后的结果：" + balloon);
console.log("第一次递增后的结果：" + money);

balloon--;
money++;
console.log("第二次递减后的结果：" + balloon);
console.log("第二次递增后的结果：" + money);
```





自增一般在循环中用的比较多,后面我们在学习循环的时候,如果忘了自增自减可以回来看一看.



### <3> 布尔类型 / 条件判断

#### 3.1 布尔类型

##### 布尔类型

布尔类型数据简单来说就是`true`(真)和`false`(假),它在我们后面学习流程控制语句和条件判断的时候使用非常频繁.

布尔类型的数据是区分大小写的,也就是说`true`、`false`是布尔类型数据,`TRUE`、`FALSE`都不是布尔类型数据.

你可以把`true`、`false`理解为一个值,它和字符串、数值一样,都是作为一个值来赋给变量的,例如：

```js
let flag = true;
let allow = false;
```

上面的代码表示定义了两个变量,分别赋值了`true`、`false`.

##### 布尔运算

在实际应用当中,布尔类型的数据大多情况下是通过计算得到的,这种计算叫做**布尔运算**.

##### 基本布尔运算

例如我们前面判断两个数据是否相等的时候,就会进行布尔运算,代码如下：

```js
let number1 = 45;
let number2 = 45;
let isEqual = number1 === number2;
console.log(isEqual);
```

上面的代码中`number1 === number2`就会进行布尔运算,因为`number1`和`number2`相等,所以结果是`true`.

除了全等和相等之外,还有很多布尔运算,比如`>`(大于)、`>=`(大于等于)、`<`(小于)、`<=`(小于等于)、`!==`(不等)、`!`(非).

这些运算符的含义和数学当中的运算符含义是一样的,我们可以通过代码来解释一下,代码如下：

```js
let a = 12;
let b = 3;

console.log('a > b结果：' + (a > b)); // true

console.log('a >= b 结果：' + (a >= b)); // true

console.log('a < b 结果：' + (a < b)); // false

console.log('a <= b 结果：' + (a <= b)); // false

console.log('a !== b 结果：' + (a !== b)); // true

let c = a > b;
// 非,表示取反,如果变量值是true,取反后是false
console.log('!c 结果：' + !c); // false
```

基本我们在初期遇到的布尔类型的运算就这么多了

#### 两种布尔运算的简便写法

另外再介绍两种不需要通过运算符就能得到布尔类型数据的,如下表所示：

| 数据类型 | 转换为true的值 | 转换为false的值 |
| -------- | -------------- | --------------- |
| 字符串   | 任何非空字符串 | ""(空字符串)    |
| 数字     | 任何非零数字   | 0               |

如何来理解上面这张表呢?我们来举个例子：

```js
let str = 'Bob';

if (str) {
  console.log('代码被执行了'); // 会被执行
}
// 上面代码等同于
if (str !== '') {
  console.log('代码被执行了'); // 会被执行
}
```

解释一下上面的代码,

```js
if (条件) {
  // 待执行代码
}
```

这段代码中,括号`()`里面的是“条件”,大括号`{}`里面的是要执行的代码,整个代码的意思就是,如果`()`里面的条件为`true`,那么就执行`{}`里面的代码,否则不执行.

> 大家不用深究具体含义,只要理解意思就好.

在这一节当中,我们更关注的是括号里面的“条件”,可以看到非空字符在这里被当作`true`来使用.具体原理我们不用深究,暂时知道这么用就好,否则会徒增学习负担.

那么,类似的,如果条件里面是一个空字符串,就会被当作`false`,代码如下：

```js
let str = ''; // 特别注意一下,空格也是非空字符串

if (str) {
  console.log('代码被执行了'); // 不会被执行
}
// 上面代码等同于
if (str !== '') {
  console.log('代码被执行了'); // 不会被执行
}
```

大家可以自己尝试一下非零数字和零.

这是一种比较方便的写法,如果理解起来有困难,可以用第二种方式.

##### 逻辑或(||)/逻辑与(&&)

**逻辑或**

逻辑或类似于电路中的并联电路,如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/3/%E5%B9%B6%E8%81%94%E7%94%B5%E8%B7%AF.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

两个开关中只要有一个开关关闭,灯就会亮. 我们可以认为开关关闭就是`true`,开关打开就是`false`, 灯亮表示最后的结果是`true`,灯灭表示最后结果为`false`.

> 可以总结为一句话,一真即真,都假即为假.

下面我们将电路转换为代码：

```js
let switch1 = true; // 表示开关1是闭合的
let switch2 = false; // 表示开关2是打开的

let result = switch1 || switch2; // 如果结果是true,就表示灯亮
console.log(result);
```

**逻辑与**

逻辑与类似于电路中的串联电路,如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/3/%E4%B8%B2%E8%81%94%E7%94%B5%E8%B7%AF.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

两个开关必须都关闭,灯才会亮.

将电路转换为代码：

```js
let switch1 = true; // 表示开关1是闭合的
let switch2 = false; // 表示开关2是打开的

let result = switch1 && switch2; // 如果结果是false,就表示灯灭
console.log(result);
```

至此我们基本学完了常用的所有逻辑运算.

#### 3.2 条件判断

到目前位置，我们学习的代码都是按照从上到下的顺序来执行的，为了改变代码执行的顺序，我们需要用到条件判断语句，来使某些代码执行或者不执行。

##### if

条件判断语句的格式很简单，我们在上一节接触过，格式如下：

```js
let x = 2;

if (x > 0) {
  console.log('正数');
}
```

这句代码的意思就是,因为变量`x`是 2,是大于 0 的,所以会输出`console.log('正数');`这句话.

代码演示如下：

代码演示



**注意：** 当 if 条件下面只有一条语句,那么花括号(`{}`)可以不加,这个我们了解就好,但是建议初学者不管在什么情况下都加上花括号(`{}`).去掉花括号(`{}`)后的代码如下：

```js
if (x > 0) console.log('正数');

// 上面代码等同于
if (x > 0) {
  console.log('正数');
}
```

##### if-else

`if`条件判断规定了符合条件的执行内容,`if-else`不仅规定了符合条件的执行内容,还规定了不符合条件的执行内容.

你可以将`if-else`理解为一句话,**如果...要不然....**

比如下面这段代码：

```js
let myAge = 23;

if (myAge >= 18) {
  console.log('你已成年');
} else {
  console.log('你未成年');
}
```

这句话的意思是,如果你年龄满 18 周岁,你就是成年人,要不然你就是未成年人.因为 myAge 这个变量被赋值为 23,所以最后会输出"你已成年",而不会输出“你未成年”是.不是很好理解呢?

##### if-else-if

在实际情况中,我们不可能只会有两种情况,比如说上面的场景中还有一种情况,就是 16~18 岁的情况,具体可以分为下面三种：

1. 小于 16 岁,未成年人
2. 大于等于 16 岁,小于 18 岁,完全能力人
3. 大于等于 18 岁,成年人

用代码表示如下：

```js
let myAge = 17;

if (myAge < 16) {
  console.log('你还是未成年人');
} else if (myAge >= 16 && myAge < 18) {
  console.log('你是完全能力人');
} else {
  console.log('你是成年人');
}
```

`else if`可以理解为第二个`if`,方便我们添加第二种或者第三种条件,括号`()`里面添加的是附加条件.



诸如此类的场景还有很多,比如说,我们安排自己的行程,如果 12 月 25 日下雨,就雨中漫步,如果下雪,就去堆雪人,如果刮风,就呆在家里,其它情况就去上班.用代码表示：

```js
let weather = 'snow';

if (weather === 'rain') {
  console.log('雨中漫步');
} else if (weather === 'snow') {
  console.log('堆雪人');
} else if (weather === 'windy') {
  console.log('呆在家里');
} else {
  console.log('上班');
}
```

上述代码大家可以自己去验证一下,或者自己想一种场景去用代码实现.

##### switch

`switch`语句可以说是`if else if`的变异体,我们先用`switch`将根据天气决定要做什么的案例修改一下：

```js
let weather = 'rain';

switch (weather) {
  case 'snow':
    console.log('堆雪人');
    break;
  case 'windy':
    console.log('呆在家里');
    break;
  case 'rain':
    console.log('雨中漫步');
    break;
  default:
    console.log('工作');
    break;
}
```

我们来结合下面这张图来理解一下：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/3/switch%E6%B5%81%E7%A8%8B.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

1. 首先我们在“开始”位置传入一个值`weather='rain'`;
2. 条件 1 你可以理解为`case 'snow'`,翻译过来就是,`weather`是不是等于`snow`呢?很明显不是,`weather`是`rain`,所以会走右侧的`false`;
3. 然后进入条件 2,`weather`是不是等于`windy`呢?结果是`false`,最后走到条件 3 的时候,`weather`的确是`rain`,所以会执行`console.log('雨中漫步');`
4. `default`你可以理解为`else`,就是当上面所有的`case`中都不包含`weather`值,那么就会执行`default`后面的代码,比如说一开始`let weather = '下冰雹'`.

代码中的`break`就是打断的意思,表示跳出`switch`代码块,后面的不再执行.

### <4> 数组

#### 4.1 认识数组

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/4/%E5%86%B0%E5%9D%97%E6%A8%A1%E5%85%B7.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

什么是数组呢？它就类似于上图所示的冰块模具，你可以将变量理解为单个方块的冰块模具，数组就是多个方块的冰块模具，以前我们用变量一次只能存储一个值，数组则可以一次存放多个值。

> 使用熟练后，可以深究一下存储原理。

##### 数组的表示方法：

`JavaScript`中,数组的表示方法是一个方括号(`[]`),例如：

```js
[]
```

你可以将上面的代码中的`[]`理解为一个**空数组**,空数组就是没有存放任何内容的数组.

下面的数组是一个有内容的数组,内容和内容之间要用逗号(`,`)隔开.

```js
[1,2,3,4]
```

数组有一个很有意思的特性,就是它可以存放不同类型的值,例如下面的数组中,就存放了各种不同类型的数据(也可以叫值).

```js
[1,'第一名',true]
```

更“过分”的是,它还可以存放数组,如下面的代码：

```js
[1,'第一名',true,[2,'第二名',false]]
```

所以呢,数组真的是包罗万象的.

那么我们要使用数组,肯定不能拿着方括号直接去用,我们还需要一个变量来存储它

> 这里的存储,准确来将,应该是存储了指向数组的地址.不过这种复杂的东西我们最好在初学的时候不要纠结,更多的是要找一种便于理解的方式来理解它的功能.

存储数组的变量与存储值的变量是一样的,因为你完全可以将数组理解为一个“胖”一点的变量,下面我们将上面的数组存储在一个变量中：

```js
let arr = [1,'第一名',true,[2,'第二名',false]];
```

到这里我们就完成了数组的创建和赋值过程.

或许还有另一种创建数组的方式,比如：

```js
// 创建一个空数组并赋值
let arr = new Array();

// 创建一个有内容的数组
let arr2 = new Array(1,2,'arr');
```

> 建议大家一开始只要记住一种即可,就是方括号(`[]`),熟悉了以后再去理解另一种.这样可以降低学习成本.

##### 数组的索引

说完了数组的定义和赋值,接下来要讲到的是数组的索引,什么是数组的索引呢?

还是以冰块模具为例,索引就好像我们给模具的每一个小格子上标的序号,从0开始.数组也一样,每一个值对应一个编号：

```js
['张三','李四','王五','Lisa']

  0      1      2      3.
```

- **根据索引(下标)取出数组中对应的值**

比如说我要取出`['张三','李四','王五','Lisa']`这个数组中的'王五',可以这么做：

```js
// 定义数组
let arr = ['张三','李四','王五','Lisa'];
// 定义一个变量来接收取到的值
let str = arr[2];
// 输出取到的值
console.log(str); // 王五
```

- **数组索引(下标)可以用来修改对应位置的值**

定义一个数组,如下：

```js
let arr = ['张三','李四','王五','Lisa'];
```

现在要做的是将王五修改为"Tom",做法如下：

```js
let arr = ['张三','李四','王五','Lisa'];
// 修改'王五'为'Tom'
arr[2] = 'Tom';
// 输出数组
console.log(arr);
```

**数组索引(下标)可以在新的位置上插入值**

举个例子：

```js
let arr = ['张三','李四','王五','Lisa'];

// 修改值
arr[0] = 'Three';
arr[1] = 'Four';
arr[2] = 'Five';
arr[3] = '丽莎';
console.log(arr);

// 添加值
arr[4] = 'Polly';

console.log(arr);
```

从上面的例子可以看出,在已有索引上执行`arr[x] = 'XXX'`,是修改操作,如果是在未有的位置上执行`arr[x] = 'XXX'`操作,是添加操作.



#### 4.2 数组元素操作（增/删/改/查）

在前一节，我们可以根据数组的下表来修改和添加数组中的元素，在这一节中我们要学习几种常用的操作数组的方法。

##### 数组元素操作 -- 增

###### push 方法（从尾加）

`push`方法可以在数组的末尾添加值，使用方法：

```js
变量名.push('要添加的值');
```

比如说我们要在下面这个数组的后面添加一个值：

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

// 在末尾添加“河海大学”
schools.push('河海大学');
console.log(schools); // 清华大学','北京大学','浙江大学','同济大学','河海大学'
```

比如说我们要添加多个值：

```js
schools.push('河海大学');
schools.push('大连理工大学');
schools.push('哈尔滨工业大学');

// 上述三步操作可以一次性完成
schools.push('河海大学', '大连理工大学', '哈尔滨工业大学');
```

###### unshift 方法(从头加)

该方法与`push`方法类似,表示从数组的前面添加值.请同学们在右侧工程中自行尝试.

##### 数组元素操作--删

删除的方法和增加的方法相对应,分为从前往后删和从后往前删除,首先要说的是从后往前删除的方法

###### pop 方法(从后往前删除)

`pop`方法对应的是`push`方法,表示从后往前删除,例如：

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

// 在末尾添加“河海大学”
schools.push('河海大学');
console.log(schools); // 清华大学','北京大学','浙江大学','同济大学','河海大学'

// 从末尾删除一个元素
schools.pop();
console.log(schools); // 清华大学','北京大学','浙江大学','同济大学'
```

可以看出,使用了`pop`方法以后,从末尾添加的`"河海大学"`被删除了.

代码演示如下：

代码演示

###### shift 方法(从前往后删除)

`shift`表示从开始位置删除一个元素,请同学们自行尝试并理解

###### splice 方法(删除指定位置的值)

`splice`方法在括号内可以写一个参数,也可以写两个参数,具体作用我们用案例来解释一下.

**一个参数**

表示删除从指定位置开始到结束位置的所有元素,并返回被删除的元素

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

// 删除从下标为1的位置到结束位置的值
let deleteSchools = schools.splice(1);
// 删除之后，原数组中的剩余内容
console.log(schools); // ["清华大学"]
// 删除的内容
console.log(deleteSchools); // ["北京大学", "浙江大学", "同济大学"]
```

**两个参数**

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

// 从下标为0开始,往后数两个元素,删除
let deleteSchools = schools.splice(0, 2);
console.log(schools); // ['浙江大学', '同济大学']
console.log(deleteSchools); // ['清华大学', '北京大学']
```

##### 数组元素操作--改

###### splice 方法(需改指定位置的元素)

splice 方法难理解一点,这里需要讲解一下,`splice`方法括号里需要添加三个值(也叫参数).分别代表三个意思,先来解释一下这三个值：

1. 第一个值,整数类型,表示起始位置
2. 第二个值,整数类型,表示步长(往后选几个元素,1 代表往后选 1 个元素)
3. 第三个参数,要替换的数组的值

这里要将下标做进一步的解释,否则无法理解这个方法,如下图所示：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/4/splice.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

可以看到,数组的下标不是在正下方,而是在左下角,实际上,正确的下标就是应该在左下角,下标其实类似于公交车的站点.

了解了这三个参数的意义以后,下面我们在实际案例中运用并加深理解.

**案例 1：**

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

schools.splice(2, 0, '江西理工大学');
console.log(schools); //  ["清华大学", "北京大学", "江西理工大学", "浙江大学", "同济大学"]
```

在这个案例中,`splice`方法的第一个参数是 2,第二个参数是 0,也就是从下标 2 开始,往后走 0 个步长,然后用"江西理工大学"替换这 0 个步长里的内容.

经过一系列操作以后,给人的感觉貌似是在“北京大学”和“浙江大学”之间添加了“江西理工大学”,其实不然,`splice`的意义其实还是替换的意思.

**案例 2：**

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

schools.splice(2, 1, '江西理工大学');
console.log(schools); // ["清华大学", "北京大学", "江西理工大学", "同济大学"]
```

当步长为 1 以后,从 2 开始,往后走 1,就选中了"浙江大学",然后用“江西理工大学”替换了“浙江大学”.

**案例 3：**

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

schools.splice(2, 2, '江西理工大学');
console.log(schools); // ["清华大学", "北京大学", "江西理工大学"]
```

这个案例中步长为 2,开始位置为 2,这样就选中了“浙江大学”和“同济大学”,然后将这两个大学用“江西理工大学”替换

##### 数组元素操作--查

查询数组中是否含有某个元素,我们在这一节里只学习一个方法--indexOf().

`indexOf()`括号内可以写两个参数,不过我们常用的是添加一个参数的情况,大家重点关注一个参数的情况即可.

**一个参数**

比如说我们要查询`schools`数组内是否有某个学校：

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

let result = schools.indexOf('大连理工');
console.log(result); // -1
```

**返回值是`-1`表示未找到,非`-1`数字表示找到的元素的下标**

**两个参数**

第一个参数是我们要找的值,第二个参数是开始寻找的位置,比如在一个参数的情况下我们来寻找"浙江大学".

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

let result = schools.indexOf('浙江大学');
console.log(result); // 2 表示“浙江大学”所在的下标为2
```

结果是 `2`，表示找到了。但是当使用第二个参数规定开始寻找的位置，就未必能找到了。例如：

```js
let schools = ['清华大学', '北京大学', '浙江大学', '同济大学'];

let result = schools.indexOf('浙江大学', 3);
console.log(result); // -1
```

因为我们是从下标为 `3` 的位置（同济大学）开始寻找的，所以找不到。

所以，使用第二个参数的时候，一定要小心哦。

**注意：**这里的下标要理解为下图所示的下标.

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/4/splice.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

#### 4.3 二维数组

我们知道一维数组是一个方括号(`[]`），那么二维数组就是在一维数组内继续添加(`[]`），即数组内部继续添加数组：

我们在第一节学习数组的时候，见过这样一个数组：

```js
[1, '第一名', true, [2, '第二名', false]];
```

可以看到在一维数组内部还有一个数组,如果将一维数组内部除了非数组的数据去掉以后,这个数组就变成了一个二维数组：

```js
// 二维数组
[[2, '第二名', false]];
```

我们在内部再多增加几个数组,改变一下摆放的格局,是不是就像大格子里面有小格子,小格子里面有内容?而小格子就是大格子的内容。假设数组名为 `arr`：

```js
[
  [2, '第二名', false],
  [2, '第二名', false],
  [2, '第二名', false],
];
```

首先我们来看一下如何取值.

**第一步**,取出数组内部的数组

```js
let arr2 = arr[0];
console.log(arr2); // [2,'第二名',false]
```

**第二步**,取出`arr2`内部的元素,比如说我们要取出 2：

```js
let number = arr2[0];
console.log(number); // 2
```

**第三步**,将两步合成一步：

```js
let number = arr[0][0];
console.log(number); // 2
```

到这里我们就完成了二维数组的一次取值过程.

学会了如何从二维数组里面取值,那么如何给一个空的数组里面存值呢?

比如说我们要用二维数组来存放几个人的基本信息,信息如下：

| 姓名       | 性别 | 等级 | 年龄 |
| ---------- | ---- | ---- | ---- |
| 宇智波佐助 | 男   | 下忍 | 12   |
| 春野樱     | 女   | 下忍 | 12   |
| 漩涡鸣人   | 男   | 下忍 | 12   |

我们的做法是这样：

```js
// 定义一个一维数组
let arr1 = [];
// 给一维数组里面添加数据
arr1[0] = '宇智波佐助';
arr1[1] = '男';
arr1[2] = '下忍';
arr1[3] = 12;
console.log(arr1); // ['宇智波佐助','男','下忍',12]
// 给一维数组里面添加数据
arr2 = [];
arr2[0] = '春野樱';
arr2[1] = '女';
arr2[2] = '下忍';
arr2[3] = 12;
console.log(arr2); // ['春野樱','女','下忍',12]
// 给一维数组里面添加数据
arr3 = [];
arr3[0] = '漩涡鸣人';
arr3[1] = '男';
arr3[2] = '下忍';
arr3[3] = 12;
console.log(arr3); // ['漩涡鸣人','男','下忍',12]
// 将一维数组添加到另一个数组中，形成二维数组
let arr = [];
arr[0] = arr1;
arr[1] = arr2;
arr[2] = arr3;
console.log(arr);
// [
//   ['宇智波佐助', '男', '下忍', 12],
//   ['春野樱', '女', '下忍', 12],
//   ['漩涡鸣人', '男', '下忍', 12],
// ]
```

`arr[0] = [];`表示给一维数组里面添加数组,这一步很关键,如果不在一维数组里添加数组`[]`就直接使用`arr[0][0]`会报错

因为你做的`arr[0]`操作获取到的数据是`undefined`,再去执行`arr[0][0]`就是无效操作了,因为没有选到数组,还做数组操作,就是错误的.

我们还可以使用我们学习过的`push`方法来给数组赋值：

```js
let arr = [];
arr.push([]);
arr[0].push('宇智波佐助');
arr[0].push('男');
arr[0].push('下忍');
arr[0].push(12);

arr.push([]);
arr[1].push('春野樱');
arr[1].push('女');
arr[1].push('下忍');
arr[1].push(12);

arr.push([]);
arr[2].push('漩涡鸣人');
arr[2].push('男');
arr[2].push('下忍');
arr[2].push(12);

console.log(arr);
```

结果是一样的,请根据自己的喜好来使用.

根据故事的进展,宇智波佐助出逃,佐井进入了小队,所以我们需要将宇智波佐助的信息替换成佐井.

做法和一维数组类似：

```js
arr[0][0] = '佐井';
arr[0][1] = '男';
arr[0][2] = '下忍';
arr[0][3] = 14;
```

或者你比较懒,可以直接一步到位：

```js
arr[0] = ['佐井', '男', '下忍', 14];
```

因为这是替换了一个人,所以修改个人信息的时候,用第二种方式比较简单,大多数情况下都是变更部分信息,比如说参加中忍考试以后,两个升为中忍,只能去使用第一种方法来修改信息：

```js
// 修改佐助等级为中忍
arr[0][2] = '中忍';
// 修改春野樱等级为中忍
arr[1][2] = '中忍';
```

### <5> 循环

#### 5.1 for 循环

在上一章节我们学习了数组，我们也学会了使用下标访问数组中的元素，那么大家试想一下，如果我想打印一个数组中的所有元素该怎么写呢？

```js
let peppaFamily = ["佩奇", "乔治", "猪妈妈", "猪爸爸"];
console.log(peppaFamily[0]);
console.log(peppaFamily[1]);
console.log(peppaFamily[2]);
console.log(peppaFamily[3]);
```

代码演示



如果这个数组比较长的话，`console.log`语句会对应增加：

```js
let peppaFriends = [
  "小狗丹尼",
  "小猫坎迪",
  "狐狸弗雷迪",
  "小狼温蒂",
  "大象艾米丽",
  "小兔瑞贝卡",
  "小羊苏西"
];
console.log(peppaFriends[0]);
console.log(peppaFriends[1]);
console.log(peppaFriends[2]);
console.log(peppaFriends[3]);
console.log(peppaFriends[4]);
console.log(peppaFriends[5]);
console.log(peppaFriends[6]);
```

如果这个数组的长度是 100 位，哦买噶！我们得“console.log”**一百次！**想想都叫人头秃……

好在 JavaScript 和其他编程语言一样都可以通过**循环**来解决这种问题。

##### for 循环

一个 for 循环会一直重复执行，直到指定的循环条件为 false。 JavaScript 的 for 循环，和 Java、C 的 for 循环，是很相似的。

###### for 循环的写法

一个 for 语句是这个样子的：

![img](https://document.youkeda.com/P3-4-HTML-CSS/5/1.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

在上面这个 for 循环中： 初始条件：i = 0 （需要用变量声明的关键词 let 进行声明）； 循环条件：i < 4 （循环条件为 false 时，终止循环）； 每次循环执行的内容：console.log(i)； 更新条件表达式：i++ (即每次循环之后 i 加 1)；

所以：

| 循环次数 | i的值 | 循环条件：i < 4 | 执行内容       | 输出 | 更新i值为 |
| -------- | ----- | --------------- | -------------- | ---- | --------- |
| 第一次   | 0     | true            | console.log(i) | 0    | 1         |
| 第二次   | 1     | true            | console.log(i) | 1    | 2         |
| 第三次   | 2     | true            | console.log(i) | 2    | 3         |
| 第四次   | 3     | true            | console.log(i) | 3    | 4         |
| 第五次   | 4     | false           | 无，跳出循环   | 无   | 不更新    |

上述循环执行到第五次的时候，由于循环条件为 false，循环终止了。这之后就跳出了循环。这里要注意：

- i 的自增是在执行完大括号中的内容后执行的，所以最后这里 i 是 4。
- 因为我们用了 `let` 来声明变量 i，所以 i 的作用域只在 for 循环内。

###### for 循环的使用

现在我们来打印小猪佩奇一家所有成员：

```js
let peppaFamily = ["佩奇", "乔治", "猪妈妈", "猪爸爸"];

for (let i = 0; i < peppaFamily.length; i++) {
  console.log(peppaFamily[i]);
}
// 输出:
// 佩奇
// 乔治
// 猪妈妈
// 猪爸爸
```

> 注意：在 for 循环中，”初始条件“、”循环条件“和”更新表达式“之间需用英文分号“;”隔开。

要循环访问数组，除了上面这种写法，js 中还有两个跟 “for” 相关的写法可供选择：for...in 和 for...of。

大家了解即可。

###### for...in 和 for...of 的写法

1. for...in 循环的语法是这样的：

```js
let peppaFamily = ["佩奇", "乔治", "猪妈妈", "猪爸爸"];

for (let i in peppaFamily) {
  console.log(peppaFamily[i]);
}
// 输出:
// 佩奇
// 乔治
// 猪妈妈
// 猪爸爸
```

for...in 循环会访问数组中的每一项，这里的 i 对应数组中每一项的下标。

> for...in 不但可以循环数组，还能循环对象。

1. for...of 循环

```js
let peppaFamily = ["佩奇", "乔治", "猪妈妈", "猪爸爸"];

for (let item of peppaFamily) {
  console.log(item);
}
// 输出:
// 佩奇
// 乔治
// 猪妈妈
// 猪爸爸
```

for...of 循环也会访问数组中的每一项，这里的 item 对应数组中每一项。

> 两者的区别：for...in 循环遍历的结果是数组元素的下标，而 for...of 遍历的结果是元素的值。

#### 5.2 while循环

##### while 循环

除了 for 循环外，js中还有其他的循环方式，这里我们学习while循环。

除了for循环外，js中还有其他的循环方式，这里我们学习while循环。

while有“当”的意思，”当“满足某个条件的时候，就会执行一些内容，while语句的语法如下：

![img](https://document.youkeda.com/P3-4-HTML-CSS/5/2.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

在这里我们可以看到，while循环和for循环一样，都有“初始条件”、“循环条件”和“更新表达式”这三个东西：

初始条件：i=0；循环条件：i < 4；执行内容：

`console.log(i); i++;`； 更新条件的表达式：i++；

**注意：初始条件写在 while 循环外，更新条件的表达式写在执行内容里。**

现在我们用 while 循环来打印小猪佩奇的朋友们：

```js
let peppaFriends = ['小狗丹尼', '小猫坎迪', '狐狸弗雷迪', '小狼温蒂', '大象艾米丽', '小兔瑞贝卡', '小羊苏西'];

let i = 0;
while (i < peppaFriends.length ) {
  console.log(peppaFriends[i]);
  i++;
}
```

“当” i < peppaFriends.length（即 i < 7） 时，执行 console.log(peppaFriends[i])，并将 i 加 1 。

一共执行 7 次，在最后一次循环中，i = 6，符合 while 的判断条件，执行 console 语句打出最后一个数组元素，并将 i 加至 7。

到此，已打印出所有的佩奇小伙伴了。

不过大家试想一下，如果我们将更新条件的表达式 i++ 放到 console 语句前会发生什么呢？

```js
let peppaFriends = ['小狗丹尼', '小猫坎迪', '狐狸弗雷迪', '小狼温蒂', '大象艾米丽', '小兔瑞贝卡', '小羊苏西'];

let i = 0;
while (i < peppaFriends.length ) {
  i++;
  console.log(peppaFriends[i]);
}
```

输出的居然是这样的：

![img](https://document.youkeda.com/P3-4-HTML-CSS/5/3.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

为什么呢？我们来仔细看看：

第一次循环时，i = 0，i < 7 符合 while 的判断条件，执行大括号中的内容，i + 1 （变成了 1），并且打出 console.log(peppaFriends[1])，即“小猫坎迪”；

最后一次循环时，i = 6，i < 7 符合 while 的判断条件，执行大括号中的内容，i + 1 （变成了 7），并且打出 console.log(peppaFriends[7])，数组没有下标为7的元素，输出 undefined。

##### do...while 循环

while 循环有两种写法：while 和 do...while。

两者的区别在于先判断还是先执行：

写法一：while 先判断，后执行。 写法二：do...while，先 “do” (执行)，后 while (判断)。

do...while 的语法如下：

![img](https://document.youkeda.com/P3-4-HTML-CSS/5/5.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

**同样的：初始条件写在 while 循环外，更新条件的表达式写在执行内容里。**

但因为 do...while 是先执行后判断的，所以一定会执行一次 do 之后的内容。比如：

```js
let i = 0;

do {
  console.log(i); // 输出：0
  i++;
} while (i < 0 );
```

#### 5.3 跳出循环 break/continue

```js
let num = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368]
```

在上一章节的第三题中，我们要在上面的“斐波那契数列”中找到并打印出所有能被 5 整除的数字，代码如下：

```js
let num = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368];

for(let i = 0;i < num.length;i++) {
  if (num[i]%5 === 0) {
    console.log(num[i]);
  }
}
```

如果题目的要求变成了找到并打印出第一个能被 5 整除的数字，那我们在找到第一个符合条件的数字时就应该阻止循环继续下去。

那么我们该怎么停止循环呢？

这里我们就要用到“break”来跳出循环。

##### 跳出整个循环：break

当符合条件时，利用 break 来跳出整个循环：

```js
let num = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368];

for(let i = 0;i < num.length;i++) {
  if (num[i]%5 === 0) {
    console.log(num[i]);
    // 用 break 跳出循环
    break;
  }
}

// 循环之后的语句
console.log("循环之后的语句");
```

break 的作用就是跳出循环，不管循环有没有结束都不会再继续下去，而是直接执行循环之后的语句。

如果我们要把数组中所有不能被5整除的元素做统一处理，比如除以5并打印，那么我们在遇到能被 5 整除的数字时，应该不作处理直接进行下一次循环。

跳过循环中的某一次迭代，我们可以使用“continue”。

> 迭代：每一次对过程的重复被称为一次“迭代”。

###### 跳过某次迭代：continue

当符合条件时，利用 continue 来跳过某次迭代：

```js
let num = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368];

for(let i = 0;i < num.length;i++) {
  if (num[i]%5 === 0) {
    // 用 continue 跳出符合条件的这一次迭代
    console.log("跳过了第" + (i + 1) + "个数：" + num[i]);
    continue;
  }
  const handledNum = num[i] / 5;
  console.log(handledNum);
}

// 循环之后的语句
console.log("循环之后的语句");
```

点击播放上述代码，查看运行结果：

代码演示

###### break 和 continue 的区别

break 是终止整个循环，而 continue 是结束当前迭代，进入下一次迭代，并不会终止循环。

###### 在 while 中使用 break 和 continue

在 while 中使用 break 和 continue，和在 for 循环中使用是一样的。

先来写一下 break 的使用：

```js
let num = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368];
let i = 0;

while (i < num.length) {
  if (num[i]%5 === 0) {
    console.log(num[i]);
    // 用 break 跳出循环
    break;
  }
  i++;
}

// 循环之后的语句
console.log("循环之后的语句");
```

再写一下 continue 的使用：

```js
let num = [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181, 6765, 10946, 17711, 28657, 46368];
let i = 0;

while (i < num.length) {
  if (num[i]%5 === 0) {
    // 用 continue 跳出符合条件的这一次迭代
    console.log("跳过了第" + (i + 1) + "个数：" + num[i]);
    i++;
    continue;
  }
  const handledNum = num[i] / 5;
  console.log(handledNum);
  i++;
}

// 循环之后的语句
console.log("循环之后的语句");
```

> 这里要注意一下，因为 while 循环中，i++ 是放在“{}”中执行的，所以在执行 continue 之前要先执行 i++ 哦，不然会陷入死循环的。

### <6> 函数

#### 6.1 函数概述

上个章节中我们学习了用循环处理数组中的元素，比如找到第一个被5整除的数字，但是每次要处理一个新的数组就需要把代码重新写一遍，这样工作量很大，怎么办呢？

JavaScript和其他编程语言一样，我们可以使用函数来解决这个问题。

函数是一段可以反复调用的代码块，往往能够实现一个特定的功能，它可以解决代码重复的问题。在JavaScript中，函数是头等（first-class）对象，有时我们也可以称其为方法。

我们可以把要重复调用的代码写成一个函数，这样就可以在每次需要实现对应功能的时候，调用这个函数。

比如你晚上回到家，要吃晚饭，那你需要“洗菜”、“切菜”、“炒菜”、“装盘”，然后才能吃。

然后早上起来，要吃早餐，又要“洗菜”、“切菜”、“炒菜”、“装盘”然后才能吃。

现在你把这个过程取个名字叫“做菜”，告诉给家政阿姨。

每次要吃饭了就跟阿姨说：“阿姨，麻烦去’做菜‘吧。”，阿姨就会执行上述步骤帮你把菜做好。

这个“做菜”，就是一个函数，“洗菜”、“切菜”、“炒菜”、“装盘”就是函数里的代码块，通过调用“做菜”这个函数，可以重复执行函数中的代码。

这章节，在学习如何自定义函数之前，先来看看JavaScript中的一个内置函数Math.random()。这个函数大家应该不会陌生，java里也有个差不多的函数。

##### 获取随机数Math.random()

下面这句代码中的Math.random() 就是js 的内置函数。Math是一个内置对象，用于执行数学任务。

```js
const num = Math.random();
```

通过上面这行代码，我们可以获得一个范围在 [0, 1) 之间的随机数。即从0（包括0）往上，但是不包括1（排除1）。

如果我们要获取一个三位数随机数，即范围在 [100, 1000) 之间，那么我们可以这么做：

1. 先获取 [0, 1000) 之间的随机数：

```js
const num = Math.random() * 1000;
```

1. 再获取 [100, 1000) 之间的随机数

要获取 [100, 1000) 的数，那么 Math.random() 应该属于 [0.1, 1)。

我们处理一下：

```js
// num1 的范围是 [0.1, 1)
const num1 = Math.random() * 0.9 + 0.1;
// num2 的范围是 [100, 1000)
const num2 = Math.floor(num1 * 1000);

console.log(num2);
```

> Math.floor(x) 是js内置方法，返回小于 x 的最大整数。比如，Math.floor(2.3) 返回 2，Math.floor(4.9) 返回 4。

#### 6.2 自定义函数

如果我们要多次生成三位数随机数，那么就需要写很多次下面这段代码：

```js
// num1 的范围是 [0.1, 1)
const num1 = Math.random() * 0.9 + 0.1;
// num2 的范围是 [100, 1000)
const num2 = Math.floor(num1 * 1000);

console.log(num2);
```

这样不但工作量大，代码看起来也会凌乱。

其实 JavaScript 和其他编程语言一样，可以自定义函数。我们可以用自定义函数来解决代码复用的问题。

自定义函数是需要自行声明的，我们先来看函数的声明。

##### 函数的声明

js 中函数声明有三种方法，这里我们主要讲两种：function 命令和函数表达式。

##### 1. 用 function 命令声明

用 function 命令声明函数的格式如下：

![img](https://document.youkeda.com/P3-4-HTML-CSS/6/1.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

上面的代码声明了一个名为“print”的自定义函数，它的作用是打印一段文本，文本内容为“JavaScript 真有趣”。

大括号“{}”中的内容就是每次调用该函数的时候会被执行的代码块，也称函数体。

要注意，用 function 命令声明函数有四个东西缺一不可：

1. 关键词“function”；
2. 函数名“print”，当然，这个名称是自己取的；
3. 函数名之后的小括号“()”；
4. 包裹函数体用的大括号“{}”，“{}”中可以没有代码；

> 函数名往往和函数的功能有关系，一般我们用小驼峰命名法来给函数命名。小驼峰命名法：第一个单词首字母小写，后面其他单词首字母大写。比如：firstName、checkFirstName 等。

点击播放函数的声明：

代码演示



**可以看到，声明完函数之后，函数体是不会被执行的。如果我们需要它执行，那么可以通过函数名来调用它。**

##### 函数的调用

现在，我们通过函数名来调用上面这个“print”函数：

```js
print(); // 调用格式为：函数名 + ()
```

调用几次，函数体就会执行几次，点击播放函数的调用，在控制台“console”中查看执行结果：

代码演示



注意，在调用函数的时候，要在函数名后加上英文小括号“()”，即圆括号运算符。

##### 2. 用函数表达式声明

除了用 function 命令声明函数，还可以采用变量赋值的写法。

函数表达式声明函数的格式如下：

![img](https://document.youkeda.com/P3-4-HTML-CSS/6/2.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

这种写法将一个匿名函数赋值给变量。赋值等号右边为匿名函数，又称函数表达式。

注意，采用函数表达式声明函数时，function 命令后面不带有函数名。

调用的时候和用 function 命令声明的函数调用一样，函数名 + ()。

这里的函数名指的是变量名。

```js
print();
```

es6 中函数表达式声明可以用箭头函数简写为：

```js
let print = () => {
  console.log("JavaScript 真有趣");
};
```

箭头函数的小括号前省略了 function，小括号后加了箭头“=>”。

##### 函数声明的提升

采用function命令声明函数时，整个函数会被提升到代码头部。所以，下面的代码不会报错：

```js
f();
function f() {}
```

在上面的代码中，看起来函数 f 的调用在前，声明在后，但其实因为用function命令声明函数时函数声明会被提升到代码头部，所以上面的代码相当于：

```js
// 被提升到头部
function f() {}
f();
```

但是用函数表达式声明函数的时候不存在函数声明提升，编译的时候就会报错。

> 函数声明提升大家了解即可。

##### 两种声明方式的区别

1. 结尾的大括号后是否需要加“;”：

- function 命令声明：结尾的大括号后不需要加“;”
- 函数表达式：结尾的大括号后需要加“;”

1. 有无声明提升：

- function 命令声明：有提升；
- 函数表达式：没有提升；

因为函数表达式是一个表达式，所以要加“;”。总的来说两种声明方式的区别还是比较小的。

> 注意：以上代码中的符号，比如引号、括号、分号等均为英文状态下的符号。

##### 函数的重复声明

如果同一个函数被多次声明，后面的声明就会覆盖前面的声明。

```js
function print() {
  console.log("JavaScript 真有趣");
}

function print() {
  console.log("JavaScript 真有趣...个鬼嘞");
}

print();
```

运行结果：

```js
JavaScript 真有趣...个鬼嘞
```

前一次声明在任何时候都是无效的，这一点要特别注意。

##### 立即执行函数

当函数只使用一次时，通常使用IIFE (Immediately Invokable Function Expressions)：

```js
(function() {
  console.log("这个函数只执行一次");
})();
```

它会在函数声明后立即调用函数，除这一次调用外因为是匿名函数，所以无从调用。

> IIFE 大家了解即可。

#### 6.3 函数参数

我们用function命令声明生成六位随机数的函数，它是这样写的：

```js
function code() {
	const num1 = Math.random()*0.9 + 0.1 ;
	const num2 = Math.floor(num*1000000);
	
	console.log(num2);
}
```

那如果我们要生成思维随机数，只需要在num2的计算中做小小的修改就可以了：

```js
function code() {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * 10000);
  
  console.log(num2);
}
```

但是这样，我们需要把`const num2 = Math.floor(num1 * 10000);`这句之外的其他代码原样抄写一遍。这就很不帅气。

我们希望这个函数能够根据我们给出的“位数”要求，生成合适的随机数。

那我们要怎么把要求给到函数呢？

很简单，我们可以通过参数给函数传数据：

```js
// 在圆括号运算符中加入参数 figure，用来接收外部传入的数据
function code(figure) {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));
  
  console.log(num2);
}

// 不要忘记调用函数，调用函数后函数才会执行
code(4);
code(6);
```

打印结果：

```js
6750
905910
```

> 上面 Math.pow(x,y) 是js内置方法，求取 x 的 y 次幂。比如，Math.pow(10, 4) 的计算结果为 10000。

上面代码中的 figure 就是函数的参数，这个参数接收外部传给函数的数据，传入的数据不同函数运行后得到的结果可能不同。

##### 多个参数

函数可以接受多个参数，多个参数以“,”（英文逗号）分隔：

```js
// 参数 figure(位数) txt(文本) 
function code(figure, txt) {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));
  
  console.log(txt + num2);
}

code(6, "六位随机数：");
```

打印结果：

```js
六位随机数：556540
```

上述函数接受两个参数：figure 和 txt。

在调用的时候，我们传入了两个数据： 6 和 "六位随机数："。

通过打印结果，我们可以知道：figure 对应 6，txt 对应 "六位随机数："。

即，**调用函数时，需要按顺序传入数据。**

那如果参数数量和传入数量不匹配会发生什么呢？

##### 参数数量和传入数量不匹配

如果传入的数据个数超过了函数的参数：

```js
// 参数 figure(位数) txt(文本) 
function code(figure, txt) {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));
  
  console.log(txt, num2);
}

code(6, "六位随机数：", "第三个参数");
```

打印结果：

```
六位随机数：556540
```

结果并没有受到影响，这是因为 **JavaScript 允许传入任意个参数而不影响调用**，因此传入的参数比定义的参数多也没有问题。这一点和 Java 有区别，在 JavaScript 中这样是不会报错的。

如果传入的数据比定义的参数少也不会因为数量不匹配而报错：

```js
// 参数 figure(位数) txt(文本) 
function code(figure, txt) {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));
  
  console.log(txt, num2);
}

code(6);
```

打印结果：

```
undefined 556540
```

因为对应的参数 txt 未传入数据，所以在函数中其值为 undefined。

##### 参数默认值

像上面传入的数据的个数比定义的参数少的情况，很容易出现运行结果与预期不符的情况，为了防止这种问题，我们可以给参数设置默认值：

```js
// 参数 figure(位数) txt(文本) 
function code(figure, txt = "随机数：") {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));
  
  console.log(txt, num2);
}

code(6);
```

打印结果：

```
随机数： 556540
```

因为对应的参数 txt 未传入数据，所以在函数中取默认值：“随机数：”。

这里注意写法，我们是用等号 = 给参数赋默认值的。

#### 6.4 函数的返回值

和其他编程语言一样，js中函数可以分为“无返回值”和“有返回值”两种，之前我们写的自定义函数都是无返回值函数，这里我们来讲讲有返回值函数。

```js
let num = Math.random();
```

Math.random() 就是一个有返回值的内置函数，它会返回生成的随机数。

现在我们改造一下之前写的可定制位数的随机数函数，写个有返回值的自定义函数：

```js
// 参数 figure(位数)
function code(figure) {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));

  // 用“return”把生成的随机数作为函数的结果返回
  return num2;
}

let result = code(6);
console.log(result);
```

运行结果：

```
556540
```

这里我们用“return”把生成的随机数作为函数的返回值返回，然后把返回值赋给了变量 result，再打印 result，得到的就是“556540”这个结果。

函数是否需要返回值是看实际需求的，如果我们只是为了看看生成的随机数，完全可以直接在函数中打印出来。

但如果我们要拿这个随机数做验证码的话，后续还要根据这个随机数对用户输入的内容进行验证的话，就需要写个变量把随机数保存起来了：

```js
// 用户输入的验证码
let userCode = 682314;

// 参数 figure(位数)
function code(figure) {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));
  
  return num2;
}

let result = code(6);

// 后续的验证
if (result === userCode) {
  console.log("验证码正确");
} else {
  console.log("验证码错误");
}
```

从上面的例子中我们知道，在函数中使用 return 可以返回 return 语句所带的那个表达式。

那如果在 return 语句之后，还有别的语句，这些语句还会执行吗？

答案是不会。

##### 函数中 return 后的语句将不会执行

我们来看一个例子：

```js
// 参数 figure(位数)
function code(figure) {
  const num1 = Math.random() * 0.9 + 0.1;
  const num2 = Math.floor(num1 * Math.pow(10, figure));
  
  return num2;

  console.log("return 之后的语句");
}

let result = code(6);
console.log(result);
```

**注意：在函数中遇到return语句，就直接返回return后面的那个表达式的值，后面即使还有语句，也不会被执行。**



#### 6.5 内置函数——计时器1

我们常在注册、登录时遇到验证手机号的情况，点击获取验证码之后，为了防止用户频繁获取验证码，我们会在惦记获取后开始倒计时60s，在这段时间里用户不能再次获取验证码。

倒计时每一秒会更新一下，这个可以用js提供的定时执行代码函数setTimeout()和setInterval()来完成。这个定时执行代码的功能叫做定时器（timer）.

延时执行setTimeout()

setTimeout 函数用来指定某个函数或某段代码，在多少毫秒之后执行，它返回一个整数，表示定时器的编号，以后可能用来取消这个定时器。

setTimeout 函数的基础语法如下：

![img](https://document.youkeda.com/P3-4-HTML-CSS/6/3.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

setTimeout函数接受两个参数，第一个参数func | code 是将要推迟执行的函数名或者一段代码，第二个参数delay时推迟执行的毫秒数。

一下时setTimeout的三种写法，大家关注它的第一个参数的写法和运行顺序：

```js
console.log(1);

/**
 * 第一个参数是代码，注意代码需用引号包裹，否则会立即执行代码
 * 第二个参数是 1000，即 1000ms 后执行 console.log(2)
 */
setTimeout('console.log(2)', 1000);

/**
 * 第一个参数是匿名函数
 * 第二个参数是 2000，即 2s 后执行 console.log(3)
 */
setTimeout(function () {
  console.log(3);
}, 2000);

// 第一个参数是函数名，注意函数名后不要加小括号“()”，否则会立即执行 print4
setTimeout(print4, 3000);

console.log(5);

function print4() {
  console.log(4);
}
```

运行结果：

```js
1;
5;
2;
3;
4;
```

观察上述代码运行顺序：

```js
// 立即执行
console.log(1);
// 立即执行
console.log(5);
// 1s 后执行
console.log(2);
// 2s 后执行
console.log(3);
// 3s 后执行
print4(); // 即：console.log(4)
```

从运行结果可以看出，setTimeout 可以指定某个函数或某段代码，在多少毫秒之后执行，执行一次。

现在我们用 setTimeout 来做验证码的 60s 倒计时，目标效果是每隔一秒打印出剩余秒数。

虽然 setTimeout 只能执行一次，但是我们可以用递归的方式来写计时器。

> 注意，函数可以调用本身，这就是递归（recursion）。

每隔一秒会执行一次代码，每次执行的代码要能够：

1. 打印剩余秒数；
2. 将秒数减一；
3. 如果剩余秒数 >0，则调用 setTimeout 在一秒后重复上述的 1、2、3，否则不再调用，并清除计时器，即计时结束；

```js
// 首先定义计时总秒数，单位 s
let i = 60;

// 定义变量用来储存定时器的编号
let timerId;

// 写一个函数，这个函数即每次要执行的代码，能够完成上述的 1、2、3
function count() {
  console.log(i);
  i--;
  if (i > 0) {
    timerId = setTimeout(count, 1000);
  } else {
    // 清除计时器
    clearTimeout(timerId);
  }
}

// 首次调用该函数，开始第一次计时
count();
```

点击播放上述代码，查看运行结果：

代码演示



我们在 count 方法里调用 count 方法，实现了倒计时的效果。

##### 回调函数

用生活中当例子来解释回调函数就是：

你去商店预定中秋的月饼，预定的时候留下了你的手机号。等月饼到货后，店员给你打电话通知你去取。

手机号：回调函数； 到货：触发回调函数的具体条件； 到货后给你打电话：调用回调函数；

上面讲到的定时器 setTimeout 的第一个参数即“回调函数”，我们把函数指针（指向函数的指针变量）作为参数传给 setTimeout，当延时时间到了（触发条件达成）之后，就会通过函数指针调用函数，即调用回调函数。

除了定时器 setTimeout 中会用到回调函数，其实在实际开发中，我们也常会遇到要用回调函数的时候。

#### 6.6 内置函数——计时器2

下面我们来看setInterval，它的用法与setTimeout完全一致，区别仅仅在于set Interval制定某个任务每隔一段时间就执行一次，也就是无限次的定时执行。

##### 无限调用setInterval

setInterval 函数基础语法如下：

![img](https://document.youkeda.com/P3-4-HTML-CSS/6/4.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

现在我们用setInterval 来实现1s打印数字1:

```js
let timer = setInterval(print, 1000);

function print() {
  console.log(1);
}
```

上述代码能够每隔 1s 打印数字 1，但是这离我们的计时器还有三个地方需要改进：

1. 上述代码是在 1s 后开始第一次打印，而计时器是立即进行第一次打印（打印 60），1s 后再进行第二次打印的；
2. 每次打印的数字是不同的；
3. 计时器是有限次数，不是无限调用；

要做到第一个点很容易，调整代码执行顺序如下即可：

```js
print();
let timer = setInterval(print, 1000);

function print() {
  console.log(1);
}
```

现在实现第二点，我们参考 setTimeout 的写法，先定义计时总秒数，每执行一次打印就将秒数减一即可：

```js
let i = 60;
print();
let timer = setInterval(print, 1000);

function print() {
  console.log(i);
  i--;
}
```

现在我们来解决第三个问题，这个问题也是比较容易的，当 i 减少到 0 的时候，应该停止再次调用 print 方法，即清除计时器，我们用以下语句来清除计时器：

```js
clearInterval(timer);
```

修改一下代码：

```js
let i = 60;
print();
let timer = setInterval(print, 1000);

function print() {
  console.log(i);
  i--;
  if (i < 1) {
    clearInterval(timer);
  }
}
```

### <7> 对象

#### 7.1 对象概述

对象（Object）是 JavaScript 语言的核心概念，也是最重要的数据类型。

##### 什么是对象

什么是对象？简单说，对象就是一组“键值对“（key-value）的集合是一种无序的复合数据集合：

![img](https://document.youkeda.com/P3-4-HTML-CSS/7/1.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

- 大括号：定义一个对象
- person：定义的对象被赋值给
- `person`，则`person`将指向这个对象；
- `name:'henry'`：键值对（key: value），键值之间用`:`隔开；
- `age: 18`：键值对（key: value）；
- 一个对象中可以包含多个键值对，每个键值对之间用`,`隔开，最后一个键值对后可以加`,`，也可以不加。

这里要注意，当一个对象被赋值给`person`，在`person`中保存的其实是对象的内存地址。而不是对象本身。这种赋值被称为“引用”。

这种定义对象的方法称为“字面量”。

##### 键名

对象的键名基本都是字符串，键名加不加引号是一样的：

```js
let person = {
  name: 'henry',
  age: 18
}

// 和上面的写法意思一样
let person = {
  'name': 'henry',
  'age': 18
}
```

##### 方法

对象的每一个键名又称为“属性”（property），它的“键值”可以是任何数据类型，当它是函数的时候，我们把这个属性称为“方法”，它可以像函数那样调用：

```js
let person = {
  name: 'henry',
  age: 18,
  run: function() {
    console.log('running');
  }
}

person.run();
```

##### 对象的创建

除了上面提到的“字面量”方法，我们还可以通过构造函数创建新对象。

使用构造函数创建对象，我们需要两步走：

1. 创建一个构造函数，构造函数的名称常根据大驼峰命名法命名；
2. 通过 new 创建对象实例；

其中，构造函数可以声明对象的名称、属性和方法。

> 大驼峰命名法：当变量名或函数名是由一个或多个单词连结在一起，而构成的唯一识别字时，所有单词的首字母均需要大写。

让我们来实操一下，用构造函数来创建 person 对象：

```js
// 第一步：创建构造函数
function People(name, age) {
  this.name = name;
  this.age = age;
}

// 第二步：通过 new 创建对象实例
let person = new People('henry', 18);
console.log(person);
```

首先我们为“人”（people）创建了一个构造函数 People，然后用构造函数 People，创建了对象实例 person。

注意，构造函数 People 中的 `this` 是函数运行时，在函数体内部自动生成的一个对象，只能在函数体内部使用。this 就是函数运行时所在的环境对象。

我们用这个构造函数来创建一个对象实例，那么构造函数里的 `this.name = name` 就表示将传入的参数 `name` 赋值给对象实例中对应的属性 `name`。

#### 7.2 自定义对象的属性操作

上一节中我们定义的`person`对象就是一个自定义对象

我们已经知道对象是由键值对组成的无序的复合数据集合，键值可以是任何数据类型。当它是函数的时候，我们把它称为“方法”，调用方法和调用函数的写法一样：

```js
let person {
	name: 'henry';
	age: 18,
	run:function() {
		console.log('running');
	}
}
person.run();
```

那如果我们要读取对象中的其他属性该怎么办呢？

##### 属性的读取

`JavaScript`中有两种方法读取一个对象的属性：点运算和方括号运算符。

```js
let person {
  name: 'henry';
  age: 18;
}
console.log(person.name);
console.log(person['name']);
```

上述代码将输出：

```js
henry
henry
```

两种写法的效果是一样的，都能读取对应属性的值，但是方括号运算符的方括号中可以是一个变量。

这句话怎么理解呢，我们来看一下代码：

```js
let person = {
	name: 'henry';
  age: 18;
}
let variable = 'name';
console.log(person[variable]);

variable = 'age';
console.log(person[variable]);
```

这里我们定义了一个变量`variable`，在读取对象属性的时候，使用了方括号运算符，然后在方括号中使用了变量`variable`.



**代码结果:**

由于变量开始是name，而后变成age：

```js
henry
18
```

我们已经知道，对象中属性的值可以是任何数据类型，那如果某个属性的值是对象，该怎么读取这个键值对象中的属性呢？

我们还是用点运算符或者方括号运算符：

```js
let person = {
	name: 'henry',
  age: 18,
  parents:{
    papa: 'jack',
    mama: 'mary';
  }
}
console.log(person.parents.papa);
console.log(person['parents']['mama']);
```

上述代码将输出：

```js
jack
mary
```

像`person.parents.papa` 或 `person['parents']['mama']` 这样的写法被称为“链式引用”。

##### 属性的赋值

属性的赋值和读取一样，可以通过点运算符和方括号运算符完成：

```js
let person = {
  name: 'henry',
  age: 18
}

person.name = 'tom';
person['age'] = 10

console.log(person.name);
console.log(person.age);
```

输出：

```js
tom
10
```

##### 属性的查看

查看一个对象本身的所有属性，可以使用Object.keys方法：

```js
let person = {
  name: 'henry',
  age: 18;
}
console.log(Object.keys(person));
```

> 上述代码中的Object，是JavaScript提供的基础对象，JavaScript的所有其他对象都继承自Object对象，即那些对象都是Object的实例。keys是Object对象的一个静态方法。

```js
['name','age']
```



可以看到`Object.keys(person)`返回的是一个数组，这个数组由`person`对象的所有属性名构成。

##### 属性的删除和增加

如果要删除对象中的某个属性，可以使用delete命令

````js
let person = {
	name : 'henry',
  age: 18
}
delete person.name;
console.log(person)
````

输出：

```
{age: 10}
```

增加一个属性就更容易了：

```js
let person = {
	name: 'henry',
  age: 18;
}
person.gender = 'male';
```

输出：

```js
{name: 'henry' , age: 18 , gender: 'male'}
```

#### 7.3 遍历对象属性

如果想要在一个对象中查找某个符合条件的属性，我们就需要遍历对象了。



在JavaScript中我们可以通过`for...in`或借助`Object.keys`来实现。

##### 用`for...in`遍历属性

我们先来看如何用`for...in`遍历对象中的各个属性值。

```js
let person = {
	name: 'henry',
  age: 18;
}
for (let key in person) {
  console.log('键名：' + key + '键值：' + person[key]);
}
```

借助`Object.keys`遍历属性

由于Object.keys方法返回的是一个由对象中所有属性名组成的数组，我们可以借助这一点来遍历对象。

```js
let person = {
  name: 'henry',
  age: 18;
}
let keys = Object.keys(person);
for(let i<0 ; i < keys.length ; i++) {
  console.log('键名：' + keys[i] + '键值：' + person[keys[i]]);
}
```

#### 7.4 对象的继承

我们知道，Java中是有“继承”这个概念的，在JavaScript也有。之前我们也提到过：

> Object 是 JavaScript 提供的基本对象，JavaScript的所有其他对象都继承自 Object 对象，即那些对象都是Object的实例。keys是Object对象的一个静态方法。

就是说，我们之前学习的“自定义对象”，其实就是继承自JavaScript提供的Object对象的。

因此，除了“字面量”和自定义的构造方法创建对象外，我们还可以用JavaScript提供的构造函数Object()或者“继承”来创建对象。

```js
// 字面量
let o1 = {
  name: 'alice',
};

// 构造函数
let o2 = new Object();
let o3 = new Object();

// 继承
function O4() {
}; 
O4.prototype = o1; 
let o4 = new O4();
```

在上面的代码中，最后一种方法创建的 o4 对象继承自 o1，那么 o1 就是 o4 的原型。

##### 原型

什么是原型，原型其实也是 JavaScript 中的一个对象。那为什么要提出原型的概念呢，这是为了找对象继承的上一级对象。

o1 继承自 Object，Object 就是 o1 的原型。

o4 继承自 o1，o1 就是 o4 的原型。

一个对象，它称呼继承的上一级对象为原型，它自己也可以称作原型链下一级对象的原型。

##### 属性是否存在：in

我们可以用 in 运算符来判断对象是否拥有某个属性：

```js
let person = {
  name: 'henry',
  age: 18,
};

'name' in person;
'gender' in person;
'toString' in person;
```

输出：

```js
true;
false;
true;
```

`toString` 是 Object 对象的属性。person 继承自 Object 所以也有这个属性。

可见，由于继承的存在，一个对象中的属性分成了两类：继承属性和自身属性。

之前我们用到的 Object.keys 方法返回的属性就包括了这两种属性。

那么我们要如何判断对象自身属性中是否拥有某个属性呢？

这个也不难，我们可以用 Object 对象提供的 hasOwnProperty 方法进行判断。

##### 自身属性是否存在：hasOwnProperty

```js
let person = {
  name: 'henry',
  age: 18,
};

person.hasOwnProperty('name');
person.hasOwnProperty('gender');
person.hasOwnProperty('toString');
```

输出：

```js
true;
false;
false;
```

可以看到toString 不属于对象person的自身属性。



##### Object 与 JSON、Map的区别

JavaScript中有几个写法和对象长得相似的概念，JSON、Map，大家了解即可。

##### JSON

JSON是一种轻量级的文本数据交换格式，它用JavaScript的语法书写，但独立于这种语言，可以认为这是编程语言间用于传递数据而约定的数据格式。

JSON格式和JavaScript对象的转换

1. JSON.parse(): JSON格式 => JavaScript对象

```js
// 一个 JSON 字符串
const jsonStr =
  '{"sites":[{"name":"Runoob", "url":"www.runoob.com"},{"name":"Google", "url":"www.google.com"},{"name":"Taobao", "url":"www.taobao.com"}]}';

// 转成 JavaScript 对象
const obj = JSON.parse(jsonStr);
```

2. JSON.stringify: JavaScript对象 => JSON 格式

现在我们把上面的到的obj转换成JSON格式：

```js
const jsonStr2 = JSON.stringify(obj);
```

##### Map

Map 和 Object 很相似，都可以保持键值对，但是他们仍有些重要的区别：

1. 一个Object的键通常是字符串，但一个Map的键可以是任意值，包括函数、对象、基本类型，因此Map会方便很多；
2. Map中的键值是有序的，而添加到对象中的键则不是；
3. Map的键值对个数可以直接获取，Object则要借助Object.keys()等计算得到；
4. Map可直接进行迭代，Object则需要借助Object.keys()等；
5. Map不存在键名和原型键名冲突问题，可以直接覆盖，Object则不行。

从某种程度上来说，Map比Object更灵活方便，但是考虑到Map不能直接转化为JSOn格式进行通讯，所以我们可以把Map作为Object的补充来使用。



#### 7.5 内置对象——Math、Storage

##### Math对象

在上一章写随机数到时候我们用到了Math.random方法，其实Math也是JavaScript到一个原生对象，它能提供各种数学功能，该对象不是构造函数，不能生成实力，所有的属性和方法都必须在Math对象上调用。

之前我们已经接触了Math.random 和 Math.floor 方法。

现在我来看看Math提供的其他用途。

##### 常量

Math对象的静态属性，提供以下一些数学常数：

```js
Math.E // 常数e。
Math.LN2 // 2 的自然对数。
Math.LN10 // 10 的自然对数。
Math.LOG2E // 以 2 为底的e的对数。
Math.LOG10E // 以 10 为底的e的对数。
Math.PI // 常数π。
Math.SQRT1_2 // 0.5 的平方根。
Math.SQRT2 // 2 的平方根。
```

我们会用到比较多的一般是常数π，即 Math.PI。



##### 静态方法

Math对象提供以下一些静态方法：

```js
Math.abs() // 绝对值
Math.ceil() // 向上取整
Math.floor() // 向下取整
Math.round() // 四舍五入取整
Math.max() // 最大值
Math.min() // 最小值
Math.pow() // 指数运算
Math.sqrt() // 平方根
Math.log() // 自然对数
Math.exp() // e的指数
Math.random() // 随机数
```

> 注意，以上方法除了Math.random()都需要传入合适的参数，即需要处理的数字。

这里我们注意几个取整方法.

使用的时候，给方法传入需要处理的数字即可：

```js
Math.ceil(4.6) // 向上取整，取大于等于 x，并且与它最接近的整数。
Math.floor(4.6) // 向下取整，取小于等于 x，并且与它最接近的整数。
Math.round(4.6) // 四舍五入取整，取与 x 最接近的整数。
```

输出：

```
5
4
5
```

除了Math之外，我们还要介绍一个常用的内置对象：Storage。

##### Storage 对象

Storage 借口用于脚本在浏览器保存数据。两个对象部署了这个借口：window.sessionStorage 和 window.localStorage。

sessionStorage 保存的数据用于浏览器的一次会话(session)，当会话结束（通常是窗口关闭），数据被清空；localStorage 保存的数据长期存在，下一次访问该网站的时候，网页可以直接读取以前保存的数据。

我们主要看一下window.localStorage 的用法：

**数据的存入：setItem**

写法：

```js
window.localStorage.setItem('myLocalStorage' , 'storage value');
```

window.localStorage.setItem('key','value)方法接受两个参数：

1. key：键名
2. value：键值

两个参数都是字符串，不是字符串的参数会被转换成字符串后再存入浏览器。

> 打开网页的开发者工具（右键 => 检查 => application => LocalStorage)，查看存储情况。
>
> ![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/7/4.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

注意，如果要存入的数据不是字符串类型的数据，最好先转换成字符串类型，比如要存入一个对象，可以这么写：

```js
const obj = {
  name: 'henry',
  age: 18
}
const value = JSON.stringify(obj);
window.localStorage.setItem('myLocalStorage', value);
```

> JSON.stringify() 方法可以将一个 JavaScript 值（对象或者数组）转换为一个 JSON 字符串。

##### 读取数据：getItem

写法：

```js
window.localStorage.getItem('myLocalStorage');
```

window.localStorage.getItem('key') 接受一个参数，即键名。

##### 清除缓存：clear

写法：

```js
window.localStorage.clear();
```

#### 7.6 内置对象——String

JavaScript 原生提供的三个包装对象之一就是`String`（另外两个是Number、Boolean)。它给字符串提供了很多好用的方法，但是我们只要掌握很少的几个就足够了，我们一起来看一下。

> 包装对象：原生对象可以把原始类型的值变成（包装成）对象。
>
> `let v2 = new String('abc');`
>
> 包装对象的最大目的：1.使得JavaScript的对象涵盖所有的值；2.使得原始类型的值可以方便地调用某些方法（比如下面的这些方法）。

##### 字符串长度：length

```js
let len = 'here is an apple'.length;
```

> 字符串中空格也是计算在长度之内的。

##### 查找字符：indexOf()

从字符串中查找某个字符串是否存在：

```js
let str = 'here is an apple';
const index = str.indexOf('an');
console.log(index);
```

当 str 中存在子字符串 an 时，返回的值为 an 中的 a 所在的下标（下标从 0 开始计），即 8。

当 str 中不存在子字符串 an 时，返回的值为 -1。

##### 去掉两端空格：trim()

我们在输入内容的时候常常会遇到多输入空格的时候，这时候就可以用`trim()`把字符串开头和结束位置的空格去掉了。

```js
// 'here' 之前有一个空格，'apple' 之后有三个空格
let str = ' here is an apple   ';
const trimedStr = str.trim();
console.log(str.length);
console.log(trimedStr.length);
```

> 注意：`trim`是去掉字符串前后的空格，不论前后有多少空格，都会去掉，但不会去掉中间的空格。另外，`trim()`不会改拜年原字符串`str`，而是复制一份原字符串，修改后返回给`trimedStr`

##### 截取字符串：substring/substr

如果要截取一个字符串中的一部分，可以用`substring`或`substr`

比如我们现在有一个URL

```js
https://www.youkeda.com/userhome#collecc
```

要求截取其中#之后的内容，可以这样做：

```js
let url = 'https://www.youkeda.com/userhome#collect';

// 首先找到 # 后第一个字母的下标
const index = url.indexOf('#') + 1;

// 有 hash 才能进行截取，没有就直接提示不存在
if (index) {
  // 用 substring 截取字符串
  const hash1 = url.substring(index, url.length);

  // 计算 hash 的长度
  const lenHash = url.length - index;
  // 用 substr 截取字符串
  const hash2 = url.substr(index, lenHash);

  console.log(hash1);
  console.log(hash2);
} else {
  console.log('不存在 hash');
}
```

- substring(start, end)： start —— 要截取的字符串的开始下标 end —— 要截取的字符串的结束下标。
- substr(start, len)： start —— 要截取的字符串的开始下标 len —— 要截取的字符串的长度。

> 注意，substring 和 substr 的第二个参数不写的时候，会一直截取到字符串结束为止。

它们和 `trim()`方法一样都不会改变原字符串，而是返回处理后的字符串。

##### 分个字符串：split

`split`方法按照给定规则分割字符串，返回一个由分割出来的子字符串组成的数组：

```js
const splitedStr = 'a|b|c'.split('|');
console.log(splitedStr);
```

`split` 也不会改变原字符串，而是返回一个由分割出来的子字符串组成的数组。

##### 小结

关于字符串我们需要掌握的几个基础用法：

| 属性/方法           | 作用                                                         |
| ------------------- | ------------------------------------------------------------ |
| str.length          | 返回字符串长度                                               |
| str.indexOf(sub)    | 返回子字符串 sub 的开始下标，不存在则返回 -1 注意：这里的参数 sub 是个字符串变量 |
| str.trim()          | 字符串前后去空格                                             |
| str.substring(s, e) | 截取下标从 s 到 e 的子字符串 注意：这里的参数 s 和 e 是个数字变量 |
| str.substr(s, len)  | 截取下标从 s 开始，长度为 len 的子字符串 注意：这里的参数 s 和 len 是个数字变量 |
| str.split(pattern)  | 按规格 pattern 分割字符串 注意：这里的参数 pattern 是个字符串变量 |

#### 7.7 内置对象——Array

Array 是 JavaScript的原生对象之一，它为数组提供了很多使用的方法，这里我们学习其中的几个。

##### 连接数组：jion()

jion()方法以制定参数作为分隔符，将所有数组成员连接为一个字符串返回。如果不提供参数，默认用逗号分隔。

```js
let arr = [1,2,3,4];

arr.jion(" ");
arr.jion(" | ");
arr.jion();
```

这个方法和字符串里的`split`方法正好是一对作用相反的方法：

```js
let str = "a|b|c";

const splited = str.split("|");
console.log(splited);

const joined = splited.jion("|");
console.log(jioned);
```

`jion()`方法不会改变原数组。

##### 倒序排列：reverse()

reverse方法用于颠倒排列数组元素，返回改变后的数组。：

```js
let arr = ["a", "b", "c"];

arr.reverse(); // ["c", "b", "a"]
arr; // ["c", "b", "a"]
```

> 注意，该方法将改变原数组。

这个方法对原本有序的数组用起来很方便，比如原来是按时间顺序排列，现在要倒序，直接使用 `reverse()` 即可。

那如果数组原本就是无序的，该怎么排序呢？这里我们会用到 `sort()` 方法。

##### 排序：sort()

sort 方法对数组成员进行排序，默认是按照**字典顺序**排序。如果想让 sort 方法按照自定义方式排序，可以传入一个函数作为参数。

现在我们将下面的数组按照人物年龄从小到大排列：

```js
let arr = [
  { name: "jenny", age: 18 },
  { name: "tom", age: 10 },
  { name: "mary", age: 40 },
];

arr.sort(function (a, b) {
  return a.age - b.age;
});

console.log(arr);
```

这里我们传入了一个函数，这个函数有两个参数，即进行比较的两个数组成员，原数组中 a 排在 b 之前。

这个函数有个返回值，当返回值大于 0 时，表示第一个成员应该排在第二个成员之后，否则排在第二个成员之前。

> 注意，该方法将改变原数组。

##### 遍历：map/forEach

遍历数组我们之前用的是 `for` 循环，但其实 JavaScript 为我们提供了两个很方便的遍历方法：map 和 forEach。

##### 有返回值的遍历：map

先看 map 方法的使用，它接受一个函数，然后将数组的所有成员依次传入这个参数函数，最后把每一次的执行结果组成一个新数组返回：

```js
let arr = [
  { name: "jenny", age: 18 },
  { name: "tom", age: 10 },
  { name: "mary", age: 40 },
];

// elem: 数组成员
// index: 成员下标
// a: 整个数组
const handledArr = arr.map(function (elem, index, a) {
  elem.age += 1;
  console.log(elem, index, a);
  return elem.name;
});

console.log(arr);
console.log(handledArr);
```

map 方法的参数函数可以有三个参数：elem, index, a。

- elem：表示依次传入的数组成员
- index：表示依次传入的数组成员所对应的下标
- a：表示整个数组

在上面的代码中，map 方法的返回值是一个由 `return` 后的内容 `elem.name` 组成的数组。

##### 无返回值的遍历：forEach

forEach 的用法和 map 基本一致，不过 forEach 没有返回值：

```js
const handledArr = arr.forEach(function (elem, index, a) {
  elem.age += 1;
  console.log(elem, index, a);
  return elem.name;
});

console.log(handledArr);
```

输出：

```js
undefined;
```

> 注意，当你在 map 和 forEach 之间难以选择时，可以想一下你是否需要返回值，map 会返回操作后的数组，forEach 则没有返回值。

##### 小结

关于数组我们需要掌握的几个基础用法：

| 属性/方法         | 作用                                                         |
| ----------------- | ------------------------------------------------------------ |
| arr.join(pattern) | 按规则 pattern 连接数组，返回字符串                          |
| arr.reverse()     | 将原数组倒序排列                                             |
| arr.sort(func)    | 自定义排序，根据传入的参数函数 func 将数组成员排序           |
| arr.map(func)     | 根据传入的参数函数 func 对数组进行遍历操作，返回操作后的数组 函数有三个参数，依次为：数组成员、对应下标、整个数组 |
| arr.forEach(func) | 根据传入的参数函数 func 对数组进行遍历操作，无返回值 函数有三个参数，依次为：数组成员、对应下标、整个数组 |

#### 7.8 内置对象——Date

在实际的工作中为们常常会遇到要处理时间的情况：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/7/2.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

因此很有必要学习一下JavaScript提供的时间库的一些功能。

JavaScript提供一个原生的时间库：`Date`对象。它以国际标准时间（UTC）1970年1月1日00:00:00作为时间的零点，可以表示的范围是前后各一亿天（单位为毫秒）。在这里我们只学习其中一些必须的基础内容。

##### 获取当前时间：new Date（）

我们可以把Date作为一个构造函数，用new命令生成一个时间对象的实力，在不加参数的情况下，返回的是当前时间：

```js
let now = new Date();
console.log(now);
```

那如果给构造函数传入一些参数的话，就能够生成特定的时间对象了，这里可以传入数字，字符串，毫秒数：

```js
// 传入表示“年月日时分秒”的数字
let dt1 = new Date(2020, 0, 6, 0, 0, 0);
console.log(dt1);

// 传入日期字符串
let dt2 = new Date("2020-1-6");
console.log(dt2);

// 传入距离国际标准时间的毫秒数
let dt3 = new Date(1578240000000);
console.log(dt3);
```

输出结果：

```js
2020-01-05T16:00:00.000Z
2020-01-05T16:00:00.000Z
2020-01-05T16:00:00.000Z
```

> 注意，传入表示“年月日时分秒”的数字时，1. 如果只传入一个数字，会被认为传入的是毫秒数；2. 月份的范围是 0-11，而不是 1-12。

##### 日期运算

###### 时间差：毫秒数

两个时间对象是可以直接相减的，返回值为两者的毫秒数差：

```js
let dt1 = new Date(2020, 2, 1);
let dt2 = new Date(2020, 3, 1);

// 求差值
let diff = dt2 - dt1;

// 一天的毫秒数
let ms = 24 * 60 * 60 * 1000;

console.log(diff / ms); // 31
```

可以看到，2020 年 3 月 1 日和 2020 年 4 月 1 日之间相差的时间正好为 31 天。

###### 早晚比较：大小于符号

如果要比较两个时间的早晚，可以直接使用 `>`或者`<`：

```js
let dt1 = new Date(2020,2,1);
let dt2 = new Date(2020,3,1);

console.log(dt1>dt2); //false
console.log(dt1<dt2); //true
```

##### 解析日期字符串：Date.parse()

Date.parse方法用来解析日期字符串，返回该时间距离时间零点(1970年1月1日00:00:00) 的毫秒数：

```js
let dt = Date.parse("2020-1-6");
console.log(dt); // 1578240000000
```

`Date.parse()`方法可以把日期字符串转成距离时间零点的毫秒数。

时间对象中有三大类方法to方法、get方法和set方法，这里我们会学习这两大类中的一部分方法。

##### 时间对象转时间字符串的：to方法

to方法有很多，我们来看其中的`toJSON`方法：

```js
let dt = new Date();
let dtStr = dt.toJSON();

console.log(dtStr); // 2022-06-07T02:34:02.621Z
```

打印的时间和当前的时间差8个小时。这是因为打印的时间是现在UTC时区的时间，而我们的时间是东八区时间，比国际标准时间快8个小时。

##### 获取时间对象的年/月/日：get方法

Date对象提供了一系列get方法，用来获取实例对象某个方面的值。

```js
let dt = new Date();
dt.getTime(); // 返回实例距离1970年1月1日00:00:00的毫秒数。
dt.getDate(); // 返回实例对象对应每个月的几号（从1开始）。
dt.getDay(); // 返回星期几，星期日为0，星期一为1，以此类推。
dt.getFullYear(); // 返回四位的年份。
dt.getMonth(); // 返回月份（0表示1月，11表示12月）。
dt.getHours(); // 返回小时（0-23）。
dt.getMilliseconds(); // 返回毫秒（0-999）。
dt.getMinutes(); // 返回分钟（0-59）。
dt.getSeconds(); // 返回秒（0-59）。
```

> 注意，所有这些 get*方法返回的都是整数，不同方法返回值的范围不一样： 分钟和秒：0 到 59 小时：0 到 23 星期：0（星期天）到 6（星期六） 日期：1 到 31 月份：0（一月）到 11（十二月）

- 除了“日期”外，其他的时间范围都是从 0 开始的。

以上方法了解即可，需要用到的时候在 MDN 上进行查询即可。

现在我们来尝试用 dt.getFullYear() 来获取当前的完整年份：

```js
let dt = new Date();
let year = dt.getFullYear();

console.log(year);

```

##### 设置时间对象的年/月/日：set方法

set方法和get方法正好相反，它能够设置时间对象的某个方面的值。

```js
let dt = new Date();
dt.setTime(ms); // 设置实例距离1970年1月1日00:00:00的毫秒数。
dt.setDate(date); // 设置实例对象对应每个月的几号（从1开始）。
dt.setFullYear(year); // 设置四位的年份。
dt.setMonth(month); // 设置月份（0表示1月，11表示12月）。
dt.setHours(hour); // 设置小时（0-23）。
dt.setMilliseconds(ms); // 设置毫秒（0-999）。
dt.setMinutes(min); // 设置分钟（0-59）。
dt.setSeconds(sec); // 设置秒（0-59）。
```

> set 方法没有setDay方法，因为星期几是计算得到的。

同样的，以上方法了解即可，需要用到的时候在MDN上进行查询即可。

现在我们来尝试用dt.getFullyear()来获取当前的完整年份：

```js
let dt = new Date();
dt.setFullYear(2030);

console.log(dt);
```

##### 小结

时间对象、日期字符串和毫秒数之间是可以相互转换的，一图胜千言，我们把转换的规则总结成了一张图：

![img](https://qgt-document.oss-cn-beijing.aliyuncs.com/P3-4-HTML-CSS/7/3.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

### <8> BOM

#### 8.1 BOM

在之前的7章中，我们已经学会了`JavaScript`的基础语法。从本节开始，我们将前面的基础语法与`HTML`，`CSS`一起联合起来使用，重点学会页面交互过程。

##### BOM

我们知道为了让网页能显示出来，我们的在浏览器中输入网址，敲击回车，浏览器能自动帮我们渲染网页内容。和浏览器渲染有关的对象，我们叫做浏览器对象模型（Brower Object Model) -----BOM。

**BOM**是由一系列相关对象构成，每个对象都提供了很多方法和属性。

但BOM缺乏标准，BOM属于约定俗称，比如Chrome怎么实现，FireFox、IE等等就照抄一下。所以不同浏览器并不完全相同，在前端有一门高级技术叫做浏览器兼容处理，也就是处理这类问题，我们在之后会涉及到。

现在业界主要以 **Chrome** 为准（这也是我们希望大家用Chrome进行学习到原因）。在这里我们主要学习BOM一些共同的对象和API。

##### BOM对象

在BOM里最重要的对象有4个，分别如下：

- window （窗口）：window是整个网页的框架，每个网页的内容都是装载在window里面
- navigator （浏览器）：navigator 里面存储浏览相关信息
- history （历史）：我们知道每个网页都可以前进后退，history是拿来存储整个网页栈的。
- screen （显示屏幕）：screen 包含我们显示屏幕的信息，这个是硬件信息。
- Location （地址）：location 包含当前访问的地址（网址）信息。

下面用页面演示一下：

![img](https://style.youkeda.com/img/course/f4/8/1.jpeg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

特别强调几点

1. screen是整个电脑唯一的
2. navigator 是整个浏览器唯一的，如果有多个浏览器就会有多个navigator
3. window是每个网页唯一的，每个网页都有一个独立的window
4. history，location是每个网页的信息，当然也是网页唯一的。

#### 8.2 window

##### HTML中嵌入JavaScript

在所有的BOM中最重要的是window对象，我们这节来详细学习一下。

在之前的学习中我们只是单纯写`javascript`，我们这次把javascript卸乳道HTML代码中，方便执行。

我们在页面中打印 学习 ，代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>study</title>
  </head>
  <body>
    <h1>学习</h1>
    <script src="./index.js"></script>
  </body>
</html>
```

我们在`body`底部加入`<script src="./index/js"></script>`,嵌入执行脚本，然后在`index.js`脚本中加入`javascript`代码，执行一下：

最后在控制台打印出了

````js
"学习"
````

##### window 

在`JavaScript`学习中，最好用的学习和排查问题方法就是-- console.log，在这里我们打印一下window，看看window到底是什么

JSConsole的内容如下图所示：

![img](https://style.youkeda.com/img/course/f4/8/2.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

我们看到`window`对象中，有很多**方法**，比如`alert`, `confirm` …… 还有一些**属性对象**比如： `console`, `screen`, `navigator`, `location`……

如果看不清楚，我们还可以打开 MDN 文档(https://developer.mozilla.org/zh-CN/docs/Web/API/Window)

官方解释为：

> 1. window 对象表示一个浏览器窗口或一个 frame 框架，它处于对象层次的**最顶端**，它提供了处理浏览器窗口的方法和属性。
> 2. window 对象是浏览器对象中的**默认对象**，所以可以隐式地引用 window 对象的属性和方法。在浏览器环境中，添加到 window 对象中的方法、属性等，其作用域都是全局的。

第一点不难理解，我们主要解释第二点，什么叫做默认对象？什么叫做隐式引用？

举个例子：

```js
console.log('优课达');
window.console.log('优课达');

console.log(navigator);
console.log(window.navigator);

function hello() {}
console.log(hello);
console.log(window.hello);
```

我们看出`console.log`等于`window.console.log`, `navigator`等于`window.navigator`, 甚至自定义的**顶层函数**，也是挂载在 window 下面的。

除此之外，之前讲的`Math对象`，`setTimeout函数`，`setInterval函数`都是挂载在 window 下面，这里课程就不演示了，大家有兴趣自己去尝试一下。

总结一下：

> window 是默认对象，如果是调用 window 上面的方法，可以省略，也可以称为隐式调用 window 上面的属性和方法。

#### 8.3 Location/History

我们继续学习`Location`对象，其用来保存当前网页位置的信息。和之前一样，我们直接使用`console.log`打印出来看看。

可以查看 MDN 文档：https://developer.mozilla.org/zh-CN/docs/Web/API/Location

##### Location 属性

通过文档，我们看到 Location 中常用属性如下：

| 属性     | 值                                                           | 解释                                                         |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| href     | https://resource.youkeda.com/wss_test/5dc54e230f101ed7c2256d0d/5e33d104680dca7ebc7a223b/index.html?time=1580454161498 | href 是整个网页地址                                          |
| hostname | resource.youkeda.com                                         | hostname 是网页域名                                          |
| host     | resource.youkeda.com                                         | host 是网页域名 + 端口信息，在这里端口默认 80 省略了，所有和 hostname 一样 |
| protocol | https                                                        | protocol 代表协议信息                                        |
| origin   | [https://resource.youkeda.com](https://resource.youkeda.com/) | origin 页面来源的域名的标准形式                              |
| pathname | /5dc54e230f101ed7c2256d0d/5e33d104680dca7ebc7a223b/index.html | pathname 包含 url 路径部分                                   |
| search   | ?time=1580454161498                                          | search 表示 URL 参数                                         |

用图表示如下（pathname 太长，部分省略代替）：

![img](https://style.youkeda.com/img/course/f4/8/3.jpeg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

上面的不同属性都表示 URL 的不同部分，大家可以尝试利用这个规则去分析其他网页信息。

###### Location 方法

在 Location 方法中，我们重点只需要掌握一个方法 --- **reload()**。

为了防止无限快速循环，我们设置一个定时器延迟调用 reload。

```js
Location**setTimeout**(() => {

​    window.location.**reload**();

}, 3000);
```

其他方法，大家了解一下即可，几乎不会用到。

##### 跳转到新的地址

我们同样可以修改 Location，直接将网页地址赋值给 Location 即可，代码如下：

```js
window.location = 'https://www.youkeda.com';
```

##### History

**History** 允许操作浏览器的曾经在标签页或者框架里访问的会话历史记录，由这个名称我们得知，History 会存储该窗口的历史记录。

mdn 地址为: https://developer.mozilla.org/zh-CN/docs/Web/API/History

我们以上面跳转到新地址举例，如果原始网页为 `https://www.youkeda.com`， 那 history 中存储为

```js
// 会话记录
['https://www.youkeda.com'];
```

如果我们在网页中点击某个链接，或者使用`window.location = xxx`跳转到`https://www.baidu.com`, 那 history 中存储为

```js
// 会话记录
['https://www.youkeda.com', 'https://www.baidu.com'];
```

后续访问，以此类推。大家学过 JS 基础的话应该能看出来这是一个数组（或者说是列表），在实际存储中用到的数据结构和数组特别类似，叫做**栈**。

在 history 中需要掌握两个方法， **back()**和**forward()**，分别对应到浏览器左上角的返回和前进按钮。

#### 8.4 Navigator/Screen

##### Navigator

**Navigator** 表示用户代理的状态和表示，也就是浏览器基本信息，在这里我们需要了解一个属性--userAgent，代表当前浏览器的用户代理。

结果如下（当然每个人浏览器不同，结果不同）：

```js
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_2) AppleWebKit/537.36 (KHTML, like
Gecko) Chrome/79.0.3945.130 Safari/537.36
```

从这个信息我们可以得知

> *Mozilla 是一个基金会，表示这是一个主流浏览器Intel* **Mac OS X 表示电脑信息为Mac** Chrome/79.0 表示浏览器版本

### <9> DOM

#### 9.1 初识DOM

本章节是整个JavaScript甚至整个前端最核心的内容，所以一定要认真了解。

在之前课程中，我们学习过了HTML，CSS，本章节也掌握了JavaScript的一些基本语法，大家是否有疑问：

前端三板斧，那JavaScript和HTML、CSS有什么联系呢？怎么使用JavaScript来操作HTML和CSS呢？

这就归功于本节课的重点---文档对象模型，Document Object Model 一般我们简称为DOM

官方解释为：

> 文档对象模型（DOM）可以将web页面与脚本或编程语言连接起来。

我们来理解下这句话，有两个重点：

1. web页面

> 这里的web页面也就是之前我们用HTML和CSS绘制的页面，也称作文档。

2. 脚本或编程语言 为什么这里不直说将Web页面和JavaScript语言连接起来，而要绕一下说脚本或编程语言呢？

> 因为DOM是一种规范、或者是一种约定，只要遵循这个规范，那么无论是`JavaScript`，还是`python`，或者`Java`都可以被连接起来。

那紧接着，我们来看看DOM是如何实现连接的。

##### DOM 映射

我们平时写HTML的时候，大多都认为HTML是平面的东西，一堆文字包裹在一堆标签中间，但实际上像HTML和XML这种形式的文档都是树状结构，也对应数据结构中的数。

我们写一个简单的Web页面（HTML代码编写），并尝试将其转换成树。

```html
<html>
  <head>
    <title>youkeda</title>
  </head>
  <body>
    <div>
      <h1>优课达</h1>
      <p>学的比别人好一点</p>
    </div>
  </body>
</html>
```

转换成的树图示如下：

![img](https://style.youkeda.com/img/course/f4/9/1.jpeg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

图示就是一棵倒着的树，最顶部我们称为树根，这棵树就是 DOM 树。

我们总结下 DOM 树特性：

1. 树根是 DOCUMENT，也可以称为整个页面文档
2. 每个 HTML 标签我们称之为 **DOM 节点**，英文为**Node**或者**ELement**
3. 每个 HTML 标签包裹的子标签，在树上体现为分支，称为**儿子节点**。比如上图，`P`和`H1`都是`DIV`的儿子节点。`DIV`同样也是`BODY`的儿子节点。
4. 儿子节点类推可以得知`P`,`H1`是`BODY`的**孙子节点**。
5. 所有`P`, `H1`的长辈，我们称为`P`和`H1`的**祖先节点**。
6. `P`, `H1`是亲兄弟，我们称为**兄弟节点**。

#### 9.2 访问DOM 

##### 获取DOCUMENT

从上节课中我们知道web页面最终会映射到一颗DOM树，DOM树连接网页和JavaScript语言，那我们该怎么获取DOM树的根部元素呢？

很简单，DOCUMENT元素会存在全局变量window下面，我们可以通过如下代码来访问：

```js
window.document;
```

代码演示



最终 JSConsole 中的效果如下：

![img](https://style.youkeda.com/img/course/f4/9/3.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

从 JSConsole 我们知道，`window.document`得到的是一个`HTMLDocument`对象，这个对象内容有点多，大家不需要全部了解，只需要看几个属性即可，比如 document 内容 key 为`documentElement`:

![img](https://style.youkeda.com/img/course/f4/9/4.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

还可以了解一下`body`, `head`属性，分别对应 HTML 中的`body`,`head`内容。

##### Chrome 调试工具

上面的打印结果非常难以阅读，Chrome 浏览器为了方便大家阅读，开发一套开发者工具，大家可以在**非工程目录区域**点击右键，点击**检查**开启开发者窗口，如下图所示：

![img](https://style.youkeda.com/img/course/f4/9/5.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

然后执行下面三个步骤：

1. 开发者窗口里面切换到**Console**面板
2. 再次点击代码演示
3. 可以看到 Console 里面出现 **#document**，这个是 Chrome 单独处理过的，可读性较强（学习平台中的 JSConsole 是最原生的对象类型）。

大家以后可以在此处查看 Console，以后课程内容，我会同时截取两处的图片方便大家查看。

具体操作步骤如下图所示：

![img](https://style.youkeda.com/img/course/f4/9/6.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

从这个结果更能明确发现，`window.document`也就是整个 HTML（网页）内容。

##### 选择器查询

通过上面的代码，我们可以得到了整个网页内容，那如果我们想获取某一个特殊节点应该怎么办呢？我们用 **前端基础课程** 的大作业(**QQ 注册页**）这个复杂的 HTML 代码作为案例。 代码如下：

```html
<!DOCTYPE html>
<head>
  <meta charset="UTF-8" />
  <link rel="stylesheet" type="text/css" href="./index.css" />
  <title>QQ注册</title>
</head>
<body>
  <nav class="nav">
    <a class="qq">
      <img src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/3-qq/qq.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" />
      <span>QQ</span>
    </a>
    <ul class="right">
      <li class="bright">
        <img
          src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/3-qq/bright.png"
          alt="QQ靓号"
        />
      </li>
      <li class="language">
        <span>简体中文</span>
        <img
          class="arrow"
          src="https://document.youkeda.com/P3-1-HTML-CSS/1.9/3-qq/arrow-down.png"
        />
      </li>
      <li class="contact">意见反馈</li>
    </ul>
  </nav>
  <main class="main">
    <div class="bg"></div>
    <div class="content">
      <div class="core">
        <h1>欢迎注册QQ</h1>
        <div class="subtitle">
          <h2>每一天，乐在沟通。</h2>
          <a class="free-bright">免费靓号</a>
        </div>

        <form action="">
          <input type="text" placeholder="昵称" />
          <input class="password" type="password" placeholder="密码" />
          <div class="mobile">
            <select>
              <option>+86</option>
              <option>+852</option>
            </select>
            <input type="text" placeholder="手机号码" />
          </div>
          <p class="mobile-tip">可通过该手机号找回密码</p>
          <button class="submit">立即注册</button>
          <div class="agreement">
            <input type="checkbox" />
            <label>我已阅读并同意相关服务条款和隐私政策</label>
          </div>
        </form>
      </div>
      <footer>Copyright © 1998-2019Tencent All Rights Reserved</footer>
    </div>
  </main>
</body>
```

我们如何获取到`subtitle`这个节点呢？

```html
<div class="subtitle">
  <h2>每一天，乐在沟通。</h2>
  <a class="free-bright">免费靓号</a>
</div>
```

这就需要用到**选择器查询方法** --- **querySelector()**

这个方法需要传递一个字符串形式的**selectors**作为筛选条件。这需要利用大家已经学过的 CSS 知识，在此处我们可以使用`'.subtitle'`作为条件。 但如果页面中有很多个 class 为`subtitle`的节点，可能筛选结果就不太准确了，我们可以加强了筛选条件，为：

```js
//基础筛选条件
'.subtitle';

//加强版本，加上父亲筛选， 筛选 main标签下面 -> class为core的节点下面 -> class为subtitle的节点
'main .core .subtitle';
```

完整的代码如下：

```js
document.querySelector('main .core .subtitle');
```

最终的结果如下：

![img](https://style.youkeda.com/img/course/f4/9/7.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)![img](https://style.youkeda.com/img/course/f4/9/8.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

两者结合我们知道筛选到的节点满足我们的要求，并且这个节点是`HTMLDivElement`类型，我们又认识一种新的 DOM 对象。

**迭代查询**

当我们得到 subtitle 元素后，我们还可以利用这个元素，继续筛选器内部元素，比如我们想筛选器内部的 a 标签，我们可以继续完善代码：

```js
let subtitle = document.querySelector('main .core .subtitle');
console.log(subtitle.querySelector('a'));
```

最终可以得到一个 `HTMLAnchorElement` 节点，在这里我就不演示了

##### 选择器全量查询

在上面的技术中，我们只能查询到第一个满足条件的节点，那该怎么查询所有满足条件的节点呢？

很简单，换一个方法，改为**querySelectorAll()**，我们来看个新的案例，查询上面 HTML 中的所有 **input** 节点。

代码如下：

```js
document.querySelectorAll('input');
```

最终效果如下：

![img](https://style.youkeda.com/img/course/f4/9/9.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)![img](https://style.youkeda.com/img/course/f4/9/10.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

可以发现，我们找到了 4 个`input`节点，并且查询返回的是一个**类数组**，我们可以直接通过索引访问。

> 类数组，顾名思义类似数组形式，（可以通过索引访问的对象我们都可以称之为类数组），从 JSConsole 中我们实际得到的是**NodeList**对象。

##### 其他筛选方法

`querySelector` 和 `querySelectorAll` 是最新提出的方法，在这两个方法之前，有一套最原生的 DOM 查询函数，我们简单介绍下：

**getElementById()**: 根据 **id** 查询某个节点

**getElementsByClassName()**: 根据 **class** 查询多个节点

**getElementsByTagName()**: 根据 **标签名** 查询多个节点

那 querySelector(All) 和 getElementXXX 有什么具体区别呢？ 最主要的区别在于 --- **动态性**。

> querySelector 查询出来的元素是拷贝的原始数据，不会再随着页面 DOM 节点的改变而变化 get 系列方法 查询出来的元素就是原始数据，所以会随着页面的 DOM 节点的改变而变化

这部分不要求掌握！大家只需要记住在以后的场景中，大多数都是用 `querySelector(All)` 即可。

#### 9.3 DOM属性

本节课我们学习DOM内部细节，学习他的重要属性，在学习之前，我们先统计下上个小节我们遇到的DOM种类。

```html
<!-- HTMLDocument 根文档 -->
<html>
  ……
</html>

<!-- HTMLDivElement DIV类型 -->
<div class="subtitle">
  ……
</div>

<!-- HTMLAnchorElement 超链接类型 -->
<a class="free-bright">免费靓号</a>

<!-- HTMLInputElement Input类型 -->
<input class="password" type="pasworkd" placeholder="请输入密码" />
```

我们发现基本每一种 HTML 标签都有一种 DOM 类型对应，当然还有非常多的类型，大家可以打开 MDN 网站https://developer.mozilla.org/zh-CN/docs/Web/API，在页面中搜索`Element`。

这些类型不要求牢记，大家稍微了解一下即可。我们马上来重点学习下他们的共同属性。

##### DOM 属性

###### DOM 类别

在上面我们看到很多 DOM 种类，但可以归纳为几个类别：

1. **元素节点**
2. **特性节点**
3. **文本节点**
4. …… 其他类别不重要，忽略

那这三种节点分别对应什么 HTML 代码呢？我们来看个案例

html 代码如下：

```html
<!DOCTYPE html>
<head>
  <meta charset="UTF-8" />
  <title>优课达</title>
</head>
<body>
  <div id="test">优课达</div>
  <script src="./index.js"></script>
</body>
```

JS 代码如下：

```js
let divDom = document.querySelector('div#test');
console.log(divDom.nodeType, divDom.nodeName, divDom.nodeValue);

// 获取DIV节点的第一个儿子节点，代表 '优课达' 这个字符串
let txtDom = divDom.firstChild;
console.log(txtDom.nodeType, txtDom.nodeName, txtDom.nodeValue);

// 获取DIV节点的id属性
let attDom = divDom.attributes.id;
console.log(attDom.nodeType, attDom.nodeName, attDom.nodeValue);
```

对应的结果为：

| 节点   | nodeType | nodeName | nodeValue | 类型         |
| ------ | -------- | -------- | --------- | ------------ |
| divDom | 1        | DIV      | null      | **元素节点** |
| txtDom | 3        | #text    | 优课达    | **文本节点** |
| attDom | 2        | id       | test      | **特性节点** |

我们总结下特性如下：

1. 整个 HTML 中，无论是标签，标签属性，还是纯文本字符串都是`Element`, 不同的地方在于`nodeType`分别为`1, 2, 3`。
2. HTML 标签都是**元素节点**，可以用`nodeName`获取标签名称
3. 纯文本都是**文本节点**，可以用`nodeValue`获取文本内容
4. 标签的每个属性都是**特性节点**，可以用`nodeName`取得属性 Key，用`nodeValue`取得属性 Value
5. `attributes`可以获取元素节点的所有属性，得到的结果是一个字典，通过属性 Key 获取对应的特性节点。

##### DOM 内容

我们继续修改上面的代码，如下：

```html
<!DOCTYPE html>
<head>
  <meta charset="UTF-8" />
  <title>优课达</title>
</head>
<body>
  <div id="test">
    优课达
    <p>youkeda</p>
    <p>学的比别人好一点</p>
  </div>
  <script src="./index.js"></script>
</body>
let divDom = document.querySelector('div#test');
console.log(divDom.outerHTML, divDom.innerHTML, divDom.innerText);
```

代码演示



根据结果总结如下：

| 属性      | 值                                                           | 总结                      |
| --------- | ------------------------------------------------------------ | ------------------------- |
| outerHTML | `<div id="test">优课达<p>youkeda</p><p>学的比别人好一点</p></div>` | **整个 DOM 的 HTML 代码** |
| innerHTML | `优课达<p>youkeda</p><p>学的比别人好一点</p>`                | **DOM 内部 HTML 代码**    |
| innerText | `优课达`                                                     | **DOM 内部纯文本内容**    |

在实际情况下，大家根据需要利用不同的属性获取内容。

##### DOM 亲属

在上面我们知道可以利用`firstChild`属性获取到元素的**第一个儿子节点**。那还能获取哪些其他亲属呢？ 我们来看一个案例：

HTML 依然用上面的代码，Javascript 代码如下：

```js
let divDom = document.querySelector('div#test');
console.log(divDom.firstChild, divDom.lastChild);
console.log('-----');
console.log(divDom.childNodes);
console.log('-----');
console.log(divDom.parentNode);
```

代码演示



最终的结果如下：

![img](https://style.youkeda.com/img/course/f4/9/14.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

| 属性       | 值                                                           | 总结                            |
| ---------- | ------------------------------------------------------------ | ------------------------------- |
| firstChild | `优课达`                                                     | **指定节点的第一个子节点**      |
| lastChild  | `<p>学的比别人好一点</p>`                                    | **指定节点的最后一个子节点**    |
| childNodes | `优课达<p>youkeda</p><p>学的比别人好一点</p>`                | **指定节点的子节点的集合**      |
| parentNode | `<body><div id="test">优课达<p>youkeda</p><p>学的比别人好一点</p></div><script src="./index.js"></script></body>` | **指定节点在 DOM 树中的父节点** |

###### DOM 样式

通过 DOM，我们同样可以访问到其 CSS 特性，我们来下面案例：

html 代码如下：

```html
<!DOCTYPE html>
<head>
  <meta charset="UTF-8" />
  <title>优课达</title>
</head>
<body>
  <h1 class="test youkeda" style="color: #FF3300; font-size: 24px;">优课达</h1>
  <script src="./index.js"></script>
</body>
```

JS 代码如下：

```js
const h1Dom = document.querySelector('h1');
console.log(h1Dom.classList);
console.log(h1Dom.style);
console.log(h1Dom.style.color);
```

代码演示



![img](https://style.youkeda.com/img/course/f4/9/15.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

在打印出来的结果中展开，我们总结如下：

| 属性      | 类型                     | 值                             | 总结                                        |
| --------- | ------------------------ | ------------------------------ | ------------------------------------------- |
| classList | `DOMTokenList`**类数组** | `['test', 'youkeda']`          | **classList 数组方式存储所有的 class 名称** |
| style     | `CSSStyleDeclaration`    | `color`属性为`rgb(255, 51, 0)` | **对象或字典的方法存储 CSSStyle**           |

当然这些内容都是可以修改的，我们在下一节会具体讲到。

##### DOM 数据属性

网页设计的初衷是，使 **数据** 和 **特定的 HTML 标签** 相 *关联* 。而我们肉眼能看到的数据只是 HTML 标签内部纯文本（innerText）部分， 数据肯定不止肉眼所见那么少，因为有的数据不一定是为了展示，而是有其它用途。

那我们该怎么利用 HTML 存储呢？

HTML 提供一种数据属性的标准，利用`data-*`允许我们在标准内于 HTML 元素中存储额外的信息。例如代码：

```html
<!DOCTYPE html>
<head>
  <meta charset="UTF-8" />
  <title>优课达</title>
</head>
<body>
  <article data-parts="3" data-words="1314" data-category="python">
    ...
  </article>
  <script src="./index.js"></script>
</body>
```

学习过语义化标签，我们知道`article`一般用于放置文章区域。

对文章而言，除了文章内容，我们还有其他额外数据，例如：**段落**，**字数**, **分类**，etc...

那这些额外数据，不一定是直接展示的，有可能字数是某种特效才展示，分类数据是动态更新时需要用到。

那么我们就可以利用`data-*`来存储，如上面的代码：

```html
<article data-parts="3" data-words="1314" data-category="python"></article>
```

注意，数据属性**很重要**，在前端中广泛应用，大家有兴趣可以用 chrome 开发者工具去试试看看一下其他网站的代码。

那我们该怎么通过 JS 来获取呢？按上面的推理，肯定也存在 DOM 的某个属性中，代码如下：

```js
const article = document.querySelector('article');
console.log(article.dataset);
```

代码演示



![img](https://style.youkeda.com/img/course/f4/9/16.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

从结果可以看出，`dataset`是个 Map 对象，它是`data-*`这个`*`的**Key-Value**集合。

##### 总结

本章内容比较多，但都比较简单、容易理解。大家也不需要死记硬背，说实话到现在为止我也经常忘记。

教给大家一个方法，记住大概意思，比如`dataset`，只需要记住`data`，然后在 DOM 打印结果属性中去找寻。

#### 9.4 DOM操作（一）

##### 引言

通过前面三节课，我们已经对DOM有了很深入的了解。我相信，给到大家任意一个网页，大家都能使用JavaScript完成任意网页内容提取。有了这个能力，以后大家如果想转行当爬虫工程师也是非常轻松的。

大家是不是又一次感受到，软件行业的相通性，也就是一通百通的道理。

既然对DOM有了足够的了解，那我们再接再厉，本节课开始学习操作DOM。

之前的三节课程可以说是理论知识，本节课我想改变一下形式，利用实战案例带大家了解DOM操作该怎么使用！

##### DOM样式修改

在WEB基础课程 第8章 ，我们在讲到`positon:absolte`时，给大家讲到过一个案例，如下图所示：

<img src="https://style.youkeda.com/img/course/f4/9/17.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" alt="img" style="zoom:50%;" />

<img src="https://style.youkeda.com/img/course/f4/9/18.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" alt="img" style="zoom:50%;" />

> 默认未选中的状态如左，点击选中的状态如右。

先不考虑点击事件，点击事件在后面一个章节会介绍道，我们先内置点击代码。

```html
<!DOCTYPE html>
<head>
  <meta charset="utf-8" />
  <link rel="stylesheet" type="text/css" href="./post.css" />
  <title>优课达</title>
</head>
<body>
  <section class="box">
    <img
      class="java"
      src="https://document.youkeda.com/new-learn-path/Bitmap.png"
    />
    <div class="title">Java</div>
    <div class="select"></div>
  </section>

  <script src="./post.js"></script>
</body>
```

代码中`<div class="select"></div>`也及时那个圆圈选择框。

我们可以试想下，有什么办法能实现上面的效果呢？

> 我们是否可以在点击的时候，向`select`插入一个`img`节点，渲染选中的打勾图片。然后再次点击的时候清除`select`内部节点。

当然方案不止这一个，大家可以扩展思维，如果按照这个目标，我们需要哪些技术？

1. 如何使用JavaScript创建节点？（在这里创建`img`节点）

2. 如何设置节点的样式、属性？（`img`节点设置`src`属性）
3. 如何在已存在节点内部添加子节点？（`img`节点需要添加到`select`中）
4. 如何清空节点内部子节点？（再次点击时清空select`的子节点）

根据这个思路，我们来看看JavaScript代码，如下：

```js
//保存当前是否选中的状态
let isSelected = false;

//获取整个元素的节点
const box = document.querySelector('.box');

//获取select节点
const select = document.querySelector('.select');

//给整个元素添加点击事件
box.addEventListener('click', function(){
  //点击以后触发这个函数
  
  //修改当前选中状态，取反即可
  isSelected = !isSelected;
  
  //如果当前是选中状态，则添加img到select中
  if(isSelected) {
    // 创建一个img标签节点
    const img = document.createElement('img');
    
    //设置img的src属性和样式，让其撑满select框
    img.src = 'https://style.youkeda.com/img/sandwich/check.png';
    img.setAttribute('style', 'width: 100%; height: 100%;');

    // 将这个节点添加到select框中
    select.appendChild(img);
  } else {
    //如果不是选择状态，则清空内部子元素
    select.innerHTML = '';
  }
})
```

大家点击下右侧的HTML，可以看到效果很完美，我们再次回顾下，本次实战中用到的知识点。

###### 1. 创建标签节点

Document.createElement(tagName)

> 此方法用于创建一个由标签名称tagName指定的HTML元素，就是上节课提到的元素标签节点。

如果想创建一个`div`标签，我们可以使用：

```js
const div = document.createElement('div');
```

如果想继续在这个`div`标签内部，添加纯文本内容。可以继续使用创建文本方法 **document.createTextNode()**，代码如下：

```js
const div = document.createElement('div');
const txt - document.createTextNode('优课达-学的比别人好一点');
```

我们继续把`txt`添加到`div`中，把`div`添加到`body`中，代码如下：

```js
const div = docuemnt.createElement('div');
const txt = document.createTextNode('优课达-学的比别人好一点')l
div.appendChild(txt);
document.body.appendChild(div);
```

可以看到右侧浏览器中，渲染出来我们使用java Script动态创建的内容

###### 2. 添加新节点

appendChild(newNode)

在上面的案例中，我们多次用到`appendchild()`，此方法可以往该节点中插入儿子节点。

上面案例比较多，我就不距离了，我再给大家介绍一些和此方法类似的API。

InserBefore(newNode , referenceNode)

此方法和`appendChild()`刚好相反，`appendChild`是在所有儿子节点之后添加，`inserBefore`是在某个目标儿子节点之前添加。

`insertBefore(newNode, referenceNode)`，需要两个参数，`newNode`表示新节点，`referenceNode`表示目标节点，也就是新节点插入到目标节点之前。

我们来看一个案例：

```html
<!DOCTYPE html>
<head>
  <meta charset="utf-8" />
  <title>优课达</title>
</head>
<body>
  <ul class="root">
    <li class="sars">SARS</li>
  </ul>
  <script src="./index.js"></script>
</body>
```

在案例中，我们有一个列表，里面陈列着疾病`SARS`。后来我们发现`H1N1`，因为没有`SARS`严重，我们将其放在`SARS`后。 2020 年发生`新型冠状病毒`，比`SARA`严重，需要插入到其前面，最终的顺序为

```html
<ul class="root">
  <li>新型冠状病毒</li>
  <li>SARS</li>
  <li>H1N1</li>
</ul>
```

那如何用 JS 来完成这个动态逻辑呢？我们来看看代码：

```js
const root = document.querySelector('ul.root');
const sars = document.querySelector('li.sars');

// 创建 H1N1
const H1N1 = document.createElement('li');
const H1N1Txt = document.createTextNode('H1N1');
H1N1.appendChild(H1N1Txt);
root.appendChild(H1N1);

// 创建 新型冠状病毒
const nCoV = document.createElement('li');
const nCoVTxt = document.createTextNode('新型冠状病毒');
nCoV.appendChild(nCoVTxt);
root.insertBefore(nCoV, sars);
```



最终的效果和我们想象的一样。但有点瑕疵，上面代码中重复代码太多，本次是添加两个疾病节点，如果以后添加 100 个疾病节点，那该怎么办呢？

对，我们既然学习过函数，那我们此处就应该用上这个技巧，我们修改下代码如下：

```js
function createDisease(txt) {
  const dom = document.createElement('li');
  const domTxt = document.createTextNode(txt);
  dom.addChild(domTxt);
  return dom;
}
const root = document.querySelector('ul.root');
const sars = document.querySelector('li.sars');

//创建H1N1
const H1N1 = createDisease('H1N1');
root.appendCHild(H1N1);

//创建nCov
const nCov = createDisease('nCov');
root.inserBefore(nCov,sars);
```

这样，代码抽离出来精致多了！学以致用，写代码需要多思考思考。

###### 3. 设置样式、属性

在上面，我们通过如下代码设置CSS样式，这个和直接在HTML代码中写`style`语法一样。

```js
img.setAttribute('style','width:100%',height:'100%');
```

在上一节课我们知道`dom.style`是一个Map对象，因此如果我们不想全量替换样式，我们还可以单独设置某些属性，如下代码：

```js
dom.style.color='xxxx';
```

**setAttribute()**不仅仅可以设置`style`之外，所有HTML属性都能用他设置，比如:`id`、`src`、`type`、`disabled`，etc...

**classList**

再交给大家一个小技巧，试想一下如果我们需要给img设置太多的样式，这样写起来是不是太麻烦了？那我们有什么简便方法呢？

在上一节，我们已经知道`classList`能够获取到DOM上所有的类，那我们是否可以把样式写成CSS，然后在此处只用添加或删除class呢？当然可以的。

###### 4. innerHTML

在案例中，我们使用`innerHTML = ''`清空`select`节点所有的后代内容。

大家肯定在想那我们是不是可以利用`innerHTML`，给某个元素添加内容呢？当然可以的，我们继续使用疾病的案例：在上面的JS代码中，我们使用`appendChild`添加`textNode`节点，我们改变一下写法，代码如下：

```js
function createDisease(txt) {
  const dom = document.createElement('li');

  // 我们可以直接用innerHTML设置其纯文本
  dom.innerHTML = txt;
  return dom;
}
```

我们用innerHTML设置其纯文本，效果和之前的一致。

##### 总结

本节虽然只有一个案例，但是涉及到的知识点还是比较多的，没事，我们后面还有很多案例可以让我们继续巩固这部分知识。

在上面的案例中，我们发现为了实现某个效果，其实我们有多种方法。这就是前端的特性，我们没有唯一的标准答案，只有较好的方法技巧和规则。

#### 9.5 DOM操作（二）

##### 案例介绍

我们在使用手机浏览器中的百度的时候，大家肯定发现过如下两个图片状态：

<img src="https://style.youkeda.com/img/course/f4/9/19.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" alt="img" style="zoom:50%;" />

<img src="https://style.youkeda.com/img/course/f4/9/20.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" alt="img" style="zoom:50%;" />

> 左侧图片是输入文字之前，右侧图片是输入肺炎之后

我们本节就来模拟一个简化版的百度搜索，最终的效果演示一下：

我们分解下页面开发步骤：

1. 首先，我们在不考虑鼠标交互的情况下，完成静态HTML页面
2. 监听搜索框Input输入事件（这部分代码内置，下一章我们马上讲到）
3. 当输入内容是肺炎时，显示模糊搜索结果
4. 当输入内容不是肺炎时，显示登录查看历史

##### 开发静态HTML页面

这部分我们就教学了，到现在这个阶段，应该是收到亲来，我们演示一下这部分效果：

我们分析下页面代码：

```html
<body>
  <div>
    <nav>
      <!-- 头部搜索框区域 -->
    </nav>
    <main>
      <!-- 输入非'肺炎'情况 -->
      <section class="login">
        登录查看历史
      </section>
      <!-- 输入'肺炎'情况 -->
      <ul class="search-result">
        <li>
          <i class="search"></i>
          <p><em>肺炎</em>疫情实时动态</p>
          <i class="edit"></i>
        </li>
        ……
      </ul>
    </main>
  </div>
</body>
```

代码主要分为3块区域，搜索框，登录查看历史，肺炎相关列表，当然最后的两个区域不会共存。

##### 监听Input输入事件，处理区域显示隐藏

监听Input输入事件，我们暂时内置代码如下：

```js
const input = document.querySelector('input');

// 监听键盘事件
input.addEventListener('keyup', function() {
  // this 是DOM节点，this.value可以获取input内输入的值
  console.log(this.value);
});
```

大家在Input输入框里面输入内容，内容会实时在JSConsole打出，这就说明我们已经完成输入事件的监听。

##### 监听输入肺炎时，显示肺炎查询结果

显示和隐藏我们知道可以利用CSS知识`display:block/none;`进行控制

因此首先我们修改CSS将登陆查看历史设置可见，将搜索结果设置不可见。

```css
main .search-result {
  padding: 0;
  display: none;
}
```

接着修改 Javascript 代码，动态控制显示和隐藏如下：

```js
const input = document.querySelector('input');

const login = document.querySelector('.login');
const searchResult = document.querySelector('.search-result');

// 监听键盘事件
input.addEventListener('keyup', function() {
  // this 是DOM节点，this.value可以获取input内输入的值
  if (this.value === '肺炎') {
    login.style.display = 'none';
    searchResult.style.display = 'block';
  } else {
    login.style.display = 'block';
    searchResult.style.display = 'none';
  }
});
```

大家尝试在右侧输入**肺炎**和其他内容，可以看到控制效果和我们想要的一致。

##### 肺炎搜索结果动态显示

我们知道搜索结果肯定不会是页面写死的，在实际情况下，这些数据都会实时变换的。 这部分数据是由 Javascript 发起网络请求返回的数据，然后利用动态生成节点的方法插入页面。

我们还未学习网络请求，暂时先模拟在 Javascript 代码中，如下代码：

```js
let data = [
  '<em>肺炎</em>实时疫情动态',
  '<em>肺炎</em>的症状有哪些症状',
  '<em>肺炎</em>武汉',
  '<em>肺炎</em>症状',
  '<em>肺炎</em>最新',
  '<em>肺炎</em>是怎么引起的',
  '<em>肺炎</em>最新消息',
  '<em>肺炎</em>实时',
  '<em>肺炎</em>症状及表现',
  '<em>肺炎</em>最新情况'
];
```

我们需要利用这份数组数据，生成多个`li`标签内容，`li`标签模板如下：

```html
<li>
  <i class="search"></i>
  <p><em>肺炎</em>疫情实时动态</p>
  <i class="edit"></i>
</li>
```

我们封装一个函数，用于生成这个`li`DOM节点，代码如下：

```js
function createSearchItem(txt) {
  const item = document.createElement('li');
  item.innerHTML = `<i class="search"></i><p>${txt}</P><i class="edit"></i>`
  return item;
}
```

在这里我们使用`innerHTML`和`模版字符串`快速创建`li`内容。

最后我们需要遍历搜索结果数据数组，依次创建`li`,并插入到页面中，代码如下：

```js
let data = [
  '<em>肺炎</em>实时疫情动态',
  '<em>肺炎</em>的症状有哪些症状',
  '<em>肺炎</em>武汉',
  '<em>肺炎</em>症状',
  '<em>肺炎</em>最新',
  '<em>肺炎</em>是怎么引起的',
  '<em>肺炎</em>最新消息',
  '<em>肺炎</em>实时',
  '<em>肺炎</em>症状及表现',
  '<em>肺炎</em>最新情况'
];

function createSearchItem(txt) {
  const item = document.createElement('li');
  item.innerHTML = `<i class="search"></i><p>${txt}</p><i class="edit"></i>`;
  return item;
}

const input = document.querySelector('input');

const login = document.querySelector('.login');
const searchResult = document.querySelector('.search-result');

// 监听键盘事件
input.addEventListener('keyup', function() {
  // this 是DOM节点，this.value可以获取input内输入的值
  if (this.value === '肺炎') {
    // 先把原始内容清空
    searchResult.innerHTML = '';
    for (let i = 0; i < data.length; i++) {
      searchResult.appendChild(createSearchItem(data[i]));
    }

    login.style.display = 'none';
    searchResult.style.display = 'block';
  } else {
    login.style.display = 'block';
    searchResult.style.display = 'none';
  }
});
```

大家在右边输入**肺炎**测试下，最终效果和百度一样。

##### 总结

我们总结下本节课的解决思路：

首先我们在不考虑动态效果情况下，把页面中所涉及到的所有元素都用**静态页面**的形式写出来。

其次利用 Javascript 控制区域的**显示和隐藏**，达到动态效果。

最后根据写好的**静态页面模板和数据，动态创建 DOM 节点**。

接下来我们自己上手练习一下。

### <10> DOM事件

#### 10.1 DOM事件

##### DOM绑定事件

在上章节中，我们已经开始接触事件了，比如下面代码：

```js
// 监听Input输入事件
dom.addEventListener("input", function () {});

// 监听鼠标放置，移动事件
dom.addEventListener("mouseover", function () {});

// etc...
```

我们可以看到DOM通过`addEventListener(eventName,callback)`绑定`eventName`事件，这是现在官方认定的绑定操作。

可能有些同学看到过如下两种不恰当的写法：

一、事件嵌套到HTML代码中

```html
<div onclick="console.log('xxx')"></div>
```

> 这种写法会导致 Javascript 代码镶嵌在 HTML 代码中，导致 HTML 代码非常庞大，不利于文件分离。

#### 二、事件方法替换

```js
dom.onclick = function () {};
```

这种写法只能在这个 DOM 上绑定一个点击事件，下一个设置`onclick`将会顶替上面的事件方法。 相比较而言`addEventListener()`可以添加多个监听事件。

因此建议大家在之后的 DOM 绑定操作，统一使用`addEventListener()`。

##### DOM 事件

我们打印一下 DOM 事件对象，这个事件对象会通过回调函数参数传递给我们，如下代码：

```js
const h1 = document.querySelector("h1");
h1.addEventListener("click", function (e) {
  console.log(e);
});
```

点击一下`优课达-学的比别人好一点`，可以看到图示结果：

![img](https://style.youkeda.com/img/course/f4/10/9.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

从这个结果可以看出，这是一个`MouseEvent`, 这个对象我们需要掌握其中几个关键属性

| 属性        | 值                                 | 解释                    |
| ----------- | ---------------------------------- | ----------------------- |
| target      | `<h1>优课达-学的比别人好一点</h1>` | 点击事件触发的 DOM 节点 |
| type        | `click`                            | 事件名称                |
| pageX/pageY | `92/47`                            | 鼠标事件触发的页面坐标  |

那除了上面事件，还有哪些常用事件呢？我们来看看官方的事件文档：https://developer.mozilla.org/zh-CN/docs/Web/Events

这些事件，我们不需要全部掌握，我们来分类介绍一下（大家阅读一下即可）：

###### 焦点事件

**focus**: 表单组件（Input, Textarea, etc..）获取焦点事件 **blur**: 表单组件（Input, Textarea, etc..）失去焦点事件

###### 鼠标事件

**click**: 点击事件 **dblclick**: 双击事件 **mousedown**: 在元素上按下任意鼠标按钮。 **mouseenter**: 指针移到有事件监听的元素内。 **mouseleave**: 指针移出元素范围外（不冒泡）。 **mousemove**: 指针在元素内移动时持续触发。 **mouseover**: 指针移到有事件监听的元素或者它的子元素内。 **mouseout**: 指针移出元素，或者移到它的子元素上。 **mouseup**: 在元素上释放任意鼠标按键。

###### 键盘事件

**keydown**: 键盘按下事件 **keyup**: 键盘释放事件

###### 视图事件

**scroll**: 文档滚动事件 **resize**: 窗口放缩事件

###### 资源

**load**： 资源加载成功的事件

从下一张开始，我们也将通过具体案例，讲解这些事件的使用。

#### 10.2 点击事件

##### Ucode案例

在DOM事件中，最常用的是点击事件，比如点击页面跳转，点击按钮进行操作等。

我们以 **UCode** 我的空间中新年快乐项目为例，让大家了解一下点击事件如何使用

工程面板截图如下：

![img](https://style.youkeda.com/img/course/f4/10/1.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

在这个面板中，我可以可以看到底部右侧的两个按钮和右侧的三个`.`都是可以点击的，点击以后的效果如下所示：

<img src="https://style.youkeda.com/img/course/f4/10/2.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" alt="img" style="zoom:50%;" />

<img src="https://style.youkeda.com/img/course/f4/10/3.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10" alt="img" style="zoom:50%;" />

##### 一、静态页面

我们首先在不考虑事件的情况下，完成所有页面样式的展示。

##### 二、Like按钮点击事件

我们先来看看完整的按钮效果，图片如下：

![img](https://style.youkeda.com/img/course/f4/10/4.gif)

那我们该如何实现这个效果呢？

1. 点击按钮后，添加`has-like`class，再次点击（取消Like），删除`has-like`class
2. 点击按钮后，将数字+1，再次点击（取消Like），数字-1

我们首先给按钮添加点击事件，并且利用`hasLike`变量表示是否喜欢：

```js
// 默认是未点击喜欢
let hasLike = false;

const likeBtn = document.querySelector(".like-btn");
likeBtn.addEventListener("click", function () {
  // 点击事件
  hasLike = !hasLike;
  console.log(hasLike);
});
```

大家可以点击右侧`Like`按钮，我们会发现控制台依次打印`true`, `false`, `true`, etc...

##### 三、根据 hasLike 修改页面信息

第二步，根据`hasLike`的值，修改页面信息，我们继续完善代码：

```js
// 默认是未点击喜欢
let hasLike = false;

const likeBtn = document.querySelector(".like-btn");
const likeBtnRight = likeBtn.querySelector(".right");
likeBtn.addEventListener("click", function () {
  // 点击事件
  hasLike = !hasLike;
  if (hasLike) {
    likeBtn.classList.add("has-like");
    likeBtnRight.innerHTML = parseInt(likeBtnRight.innerText.trim()) + 1;
  } else {
    likeBtn.classList.remove("has-like");
    likeBtnRight.innerHTML = parseInt(likeBtnRight.innerText.trim()) - 1;
  }
});
```

最终的效果和上面 GIF 图片一致。

##### 四、点击三个点显示操作列表

我们也来看看最终的效果，如下图：

![img](https://style.youkeda.com/img/course/f4/10/5.gif)

那我们该如何实现上面的效果呢？

监听三个点的按钮，点击控制`options`区域的显示和隐藏，及`display: block/none;`。

代码相比上面稍简单一下，代码如下：

```js
let showMore = false;
const moreBtn = document.querySelector(".workspace-item-more .select");
const morePanel = document.querySelector(".workspace-item-more .options");
moreBtn.addEventListener("click", function () {
  showMore = !showMore;

  // 控制morePanel的显示和隐藏
  if (showMore) {
    morePanel.style.display = "block";
  } else {
    morePanel.style.display = "none";
  }
});
```

大家仔细阅读一下上面的代码，同样我们通过 DOM 的 style CSS 样式控制元素的显示和隐藏。

##### 总结

大家学到这儿，应该是有一点点感觉了，没有感觉的同学在把前几章的代码再次回顾一下。

其实这几个案例都可以总结成一句话

> 监听 **DOM 事件**，使用 **DOM 操作**，修改 **DOM 属性**

后面课程我们将继续使用各种常见真实案例，让大家练手，让大家从实战中真正掌握这门技术。

#### 10.3 冒泡、捕获、委托

这节课的主题是你不会经常遇到的，但是如果你不理解的话，它会是一种真正的痛苦，非常多的场景都会用到这个知识。

我们先来看看一个案例，在上一节课UCode基础上，我们想在某个工程模版上添加点击事件，跳转到对应的工程详细页面（在这里，我们用`http://www.youkeda.com`官网代替）。

我们在JS中对面板添加点击事件，代码乳腺癌：

```js
// ......
// 省略前面的代码

const workspace = document.querySelector('.workspace');
workspace.addEventListener('click', function() {
  window.location.href = 'https://www.youkeda.com';
});
```

看起来好像没问题，是吧？我们尝试点击一下`Like`按钮，看看发生什么事情？如下图动图一样：

![img](https://style.youkeda.com/img/course/f4/10/7.gif)

点击`Like`按钮先变成红色，然后页面突然跳转了！为什么呢？

##### 冒泡

因为点击事件先出发`Like`click事件，再次出发`workspace`click事件，这就是事件冒泡

我们来看一个完整的图示：

![img](https://style.youkeda.com/img/course/f4/10/9.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

从上到下，整个是`button.like-btn`的DOM树

1. 点击事件触发
2. `button.like-btn`监听事件
3. 冒泡找到其父亲节点，触发父亲节点的监听事件
4. 依次冒泡直到 html 根元素为止。

我们也可以用代码来认证我们的思考，依次在组件节点上添加点击事件，如下:

```js
const likeBtn = document.querySelector('.like-btn');
likeBtn.addEventListener('click', function() {
  console.log('.like-btn');
});

const workspaceOpt = document.querySelector('.workspace-opt');
workspaceOpt.addEventListener('click', function() {
  console.log('.workspace-opt');
});

const workspace = document.querySelector('.workspace');
workspace.addEventListener('click', function() {
  console.log('.workspace');
});

document.body.addEventListener('click', function() {
  console.log('body');
});
```

大家尝试点击一下`Like`按钮，可以看到打印结果如下：

```python
".like-btn"
".workspace-opt"
".workspace"
"body"
```

这就是整个冒泡过程，那如何修复上面的冒泡导致效果异常呢？

很简单， **阻止冒泡 - e.stopPropagation();** ，我们改进一下代码，

```js
// ......省略
likeBtn.addEventListener('click', function(e) {
  // 点击事件
  e.stopPropagation();

// ......省略
```

可以看到，最终点击`Like`按钮，并不会导致页面跳转，也就是冒泡事件被阻止了。

##### 捕获

捕获和冒泡是完全相反的，冒泡是从当前元素沿着祖先节点往上冒泡，而捕获是从根HTML节点开始依次移动到当前元素。

我们上面使用的`addEventListener`是在冒泡阶段监听事件，如果想在捕获阶段监听事件，我们需要传递第三个参数为`true`，代码如下：

```js
dom.addEventListener('click', function() {}, true);
```

在实际场景中，捕获使用的非常少，以后遇到具体情况我们再具体分析，此处大家需要了解一下即可。

##### 委托

**委托**其实是**冒泡事件**的一种应用，这个概念依赖于这样一个事实,如果你想要在**大量子元素中单击任何一个都可以运行一段代码**，您可以将事件监听器设置在其**父节点**上，并让子节点上发生的事件冒泡到父节点上，而不是每个子节点单独设置事件监听器。

举个例子，在上一节的课程中，为了监听每个图片点击事件，代码如下：

```js
const box = document.querySelector('.box');
const imgArr = box.children;
for(let i=0;i<imgArr.length;i++) {
  imgArr[i].addEventListener('click',function(){
    document.body.style.backgroundImage = `url(${imgArr.src})`
  });
}
```

那我们利用委托应该怎么做呢？对，我们只需要监听`box`即可，代码修改如下：

```js
const box = document.querySelector('.box');

box.addEventListener('click',function(e){
  // document.body.style.backgroundImage = `url(${imgArr.src})`
  });
})
```

那问题来了，我们怎么获取当前点击图片的地址呢？我们需要使用这个地址赋给`body.style`。

不着急，我们首先把这个`MouseEvent`打印出来看看。演示一下：

![img](https://style.youkeda.com/img/course/f4/10/10.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

从图片可以看出，虽然我们的事件监听在`.box`上，但`MouseEvent`但`target`却在`<img />`上面，也就是

> target 表示真实响应时间的DOM节点

通过这个分析，我们就知道代码怎么写了，完善一下如下：

```js
const box = document.querySelector('.box');

box.addEventListener('click', function(e) {
  // 注意box区域比img大，如果点击在空白间隔区域，那么返回的节点将不会是IMG，需要特殊处理一下
  if (e.target.nodeName === 'IMG') {
    document.body.style.backgroundImage = `url(${e.target.src})`;
  }
});
```

最终效果和之前的写法一样，这就是委托最常用的案例，利用父元素统一监听所有儿子节点的监听事件。

##### 总结

本节课的知识更多是一种技巧性，应用性的知识，大家遇到这类知识，不要死记硬背。比如冒泡，捕获，记不清楚顺序没关系，我们写个案例试一下就行了。

#### 10.4 移动事件

##### 鼠标移动事件

在上一章中，我们在完成京东图片切换的时候，已经接触到鼠标移动事件了，本节课我们详细介绍一下这块知识。

在第一小节中，我们知道这些鼠标移动事件一共有5个如下：

**mouseenter:** 指针移动到有时间事件的元素内。 **mouseleave:**指针移出元素范围外（不冒泡）。 **mousemove:**指针在元素内移动时持续触发。 **mouseover:** 指针移到有时间监听的元素或者它的子元素内。 **mouseout:**指针移出元素，或者移到它的子元素上。

看这个内容还是很混乱的，我们把它分类一下

1. mousemove

> 这个是鼠标移动事件，比较简单

2. mouseenter/mouseleave

> 这个是鼠标进入和离开事件，但是仅仅只作用于当前DOM节点，不会作用于其后代节点

3. mouseover/mouseout

> 这个也是鼠标进入和离开事件，但和`enter/leave`不同的是：此事件除了作用于当前DOM节点，也会同时作用于其后代节点。

在平时使用中，90%我们都只会使用mouseover/mouseout，这个事件。

#### 10.5表单元素事件

##### 表单元素事件

本节课我们学习一下表单元素的事件，该事件能让我们捕捉表单元素状态变化和内容值的修改。

##### 焦点事件

我们先来看看获取焦点和失去焦点两个事件--focus和blur，非常简单，我们直接来看案例。

我们给QQ注册页的昵称输入框加入焦点事件：

```js
const nick = document.qeurySelector('input.nick');
nick.addEventListener('focus',function(){
  console.log('获取焦点');
});
nick.addEventListener('blur',function(){
  console.log('失去焦点');
});
```

大家点击昵称输入框，然后点击其他区域，可以看到陆续打印一些信息：

```js
'获取焦点'
'失去焦点'
'获取焦点'
'失去焦点'
etc...
```

##### 内容值变化

对于表单元素，有两种事件可以监听元素内容变化---input和change

我们写个案例看看情况，仍然对昵称输入框架上上面两种事件的监听，代码如下：

```js
const nick = document.querySelector('input.nick');
nick.addEventListener('input',function(){
	console.log('-----input');
	console.log(nick.value);
});
nick.addEventListener('change',function(){
	console.log('-----change');
	console.log('nick.value');
});
```

只要在输入框里面输入值，就会触发input事件。而要等到输入框失去焦点，才能触发change事件。

我们总结下，这两种是事件的区别：

| 事件   | 介绍                                                         |
| ------ | ------------------------------------------------------------ |
| change | 当用户提交对元素值当更改时触发，change事件不一定会对元素值当每次更改触发 |
| input  | 只要value值修改就会触发                                      |

我们来利用这个技术练习一下。

#### 10.6 滚动事件

##### 场景

最后我们来学习下页面滚动事件，在什么时候需要使用监听滚动呢？一般用在哪些场景呢？我们来看看一些案例：

1. 无尽滚动

我们在很多网站都看到过网页每次滚动到底部，会加载新的内容，再次滚动到底部，又会加载新内容，比如在优课达问吧页面：

````web-idl
https://apps.youkeda.com/learn
````

2. 动态效果

滚动一般用于展示一些动态效果，比如知乎头部，效果如下图：

![img](https://style.youkeda.com/img/course/f4/10/14.gif)

我们发现当页面滚动时，知乎头部会切换成新的头部。

那本节课我们将以这两个场景来学习滚动事件。

##### 事件描述

滚动事件，事件名称为---scoll。首先来看看事件如何处理和监听，我以之前的前端基础课程中文章为例，加入JS代码如下：

```js
window.addEventListener('scroll', function () {
  console.log(window.scrollY);
});
```

大家尝试滚动一下页面，我们会发现`JSConsole`里面陆续打印一些数字，这些数字就是`scrollY`（Y轴滚动距离）

##### 无尽滚动

那接下来我们加一下无尽滚动效果，当页面快滚动到底部时，添加新的文章内容到`body`中。

代码如下：

```js
window.addEventListener('scroll', function () {
  // 可以通过clientHeight获取内容高度
  const height = document.body.clientHeight;

  // 通过screen.height获取浏览器的高度
  const screenHeight = window.screen.height;

  // 当距离底部的距离小于500时，触发页面新增内容
  if (height - window.scrollY - screenHeight < 500) {
    console.log('加载新文章内容');
    // 在底部添加10张图片
    const div = document.createElement('div');
    let str = '';
    for (let i = 0; i < 10; i++) {
      str += `
       <img
        class="first"
        alt=""
        src="https://document.youkeda.com/P3-1-HTML-CSS/1.8/1.jpg?x-oss-process=image/resize,h_300"
      />
      `;
    }
    div.innerHTML = str;
    document.body.appendChild(div);
  }
});
```

大家先阅读下上面的代码，主要使用到的技术

1. 内容高度 `document.body.clientHeight`
2. 浏览器高度 `window.screen.height`
3. 滚动距离 `window.scrollY`
4. 滚动距离底部距离 `内容高度 - 浏览器高度 - 滚动距离`

大家可以滚动右侧浏览器，可以看到页面可以一直滚动，这就是无尽滚动基本原理。

##### 其它事件

到本节为止，我们已经讲了 80%的事件，覆盖 99%的使用场景。剩下的小众事件我们不在课程中讲，大家看看文档就能理解，比如：

*键盘事件*：https://developer.mozilla.org/zh-CN/docs/Web/API/KeyboardEvent

### <11> 网络请求

#### 11.1 协议

本节课开始，我们学习一些网络知识，在之前我们其实隐隐约约接触过这些知识来。

比如：我们在网上冲浪时，会在浏览器地址栏输入一个网址，然后就能打开网页了。比如，输入

```web-idl
https://www.douban.com/
```

就可以访问到豆瓣的主页：

![豆瓣网站](https://style.youkeda.com/img/course/f4/11/douban.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

那么大家是否好奇：`https` 是什么意思，作用又是什么呢？

##### 什么是协议

协议，网络协议的简称，网络协议是通信计算机双方必须共同遵从的一组约定。如怎么样建立连接、怎么样互相识别等。只有遵守这个约定，计算机之间才能相互通信交流。

###### HTTP/HTTPS 协议

目前网站主要有两种协议，HTTP 和 HTTPS，具体的原理我们可以不用深究，我们只需要知道他们的区别：

![img](https://style.youkeda.com/img/course/f4/11/ht%3Ahts%E5%8C%BA%E5%88%AB.jpg?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

> 如果大家对两种协议感兴趣，可以查看这个[文档](https://ham.youkeda.com/articles/detail/5f3756865e205f30b2c2b0f5)

#### 11.2 URL

上一节讲到了豆瓣首页地址：[豆瓣首页](https://www.douban.com/)的开头表示使用了`HTTPS`协议。那么为什么把协议放在地址的开头呢？

我们来看一个豆瓣的页面内容：

![豆瓣网站](https://style.youkeda.com/img/course/f4/11/douban2.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

这个页面就比较复杂了。地址栏输入的地址，叫做`URL`，也就是我们常说的网址，这个页面的`URL`就是：

```
https://www.douban.com/gallery/topic/116390/?from=hot_topic_note&sort=new
```

`URL` 是缩写，其英文全称是：`Uniform Resource Locator`（统一资源定位符）。`URL` 的格式规范规定了由哪几部分组成，以及各种符号的作用：

![URL格式](https://style.youkeda.com/img/course/f4/11/py2-1-2.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

格式说明：

- 协议类型与域名之间以 `://`（固定写法）分隔。

- 路径（英文常称为

   

  ```
  path
  ```

  ）以单斜杠

   

  ```
  /
  ```

   

  开头，中间每层的分隔符也是单斜杠

   

  ```
  /
  ```

   

  。

  - 路径相当于一层一层的文件夹。但要注意与 windows 的文件夹分隔符 `\` 不要混淆了。

- 参数：

  - 路径与参数之间用 `?` 分隔。看到问号 `?` 就知道后面的内容就是参数了。
  - 多个参数之间用 `&` 分隔。
  - 参数用“参数名=参数值”（`key=value`）的格式表示。

> 这些规则看起来有点多，但不需要刻意背，上网的时候多注意观察浏览器地址栏中的 `URL` 就能理解。

`URL` 的格式，就像逛校园，先根据门牌号（域名）找到校园，跟门卫出示了学生证（协议），顺着 路/大楼/层/教室号（路径）走到了教室，告诉老师你的姓名（参数），老师就可以给你传授知识啦。

##### 扩展知识点

##### 端口号

可能会看到这样的 URL：

[https://www.douban.com:443/gallery/topic/116390/?from=hot_topic_note&sort=new](javascript:void(0))

域名后的 `:443` 表示网站的端口号。`HTTP` 协议默认的端口号是 `80` ，`HTTPS` 协议默认的端口号是 `443` 。默认的端口号在 URL 中是可以省略的，其它的端口号就必须要写明了。

上网浏览时，大多数情况下看不到端口号，但是大家在开发过程中可能经常会用到不同的端口号，以 `8000` 、 `8080` 最常见，这些端口号必须写明。

##### 路径的两种情况

###### 1.相对路径

大家在开发过程中，可能会看到这样格式的 `URL`：

[gallery/topic/116390/?from=hot_topic_note&sort=new](javascript:void(0))

就要非常小心了。不是以斜杠 `/` 开头的路径，表示相对路径，但是具体相对于什么就很复杂了，要看具体情况，所以使用这种相对路径非常容易出错。

建议大家书写 `URL` 时一定要写以斜杠 `/` 开头的绝对路径；收到别人给的不是以斜杠 `/` 开头的路径时，也要确认清楚。

###### 2.默认路径

我们在上网时，仅输入了 [https://www.douban.com](javascript:void(0)) 或 [https://www.douban.com/](javascript:void(0)) 都能打开豆瓣首页，并没有输入路径啊。

实际上，没有输入路径时，表示请求网站的默认页面，那么服务器就会返回一个**默认**页面给浏览器。至于具体**默认**页面是什么页面，是由服务器决定的，通常服务器**默认**的页面是首页。

#### 11.3 API+GET请求

##### 什么是API

API全称 Application Programming Interface，应用程序接口，API一般是指一些预先定义的函数，目的是可以为开发人员快速访问某一程序，而无序了解和访问眢吗，或理解它内部工作机制的细节。

简单的讲，API可以快速调用某个程序。

这在计算机里叫做接口，我们生活中也有很多接口，比如U盘可以存储信息，我们访问U盘，只需要把U盘插到电脑上就可以访问，插入的USB接口就是一个接口，我们不需要关心它是如何实现的。

又比如电视机上有很多接口，有的连话筒，有的连视频，我们只需要直接插上对应的线就可以实现对应的功能，并不关心它的具体机制。

如果大家想要了解更多`API`的知识，可以点击查看这个[文档](https://ham.youkeda.com/articles/detail/5f3756bd5e205f30b2c2b125)

##### fetch 调用 API

我们看一个显示优课达公司信息的`API`：

```
https://www.fastmock.site/mock/b73a1b9229212a9a3749e046b1e70285/f4/f4-11-1-1
```

把这个 URL 贴到浏览器，可以看到查询返回结果为：

![img](https://style.youkeda.com/img/course/f4/11/1.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

文字内容如下：

```json
{
  "company": "优课达",
  "slogan": "学的比别人好一点"
}
```

在浏览器中可能看到很多其他信息，这是因为网站原因，大家可以忽略，只关心返回信息即可。

所谓 `API`，本质上就是一个 `URL`。开头也是 `http`（或`https`），只是返回的内容有明显的区别，没有大量多余的字符。

`API` 返回的内容统称为`数据`，那我们该如何使用`javascript`获取这部分数据呢？我们可以使用 **fetch**这个方法，我们来看看代码：

```js
fetch(
  'https://www.fastmock.site/mock/b73a1b9229212a9a3749e046b1e70285/f4/f4-11-1-1'
)
  .then(function (response) {
    return response.json();
  })
  .then(function (myJson) {
    console.log(myJson);
  });
```



最终我们在控制台也能看到上面的公司信息。

这里我们遇到了新的语法 --- `.then`， 这是个什么东西？为了弄清楚这个，我们首先得知道`fetch()`返回结果是什么？这是一个`Promise`对象。

##### Promise

**Promise** 是**异步编程**的一种解决方案，之前异步编程是通过回调方法来实现的，比如我们看看在`fetch`之前的怎么完成网路调用呢？

```js
let oReq = new XMLHttpRequest();
oReq.addEventListener('load', function () {
  console.log(this.responseText);
});
oReq.open(
  'GET',
  'https://www.fastmock.site/mock/b73a1b9229212a9a3749e046b1e70285/f4/f4-11-1-1'
);
oReq.send();
```

这是老版的`ajax`调用，大家以后几乎用不到这种方法。

使用这种方法我们需要写一大段代码，然后通过`addEventListener`监听`load`事件，然后触发后面的`function`回调函数。如果在这个回调函数里面继续加入`setTimeout`或者`addEventListener`监听代码，那么会出现多层嵌套，专业叫做**回调地狱**。

而`Promise`对象可以通过`.then`触发回调函数，`then`中文意思**下一步**，也非常符合人的语义化习惯。

在上面`response.json()`返回的也是一个 Promise 对象，所有后续可以继续使用`.then`触发后续回调。

> 把**嵌套型**的回调调整成为**平铺型**的回调，这就完美的解决了回调地狱的问题。

##### GET 请求

像上面这种请求数据的接口，我们一般称为`GET接口`，而`fetch`在不指定类型时，默认是发起`GET请求`。

在实际情况中，服务端开发同学在给出 API 接口时，会告诉你这个 API 是一个`GET`还是`POST`类型。

##### GET 参数请求

在上面我们练习了如何在程序中调用 `GET 类型 API` 获取结果。、 很多情况下，`API` 调用需要参数，

例如，下面这个 `API`，我们传入的了参数`mood=happy` ：

```web-idl
https://www.fastmock.site/mock/b73a1b9229212a9a3749e046b1e70285/f4/reply?mood=happy
```

我们只要把包含**参数**的完整的 `URL` 直接传入到方法中就可以了。

> 如果对 URL 的格式不熟悉，需要复习本课程第一章第二节哦

下面，我们用`fetch`实现 API 调用：

最终可以得到如下效果：

```js
{
  'message': 'xxxxx'
}
```

本节课都是一些 JS 基础网络调用知识，希望大家强化编程训练，在编程的过程中加深理解 `URL` 和 `API`

#### 11.4 POST请求

我们先来看一个故事:

>话说灵剑派弟子招募大会`升仙大会`在灵剑山下的灵溪镇召开，王陆跃跃欲试，也来到灵溪镇。镇上只有一家如家客栈，如果住不进去，就只能露宿街头了。
>王陆来到如家客栈门口，只见一群人围在客栈门口，王陆很好奇，这是怎么回事呢？
>此时老板娘来到客栈门前，开口说道：欲入住咱们如家客栈，除了需要登记姓名、年龄、籍贯外，最重要的，是必须持有`准入券`，请持有`准入券`者入内登记吧。
>王陆微微一笑，嗖的一声从怀里掏出一张长方形纸片，只见白底绿纹上三个大字：`准入券`，字上鲜红大印格外醒目。老板娘接过准入券笑吟吟做个手势：客官请。

> 提交数据至服务端进行增加、修改、删除等操作，都是 `POST` 操作。与王陆登记入住客栈类似，我们在网页上提交表单进行登录的场景，就是典型的 `POST` 操作。

![URL格式](https://style.youkeda.com/img/ham/course/py2/gitee-login.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

现在，我们回到计算机的世界，`JS` 是如何实现 `POST` 操作的呢（在网络调用中`GET`和`POST`类型占比 99%，其他的我们就不用掌握了）？

###### fetch - POST 操作

我们在服务端提供了一个登录接口，接口地址为：

```js
https://www.fastmock.site/mock/b73a1b9229212a9a3749e046b1e70285/f4/f4-11-4-1
```

我们知道`fetch`默认是发起`GET`请求，那我们该如何发起`POST`请求呢？

我们查看下`fetch`文档：https://developer.mozilla.org/zh-CN/docs/Web/API/Fetch_API/Using_Fetch

在文档中搜索`POST`, 我们会发现只要加一个参数**method**就行了。代码如下：

```js
fetch(
  'https://www.fastmock.site/mock/b73a1b9229212a9a3749e046b1e70285/f4/f4-11-4-1',
  {
    method: 'POST'
  }
)
  .then(function(response) {
    return response.json();
  })
  .then(function(myJson) {
    console.log(myJson);
  });
```



最终得到的结果是

```js
{
  "isSuccess": false
}
```

登录失败了！！和上面故事描述的一样，因为我们没有提供**准入券**，我们添加一下账号密码，分别为：

```js
username: 'admin';
password: '123456';
```

我们同样看看上面 Fetch 文档，我们发现可以通过`body`属性完成`POST`请求的传参。 注意，在利用 body 传递`json`格式数据时，我们需要在`headers`里面加入`contentType信息`。

我们完善一下代码如下：

```js
// 把JSON数据序列化成字符串
const data = JSON.stringify({
  username: 'admin',
  password: '123456'
});

fetch(
  'https://www.fastmock.site/mock/b73a1b9229212a9a3749e046b1e70285/f4/f4-11-4-1',
  {
    method: 'POST',
    body: data,
    headers: {
      'content-type': 'application/json'
    }
  }
)
  .then(function(response) {
    return response.json();
  })
  .then(function(myJson) {
    console.log(myJson);
  });
```

我们看到最后登录成功，返回的结果为:

```js
{
  isSuccess: true;
}
```

##### 附录

这节课我们用到了 JSON。JSON 是一种标准的数据格式，一般用于网络之间的数据通信，如果不熟悉的通过可以回顾一下 JS 对象章节。

#### 11.5 Chrome Network

##### Chrome Network

本节课我们主要教给大家一个小技巧，怎么使用Chrome开发者工具查看网络请求。

在之前的课程中，我们陆陆续续学过`Elements`,`Console`面板，本节课涉及到的面板是`NetWork`.

##### 查看GET请求

我们先来试一试一个GET接口；以以前获取公司信息为例（为例方便显示，我们加入了简单的HTML代码）

然后按照下面步骤进行操作：

1. 首先将右侧网页开启到全屏
2. 右击选择检查
3. 在Chrome开发者工具中选择Network面板
4. 再次刷新页面

我们可以看到network中出现一行，我们点击这行，这过如下：

![img](https://style.youkeda.com/img/course/f4/11/2.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

在`Headers`里面，我们可以得到几个信息：

| 属性             | 描述       |
| ---------------- | ---------- |
| `Request URL`    | 请求地址   |
| `Request Method` | 请求类型   |
| `Status Code`    | 请求状态码 |

我们再切换到`Preview`，我们可以看到返回值的情况，如下图：

![img](https://style.youkeda.com/img/course/f4/11/3.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

通过这样的方式，我们发现，我们可以完整的观察网络请求情况。

##### 查看POST请求

同样我们介入登陆请求的代码

之后我们重复上面的步骤，查看一下network，看一看到如下：

![img](https://style.youkeda.com/img/course/f4/11/4.png?x-oss-process=image/resize,w_800/watermark,image_d2F0ZXJtYXNrLnBuZz94LW9zcy1wcm9jZXNzPWltYWdlL3Jlc2l6ZSx3XzEwMA==,t_60,g_se,x_10,y_10)

从图片中我们可以看到网络请求类型为`POST`，并且看到请求参数。大家还可以打开`Request Headers`查看头部信息，可以找到`application/json`的配置。

在实际开发过程中，利用好这些工具是提高开发效率和排查问题的最有效的手段。

