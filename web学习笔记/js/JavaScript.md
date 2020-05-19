# 廖雪峰js教程

# strict 模式

* 非strict模式：i= 1(i 是全局变量)
* strict 模式：未使用var声明的变量就使用，报错ReferenceError，引用错误
* 非strict模式：函数定义的this指向window
* strict模式下，函数里面定义的this是指向undefined

# 函数与方法的区别

方法是定义在对象里的函数



# 解决this指向不明问题

* `var that = this	`
* 函数本身的方法 apply( 需要指向的对象，[])

# parseInt()

用来解析字符串

parseInt('字符串'，进制数)

```
parseInt("10");			//返回 10
parseInt("19",10);		//返回 19 (10+9)
parseInt("11",2);		//返回 3 (2+1)
parseInt("17",8);		//返回 15 (8+7)
parseInt("1f",16);		//返回 31 (16+15)
parseInt("010");		//未定：返回 10 或 8
```

# Math.abs

返回一个绝对值







# Array

* 结构体是一种数据类型，不是变量。用数据类型去声明变量，定义变量就要分配内存。
* 结构体可以声明内部成员或者说属性。
* 结构体变量可以相互赋值，但是不能加减乘除
* 存储不一样操作也一样
* 泛型不一样，操作也一样

```
map: 遍历数组，返回回调返回值组成的新数组
forEach: 无法break，可以用try/catch中throw new Error来停止
filter: 过滤
some: 有一项返回true，则整体为true
every: 有一项返回false，则整体为false
join: 通过指定连接符生成字符串
push / pop: 末尾推入和弹出，改变原数组， 返回推入/弹出项【有误】
unshift / shift: 头部推入和弹出，改变原数组，返回操作项【有误】
sort(fn) / reverse: 排序与反转，改变原数组
concat: 连接数组，不影响原数组， 浅拷贝
slice(start, end): 返回截断后的新数组，不改变原数组
splice(start, number, value...): 返回删除元素组成的数组，value 为插入项，改变原数组
indexOf / lastIndexOf(value, fromIndex): 查找数组项，返回对应的下标
reduce / reduceRight(fn(prev, cur)， defaultPrev): 两两执行，prev 为上次化简函数的return值，cur 为当前值(从第二项开始)

```



# Array 的方法

## map()

map()方法定义在数组中，所以是数组具有的方法。调用数组的map()方法，传入自己构造的函数，就能得到一个新的数组

```
function pow(x) {
    return x * x;
}
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
//for 循环
var result = [];
for (var i=0; i<arr.length; i++) {
    result.push(f(arr[i]));
}
//map方法
var mapresults = arr.map(pow); 
console.log(results);// [1, 4, 9, 16, 25, 36, 49, 64, 81]


```

## reduce

Array的`reduce()`把一个函数作用在这个`Array`的`[x1, x2, x3...]`上，这个函数必须接收两个参数，`reduce()`把结果继续和序列的下一个元素做累积计算，其效果就是：

`[x1, x2, x3, x4].reduce(f) = f(f(f(x1, x2), x3), x4)`

比方说对一个`Array`求和，就可以用`reduce`实现：

```
var arr = [1, 3, 5, 7, 9];
arr.reduce(function (x, y) {
    return x + y;
});
```

字符串变数组变数字

```
function string2int(s) {
var arr = s.split('')
var result1 = arr.map(function(x) {
return x*1
})
 var result =  result1.reduce(function (x,y) {
   return x*10 +y
})
return result
}
```

## sort

排序算法

排序也是在程序中经常用到的算法。无论使用冒泡排序还是快速排序，排序的核心是比较两个元素的大小。**通常规定，对于两个元素`x`和`y`，如果认为`x < y`，则返回`-1`，如果认为`x == y`，则返回`0`，如果认为`x > y`，则返回`1`，这样，排序算法就不用关心具体的比较过程，而是根据比较结果直接排序。**



```
// 看上去正常的结果:
['Google', 'Apple', 'Microsoft'].sort(); // ['Apple', 'Google', 'Microsoft'];

// apple排在了最后:
['Google', 'apple', 'Microsoft'].sort(); // ['Google', 'Microsoft", 'apple']

// 无法理解的结果:
[10, 20, 1, 2].sort(); // [1, 10, 2, 20]
```

`Array`的`sort()`方法默认把所有元素先转换为String再排序，结果`'10'`排在了`'2'`的前面，因为字符`'1'`比字符`'2'`的ASCII码小

```
var arr = [10, 20, 1, 2];
arr.sort(function (x, y) {
    if (x < y) {
        return -1;
    }
    if (x > y) {
        return 1;
    }
    return 0;
});
console.log(arr); // [1, 2, 10, 20]
```

对字符串排序，是按照ASCII的大小比较的，现在，我们提出排序应该忽略大小写，按照字母序排序。要实现这个算法，不必对现有代码大加改动，只要我们能定义出忽略大小写的比较算法就可以：

```
var arr = ['Google', 'apple', 'Microsoft'];
arr.sort(function (s1, s2) {
    x1 = s1.toUpperCase();
    x2 = s2.toUpperCase();
    if (x1 < x2) {
        return -1;
    }
    if (x1 > x2) {
        return 1;
    }
    return 0;
}); // ['apple', 'Google', 'Microsoft']
```

## filter

也是定义在Array的高阶函数，用于把`Array`的某些元素过滤掉，然后返回剩下的元素

`filter()`把传入的函数依次作用于每个元素，然后根据返回值是`true`还是`false`决定保留还是丢弃该元素

* `trim()`除去字符串s两端的空格
* `indexOf()` 返回元素在数组或者字符串中首次，第一次！出现的位置

## every

`every()`方法可以判断数组的**所有**元素是否满足测试条件

## forEach

`forEach()`常用于遍历数组

```var arr = ['Apple', 'pear', 'orange'];
arr.forEach(console.log); // 依次打印每个元素	
```

# 闭包

函数A 里面包含了 函数B，而 函数B 里面使用了 函数A 的变量，那么 函数B 被称为闭包。

又或者：闭包就是能够读取其他函数内部变量的函数

```
function lazy_sum(arr) {
    // console.log(arr)
    //lazy_sun返回的是一个function
    var sum = function () {
        var arrreduce = arr.reduce(function (x, y) {
            return x + y;
        });
        console.log(arrreduce)
        return arrreduce;
        // console.log(arrreduce)//return 之后就停止执行，释放此函数了
        
    }
    return sum;
}
var f = lazy_sum([1,2,3,4,5]);//F 是一个函数
console.log(f)//打印结果：[Function: sum]
f()//调用f才是拿到求和结果
```

# MVC

Model-View-Controller

异步函数是C：Controller，Controller负责业务逻辑，比如检查用户名是否存在，取出用户信息等等；

View负责显示逻辑，通过简单地替换一些变量，View最终输出的就是用户看到的HTML。

Model是用来传给View的，这样View在替换变量的时候，就可以从Model中取出相应的数据。

VScode：

launch.json 调试文件

npm :

package.json

npm init

```
  npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (learnwx)
version: (1.0.0)
description: learn mvc
entry point: (app.js)
test command:
git repository:
keywords:
author: rong
license: (ISC) mit
Sorry, license should be a valid SPDX license expression (without "LicenseRef"), "UNLICENSED", or "SEE LICENSE IN <filename>" and license is similar to the valid expression "MIT".
license: (ISC) MIT
About to write to D:\study_test_project\node\learnwx\package.json:

{
  "name": "learnwx",
  "version": "1.0.0",
  "description": "learn mvc",
  "main": "app.js",
  "dependencies": {
    "bootstrap": "^4.5.0",
    "koa-bodyparser": "^4.3.0",
    "koa": "^2.12.0",
    "mime": "^2.4.5",
    "koa-router": "^8.0.8",
    "mz": "^2.7.0",
    "nunjucks": "^3.2.1"
  },
  "devDependencies": {},
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "rong",
  "license": "MIT"
}


Is this OK? (yes)
```

nginx闪退

80端口被占用

cmd

netstat -ano|findstr":80"通过上述命令查看80端口占用情况，查看后，pid的值为4。

输入tasklist /fi "PID eq 4"

通过上述命令查看4所对应的服务名称，为System

在运行中输入regedit打开注册表编辑器。

找到 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\HTTP

找到Start，右键修改将其制改为4。

重启



 