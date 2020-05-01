## 一、promise

路径起别名：在build\webpack.base.conf.js里

```
resolve: {
  extensions: ['.js', '.vue', '.json'],
  alias: {
    '@': resolve('src'),
    'assets': resolve('src/assets'),
    'components': resolve('src/components'),
    'pages': resolve('src/pages'),
    'router': resolve('src/router')
    //不可以'assets': resolve('@/assets'),

  }
```

promise是es6非常好用的一个特性，异步编程的解决方案。避免ajax异步请求太深，出现回调地狱。

有异步网络请求时，用promise进行封装

```
new Promise((resolve,reject)=>{
    //第一次网络请求
    setTimeout(()=>{
        resolve()
    },1000)
}).then(()=>{
//拿到请求结果后的处理代码
console.log('helloworld!');
}
```

sync同步

async异步

promise有三个状态：

* padding

  等待状态，正在进行网络请求，或者计时器没有到时间

* fulfill满足状态，当主动回调resolve，就在满足状态，并且会回调.then()

* reject:拒绝状态，当主动回调reject，就在拒绝状态，并且会回调.catch()

promise面试题

## 	

