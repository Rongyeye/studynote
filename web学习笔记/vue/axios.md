## 网络请求封装



* 安装axios框架：npm install axios --save
* 导入：import axios from 'axios'
* # 配置：

```
axios({
  url:'http://123.207.32.32:8000/home/multidata',
  // method:'post'
}).then(res=>console.log(res))
```

<img src="D:\学习笔记\web学习笔记\vue\1588067749(1).jpg" style="zoom:67%;" />

#### axios并发请求

axios.all([])

```
axios.all([
    axios({url:'http://123.207.32.32:8000/home/multidata'}),
    axios({
      url:'http://123.207.32.32:8000/home/data',
      params:{
        type:'sell',
        page:5
      }
    })
  ]).then(results=>{
  console.log(results);
  })
```

#### 对象/数组解构

* 对象解构

``` name
const obj = {
	name:'kobe',
	age:18
}
const{age,name} = obj
```

* 数组解构

```
const namearr = ['adele','calor','cristine']
//const name1 = namearr[0]
//const name2 = namearr[2]
//const name3 = namearr[3]

const [name1,name2,name3] = namearr
```



#### axios全局配置

axios.default

``` 
axios.defaults.baseURL = 'http://123.207.32.32:8000'
axios.defaults.timeout = 5000//请求超时判断，单位是毫秒
```

常见的url配置

自行百度

<img src="D:\学习笔记\web学习笔记\vue\1588172904(1).jpg" style="zoom:40%;" />

请求类型method：get对呀params，post对应data

 #### 实现接口

`declare const axios : axiosStatic;`

#### 创建不同配置的axios实例

```
//创建axios对应的实例
const instance1 = axios.create({
  baseURL:'http://123.207.32.32:8000',
  timeout:10000
})
instance1({
  url:'/home/multidata',
}).then(res=>{
  console.log(res);
})
```

#### axios 封装

#### 回调函数？？？？？？回调是啥？？？

就是把函数作为参数传到另一个函数里

```

```

#### axios拦截器

请求/响应成功，请求/响应失败

axios.interceptors





## 	项目开发

