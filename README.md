# 10天精通css3
## 第一章
---
### 1.不同浏览器及其前缀

|    浏览器      |   前缀  |
|:-:            |:---:    |
| chrome/safari | -webkit |
|  firefox      | -moz    |
|     IE        |  -ms    |
|     opera     |  -o     |
|||

### 2.特性

#### 选择器
    能够减少标签中class和id的使用数量，很好的实现结构和样式分离

#### 圆角效果
    border-radius

#### 块阴影与文字阴影
    对任意DIV和文字增加投影

#### 渐变效果
    以前只能用Photoshop做出的图片渐变效果，现在可以用CCS写出来了

#### 个性化字体
    @Font-Face 轻松实现定制字体

#### 多背景图
    一个元素上添加多层背景图片

#### 变形处理
    对HTML元素进行旋转、缩放、倾斜、移动、甚至以前只能用JavaScript实现的强大动画

#### 变形处理
    对HTML元素进行旋转、缩放、倾斜、移动、甚至以前只能用JavaScript实现的强大动画

## 第二章边框
---
#### 2-1、基础使用
```
border-radius:10px;/*只有一个值时，全部的圆角*/
```
```
border-radius: 5px 4px 3px 2px;/* 有四个值时顺时针，左上、右上、右下、左下*/
```

上半圆：高为宽的一半，左上和右上的border-radius的值和高一致
``` CSS
.wrapper1{
    width: 200px;
    height: 100px;
    border-radius: 100px 100px 0 0;
}
```

实心圆：把宽度（width）与高度(height)值设置为一致（也就是正方形），并且四个圆角值都设置为它们值的一半。
``` CSS
.wrapper1{
    width: 200px;
    height: 200px;
    border-radius: 100px;
}
```
#### 2-2、阴影 box-shadow
可以为一个div添加一个或多个阴影

```CSS
box-shadow: X轴偏移量 Y轴偏移量 [阴影模糊半径] [阴影扩展半径] [阴影颜色] [投影方式];
```
|    值      |   描述  |
|:---            |:---   |
| X轴偏移量 | 必需。水平阴影偏移量，正值表示阴影在右边，负值表示阴影在左边 |
|Y轴偏移量  | 必需。垂直阴影偏移量，正值表示阴影在上边，负值表示阴影在下边    |
|阴影模糊半径| 可选。只能为正值，值为0时，表示阴影不具有模糊效果，值越大阴影的边缘就越模糊。|
|阴影扩展半径| 可选。可正可负，正值表示整个阴影都延展扩大，负值表示缩小。 |
|投影方式| 外部阴影-outset 内部阴影-insert |
|||

### 2-3、边框背景图片
```css
border-image:url(borderimg.png) 70 70 70 70 repeat;/* url的参数为字符串 图片路径，70 70 70 70 遵循顺时针原则，上右下左，单位是像素，也支持百分比  延伸方式由三种 repeat - 重复 round - 平铺 stretch - 拉伸*/
```

## 第三章 颜色
### 1、rgba()是红绿蓝三原色加上alpha通道
```CSS
color：rgba(R,G,B,A,0.3) /*前三个参数的取值范围是0-255 第四个的范围是0-1*/
```
### 2、线性渐变
线性渐变语法
```css
/*linear-gradient(top left,color1 color2,color3,color4 ... );*/
background-image: linear-gradient(to left,rgb(240, 140, 82), rgb(230, 61, 75));
background-image:linear-gradient(to left, red, orange,yellow,green,blue,indigo,violet);

```

|    角度      |   英文     |   作用    |
|:---          |  :---     |  :---     |
|      0deg    |  to top   |  从下向上  |
|      90deg   | to right  |  从左向右  |
|     180deg   | to bottom |  从上向下  |
|      270deg  |  to left  |  从右向左  |
|        -     |  to top left   |  右下向左上  |
|        -     |  to top right  |  左下向右上  |
||||

## 第四章 文字
### 1.text-overflow 和 word-wrap
text-overflow 是用来设置文字溢出所在区域是否设置成一个 `缺省标记`
```css
text-overflow:clip||ellipsis /*clip表示剪切 ellipsis表示显示成一个缺省标记 ... */
```
但是text-overflow只是设置了文字溢出所在区域后怎么显示，要想显示一个`缺省标记`，还要设置**overflow:hidden**溢出隐藏和 **white-space:nowrap** 强制在一行显示文本
```css
text-overflow:ellipsis;
overflow:hidden;
white-space: nowrap;
```
word-wrap是用来控制在行尾是否拆开单词，默认值是``normal``即是不拆开单词，也有``break-word``选项表示拆开单词换行。这个属性真的不常用，一般用浏览器默认的就好
```css
word-wrap: break-word;
```

### 2.@font-face
`@font-face`像一个语法糖，加载来自服务器端的字体，语法如下
```css
@font-face{
    font-family: "MOOC FONT";
    src:url("http://www.imooc.com/Amaranth-BoldItalic.otf")
}
```
之后就可以使用font-*来使用字体了。语法如下：
```css
font-family: "MOOC FONT";/*必须写，且需要制定为@font-face 引入的字体名*/
font-weight:500;
font-size: 18px;
```

### 3. text-shadow
```CSS
text-shadow: X-Offset Y-Offset blur color;
```

|    值      |   描述                                       |
|:-:         |:---:                                         |
| X-Offset   | 阴影水平偏移的距离，正值向右，负值向左          |
| Y-Offset   | 阴影垂直偏移的距离，正值向上，负值向下          |
|    blur    | 模糊程度，不可为负，0表示没有效果，越大越模糊    |
|||

## 第五章 背景

### 1、 background-origin
`background-origin` 描述的是背景图片从哪里开始显示。默认从内边距开始展示。
```CSS
background-origin: border-box | padding-box | content-box;
```
`注意：`如果背景不是no-peat，这个属性无效，会从`边框`开始显示

### 2、 background-clip
`background-clip` 裁切背景图片，满足需要。语法如下，默认会裁掉边框以外的部分，`no-clip`表示从不裁切。
```css
background-clip: border-box | padding-box | content-box |no-clip;
```

### 3、 background-size

`background-size` 背景图显示，默认值`auto`表示按照原图片显示，语法如下：
```CSS
background-size: auto | <长度值> | <百分比> | cover | contain
```

|    值      |   描述                                       |
|:-:         |:---:                                         |
| auto   | 原尺寸显示          |
| 长度值   | 成对出现，分别表示宽高；如果只写一个表示宽，高等比缩放  |
| 百分比   | 1%-100%。将背景图片的宽高依次设置成所在元素的宽高的百分比，如果设置一个值，设置宽，高等比缩放    |
| cover   | 如词意，封面，拉伸覆盖    |
| contain   | 适应最大边，另一边等比缩放    |
|||

### 3、 multiple-backgrounds
给一个元素添加多个背景。

`缩写写法`
```css
background ： [background-color] | [background-image] | [background-position][/background-size] | [background-repeat] | [background-attachment] | [background-clip] | [background-origin],...
```

`拆解写法`
```css
background-image:url1,url2,url3...urlN;
background-repeat:repeat1,repeat2,repeat3...repeatN;
background-position:position1,position2,position3...positionN;
background-attachment:attachment1,attachment2,attachment3...attachmentN;
background-origin: origin1,origin2,origin3...originN;
background-clip: clip1,clip2,clip3...clipN;
background-size: size1,size2,size3...sizeN;
background-color:color;
```
`注意：`
1. 逗号隔开没组值；
2. 如果有 size 值，需要紧跟 position 并且用 "/" 隔开；
3. 如果有多个背景图片，而其他属性只有一个（例如 background-repeat 只有一个），表明所有背景图片应用该属性值；
4. background-color 只能设置一个。















