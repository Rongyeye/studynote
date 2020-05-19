# javascript 权威指南第六版

## 第一部分

### 基础知识

用；来分隔开。如果一条语句单独占一行，可以不用；

#### **数据类型：**

* (基本数据类型）原始数据类型：数字，字符串，布尔值，null ,undefined
* （引用数据类型）对象类型：键值对。
  * 特殊对象：全局对象，JavaScript代码中，Window对象充当了全局对象。
  * 数组
  * 函数：调用函数执行可执行代码，返回运算结果

**js变量无类型。**变量可以被赋予任何类型的值，

js不区分整型浮点型数值，所有的数组都是浮点类型。整型直接量：es6支持十六、十进制，禁止八进制。

**正数溢出结果：infinity**

**负数溢出结果：0**

**大整数**：又叫高精度数，在这之前你可能更愿意使用大整数进行重要的金融计算，例如，要使用整数“分”而不要使用小数“元”进行基于货币

#### **date对象**

| [Date()](https://www.w3school.com.cn/jsref/jsref_Date.asp)   | 返回当日的日期和时间。                                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [getDate()](https://www.w3school.com.cn/jsref/jsref_getDate.asp) | 从 Date 对象返回一个月中的某一天 (1 ~ 31)。                  |
| [getDay()](https://www.w3school.com.cn/jsref/jsref_getDay.asp) | 从 Date 对象返回一周中的某一天 (0 ~ 6)。                     |
| [getMonth()](https://www.w3school.com.cn/jsref/jsref_getMonth.asp) | 从 Date 对象返回月份 (0 ~ 11)。                              |
| [getFullYear()](https://www.w3school.com.cn/jsref/jsref_getFullYear.asp) | 从 Date 对象以四位数字返回年份。                             |
| [getYear()](https://www.w3school.com.cn/jsref/jsref_getYear.asp) | 请使用 getFullYear() 方法代替。                              |
| [getHours()](https://www.w3school.com.cn/jsref/jsref_getHours.asp) | 返回 Date 对象的小时 (0 ~ 23)。                              |
| [getMinutes()](https://www.w3school.com.cn/jsref/jsref_getMinutes.asp) | 返回 Date 对象的分钟 (0 ~ 59)。                              |
| [getSeconds()](https://www.w3school.com.cn/jsref/jsref_getSeconds.asp) | 返回 Date 对象的秒数 (0 ~ 59)。                              |
| [getMilliseconds()](https://www.w3school.com.cn/jsref/jsref_getMilliseconds.asp) | 返回 Date 对象的毫秒(0 ~ 999)。                              |
| [getTime()](https://www.w3school.com.cn/jsref/jsref_getTime.asp) | 返回 1970 年 1 月 1 日至今的毫秒数。                         |
| [getTimezoneOffset()](https://www.w3school.com.cn/jsref/jsref_getTimezoneOffset.asp) | 返回本地时间与格林威治标准时间 (GMT) 的分钟差。              |
| [getUTCDate()](https://www.w3school.com.cn/jsref/jsref_getUTCDate.asp) | 根据世界时从 Date 对象返回月中的一天 (1 ~ 31)。              |
| [getUTCDay()](https://www.w3school.com.cn/jsref/jsref_getUTCDay.asp) | 根据世界时从 Date 对象返回周中的一天 (0 ~ 6)。               |
| [getUTCMonth()](https://www.w3school.com.cn/jsref/jsref_getUTCMonth.asp) | 根据世界时从 Date 对象返回月份 (0 ~ 11)。                    |
| [getUTCFullYear()](https://www.w3school.com.cn/jsref/jsref_getUTCFullYear.asp) | 根据世界时从 Date 对象返回四位数的年份。                     |
| [getUTCHours()](https://www.w3school.com.cn/jsref/jsref_getUTCHours.asp) | 根据世界时返回 Date 对象的小时 (0 ~ 23)。                    |
| [getUTCMinutes()](https://www.w3school.com.cn/jsref/jsref_getUTCMinutes.asp) | 根据世界时返回 Date 对象的分钟 (0 ~ 59)。                    |
| [getUTCSeconds()](https://www.w3school.com.cn/jsref/jsref_getUTCSeconds.asp) | 根据世界时返回 Date 对象的秒钟 (0 ~ 59)。                    |
| [getUTCMilliseconds()](https://www.w3school.com.cn/jsref/jsref_getUTCMilliseconds.asp) | 根据世界时返回 Date 对象的毫秒(0 ~ 999)。                    |
| [parse()](https://www.w3school.com.cn/jsref/jsref_parse.asp) | 返回1970年1月1日午夜到指定日期（字符串）的毫秒数。           |
| [setDate()](https://www.w3school.com.cn/jsref/jsref_setDate.asp) | 设置 Date 对象中月的某一天 (1 ~ 31)。                        |
| [setMonth()](https://www.w3school.com.cn/jsref/jsref_setMonth.asp) | 设置 Date 对象中月份 (0 ~ 11)。                              |
| [setFullYear()](https://www.w3school.com.cn/jsref/jsref_setFullYear.asp) | 设置 Date 对象中的年份（四位数字）。                         |
| [setYear()](https://www.w3school.com.cn/jsref/jsref_setYear.asp) | 请使用 setFullYear() 方法代替。                              |
| [setHours()](https://www.w3school.com.cn/jsref/jsref_setHours.asp) | 设置 Date 对象中的小时 (0 ~ 23)。                            |
| [setMinutes()](https://www.w3school.com.cn/jsref/jsref_setMinutes.asp) | 设置 Date 对象中的分钟 (0 ~ 59)。                            |
| [setSeconds()](https://www.w3school.com.cn/jsref/jsref_setSeconds.asp) | 设置 Date 对象中的秒钟 (0 ~ 59)。                            |
| [setMilliseconds()](https://www.w3school.com.cn/jsref/jsref_setMilliseconds.asp) | 设置 Date 对象中的毫秒 (0 ~ 999)。                           |
| [setTime()](https://www.w3school.com.cn/jsref/jsref_setTime.asp) | 以毫秒设置 Date 对象。                                       |
| [setUTCDate()](https://www.w3school.com.cn/jsref/jsref_setUTCDate.asp) | 根据世界时设置 Date 对象中月份的一天 (1 ~ 31)。              |
| [setUTCMonth()](https://www.w3school.com.cn/jsref/jsref_setUTCMonth.asp) | 根据世界时设置 Date 对象中的月份 (0 ~ 11)。                  |
| [setUTCFullYear()](https://www.w3school.com.cn/jsref/jsref_setUTCFullYear.asp) | 根据世界时设置 Date 对象中的年份（四位数字）。               |
| [setUTCHours()](https://www.w3school.com.cn/jsref/jsref_setutchours.asp) | 根据世界时设置 Date 对象中的小时 (0 ~ 23)。                  |
| [setUTCMinutes()](https://www.w3school.com.cn/jsref/jsref_setUTCMinutes.asp) | 根据世界时设置 Date 对象中的分钟 (0 ~ 59)。                  |
| [setUTCSeconds()](https://www.w3school.com.cn/jsref/jsref_setUTCSeconds.asp) | 根据世界时设置 Date 对象中的秒钟 (0 ~ 59)。                  |
| [setUTCMilliseconds()](https://www.w3school.com.cn/jsref/jsref_setUTCMilliseconds.asp) | 根据世界时设置 Date 对象中的毫秒 (0 ~ 999)。                 |
| [toSource()](https://www.w3school.com.cn/jsref/jsref_tosource_boolean.asp) | 返回该对象的源代码。                                         |
| [toString()](https://www.w3school.com.cn/jsref/jsref_toString_date.asp) | 把 Date 对象转换为字符串。**String(false)==false.toString() =>"false"** |
| [toTimeString()](https://www.w3school.com.cn/jsref/jsref_toTimeString.asp) | **把 Date 对象的时间部分转换为字符串**。                     |
| [toDateString()](https://www.w3school.com.cn/jsref/jsref_toDateString.asp) | 把 Date 对象的日期部分转换为字符串。                         |
| [toGMTString()](https://www.w3school.com.cn/jsref/jsref_toGMTString.asp) | 请使用 toUTCString() 方法代替。                              |
| [toUTCString()](https://www.w3school.com.cn/jsref/jsref_toUTCString.asp) | 根据世界时，把 Date 对象转换为字符串。                       |
| [toLocaleString()](https://www.w3school.com.cn/jsref/jsref_toLocaleString.asp) | 根据本地时间格式，把 Date 对象转换为字符串。                 |
| [toLocaleTimeString()](https://www.w3school.com.cn/jsref/jsref_toLocaleTimeString.asp) | 根据本地时间格式，把 Date 对象的时间部分转换为字符串。       |
| [toLocaleDateString()](https://www.w3school.com.cn/jsref/jsref_toLocaleDateString.asp) | 根据本地时间格式，把 Date 对象的日期部分转换为字符串。       |
| [UTC()](https://www.w3school.com.cn/jsref/jsref_utc.asp)     | 根据世界时返回 1970 年 1 月 1 日 到指定日期的毫秒数。        |
| [valueOf()](https://www.w3school.com.cn/jsref/jsref_valueOf_date.asp) | **返回 Date 对象的原始值。**                                 |
|                                                              |                                                              |

#### **RgeExp正则表达式**

RgeExp是一种强大和常用的文本处理工具

用`\d`可以匹配一个数字，`\w`可以匹配一个字母或数字

`\s`可以匹配一个空格（也包括Tab等空白符），所以`\s+`表示至少有一个空格	

`\d{3,8}`表示3-8个数字

RegExp对象的`test()`方法用于测试给定的字符串是否符合条件。

```
var re = /^\d{3}\-\d{3,8}$/;
re.test('010-12345'); // true
re.test('010-1234x'); // false
re.test('010 12345'); // false
```

要匹配变长的字符，在正则表达式中，用`*`表示任意个字符（包括0个），用`+`表示至少一个字符，用`?`表示0个或1个字符，用`{n}`表示n个字符，用`{n,m}`表示n-m个字符：

除了简单地判断是否匹配之外，正则表达式还有提取子串的强大功能。用`()`表示的就是要提取的分组（Group）

```
var re4 = /\d{3}\-\d{0,9}/
// qq邮箱匹配
var re5 = /[1-9][\d{4,}]+@qq.com/
// 手机号匹配
var re6 =/1[3-8][0-9]{9}/
var re7 =/^1[3-8][0-9]{9}$/

console.log(re4.test('111-349573'))//true
console.log(re5.test('10000@qq.com'))//true
console.log(re6.test('13302339263'))//true
console.log(re6.test('133023392sdfa'))//false
console.log(re6.test('133023392632'))//true
console.log(re7.test('133023392632'))//false
```

```
var test = /^[\w]+\@[\w]+\.(com|org)$/   //或不是用[com|org]而是用(com|org)
console.log('test'+test.test('Rong@qq.com'))//false
```



#### null

对null执行typeof预算，结果返回字符串“object”，也就是说，可以将null认为是一个特殊的对象值，含义是“非对象”

#### undefined

undefined是预定义的全局变量（它和null不一样，它不是关键字），**它的值就是“未定义”**。用typeof运算符得到undefined的类型，则返回“undefined

#### 全局对象

当JavaScript解释器启动时（或者任何Web浏览器加载新页面的时候），它将创建一个新的全局对象，并给它一组定义的初始属性：

·**全局属性**，比如`undefined`、`Infinity`和`NaN`

·**全局函数**，比如`isNaN（）`、`parseInt（）`（见3.8.2节）和`eval（）`（见4.12节）

​	**parsInt()**

​		parseInt（）只解析整数，而parseFloat（）则可以解析整数和浮点数。如果字符串前缀是“0x”或者“0X”，		parseInt（）将其解释为十六进制数，parseInt（）和parseFloat（）都会跳过任意数量的前导空格，尽可能		解析更多数值字符，并忽略后面的内容。如果第一个非空格字符是非法的数字直接量，将最终返回NaN：		parseInt（）可以接收第二个可选参数，这个参数指定数字转换的基数，合法的取值范围是2～36

·**构造函数**，比如`Date（）`、`RegExp（）`、`String（）`、`Object（）`和`Array（）`（见3.8.2节）

·**全局对象**，比如Math和JSON(见6.9节)

#### **Window**

 JavaScript代码中，Window对象充当了全局对象。这个全局Window对象有一个属性window引用其自身，它可以代替`this`来引用全局对象。**JavaScript全局变量是全局对象的属性**

#### **变量作用域**  

全局变量拥有全局作用域，在JavaScript代码中的任何地方都是有定义的。然而在函数内声明的变量只在函数体内有定义。它们是局部变量，作用域是局部性的。函数参数也是局部变量，它们只在函数体内有定义。而<u>JavaScript中没有块级作用域。JavaScript取而代之地使用了**函数作用域**</u>（function scope）：变量在声明它们的函数体以及这个函数体嵌套的任意函数体内都是有定义的。

#### **作用域链**

我们将作用域链描述为一个对象列表，不是绑定的栈。每次调用JavaScript函数的时候，都会为之创建一个新的对象用来保存局部变量，把这个对象添加至作用域链中。当函数返回的时候，就从作用域链中将这个绑定变量的对象删除。如果不存在嵌套的函数，也没有其他引用指向这个绑定对象，它就会被当做垃圾回收掉

作用域链由一个全局对象组成。在不包含嵌套的函数体内，作用域链上有**两个对象**，第一个是定义函数参数和局部变量的对象，第二个是全局对象。在一个嵌套的函数体内，作用域链上**至少有三个对象**。理解对象链的创建规则是非常重要的。

当定义一个函数时，它实际上保存一个作用域链。当调用这个函数时，它创建一个新的对象来存储它的局部变量，并将这个对象添加至保存的那个作用域链上，同时创建一个新的更长的表示函数调用作用域的“链”。

对于嵌套函数来讲，事情变得更加有趣，每次调用外部函数时，内部函数又会重新定义一遍。因为每次调用外部函数的时候，作用域链都是不同的。内部函数在每次定义的时候都有微妙的差别——在每次调用外部函数时，内部函数的代码都是相同的，而且关联这段代码的作用域链也不相同。

### 第六章对象

**原型**每一个JavaScript对象（null除外）都和另一个对象相关联。“另一个”对象就是我们熟知的原型，每一个对象都从原型继承属性。可以通过JavaScript代码`Object.prototype`获得对原型对象的引用。通过关键字new和构造函数调用创建的对象的原型就是构造函数的`prototype`属性的值。同使用{}创建对象一样，通过new Object（）创建的对象也继承自`Object.prototype`。同样，通过new Array（）创建的对象的原型就是`Array.prototype`，通过new Date（）创建的对象的原型就是`Date.prototype`

**Object.create（）**

ECMAScript 5定义了一个名为Object.create（）的方法，它创建一个新对象，其中第一个参数是这个对象的原型。Object.create（）提供第二个可选参数，用以对对象的属性进行进一步描述。

#### **原型链**

创建一个`Array`对象：

```
var arr = [1, 2, 3];
```

其原型链是：

```
arr ----> Array.prototype ----> Object.prototype ----> null
```

#### **继承inherit**



#### selector语法



### 第七章数组

### 第八章函数



### 第十章正则表达式

## 第二部分

### 第十五	章DOM

#### 操作DOM

由于HTML文档被浏览器解析后就是一棵DOM树，要改变HTML的结构，就需要通过JavaScript来操作DOM。

始终记住DOM是一个树形结构。操作一个DOM节点实际上就是这么几个操作：

- 更新：更新该DOM节点的内容，相当于更新了该DOM节点表示的HTML的内容；
- 遍历：遍历该DOM节点下的子节点，以便进行进一步操作；
- 添加：在该DOM节点下新增一个子节点，相当于动态增加了一个HTML节点；
- 删除：将该节点从HTML中删除，相当于删掉了该DOM节点的内容以及它包含的所有子节点。

在操作一个DOM节点前，我们需要通过各种方式先拿到这个DOM节点。最常用的方法是`document.getElementById()`和`document.getElementsByTagName()`，以及CSS选择器`document.getElementsByClassName()`

由于ID在HTML文档中是唯一的，所以`document.getElementById()`可以直接定位唯一的一个DOM节点。`document.getElementsByTagName()`和`document.getElementsByClassName()`总是返回一组DOM节点。要精确地选择DOM，可以先定位父节点，再从父节点开始选择，以缩小范围。

```
// 返回ID为'test'的节点：
var test = document.getElementById('test');

// 先定位ID为'test-table'的节点，再返回其内部所有tr节点：
var trs = document.getElementById('test-table').getElementsByTagName('tr');

// 先定位ID为'test-div'的节点，再返回其内部所有class包含red的节点：
var reds = document.getElementById('test-div').getElementsByClassName('red');

// 获取节点test下的所有直属子节点:
var cs = test.children;

// 获取节点test下第一个、最后一个子节点：
var first = test.firstElementChild;
var last = test.lastElementChild;
```



