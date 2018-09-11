## 字号

设置字体大小

```css
.box {
  font-size: 14px;
}
```
设置字号最常用的单位是px、em、rem。em和rem都是相对单位，em相对于父元素的字号，rem相对于根元素的字号。<br/>
我在写h5页面时，常常使用rem给html加一个字号，然后整个页面的布局都参照html的字号设置大小，以此来实现可自动放大缩小的页面。

rem在实际应用中使用的示例：<br/>
下面是一个根据设计稿宽度计算font-size，并修改html的font-size的方法
```js
const resetRemUnit = (designWidth) => {
  const html = document.documentElement
  const width = html.clientWidth
  html.style.fontSize = width / (designWidth / 100) + 'px'
}
```
以下我们假如设计稿的宽度是750px，我们需要一个时机调用resetRemUnit方法并注册resize事件，使用页面能够根据宽度自动调整font-size
```js
resetRemUnit(750)
window.addEventListener('resize', () => {
  utils.resetRemUnit(750)
})
```
通过上面的方法，在页面的任何地方就可以使用rem做为单位实现可根据浏览器宽度自动放大缩小的页面了。假如设计稿上，宽度10px、高20px、字号14px的写法
```css
.box {
  width: .1rem;
  height: .2rem;
  font-size: .14rem;
}
```

字号的注意事项：<br/>
中文最小字号是12px
