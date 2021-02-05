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

1.  navigator:只可以跳转到内部地址，
2. navigator:跳转也和tabar冲突，设置了tabar则跳转失效

## 小程序指南

- 事件：[https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxml/event.html]

## 小程序框架

## 小程序API







