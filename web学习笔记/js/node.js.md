# node.js

## npm

Node.js上开发时，会用到很多别人写的JavaScript代码。如果我们要使用别人写的某个包，每次都根据名称搜索一下官方网站，下载代码，解压，再使用，非常繁琐。于是一个集中管理的工具应运而生：大家都把自己开发的模块打包后放到npm官网上，如果要使用，直接通过npm安装就可以直接用，不用管代码存在哪，应该从哪下载。更重要的是，如果我们要使用模块A，而模块A又依赖于模块B，模块B又依赖于模块X和模块Y，npm可以根据依赖关系，把所有依赖的包都下载下来并管理起来。否则，靠我们自己手动管理，肯定既麻烦又容易出错。

因为Node.js是运行在服务区端的JavaScript环境，服务器程序和浏览器程序相比，最大的特点是没有浏览器的安全限制了，而且，服务器程序必须能接收网络请求，读写文件，处理二进制内容，所以，Node.js内置的常用模块就是为了实现基本的服务器功能。

## global全局对象

> global.console
> {
> log: [Function: bound consoleCall],
> warn: [Function: bound consoleCall],
> dir: [Function: bound consoleCall],
> time: [Function: bound consoleCall],
> timeEnd: [Function: bound consoleCall],
> timeLog: [Function: bound consoleCall],
> trace: [Function: bound consoleCall],
> assert: [Function: bound consoleCall],
> clear: [Function: bound consoleCall],
> count: [Function: bound consoleCall],
> countReset: [Function: bound consoleCall],
> group: [Function: bound consoleCall],
> groupEnd: [Function: bound consoleCall],
> table: [Function: bound consoleCall],
> debug: [Function: bound consoleCall],
> info: [Function: bound consoleCall],
> dirxml: [Function: bound consoleCall],
>                                                                                                                                                                                     groupCollapsed: [Function: bound consoleCall],
> Console: [Function: Console],
> profile: [Function: profile],
> profileEnd: [Function: profileEnd],
> timeStamp: [Function: timeStamp],
> context: [Function: context],
> [Symbol(kBindStreamsEager)]: [Function: bound ],
> [Symbol(kBindStreamsLazy)]: [Function: bound ],
> [Symbol(kBindProperties)]: [Function: bound ],
> [Symbol(kWriteToConsole)]: [Function: bound ],
> [Symbol(kGetInspectOptions)]: [Function: bound ],
> [Symbol(kFormatForStdout)]: [Function: bound ],
> [Symbol(kFormatForStderr)]: [Function: bound ]
> }

avaScript程序是由事件驱动执行的单线程模型，Node.js也不例外。Node.js不断执行响应事件的JavaScript函数，直到没有任何响应事件的函数可以执行时，Node.js就退出了

## fs模块



Node.js内置的`fs`模块就是文件系统模块，负责读写文件。

和所有其它JavaScript模块不同的是，`fs`模块同时提供了异步和同步的方法。

回顾一下什么是异步方法。因为JavaScript的单线程模型，执行IO操作时，JavaScript代码无需等待，而是传入回调函数后，继续执行后续JavaScript代码。比如jQuery提供的`getJSON()`操作：

```
$.getJSON('http://example.com/ajax', function (data) {
    console.log('IO结果返回后执行...');
});
console.log('不等待IO结果直接执行后续代码...');
```

而同步的IO操作则需要等待函数返回：

```
// 根据网络耗时，函数将执行几十毫秒~几秒不等:
var data = getJSONSync('http://example.com/ajax');
```

同步操作的好处是代码简单，缺点是程序将等待IO操作，在等待时间内，无法响应其它任何事件。而异步读取不用等待IO操作，但代码较麻烦

Web框架、

常见的Web框架包括：[Express](http://expressjs.com/)，[Sails.js](http://sailsjs.org/)，[koa](http://koajs.com/)，[Meteor](https://www.meteor.com/)，[DerbyJS](http://derbyjs.com/)，[Total.js](https://www.totaljs.com/)，[restify](http://restify.com/)…

ORM框架、

ORM框架比Web框架要少一些：[Sequelize](http://www.sequelizejs.com/)，[ORM2](http://dresende.github.io/node-orm2/)，[Bookshelf.js](http://bookshelfjs.org/)，[Objection.js](http://vincit.github.io/objection.js/)……

模版引擎、

模版引擎PK：[Jade](http://jade-lang.com/)，[EJS](http://ejs.co/)，[Swig](https://github.com/paularmstrong/swig)，[Nunjucks](http://mozilla.github.io/nunjucks/)，[doT.js](http://olado.github.io/doT/)……

测试框架、

测试框架包括：[Mocha](http://mochajs.org/)，[Expresso](http://visionmedia.github.io/expresso/)，[Unit.js](http://unitjs.com/)，[Karma](http://karma-runner.github.io/)……

自动化构建工具

构建工具有：[Grunt](http://gruntjs.com/)，[Gulp](http://gulpjs.com/)，[Webpack](http://webpack.github.io/)……

## koa

安装

npm install koa

对于每一个http请求，koa将调用我们传入的异步函数来处理：

```
//导入koa
import Koa from 'koa'

// 创建一个Koa对象表示web app本身:
const app = new Koa();

app.use(async (ctx, next) => {
    console.log(`${ctx.request.method} ${ctx.request.url}`); // 打印URL
    await next(); // 调用下一个middleware
});

app.use(async (ctx, next) => {
    const start = new Date().getTime(); // 当前时间
    await next(); // 调用下一个middleware
    const ms = new Date().getTime() - start; // 耗费时间
    console.log(`Time: ${ms}ms`); // 打印耗费时间
});

app.use(async (ctx, next) => {
   / 设置response的Content-Type:
    ctx.response.type = 'text/html';
    // 设置response的内容:
    ctx.response.body = '<h1>Hello, koa2!</h1>';
});
// 在端口3000监听:
app.listen(3000);
console.log('app started at port 3000...');
//打开http://localhost:3000，页面内容Hello, koa2!


```

处理url

安装

npm install koa-router

```
import Koa from 'koa'

// 注意require('koa-router')返回的是函数:
const router = require('koa-router')();
//相当于
//const fn_router = require('koa-router');
//const router = fn_router();

const app = new Koa();

// log request URL:
app.use(async (ctx, next) => {
    console.log(`Process ${ctx.request.method} ${ctx.request.url}...`);
    await next();
});

// add url-route:
router.get('/hello/:name', async (ctx, next) => {
    var name = ctx.params.name;
    ctx.response.body = `<h1>Hello, ${name}!</h1>`;
});//浏览器打开http://localhost:3000/hello/:name

router.get('/', async (ctx, next) => {
    ctx.response.body = '<h1>Index</h1>';
});//浏览器打开http://localhost:3000/

// add router middleware:
app.use(router.routes());

app.listen(3000);
console.log('app started at port 3000...');
```

处理post请求

npm install koa-bodyparser --save

在合适的位置加上：

```
app.use(bodyParser())
```

这个`koa-bodyparser`必须在`router`之前被注册到`app`对象上