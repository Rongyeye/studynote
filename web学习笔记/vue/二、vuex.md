## **二**、vuex

vuex:状态（变量）管理器，集中存储管理。需要多个组件共享的变量全部存储在一个对象里，把这个对象放在顶层的Vue实例里。可以做到响应式

* 安装 npm install vuex --save



* vuex的state里管理的变量最好通过mutations来action。

```
import Vuex from 'vuex'
///1.安装插件vuex
Vue.use(Vuex)
//2.创建对象
const store = new Vuex.Store({//Store大写
  state:{//放状态信息
    sum:10000,
    counter:99


    },
  mutations:{
      increment(state){
        state.counter++
      },
      decrement(state){
        state.counter--
      }
  },
  actions:{

  },
  modules:{

  },
  gettes:{

  }
})
```

### state单一状态树

一个项目一个store

### getters

类似Vue实例计算属性computed

### mutations方法

* vuex的store**状态 state改变更新的唯一方式就是提交commit mutations**,是普通的提交方法

```
add(){
      this.$store.commit('increment')
    },
```

* mutations包含两个内容：

  * 字符串的事件类型
  * 回调函数

  ```
  increment(state){
    state.counter++
  },
  increment就是字符串，(state){ state.counter++}是回调函数。该回调函数的第一个参数就是state
  ```

  * 参数：在通过mutation更新数据时，携带一些额外的参数

  ```
  addcount(count){
    this.$store.commit('incrementcount',count)
  }
  ```

  * 如果是多个参数：可以写成对象

  ```
  addstu(){
    const stu = {name:'e',age:24,heigth:1.68}
    this.$store.commit('incrementstu',stu)
    }
  ```

* mutation的特殊提交封装

``` 
//特殊提交方法
    addstu(){
      const stu = {name:'e',age:24,heigth:1.68}
      this.$store.commit(
        {
          type:'incrementstu',
          stu
        }
      )
    }
    
    
    //特殊的提交方法
      incrementstu(state,payload){//参数要写payload！！！
        state.students.push(payload.stu)
      }
    },
```

* mutations响应规则

  * state的数据发生改变时，vue组件就会自动更新
  * 所以要先在state里初始化需要的属性。会自动观察watch这些属性的变化并更新

* mutations的常量类型

  ```
   //书写格式
   //新建一个js文件
   export const  INCREMENT ='increment'
  /app.vue
  add(){
    this.$store.commit(INCREMENT)
  },
  //store的index.js里面
  [INCREMENT](state){
            state.counter++
          },
          
  ```

* mutations同步函数

  * 通常情况下vuex会要求我们mutations的方法是同步方法
  * 在用devtools调试时，可以用devtools来捕捉mutation快照
  * 如果是异步操作，devtools不能很好的跟踪这个操作会是什么时候完成

### action

action类似mutation，用来替代mutation进行异步操作

context 上下文

```
actions:{
  aupdateInfo(context,payload){
          // setTimeout(()=>{
          //   context.commit('updateInfo')
          //   console.log(payload.message);
          //   payload.success()
          // },1000)
    return new Promise((resolve,reject)=>{
      setTimeout(()=>{
      //context上下文指代store
        context.commit('updateInfo')
        //与mutations 不同，因为修改state只能通过mutations
        //所以context.commit到mutations,执行mutation的方法
        console.log(payload);
        resolve('1111')
      },1000)
    })
  }
},
```

```
        //在app.vue 里，与mutation不同，用dispath执行action里的方法
ayscupdateName(){
  this.$store.dispatch('aupdateName')
}
```

官方给出的逻辑图

![]()

#### getters 

模块里的getters里的函数可以有一个参数rootState，即store对象里的state。

```
fullName3(state,getters,rootState){//
  return getters.fullName2+rootState.counter
}
```



### modules

避免state变得臃肿，可以用module划分store为多个模块，每个模块有自己的state，mutations

### vue的哪些方法是响应式？复习

* pop/push/splice替换/vue.set()

  

## vue-devtools

vue开发的浏览器扩展工具调试工具安装https://blog.csdn.net/weixin_38654336/article/details/80790698

在chorm里的插件

