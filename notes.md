### 导论
JS是嵌入式脚本语言，需要宿主环境(浏览器、服务器)提供额外的API

以浏览器为例：
- 浏览器控制类：操作浏览器
- DOM 类：操作网页的各种元素
- Web 类：实现互联网的各种功能

如果宿主环境是服务器，则会提供各种操作系统的 API，比如文件操作 API、网络通信 API等等。这些你都可以在 Node 环境中找到。

1995年5月，Brendan Eich 只用了10天，就设计完成了这种语言的第一版。它是一个大杂烩，语法有多个来源。

- 基本语法：借鉴 C 语言和 Java 语言。
- 数据结构：借鉴 Java 语言，包括将值分成原始值和对象两大类。
- 函数的用法：借鉴 Scheme 语言和 Awk 语言，将函数当作第一等公民，并引入闭包。
- 原型继承模型：借鉴 Self 语言（Smalltalk 的一种变种）。
- 正则表达式：借鉴 Perl 语言。
- 字符串和数组处理：借鉴 Python 语言。

### 基本语法
#### 语句和表达式
语句（statement）是为了完成某种任务而进行的操作，如 var a = 1 + 3;

表达式（expression）是为了得到返回值，且一定有返回值，如 1 + 3

语句以 ; 结尾，表达式加了分号就被视为语句

#### 变量提升
JavaScript 引擎的工作方式是，先解析代码，获取所有被声明的变量，然后再一行一行地运行。这造成的结果，就是所有的变量的**声明**语句，都会被提升到代码的头部，这就叫做变量提升（hoisting）。
```javascript
console.log(a);
var a = 1;
// 得到undefined

// 等价于
var a;
console.log(a);
a = 1;
```

#### 标识符
标识符（identifier）指的是用来识别各种值的合法名称。
- 第一个字符，可以是任意 Unicode 字母（包括英文字母和其他语言的字母），以及美元符号（$）和下划线（_）。
- 第二个字符及后面的字符，除了 Unicode 字母、美元符号和下划线，还可以用数字0-9。

中文是合法的标识符，可以用作变量名。

```javascript
var 临时变量 = 1;
```

### 数据类型
#### typeof
typeof 是运算符，不是函数
```javascript
typeof null  // object
typeof a  // undefined
typeof []  // object

var a = ()=>{}
typeof a  // function
```

**问：数组和函数都是object，为什么typeof函数返回的是function？**

#### null 和 undefined
```javascript
null == false  // false
undefined == false // false
!null // true
!undefined // true
undefined == null // true
Number(null)  // 0
Number(undefined)  // NaN
Boolean(null)  // false
Boolean(undefined)  // false
```
#### boolean
转为false的值：
- undefined
- null
- false
- 0
- NaN
- ""空字符串

[] 和 {} 对应的布尔值是true

#### 数值
JavaScript 内部，所有数字都是以64位浮点数形式储存

浮点数不精确
```javascript
1 === 1.0  // true
0.1 + 0.2 === 0.3  // false
```

NaN
```javascript
typeof NaN  // "number"
```

Infinity 无限大

函数
- parseInt() 将字符串转为整数
- parseFloat() 将字符串转为浮点数
- isNaN() 判断是否NaN
- isFinite() 判断是否为正常数值









