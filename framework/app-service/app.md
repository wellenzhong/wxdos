# App {#app}

### App\(\) {#app}

`App()`函数用来注册一个小程序。接受一个 object 参数，其指定小程序的生命周期函数等。

**object参数说明：**

| 属性 | 类型 | 描述 | 触发时机 |
| :--- | :--- | :--- | :--- |
| onLaunch | Function | 生命周期函数--监听小程序初始化 | 当小程序初始化完成时，会触发 onLaunch（全局只触发一次） |
| onShow | Function | 生命周期函数--监听小程序显示 | 当小程序启动，或从后台进入前台显示，会触发 onShow |
| onHide | Function | 生命周期函数--监听小程序隐藏 | 当小程序从前台进入后台，会触发 onHide |
| onError | Function | 错误监听函数 | 当小程序发生脚本错误，或者 api 调用失败时，会触发 onError 并带上错误信息 |
| 其他 | Any |  | 开发者可以添加任意的函数或数据到 Object 参数中，用`this`可以访问 |

**前台、后台定义：**当用户点击左上角关闭，或者按了设备 Home 键离开微信，小程序并没有直接销毁，而是进入了后台；当再次进入微信或再次打开小程序，又会从后台进入前台。需要注意的是：只有当小程序进入后台一定时间，或者系统资源占用过高，才会被真正的销毁。

**关闭小程序\(公共库版本1.1.0开始支持\)：**当用户从扫一扫、转发等入口\([场景值](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/app-service/scene.html)为1007, 1008, 1011, 1025\)进入小程序，且没有置顶小程序的情况下退出，小程序会被销毁。

**示例代码：**

```
App({
  onLaunch: 
function
(
options
) 
{
    
// Do something initial when launch.

  },
  onShow: 
function
(
options
) 
{
      
// Do something when show.

  },
  onHide: 
function
(
) 
{
      
// Do something when hide.

  },
  onError: 
function
(
msg
) 
{
    
console
.log(msg)
  },
  globalData: 
'I am global data'

})

```

### onLaunch, onShow 参数 {#onlaunch-onshow-参数}

| 字段 | 类型 | 说明 |
| :--- | :--- | :--- |
| path | String | 打开小程序的路径 |
| query | Object | 打开小程序的query |
| scene | Number | 打开小程序的场景值 |
| shareTicket | String | shareTicket，详见[获取更多转发信息](https://mp.weixin.qq.com/debug/wxadoc/dev/api/share.html#获取更多转发信息) |
| referrerInfo | Object | 当场景为由另一个小程序打开时，返回此字段 |
| referrerInfo.appId | String | 来源小程序的 appId |
| referrerInfo.extraData | Object | 来源小程序传过来的数据 |

场景值[详见](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/app-service/scene.html)。

### getApp\(\) {#getapp}

我们提供了全局的`getApp()`函数，可以获取到小程序实例。

```
// other.js
var
 appInstance = getApp()

console
.log(appInstance.globalData) 
// I am global data
```

**注意：**

`App()`必须在`app.js`中注册，且不能注册多个。

不要在定义于`App()`内的函数中调用`getApp()`，使用`this`就可以拿到 app 实例。

不要在 onLaunch 的时候调用`getCurrentPages()`，此时 page 还没有生成。

通过`getApp()`获取实例之后，不要私自调用生命周期函数。

