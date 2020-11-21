# 1.第3章-1-CSS基础与选择器

## 1.引用CSS样式

### 1.链入式

href属性：链接的外部样式表的URL。
type属性：定义所链接文档的类型，"text/css"表示链接的文档是css样式表。
<font color =red >rel 属性</font>：规定当前文档与被链接文档之间的关系。rel="stylesheet"表示被 
链接的是一个样式表文档。//rel属性不可省略
优先级：<font color =red >行内样式优先级>内嵌式>外联样式表</font>

#### 2.选择器

```html
1.<style>
#red{
color:#f00;
}
</style>//使用id选择器对页面中id属性值是“#red”的元素设置文字颜色红色。
2.<style>
.big{
font-size:20px;
}
</style>
}//使用类选择器对页面中class属性值是“.big”的元素设置字号20px。
3.<style>
*{color:#f00;}
</style>//通配符选择器（*）
```

### 3.兄弟选择器

```html
1.<style>
 h1 ~ p{ color:red; }
</style>//h1元素后面的所有的兄弟p元素，其文本颜色为红色，h1元素前的p段落元素文本颜色仍是默认的黑色。
2.<style>
 h1 + p{ color:red; }
</style>//h1元素后面紧邻的一个p元素
```

#### 4.伪类选择器

|    代码     |               作用               |
| :---------: | :------------------------------: |
|  a:hover：  | 设置元素E在其鼠标悬停时的样式。  |
|  a:link：   | 设置链接未被鼠标点击之前的样式。 |
| a:active：  |  设置链接被鼠标点击瞬间的样式。  |
| a:visited： | 设置当超链接被鼠标点击后的样式。 |

# 2.第3章-2-CSS相关属性

## 1.字体样式

### 1.font-style

| 属性值  | 说明       |
| ------- | ---------- |
| normal  | 正常的字体 |
| italic  | 斜体       |
| oblique | 倾斜的字体 |

## 2.文本样式属性

### 1.white-space:空白符处理

| 属性值 | 描述                                                  |
| ------ | ----------------------------------------------------- |
| normal | 文本中的空格、空行无效                                |
| pre    | 预格式化，按文档的书写格式保留空格、空行原样显示      |
| nowrap | 空格空行无效，强制文本不能换行，除非遇到换行标记</br> |

## 3.背景属性

### 1.background-size

| 属性值  | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| 像素值  | 设置背景图像的高度和宽度。第一个值设置宽度，第二个值设置高度 |
| 百分比  | 以父元素的百分比来设置背景图像的宽度和高度。                 |
| cover   | 把背景图像扩展至足够大，使背景图像完全覆盖背景区域。         |
| contain | 把图像扩展至最大尺寸，以使其宽度和高度完全适应内容区域       |

### 2.background-image

```html
background-image:linear- gradient(渐变角度,颜色值1,颜色 值2...,颜色值n);
```

## 4.CSS高级特性

### 1.CSS层叠性和继承性


# 3.第3章-3-CSS盒子模型&定位&动画等

## 1.CSS盒子模型
### 1.W3C盒子模型
![image](https://github.com/xietong1027/github-web/blob/master/W3C%E7%9B%92%E5%AD%90%E6%A8%A1%E5%9E%8B.png)
### 2.空格
```html
&nbsp ; /*空格*/
```
## 2.CSS3新增盒模型属性
### 1.padding定义设置的顺序//border-radiu//border相同
#### 1.各个分数性依次顺时针方向设置填充上边剧、右边距、下边距、左边距

padding:padding-top ; padding-right ; padding-bottom ; padding -left

### 2.border定义顺序

border:3px dotted red ;/*边框粗细 边框样式 边框颜色 */

### 3.box-shadow
#### 1.阴影水平偏移值h-shadow和阴影垂直偏移值v-shadow为必选参数值不能省略
### 4.背景图的处理
|        标签         |                             意义                             |
| :-----------------: | :----------------------------------------------------------: |
|    border-image     |                     边框样使用图像来填充                     |
| border-image-source |                     图像边框使用图像路径                     |
| border-image-slice  |                     边框背景图的分割方式                     |
| border-image-width  |                         图像边框厚度                         |
| border-image-outset |                     图像边框背景图的扩展                     |
| border-image-repeat | 图像边框是否应该平铺（repeat）、铺满（round）或拉伸（stretch） |
### 5.border-size定义
#### 1.content-box 表示padding 和 border不被包含在定义width 和 height 之内
#### 2.border-box表示padding 和 border 被包含在定义中，即使设置了 padding和border也不会改变盒子的大小
### 3.CSS定位
#### 1.position属性
| 值       | 描述                                               |
| -------- | -------------------------------------------------- |
| static   | 自动定位/静态定位（left/top不起作用）              |
| relative | 相对定位                                           |
| absolute | 绝对定位（将元素依据最近已经定位的父元素进行定位） |
| fixed    | 固定定位                                           |

### 4.CSS浮动

#### 1.float

#### 2.clear

### 5.移动端页面布局


#### 1.viewport

```html
<meta name = 'viewport'> content ='width '="device-width, initial -seale=1.0">
```

##### 1.设置viewport 的宽度：device-width;(宽度等于设备宽度)

##### 2.设置initial-seale=1.0属性默认不缩放

##### 3.设置user-scalable=no ;maximum -scale=1;避免用户误触，锁定页面缩放

#### 2.Flex布局

##### 1.任何一个容器都可以指定Flex布局，包括行内元素

##### 2.Webkit内核的浏览器，必须加上-webkit前缀

```html
.box{
display : -webkit-flex ;/*Safari*/
display:flex;
}  /*设置Flex布局以后，子元素的float/clear/vertical-align属性将失效
```

##### 3.justify-content属性

```html
.box{
justify-content:flex-start//左对齐 | flex-end//右对齐 | center//居中 | space-between//两端对齐，项目之间间隔相等 | space-around//每个项目两端间隔相等，项目之间的间隔比项目与边框的间隔大一倍
}
```

#### 4.align-items属性

```html
.box{
align-items:flex-start//交叉轴起点对齐 | flex-end//交叉轴终点对齐 | center//交叉轴中点对齐 | space-between//项目的第一行文字的基线对齐 | space-around//如果项目未设置高度或设为auto,将占满整个容器的高度
}
```

#### 5.order属性

```html
.item{
order:<integer>;
}/* 定义项目的排列顺序，数值越小，排列越靠前，默认为0*/
```

#### 6.flex-grow属性与flex-shrink属性

```html
.item{
flex-growL<number>;/*default 0*/
}/*默认为0，即如果存在剩余空间也不放大，换成flex0shrink是缩小，属性值作用相同*/
```
### 6.CSS3变形
#### 1.变形属性-transform

##### 1.transform-origin 改变元素原点位置 <font color =red>x-axis;y-axis;z-axis</font>

##### 2.使用rotate(angle)定义元素旋转角度

### 7.CSS过渡

#### 1.transition过渡属性

|            属性            |                 描述                 |
| :------------------------: | :----------------------------------: |
|         transition         |   用于在一个属性中设置四个过渡属性   |
|    transition-property     |     规定应用过渡的CSS属性的名称      |
|    transition-duration     |   定义过渡效果花费的时间。默认是0    |
| transition-timing-function | 规定过渡效果的时间曲线。默认是"ease" |
|      transition-delay      |    规定过渡效果何时开始。默认是0     |

##### 1.各个参数必须按照顺序进行定义，不能颠倒

##### 2.过渡属性transition经常与变形transform结合使用，设计不同变形状态间的过渡效果

### 8.CSS动画

#### 1.@ketframes规则创建动画

#### 2.transition 和animation区别

**transition**只能通过指定属性的开始值与结束值，通过两属性值之间进行平滑过渡的方式来实现动画效果，所以transition不能实现复杂的动画，而animation允许创建多个关键帧，通过对每个关键帧设置不同的属性值，实现复杂的动画效果





