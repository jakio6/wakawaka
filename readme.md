# haha
-	盒模型
	- `width*height`
	- `padding`
	- `border`
	- `margin`
> 刚才vim文件格式出了问题:<br>
> :set fenc=编码 <br>
> :set fileencodings=utf-8 在保存一下格式就换过来了

- `box-sizing: border-box`
- `position`
	- `static`:默认,不会被特殊定位,不会被`positioned`
	- `relative`:
		- 没加什么额外属性的时候和`static`差不多
		- 加了之后会偏离正常位置
		- 它边上的就当它没动
	- `fixed`
		- 固定定位,相对于视窗来定位,即使页面滚动还是会停留在相同的位置
		- 与`relative`一样,`top`,`right`,`bottom`,and `left`属性都可用
		- 固定定位的会脱离文档流
	- `absolute`
		- 最棘手的`position`值
		- 与`fixed`表现类似,但不是相对与视窗而是相对于最近的`positioned`上级元素
		- 如果觉对定位的的元素没有`positioned`上级元素,那么他是相对于文档的body元素
		- 并且会随着页面滚动而移动
- `float'
	- 可用于实现文字环绕图片
	- 不想浮动的自己clear
- 清除浮动,clearfix hack
	- 浮动元素可能会溢出到父容器之外
	- `overflow:auto`
	- `zoom:1`
	- 水很深
	- 利用伪元素清除浮动
- 百分比布局
- 限制最大最小xxx
- 响应式设计
```css
@media screen and (min-width:600px) {
  nav {
    float: left;
    width: 25%;
  }
  section {
    margin-left: 25%;
  }
}
@media screen and (max-width:599px) {
  nav li {
    display: inline;
  }
}
```
- `display:inline-block`
	- 使用`inline-block`布局,有些事情要牢记
		- `vertical-algin`属性会影响到`inline-block`元素,可能要把它设置为`top`
		- 需要设置每一列的宽度,好像凑不下就会换行啦
		- 如果HTML源码中有空格,那么列于列之间会产生空隙
- 文字布局,`column`
```css
.three-column {
  padding: 1em;
  -moz-column-count: 3;
  -moz-column-gap: 1em;
  -webkit-column-count: 3;
  -webkit-column-gap: 1em;
  column-count: 3;
  column-gap: 1em;
}
```
- `flexbox`
```css
.container {
  display: -webkit-flex;
  display: flex;
}
nav {
  width: 200px;
}
.flex-column {
  -webkit-flex: 1;
          flex: 1;
}
```

```css
.container {
  display: -webkit-flex;
  display: flex;
}
.initial {
  -webkit-flex: initial;
          flex: initial;
  width: 200px;
  min-width: 100px;
}
.none {
  -webkit-flex: none;
          flex: none;
  width: 200px;
}
.flex1 {
  -webkit-flex: 1;
          flex: 1;
}
.flex2 {
  -webkit-flex: 2;
          flex: 2;
}
```
居中
```css
.vertical-container {
  height: 300px;
  display: -webkit-flex;
  display:         flex;
  -webkit-align-items: center;
          align-items: center;
  -webkit-justify-content: center;
          justify-content: center;
}
```
- over

<div style="position:absolute;margin-right:0;margin bottom:0;">
2018-06-17
<div>

- 盒模型用普通的box类型的时候千万不能忘记了要把padding算进去,血的教训
- 
