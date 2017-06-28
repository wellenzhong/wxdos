# WXML {#wxml}

WXML（WeiXin Markup Language）是框架设计的一套标签语言，结合[基础组件](https://mp.weixin.qq.com/debug/wxadoc/dev/component/)、[事件系统](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/event.html)，可以构建出页面的结构。

用以下一些简单的例子来看看 WXML 具有什么能力：

### [数据绑定](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/data.html) {#数据绑定}

```
<
!--wxml--
>
<
view
>
 {{message}} 
<
/
view
>
```

```
// page.js

Page({
  data: {
    message: 
'Hello MINA!'

  }
})

```

### [列表渲染](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/list.html) {#列表渲染}

```
<
!--wxml--
>
<
view
wx:for
=
"{{array}}"
>
 {{item}} 
<
/
view
>
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
<
!--wxml--
>
<
view
wx:if
=
"{{view == 'WEBVIEW'}}"
>
 WEBVIEW 
<
/
view
>
<
view
wx:elif
=
"{{view == 'APP'}}"
>
 APP 
<
/
view
>
<
view
wx:else
=
"{{view == 'MINA'}}"
>
 MINA 
<
/
view
>
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
<
!--wxml--
>
<
template
name
=
"staffName"
>
<
view
>

    FirstName: {{firstName}}, LastName: {{lastName}}
  
<
/
view
>
<
/
template
>
<
template
is
=
"staffName"
data
=
"{{...staffA}}"
>
<
/
template
>
<
template
is
=
"staffName"
data
=
"{{...staffB}}"
>
<
/
template
>
<
template
is
=
"staffName"
data
=
"{{...staffC}}"
>
<
/
template
>
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
<
view
bindtap
=
"add"
>
 {{count}} 
<
/
view
>
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

