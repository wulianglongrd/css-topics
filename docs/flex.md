# flex

flex也称之为弹性布局，是在css3引入的。目前主流浏览器都支持flex布局。flex在解决居中、子元素弹性等分、左边固定+右边取余等问题都十分方便。<br/>

flex相关的属性分为容器属性和弹性元素属性。具体可参考 [Flex 布局教程：语法篇](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html) <br/>

#### 下面给出我工作中经常用到flex的示例

一种水平垂直都居中的方案
```html
<div class="container">
  我是水平垂直都居中的
</div>
```
```css
.container {
  display: flex;
  width: 300px;
  height: 100px;
  border: 1px solid #ccc;
  justify-content: center;
  align-items: center;
}
```

一种常见的后台布局<br/>
header固定 + footer固定 + 内容区域占满除页头页脚本之页的区域，若超出浏览器的高度则滚动内容区域
```html
<div class="container">
  <div class="header">
    header
  </div>
  <div class="main">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
  </div>
  <div class="footer">
    footer
  </div>
<div>
```
```css
* {
  margin: 0;
  padding: 0;
}
html, body {
  height: 100%;
  text-align: center;
}
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.header {
  height: 80px;
  border-bottom: 1px solid red;
}
.main {
  flex: 1;
  overflow: auto;
}
.main > div {
  margin: 50px;
  border: 1px solid #ccc;
  height: 300px;
}
.footer {
  height: 120px;
  border-top: 1px solid red;
}
```

一种常用的菜单布局，无论容器宽度是多少，也无论子元素多少个，子元素都是等分的
```html
<ul class="menu">
  <li>菜单一</li>
  <li>菜单二</li>
  <li>菜单三</li>
  <li>菜单四</li>
</ul>
```
```css
* {
  margin: 0;
  padding: 0;
}
.menu {
  width: 800px;
  display: flex;
  margin: 0 auto;
  border: 1px solid #ccc;
}
li {
  flex: 1;
  list-style: none;
  text-align: center;
  height: 60px;
  line-height: 60px;
}
li:not(:last-child) {
  border-right: 1px solid #ccc;
}
````

一种常用的左边固定+右边取余方法
```html
<div class="container">
  <div class="item1">
    item 1
  </div>
  <div class="item2">
    item 2
  </div>
  <div class="item3">
    item 3
  </div>
</div>
```
```css
* {
  margin: 0;
  padding: 0;
}
.container {
  display: flex;
  width: 600px;
  height: 60px;
  margin: 50px auto;
}
.container > div {
  border: 1px solid #ccc;
}
.item1, .item2 {
  width: 100px;
}
.item3 {
  flex: 1;
}
```
