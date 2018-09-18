# float

float是最常见的属性之一。当希望元素沿其容器的左侧或右侧放置时使用。浮动元素脱离文档流，使用浮动之后，需要清除浮动，否则父元素没有高度，清除浮动的方法是在浮动元素的后面跟上一个块级元素，并添加clear: both。<br/>

#### 向左浮动
```css
float: left;
```

#### 清除浮动，在容器元素上使用
```css
.clearfix {
  zoom: 1;
  &:before,
  &:after {
    content: ' ';
    display: table;
  }
  &:after {
    clear: both;
    visibility: hidden;
    font-size: 0;
    height: 0;
  }
}
```
