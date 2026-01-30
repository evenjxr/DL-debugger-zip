---
theme: fancy
highlight: a11y-light
---

## 广告开始

hello bro!!!

你在web开发过程中是否有这样的困扰。

*   生产环境验证数据交互，无法独自修改返回数据。
*   开发环境要调整头信息，切换表示。
*   指定某一个接口返回mock数据。

如果你也有以上问题，那今天给大家安利一个chrome插件，不要999， 不要99，只要0.000009，就当**交个朋友**。

## 正文正能量

所谓一图胜千言，先贴图

![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/3dc44182e9f141d3a786b51a8c1b06c0~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=ROHvtSQBhTwLn02eGR164vjfkZg%3D)

## 新增站点配置

插件主页面左侧边栏是菜单站点选项

![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/43abafeeadf742c3a14a679116e7323d~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=KVziYMwhBT4%2BfK8e0%2FIRFOJcLjk%3D)

最下面新增站点，点击跳转新页面新增，站点名称和站点host是必填的，编辑完成后添加保存按钮。

以下以cn.bing.com站点配置说明，请求头新增了header1和header2两个头信息，mock部分代理了/as/suggesions的接口返回并修改了返回内容q
![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/88ff2cc84cdb4c45af26fb0752ab7d4c~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=KOe2kMPhbdMShHpuTpX9PoDpGLM%3D)

保存配置成功后，在**未开启**调试状态下：
![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/18373a4bb84f4563b2372a608f07dc1e~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=oZdLQ5qSc%2ByqgIjrmRSZP6AaX6c%3D)

**开始**调试后

*   请求头也会新增我添加的两个头信息
    ![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/e6cb602a32ac4fea95ff7679f127477a~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=pRR2xqbvYZnkkN1xYaWQysqyFiQ%3D)

*   代理接口规则也生效 无论我输入什么返回的都是配置的内容。
    ![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/d20fcf33d812461a868323d3c92225cb~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=LSqPaZjZc6Qpjn0VfmnJa0gc%2Frk%3D)

## 总结功能特性

*   ✅ 动态添加、编辑和删除请求头规则
*   ✅ 支持 URL 模式匹配（支持通配符）
*   ✅ 实时代理接口返回数据，方便生产和开发环境的调试

## 这里解释一下**捕获**

**用法**：

1.  当新增或编辑站点时候，并配置好接口路径并保存，切换到站点页面点击捕获按钮，刷新或者重新触发你配置的path的请求，插件会记录接口返回内容作为api mock的原始数据，你可以在此基础上编辑。
    ![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/f0a950348954414584849f3b5c73b08d~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=nMoeQL3tsORerlhbI8m6pZOiZ98%3D)

2.  按path捕获数据成功后会显示这个按钮，点击会把捕获的内容填充到文本框可进一步编辑。
    ![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/57ebd13ad31a47e7aca992f8e40b67a7~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAg5byC5b2p:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiNzg4MjA1Njg0NzMxODEifQ%3D%3D&rk3s=f64ab15b&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1770368506&x-orig-sign=yhJAAGRjU3SzqFZFGYVg6aJLnIY%3D)

你也可以直接手动补全接口返回。

## 总结

以上就是最近折腾的一个小工具，因为我的使用场景有限，就先发个问题让大家看看给点意见，后续真的有用了，在push到谷歌的插件商店里。。欢迎大家使用给出建议和反馈。

压缩包：[下载插件](https://jxryicai.oss-cn-beijing.aliyuncs.com/dist.zip?Expires=1769429720\&OSSAccessKeyId=TMP.3KkriF8ZRSKPhTBAUdRrADHfH6HjW9Xpz59zyCngFGHiUc3dhpph1yctFfEoHU1hxBbtvyPHGAnyYkf4q5o7pRdFU4iMCL\&Signature=Mjf7%2BQsVrhDNlx6w7U4MG%2FdRPdU%3D)
