# 文件结构 {#文件结构}

小程序包含一个描述整体程序的 app 和多个描述各自页面的 page。

一个小程序主体部分由三个文件组成，必须放在项目的根目录，如下：

| 文件 | 必填 | 作用 |
| :--- | :--- | :--- |
| [app.js](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/app-service/app.html) | 是 | 小程序逻辑 |
| [app.json](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/config.html) | 是 | 小程序公共设置 |
| [app.wxss](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxss.html) | 否 | 小程序公共样式表 |

一个小程序页面由四个文件组成，分别是：

| 文件类型 | 必填 | 作用 |
| :--- | :--- | :--- |
| [js](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/app-service/page.html) | 是 | 页面逻辑 |
| [wxml](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxml/) | 是 | 页面结构 |
| [wxss](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/view/wxss.html) | 否 | 页面样式表 |
| [json](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/config.html#pagejson) | 否 | 页面配置 |

**注意：为了方便开发者减少配置项，我们规定描述页面的这四个文件必须具有相同的路径与文件名。**

