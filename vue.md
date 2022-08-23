
```

<p ref="p">This is to show how to use ref</p>

mounted() {
    this.$refs.p.innerHTML = "Has been mounted successfully";
  },
```
[Installation]
```
$ npm install -g @vue/cli
$ vue --version
@vue/cli 5.0.8
```

[Vue devtools] 
has two main tabs:cd

the Inspector to display debugging information in a structured way (for example inspecting a component),
the Timeline to track different kinds of data over time such as events.



【1】

框架 - JS 的一个工具集合；

使用框架的原因：更好、更快 地开发 --> 可维护 + 可复用

组件化

//待补...：导航栏、侧边栏、轮播图 这些基本功能 的 实现

框架复杂度 vs 应用复杂度 需要进行平衡，不盲目使用框架 

JS 体现了前端的天花板

```bash
          by          on       最新      缺点
vue      尤雨溪
angular  Google      1/PC端    4，5     大、API总变化
react    Facebook                       
```

Augular：4，5开始用到 TS，依赖注入的思想，

Typescript：静态类型检测

react：引入 虚拟 dom，jsx 语法， HTML + CSS 都写到 JS 中去，对原生 HTML 进行了修改，

vue：借鉴了前两者的思想和优点，学习成本低，兼容TS；数据绑定、虚拟dom、组件化

用vue开发的一个范例：http://element.eleme.io - 饿了么组件库，**单页面应用**，第一次加载页面即从服务器请求到并且加载所有资源，第一次会慢，加载完会发现没有跳转；

vue - The progressive JS Framework

vue-router：单页面应用需要

Vuex 状态管理系统

学习建议：官网、英文版、生态系统看github、研究底层实现

https://github.com/vuejs vue-核心，推荐 awesome-vue（很多资源），论坛Forum可以提问，聊天室Chat

【2】

```vue
<head>
	<script src="https://unpkg.com/vue@2.5.13/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    {{ getFullName()}}
  </div>
	<script>
    var vm = new Vue({
      el: "#app",
      data:{
        msg: "hello world!",
        age: 19,
        fullName: "Lisa Huang"
      },
      methods: {
        getFullName : function(){ 
          return this.fullName;
        }
      }
    })
  </script>
</body>
```

注意：methods 中不能使用 ()=>{}，因为 方法中需要使用到 this，可是箭头函数的 this 指向与普通函数的不同；

vue 指令语法：v-bind : href="url"

​						v-指令名 : 指令参数 = 指令表达式

```vue
<body>
  <div id="app">
    <a v-bind:href="url">baidu</a>
  </div>
	<script>
    new Vue({
      el: "#app",
      data:{
        url: "https://www.baidu.com"
      }
    })
  </script>
</body>
```

【3】事件使用及修饰符

// 事件修饰符

.stop - 阻止冒泡

.prevent - 阻止默认事件

// 按键修饰符

.enter - 鼠标按键响应 = .13 / 按键对应的数字

.space.esc.enter - 可以链式操作

// 系统修饰符

.shift

```vue
<body>
  <div id="app">
    <button v-on:click.stop="showsome(123, $event)">click me</button>
    <a v-bind:href="https://www.baidu.com" 
       v-on:click.prevent>baidu</a>
  </div>
	<script>
    new Vue({
      el: "#app",
      methods:{
        showsome:function(msg, event){
          console.log(msg)
          alert("show some")
        } 
      }
    })
  </script>
</body>
```

响应式数据绑定 - 当某变量的值改变后，UI 自动更新

```vue
<body>
  <div id="app">
    <input type="text" v-on:click="changeName">
    Output: {{name}}
    <!-- html 中 $event 可获取 事件对象 -->
    <input id="input2" type="text" v-on:keyup.space.enter="name2=$event.target.value">
    Output : {{ name2 }}
  </div>
	<script>
    new Vue({
      el: "#app",
      data: {
        name : "hello"  //⚠️必须赋值，否则UI会显示 “{{name}}”
      }
      methods:{
        changeName : function (event) {
          this.name = event.target.value
        }
      }
    })
  </script>
</body>
```

【4】双向数据绑定、条件渲染

数据绑定的底层实现：obj.properties...+观察者模式

v-bind:  dom --> js 

v-on: dom <-- js ==> 两行结合 = 双向数据绑定 v-model.trim .number .lazy

{{}} 的默认行为：将内容当成字符串去渲染

​	防止 跨域脚本攻击 xss 15‘01“ 

​	防止 用户随意更改页面的 dom

v-html 要慎用

v-once 只渲染一次初始化的值，后面更新后不进行渲染

v-if 不同条件下渲染不同的 dom 节点

v-else-if

v-else  ==> 兄弟节点才可以使用

template + v-if 实现一个条件控制多条 dom 的功能

不显示 dom 的两种方式：1-删除掉 dom，2-css / display - "none"

v-show

v-cloak 加载完 vue 库，{{}} 所在的 dom 被识别成 vue 认识的 html 模版后，v-cloak 会消失 

【5】列表渲染

v-for = "title in movies" 模版复用的思想

Vue 重写的数组方法：reverse, push, shift, splice, 

Vue.set 的使用

key 值的使用

文本框 绑定数据到  value，复选框的话 绑定到 check 上面去

待复习html：ol li ul

【6】计算属性 及 watch 监听

**计算属性**的特点：

1 只有依赖的属性更新后，才会执行

2 执行完后有缓存功能，下一次使用时直接走缓存，不会再执行代码

get set 的用法

​	如果依赖的属性变化，get 被调用

​	如果给computed的属性赋值，set 被调用

**watch** 属性

需求：input 框中的输入值改变触发的一些逻辑操作

没有return值的使用 watch 属性，并且可以使用异步操作

【7】filter 过滤器及样式变换 ?

upperCase 的使用举例 {{msg | upperCase}}，写在 filters 里面的函数

多个 style 可以同时使用，style 和 v-bind:style 会进行融合，同时起作用

通过改变类 来 改变样式，第一种方式：显示/隐藏；第二种：改变类名

【8】组件化开发

可以协作开发，代码复用

组件 - 自定义标签

饿了么组件库：element.eleme.io

template 模版 - 会覆盖掉 html 模版

主要用在组件里面

```vue
new Vue({
  el: "#app", 告诉下面的模版要覆盖到哪里去
	template: '<div>Lisa</div>'
})
```

template模版：在 js 中写 dom

html模版：在 html 中写 js

常规方法想要将一组class替换成 template，没有办法做到

如何实现可以多次渲染某 dom 节点？ -- 组件化开发 的思想

```vue
<script>
	Vue.component("my-component", {
    template: `
    <h1>contact info</h1>
    <p>123456657</p>`
  })
</script>
```

Vue 定义的组件必须在 vue的实例里面使用

```vue
<body>
  <div id="app">
    <my-component></my-component>
    <my-component></my-component>
    <my-component></my-component>
  </div>
  <script>
    Vue.component("my-component",
      {
        template: // custom component has one root node
          `<div>
          <h1>Contact Info</h1>
          <p>12345345</p>
        </div>`
      }
    )
    new Vue({
      el: "#app"
    })
  </script>
</body>
```

component 里面也可以有 methods

```vue
<body>
  <div id="app1">
    <my-component></my-component>
  </div>
  <div id="app2">
    <!-- my-component wii not be rendered successfully in app2 -->
    <my-component></my-component>
  </div>
  <script>
    var component = {
      template:
        `<div>
          <button @click="clickMe">{{count}}</button>
        </div>`,
      data: function () {
        return {
          count: 0
        }
      },
      methods: {
        clickMe: function () {
          this.count++
        }
      }
    }
    // define a local component
    new Vue({
      el: "#app1",
      components: {
        "my-component": component
      }
    })
    new Vue({
      el: "#app2"
    })
  </script>
</body>
```

 vue.js:584 [Vue warn]: Unknown custom element: <my-component> - did you register the component correctly? For recursive components, make sure to provide the "name" option.

(found in <Root>)

【9】?

webpack：前端自动化构建工具

【10】?

单文件组件使用 及 CSS 作用域

vue-cli 生成一个项目，使用 bootstrap

【Vue Mastery-Vue Router Basics】

It is a best practice to put components that get loaded by Vue Router in the Views directory.

```vue
<router-link to="/">Home< /router-link>
<router-link :to="{name: "home"}">Home< /router-link>
```

router-link : a compoent which creates a link to navigate to a router.

Named Routes

changing route from /about to /about-us

```vue
// method 1
routes:[
	{
		path: "/about-us",
    name: "about",
    component: About
	},
	{
    path: "/about",
    redirect: {name: "about"}
  }
]

// method 2
routes:[
	{
		path: "/about-us",
    name: "about",
    component: About,
		alias: "/about"
	}
}
```

