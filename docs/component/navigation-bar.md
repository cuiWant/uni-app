#### navigation-bar

页面导航条配置节点，用于指定导航栏的一些属性。只能是 [page-meta](https://uniapp.dcloud.io/component/page-meta) 组件内的第一个节点，需要配合它一同使用。

**平台差异说明**

|App|H5|微信小程序|支付宝小程序|百度小程序|字节跳动小程序|QQ小程序|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|√ 2.6.3+|2.6.3+|√ 2.9.0+|√|√|√|√|

从HBuilderX 2.9.3起，编译到所有平台均支持`navigation-bar`，但编译到微信时，受微信基础库版本限制；编译到其他平台不受平台版本限制。

**属性说明**

|属性|类型|默认值|必填|说明|最低版本
|:-|:-|:-|:-|:-|:-|
|title|string||否|导航条标题|微信基础库 2.9.0|
|title-icon|string||||App 2.6.7+|
|titleIcon-radius|string||||App 2.6.7+|
|subtitle-text|string||||App 2.6.7+|
|subtitle-size|string||||App 2.6.7+|
|subtitle-color|string||||App 2.6.7+|
|subtitle-overflow|string||||App 2.6.7+|
|title-align|string||||App 2.6.7+|
|background-image|string|||	支持以下类型： 背景图片路径 - 如"./img/t.png"，仅支持本地文件路径， 相对路径，相对于当前页面的host位置，根据实际标题栏宽高拉伸绘制； 渐变色 - 仅支持线性渐变，两种颜色的渐变，如“linear-gradient(to top, #a80077, #66ff00)”， 其中第一个参数为渐变方向，可取值： "to right"表示从左向右渐变， “to left"表示从右向左渐变， “to bottom"表示从上到下渐变， “to top"表示从下到上渐变， “to bottom right"表示从左上角到右下角， “to top left"表示从右下角到左上角|App 2.6.7+|
|background-repeat|string||||App 2.6.7+|
|blur-effect|string||||App 2.6.7+|
|loading|string|false|否|是否在导航条显示 loading 加载提示|微信基础库 2.9.0|
|front-color|string||否|导航条前景颜色值，包括按钮、标题、状态栏的颜色，仅支持 #ffffff 和 #000000|微信基础库 2.9.0|
|background-color|string||否|导航条背景颜色值，有效值为十六进制颜色|微信基础库 2.9.0|
|color-animation-duration|number|0|否|改变导航栏颜色时的动画时长，默认为 0 （即没有动画效果）|微信基础库 2.9.0|
|color-animation-timing-func|string|"linear"|否|改变导航栏颜色时的动画方式，支持 linear 、 easeIn 、 easeOut 和 easeInOut|微信基础库 2.9.0|

属性说明 [/collocation/pages?id=app-titlenview](/collocation/pages?id=app-titlenview)

**注意**
- `navigation-bar` 目前支持的配置仅为上表所列，并不支持 page.json 中关于导航栏的所有配置
- `navigation-bar` 与 pages.json 的设置相冲突时，会覆盖 page.json 的配置


#### 示例代码

```
<template>
  <page-meta>
    <navigation-bar
      :title="nbTitle"
      :titleIcon="titleIcon"
      :title-icon-radius="titleIconRadius"
      :subtitleText="subtitleText"
      :subtitle-color="nbFrontColor"
      :loading="nbLoading"
      :front-color="nbFrontColor"
      :background-color="nbBackgroundColor"
      :color-animation-duration="2000"
      color-animation-timing-func="easeIn"
    />
  </page-meta>
  <view class="content">
  </view>
</template>

<script>
  export default {
    data() {
      return {
        nbTitle: '标题',
        titleIcon: '/static/logo.png',
        titleIconRadius: '20px',
        subtitleText: 'subtitleText',
        nbLoading: false,
        nbFrontColor: '#000000',
        nbBackgroundColor: '#ffffff'
      }
    },
    onLoad() {
    },
    methods: {
    }
  }
</script>
```
