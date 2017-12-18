## 禁用背景滚动

[源码](../demos/fix-bg.html)

#### 方案1 <br/>
在弹窗的时候，同时在可能出现滚动的条的容器上添加overflow: hidden，弹窗关闭时移除
```css
.container {
  overflow: hidden;
}
```

此方法是在阅读[vant](https://github.com/youzan/vant)的[源码](https://github.com/youzan/vant/blob/dev/packages/vant-css/src/popup.css)时发现的。
[ant-design-mobile](https://github.com/ant-design/ant-design-mobile)的解决方案相同，[源码](https://github.com/ant-design/ant-design-mobile/blob/master/components/modal/style/Dialog.less)。
