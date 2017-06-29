# WXML {#wxml}

WXML（WeiXin Markup Language）是框架设计的一套标签语言，结合[基础组件](https://mp.weixin.qq.com/debug/wxadoc/dev/component/)、[事件系统](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/event.html)，可以构建出页面的结构。

用以下一些简单的例子来看看 WXML 具有什么能力：

### [数据绑定](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/data.html) {#数据绑定}

```
这里应该有代码

```

### [列表渲染](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/list.html) {#列表渲染}

```
这里应该有代码
```

```
// page.js

Page({
  data: {
    array: [
1
, 
2
, 
3
, 
4
, 
5
]
  }
})

```

### [条件渲染](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/conditional.html) {#条件渲染}

```
这里应该有代码
```

```
// page.js

Page({
  data: {
    view: 
'MINA'

  }
})

```

### [模板](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/template.html) {#模板}

```
应该有一个模板的代码
```

```
// page.js

Page({
  data: {
    staffA: {firstName: 
'Hulk'
, lastName: 
'Hu'
},
    staffB: {firstName: 
'Shang'
, lastName: 
'You'
},
    staffC: {firstName: 
'Gideon'
, lastName: 
'Lin'
}
  }
})

```

### [事件](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/event.html) {#事件}

```
这里应该有代码
```

```
Page({
  data: {
    count: 
1

  },
  add: 
function
(
e
) 
{
    
this
.setData({
      count: 
this
.data.count + 
1

    })
  }
})

```

具体的能力以及使用方式在以下章节查看：

[数据绑定](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/data.html)、[列表渲染](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/list.html)、[条件渲染](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/conditional.html)、[模板](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/template.html)、[事件](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/event.html)、[引用](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/import.html)

