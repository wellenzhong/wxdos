## 文件作用域 {#文件作用域}

在 JavaScript 文件中声明的变量和函数只在该文件中有效；不同的文件中可以声明相同名字的变量和函数，不会互相影响。

通过全局函数[`getApp()`](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/app-service/app.html#getapp)可以获取全局的应用实例，如果需要全局的数据可以在`App()`中设置，如：

```
// app.js

App({
  globalData: 
1

})

```

```
// a.js
// The localValue can only be used in file a.js.
var
 localValue = 
'a'
// Get the app instance.
var
 app = getApp()

// Get the global data and change it.

app.globalData++

```

```
// b.js
// You can redefine localValue in file b.js, without interference with the localValue in a.js.
var
 localValue = 
'b'
// If a.js it run before b.js, now the globalData shoule be 2.
console
.log(getApp().globalData)

```

## 模块化 {#模块化}

我们可以将一些公共的代码抽离成为一个单独的 js 文件，作为一个模块。模块只有通过`module.exports`或者`exports`才能对外暴露接口。

需要注意的是：

* `exports`
  是
  `module.exports`
  的一个引用，因此在模块里边随意更改
  `exports`
  的指向会造成未知的错误。所以我们更推荐开发者采用
  `module.exports`
  来暴露模块接口，除非你已经清晰知道这两者的关系。
* 小程序目前不支持直接引入
  `node_modules`
  , 开发者需要使用到
  `node_modules`
  时候建议拷贝出相关的代码到小程序的目录中。

    // common.js
    function
    sayHello
    (
    name
    ) 
    {

    console
    .log(
    `Hello 
    ${name}
     !`
    )
    }

    function
    sayGoodbye
    (
    name
    ) 
    {

    console
    .log(
    `Goodbye 
    ${name}
     !`
    )
    }


    module
    .exports.sayHello = sayHello
    exports.sayGoodbye = sayGoodbye


​在需要使用这些模块的文件中，使用`require(path)`将公共代码引入

```
var
 common = 
require
(
'common.js'
)
Page({
  helloMINA: 
function
(
) 
{
    common.sayHello(
'MINA'
)
  },
  goodbyeMINA: 
function
(
) 
{
    common.sayGoodbye(
'MINA'
)
  }
})

```

### Tips {#tips}

1. `tip`
   : require 暂时不支持绝对路径


