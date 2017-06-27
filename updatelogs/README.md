### 2017.06.22 更新日志 {#20170622-更新日志}

1. `F`
   修复 开发工具中　
   `wx.uploadFile`
   header　设置无效的问题
   [详情](https://developers.weixin.qq.com/blogdetail?action=get_post_info&lang=zh_CN&docid=19f5b374735b2b4a0cbb8d649d469652)
2. `F`
   修复 开发者工具打开公众号网页报项目属性获取失败错误的问题

### 2017.06.21 更新日志 {#20170621-更新日志}

### 基础库更新 \(1.3.0\) {#基础库更新-130}

1. `A`
   新增
   `wx.navigateToMiniProgram`
   从一个小程序打开另一个小程序
   [详情](https://mp.weixin.qq.com/debug/wxadoc/dev/api/navigateToMiniProgram.html)
2. `A`
   新增
   `wx.navigateBackMiniProgram`
   返回到上一个小程序
   [详情](https://mp.weixin.qq.com/debug/wxadoc/dev/api/navigateBackMiniProgram.html)

### 工具更新 \(0.18.182100\) {#工具更新-018182100}

1. `A`
   新增 基础库 1.3.0 调试支持
2. `A`
   新增 编辑器状态栏显示文件大小
3. `A`
   新增 编辑器增加跳转到左边 / 右边文件的快捷键
   `Ctrl(Command) + PageUp`
   和
   `Ctrl(Command) + PageDown`
4. `A`
   新增 显示图片时状态栏右侧会给出图片大小信息
5. `U`
   优化 编辑器中删除文件不会硬盘删除而是移到回收站
6. `U`
   优化 上传代码的交互，去除扫码确认，并给予默认
   `项目备注`
7. `F`
   修复
   `tabbar`
   图标工具上错误支持了 svg 图片的问题
   [详情](https://developers.weixin.qq.com/blogdetail?action=get_post_info&docid=97aadd788150cc951c46099914169882)
8. `F`
   修复 windows 设置 http\_proxy 环境变量可能导致无法登陆问题
9. `F`
   修复 新建
   `Page`
   时
   `app.json`
   中路径添加出错的问题
   [详情](https://developers.weixin.qq.com/blogdetail?action=get_post_info&lang=zh_CN&docid=63f8b1d685aa8c57f962b4e50c160c65)
10. `F`
    修复
    `wx.uploadFile`
    `wx.downloadFile`
    设置 networkTimeout 无效的问题
11. `F`
    修复 提交预览或者上传时，检查
    `tabbar`
    icon 超过 40kb 返回的错误码有误的问题
    [详情](https://developers.weixin.qq.com/blogdetail?action=get_post_info&lang=zh_CN&docid=7606af9c39030997693f53be8d30e182)
12. `F`
    修复 开启自动保存后 app.json 修改后立刻关闭再打开后内容被置空的问题的问题
13. `F`
    修复 开发者工具中可以使用
    `Image`
    但是移动设备中无法使用的问题
14. `F`
    修复 某些情况下上传代码会出现二维码无效提示的问题
15. `F`
    修复 上传成功后没有提示的问题

## 历史更新日志 {#历史更新日志}

[历史更新日志](https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/uplog.html)



