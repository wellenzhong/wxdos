# 场景值 {#场景值}

> 基础库 1.1.0 开始支持，低版本需做[兼容处理](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/compatibility.html)

当前支持的场景值有：

| 场景值ID | 说明 |
| :--- | :--- |
| 1001 | 发现栏小程序主入口 |
| 1005 | 顶部搜索框的搜索结果页 |
| 1006 | 发现栏小程序主入口搜索框的搜索结果页 |
| 1007 | 单人聊天会话中的小程序消息卡片 |
| 1008 | 群聊会话中的小程序消息卡片 |
| 1011 | 扫描二维码 |
| 1012 | 长按图片识别二维码 |
| 1013 | 手机相册选取二维码 |
| 1014 | 小程序模版消息 |
| 1017 | 前往体验版的入口页 |
| 1019 | 微信钱包 |
| 1020 | 公众号 profile 页相关小程序列表 |
| 1022 | 聊天顶部置顶小程序入口 |
| 1023 | 安卓系统桌面图标 |
| 1024 | 小程序 profile 页 |
| 1025 | 扫描一维码 |
| 1026 | 附近小程序列表 |
| 1028 | 我的卡包 |
| 1029 | 卡券详情页 |
| 1031 | 长按图片识别一维码 |
| 1032 | 手机相册选取一维码 |
| 1034 | 微信支付完成页 |
| 1035 | 公众号自定义菜单 |
| 1036 | App 分享消息卡片 |
| 1037 | 小程序打开小程序 |
| 1038 | 从另一个小程序返回 |
| 1039 | 摇电视 |
| 1042 | 添加好友搜索框的搜索结果页 |
| 1043 | 公众号模板消息 |
| 1044 | 带 shareTicket 的小程序消息卡片（[详情](https://mp.weixin.qq.com/debug/wxadoc/dev/api/share.html#获取更多转发信息)\) |
| 1047 | 扫描小程序码 |
| 1048 | 长按图片识别小程序码 |
| 1049 | 手机相册选取小程序码 |
| 1052 | 卡券的适用门店列表 |
| 1053 | 搜一搜的结果页 |
| 1056 | 音乐播放器菜单 |
| 1058 | 公众号文章 |
| 1059 | 体验版小程序绑定邀请页 |

可以在 App 的`onLaunch`和`onShow`中获取。[详见](https://mp.weixin.qq.com/debug/wxadoc/dev/framework/app-service/app.html)

**Tip:**由于Android系统限制，目前还无法获取到按 Home 键退出到桌面，然后从桌面再次进小程序的场景值，对于这种情况，会保留上一次的场景值。
