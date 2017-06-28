# 页面路由 {#页面路由}

在小程序中所有页面的路由全部由框架进行管理。

### 页面栈 {#页面栈}

框架以栈的形式维护了当前的所有页面。 当发生路由切换的时候，页面栈的表现如下：

| 路由方式 | 页面栈表现 |
| :--- | :--- |
| 初始化 | 新页面入栈 |
| 打开新页面 | 新页面入栈 |
| 页面重定向 | 当前页面出栈，新页面入栈 |
| 页面返回 | 页面不断出栈，直到目标返回页，新页面入栈 |
| Tab 切换 | 页面全部出栈，只留下新的 Tab 页面 |
| 重加载 | 页面全部出栈，只留下新的页面 |

### getCurrentPages\(\) {#getcurrentpages}

`getCurrentPages()`函数用于获取当前页面栈的实例，以数组形式按栈的顺序给出，第一个元素为首页，最后一个元素为当前页面。

**Tip：不要尝试修改页面栈，会导致路由以及页面状态错误。**

### 路由方式 {#路由方式}

对于路由的触发方式以及页面生命周期函数如下：

| 路由方式 | 触发时机 | 路由前页面 | 路由后页面 |
| :--- | :--- | :--- | :--- |
| 初始化 | 小程序打开的第一个页面 |  | onLoad, onSHow |
| 打开新页面 | 调用 API[`wx.navigateTo`](https://mp.weixin.qq.com/debug/wxadoc/dev/api/ui-navigate.html#wxnavigatetoobject)或使用组件[`<navigator open-type="navigateTo"/>`](https://mp.weixin.qq.com/debug/wxadoc/dev/component/navigator.html) | onHide | onLoad, onShow |
| 页面重定向 | 调用 API[`wx.redirectTo`](https://mp.weixin.qq.com/debug/wxadoc/dev/api/ui-navigate.html#wxredirecttoobject)或使用组件[`<navigator open-type="redirectTo"/>`](https://mp.weixin.qq.com/debug/wxadoc/dev/component/navigator.html) | onUnload | onLoad, onShow |
| 页面返回 | 调用 API[`wx.navigateBack`](https://mp.weixin.qq.com/debug/wxadoc/dev/api/ui-navigate.html#wxnavigateback)或使用组件[`<navigator open-type="navigateBack">`](https://mp.weixin.qq.com/debug/wxadoc/dev/component/navigator.html)或用户按左上角返回按钮 | onUnload | onShow |
| Tab 切换 | 调用 API[`wx.switchTab`](https://mp.weixin.qq.com/debug/wxadoc/dev/api/ui-navigate.html#wxswitchtab)或使用组件[`<navigator open-type="switchTab"/>`](https://mp.weixin.qq.com/debug/wxadoc/dev/component/navigator.html)或用户切换 Tab |  | 各种情况请参考下表 |
| 重启动 | 调用 API[`wx.reLaunch`](https://mp.weixin.qq.com/debug/wxadoc/dev/api/ui-navigate.html#wxrelaunch)或使用组件[`<navigator open-type="reLaunch"/>`](https://mp.weixin.qq.com/debug/wxadoc/dev/component/navigator.html) | onUnload | onLoad, onShow |

Tab 切换对应的生命周期（以 A、B 页面为 Tabbar 页面，C 是从 A 页面打开的页面，D 页面是从 C 页面打开的页面为例）：

| 当前页面 | 路由后页面 | 触发的生命周期（按顺序） |
| :--- | :--- | :--- |
| A | A | Nothing happend |
| A | B | A.onHide\(\), B.onLoad\(\), B.onShow\(\) |
| A | B（再次打开） | A.onHide\(\), B.onShow\(\) |
| C | A | C.onUnload\(\), A.onShow\(\) |
| C | B | C.onUnload\(\), B.onLoad\(\), B.onShow\(\) |
| D | B | D.onUnload\(\), C.onUnload\(\), B.onLoad\(\), B.onShow\(\) |
| D（从转发进入） | A | D.onUnload\(\), A.onLoad\(\), A.onShow\(\) |
| D（从转发进入） | B | D.onUnload\(\), B.onLoad\(\), B.onShow\(\) |

**Tips**:

* `navigateTo`
  ,
  `redirectTo`
  只能打开非 tabBar 页面。
* `switchTab`
  只能打开 tabBar 页面。
* `reLaunch`
  可以打开任意页面。
* 页面底部的 tabBar 由页面决定，即只要是定义为 tabBar 的页面，底部都有 tabBar。
* 调用页面路由带的参数可以在目标页面的
  `onLoad`
  中获取。



