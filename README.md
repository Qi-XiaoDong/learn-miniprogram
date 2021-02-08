# 小程序学习

## 配置小程序

### 小程序配置

#### 全局配置文件(**app.json**)
- 全局配置：[https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/app.html]

1. 当页面是由tabar的方式时，其他的跳转方式会失效

2. tabar的个数在2 - 5项

#### 页面配置文件(**每个页面文件夹的json文件**)
- 页面配置：[https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/page.html]

1. 页面配置可以覆盖全局配置

#### sitemap(小程序被检索的规则)
- sitemap配置：[https://developers.weixin.qq.com/miniprogram/dev/reference/configuration/sitemap.html]

## 新页面组织结构并创建

### 页面创建方式

1. 在app.json中Page配置一个文件路径，点击编译会生成文件

2. 右击生成文件目录

3. 逐一添加文件

### 新增的页面如何看到？

1. 将新增文件的路径写在page选项的第一个，则会默认展示

2. 添加编译模式

## 生命周期和调试

### 生命周期

- 小程序创建生命周期：[https://developers.weixin.qq.com/miniprogram/dev/reference/api/App.html]

- 页面的生命周期：[https://developers.weixin.qq.com/miniprogram/dev/reference/api/Page.html]

### 调试

- 逻辑代码调试方法

1. console.log()控制台

2. 弹框调试

- 模拟， 真机调试模式

## 基础组件的使用

- 组件地址：[https://developers.weixin.qq.com/miniprogram/dev/component/]

### swiper swiper-item（轮播）

1. swiper-item中的图片不够铺满屏幕时，可以设置样式

2. swiper-item可以做页面的切换

### navigator（跳转）
1. 相关Api ：[https://developers.weixin.qq.com/miniprogram/dev/api/route/wx.switchTab.html]
2. navigator:只可以跳转到内部地址，
3. navigator:**跳转也和tabar冲突，设置了tabar则跳转失效**
4. open-type: 跳转类型

```js
navigate: 保留当前页面跳转有返回箭头

redirect: 在当前页面跳转没有返回箭头

switchTab: 跳转到tabar页面

reLaunch: 不保留其他页面跳转

navigateBack: 提供返回按钮

exit: 退出当前小程序，target="miniProgram"时生效
```

### audio(音频播放器)

1. 相关Api：[https://developers.weixin.qq.com/miniprogram/dev/api/media/audio/wx.stopVoice.html]
2. 创建 audio对象 
```js
Page({
  onReady: function (e) {
    // 使用 wx.createAudioContext 获取 audio 上下文 context
    this.audioCtx = wx.createAudioContext('myAudio') // myAudio 为 audio组件的 id值
  },
```
### vedio(视频播放器)

1. 相关Api:[https://developers.weixin.qq.com/miniprogram/dev/api/media/video/wx.saveVideoToPhotosAlbum.html]

### movable-view movable-area（可移动视图容器）
1. 

### cover-view cover-image 覆盖在原生组件之上的文本和图片。
1. 

### from表单

1. submit：提交事件

2. reset： 重置事件

### webView 承载网页内容

1. 地址:[https://developers.weixin.qq.com/miniprogram/dev/component/web-view.html]

## 小程序指南

- 事件：[https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxml/event.html]
1. 除 bind 外，也可以用 catch 来绑定事件。与 bind 不同， catch 会阻止事件向上冒泡。
2. 绑定形式：
```js
// wxml
  <view bindtap="eventFun"></view> // 第一种方式
  <view bindtap="{{Fun}}"></view> // 第二种方式
// 第二种优点 操作函数可以切换
// wxss

page({

  data：{
    Fun：flag ? eventFun : eventFunc2,
  }
  eventFun(event){
    console.log(event);
  }
})
```
3. dataset: 在组件节点中可以附加一些自定义数据。这样，在事件中可以获取这些自定义的节点数据，用于事件的逻辑处理。

```js
  <view data-alpha-beta="1" data-alphaBeta="2" bindtap="bindViewTap"> DataSet Test </view>

  Page({
    bindViewTap:function(event){
      event.currentTarget.dataset.alphaBeta === 1 // - 会转为驼峰写法
      event.currentTarget.dataset.alphabeta === 2 // 大写会转为小写
  }
})
```

## 小程序框架
### WXML 语法

- 数据绑定：[https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/data.html]

- 条件渲染：[https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/conditional.html]

- 列表渲染：[https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/list.html]

1. 使用 wx:for-item 可以指定数组当前元素的变量名(默认为index)，

2. 使用 wx:for-index 可以指定数组当前下标的变量名：(默认为item)

3. wx:key：
-  1. 字符串，代表在 for 循环的 array 中 item 的某个 property，该 property 的值需要是列表中唯一的字符串或数字，且不能动态改变。

-  2. 保留关键字 *this 代表在 for 循环中的 item 本身，这种表示需要 item 本身是一个唯一的字符串或者数字。

4. block wx:for 块的循环
```js
<block wx:for="{{[1, 2, 3]}}">
  <view> {{index}}: </view>
  <view> {{item}} </view>
</block>
```
- 模板 ：[https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/template.html]

1. 定义模板

2. 使用模板

3. 作用域

- 引用：[https://developers.weixin.qq.com/miniprogram/dev/reference/wxml/import.html]

## 小程序API [https://developers.weixin.qq.com/miniprogram/dev/api/]

- 路由跳转 ：[https://developers.weixin.qq.com/miniprogram/dev/api/route/wx.switchTab.html]

-  文件操作 [https://developers.weixin.qq.com/miniprogram/dev/api/file/wx.saveFileToDisk.html]

1. 文件保存

2. 文档的操作

- 数据缓存：[https://developers.weixin.qq.com/miniprogram/dev/api/storage/wx.setStorageSync.html]
1. 可以利用数据缓存进行不同页面件的数据交流





