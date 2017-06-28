# 兼容 {#兼容}

小程序的功能不断的增加，但是旧版本的微信客户端并不支持新功能，所以在使用这些新能力的时候需要做兼容。

文档会在组件，API等页面描述中带上各个功能所支持的版本号。

可以通过`wx.getSystemInfo`或者`wx.getSystemInfoSync`获取到小程序的基础库版本号。

也可以通过`wx.canIUse`[详情](https://mp.weixin.qq.com/debug/wxadoc/dev/api/api-caniuse.html)来判断是否可以在该基础库版本下直接使用对应的API或者组件

### 兼容方式 - 接口 {#兼容方式---接口}

对于新增的 API，可以用以下代码来判断是否支持用户的手机。

```
if
 (wx.openBluetoothAdapter) {
  wx.openBluetoothAdapter()
} 
else
 {
  
// 如果希望用户在最新版本的客户端上体验您的小程序，可以这样子提示

  wx.showModal({
    title: 
'提示'
,
    content: 
'当前微信版本过低，无法使用该功能，请升级到最新微信版本后重试。'

  })
}

```

### 兼容方式 - 参数 {#兼容方式---参数}

对于 API 的参数或者返回值有新增的参数，可以判断用以下代码判断。

```
wx.showModal({
  success: 
function
(
res
) 
{
    
if
 (wx.canIUse(
'showModal.cancel'
)) {
      
console
.log(res.cancel)
    }
  }
})

```

### 兼容方式 - 组件 {#兼容方式---组件}

对于组件，新增的属性在旧版本上不会被处理，不过也不会报错。如果特殊场景需要对旧版本做一些降级处理，可以这样子做。

```
Page({
  data: {
    canIUse: wx.canIUse(
'button.open-type.contact'
)
  }
})

```

```
<
button
wx:if
=
"{{canIUse}}"
open-type
=
"contact"
>
 客服消息 
<
/
button
>
<
contact-button
wx:else
>
<
/
contact-button
>
```



