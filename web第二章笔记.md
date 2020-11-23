# 1.第2章-1-初始HTML5

## 1.HTML5概述

### 1.标记语言——HTML

HTML页面头部的“DOCTYPE”属性，用来定义用于解析目标DTD。HTML4<!DOCTYPE>标签可以声明三种 DTD 类型，**严格版本**（Strict）、过渡版本**（Transitional）和**基于框架（Frameset）的HTML文档HTML 被设计用来显示数据，其焦点是<font color =red >数据的外观</font>

### 2.标记语言——XML

XML也是SGML 的一个子集，XML 标签没有被预定义，您需要**自行定义标签**。XML被设计为传输和存储数据，其焦点是<font color =red >数据的内容</font>

## 2.HTML5基础

### 1.HTML5整体结构标签

## html标记：标记HTML文档的开始，通知客户端该文档是HTML文档。
head标记：在文档的起始部分，标明文档的头部信息，一般包括标题 和主题信息，结束标记"<<font color=red>/head</font>>"指明文档标题部分的结束。
body标记：用来指明文档的主体区域，该部分包容网页主体内容，
body中放置的是页面中所有的内容，如图片、文字、表格、表单、超链接等。

```html
<meta charset="UTF-8"> //简化的字符集
```

W3C推荐使用CSS文本属性也能设置网页元素样式

```html
<style type="text/css">  body{
background-color: red;
color: yellow;
}

```

### 3.HTML常用元素

align属性用于设置标题的对齐方式，其参数为left(左)、center(中)、right (右)。

```html
<img src = "图像URL"/>
```

vspace ; hspace

alt 图像不能显示时显示的内容

```HTML
<a href =" 文件名 ">链接元素</a>//超链接
```

```html
<a href = "链接地址" target="目标窗口打开方式" >Link text</a>
```

target属性：设定链接被单击之后，目标窗口的打开方式。可选值为：blank、_parent、_self、_top等。

| target值 |                      作用                      |
| :------: | :--------------------------------------------: |
| _parent  |   在上一级窗口打开，常在分帧的框架页面中使用   |
| _blacnk  |                新建一个窗口打开                |
|  _self   |        在同一个窗口打开，与默认设置相同        |
|   _top   | 在浏览器的整个窗口打开，将会忽略所有的框架结构 |

```html
<a name="label">锚（显示在页面上的文本）</a>//索引
```

ul元素（无序列表）、ol元素（有序列表）和dl元素（定义列表）。

```html
<dl>
<dt>计算机</dt>
<dd>用于大型计算的机器</dd>
<dd>可以上网冲浪</dd>
<dd>工作效率非常高</dd>
</dl>//一对<dt></dt>可以对应多对<dd></dd>即可以对一个名词进行多项解释
```

```html
<video src = "视频文件路径"control="controls"></video>//controls 属性用于为视频提 供播放控件
```

### 4.HTML表格

```HTML
<tr><td></td></tr><caption>标记用来给表格加上标题<th>定义了表格的表头，粗体居中显示<thead><tbody><tfoot>三个标签把表格分为三部分表头、表身、表脚
```

cellspacing间距、单元格之间的距离  ; colspan规定单元格可横跨的列数 ； rowspan规定单元格可横跨的列数

### 5.框架

不能将 <<font color=red>body</font>><<font color=red>/body</font>> 标签与 <<font color=red>frameset</font>><<font color=red>/frameset</font>> 标 签同时使用；

假如你添加包含一段文本的 <<font color=red>noframes</font>> 标签，就必须将这段文 字嵌套于 <<font color=red>body</font>><<font color=red>/body</font>> 标签内。

```html
<frameset cols="50%,50%" border="10">//rows水平分割cols垂直分割
<frame src="http://www.baidu.com"  noresize="noresize"/>
<frame
src="http://www.taobao.com" />
<noframes>
```

<<font color=red>iframe</font>>除了有<<font color=red>frame</font>>相同的属性（src/noresize/marginheight/marginwidth）外还有height/width

# 2.第2章-2-HTML5页面元素及属性

## 1.HTML结构元素
### 1块元素

```html
常见的块元素有<h1>~<h6>/<p>/<div>/<ul>/<ol>/<li>等，其中<div>标记是最典型的块元素
```

### 2.行内元素

```html
常见的行内元素有<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<a>、<span>等，其中<span>标记是最典型的行内元素。
```

### 3.语义化结构元素

header元素、nav元素、 section元素、article元素、aside元素、 footer元素等；
可以对应用来定义网页的页眉、导航链接、区块、网页体内容、工具栏和页脚等结构。

## 2.HTML5级块性元素

#### 1.figure元素和figcaption标签

figcaption元素用于为 figure元素组添加标题，一个figure元素内最多允许使用一个figcaption元素，该元素应该放在figure元素第一个或者最后一个子元素的位置。

### 3.HTML5新增的语义元素

#### 1.progress 元素

max，定义完成的值。 ;value，定义进度条的的当前值，如果不指定value值，则显示一个动态的进度。

# 第2章-3-Html5表单

## 1.认识表单

```html
<form ation ="url" method=get|post name="myform" target="_blank“>...</form>
```

name 设置表单名称; action 设置表单处理程序 method定义处理程序从表单中获得信息的方式，可取值为 get 和 post ; target指定目标窗口：可选当前窗口_self，父级窗口_parent，顶层窗口_top

## 2.HTML表单控件基础

空白窗口_blank

```html
<input type="TEXT" size= "" maxlength="">
```

单行的文本输入区域，size不maxlength属性定义输入区域显示的尺寸大小不输入的最大字符数

```html
<input type="button">
```

普通按钮，当这个按钮被单击时，就会调用属性onclick指定的凼数；在使用这个按钮时，一般配合使用value指定在它上面显示的文字，用onclick指定一个凼数，一般为JavaScript的一个事件

```html
用<textarea></textarea>//多行输入与标记
```

```html
<select name="star1" multiple size="4">//标记对用来创建一个菜单下拉列表框
<option value="zhmy">张曼玉</option>
<option value="wf" selected>王菲</option>//<!--selected表示默认选中项-->
</select>
```

value 属性对于不同 input 类型，用法也不同：

对于 "button"、"reset"、"submit" 类型 - 定义按钮上的文本

对于 "text"、"password"、"hidden" 类型 - 定义输入字段的初始（默认）值

对于 "checkbox"、"radio"、"image" 类型 - 定义与 input 元素相关的值，当提交表单时该值会发送到表单的 action URL。

## 3.HTML5新的input类型



| 类型         |                                                              |
| ------------ | ------------------------------------------------------------ |
| email        | 用于应该包含e-mail地址的输入域                               |
| url          | 用于应该包含URL地址的输入域                                  |
| number       | 包含数值的输入域（max最大值  min最小值 step规定合法的数字间隔 value默认值）； |
| Date Pickers | 个可供选取日期和时间的新输入类型                             |
| range        | 显示为滑动条                                                 |
| **search**   | 搜索域                                                       |
|              |                                                              |

data选取日、月、年 ；month选取年月 ；datetime选取时间、日、月、年（UTC） datetime-local选取时、日、月、年（本地时间）

