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

## 第二章
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
|阴影模糊半径| 只能为正值，值为0时，表示阴影不具有模糊效果，值越大阴影的边缘就越模糊。|
|阴影扩展半径| 可正可负，正值表示整个阴影都延展扩大，负值表示缩小。 |
|投影方式| 外部阴影-outset 内部阴影-insert |
|||









