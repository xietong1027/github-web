# 1.第4章-1-JavaScript基础

## 1.Javascript基础知识

### 1.JavaScript数据类型

1.值类型(基本类型)
字符串（String）、数字(Number)、布尔(Boolean)、空（Null）、未定义（Undefined）
2.引用数据类型
对象(Object)、数组(Array)、函数(Function)

### 2.NAN特殊的Number值

NaN是number类型中一个特殊的数值，在JavaScript中它有个奇怪的定义：非数值（Not a Number）,即是一个 **不是数字的数值**，这个数值用于表示一个本来要返回数值的操作数未返回数值的情况。

```javascript
NaN === NaN
false //NaN与本身不相等
```

### 3.underfined类型与Boolean类型

undefined类型：当声明的变量未初始化时，该变量就是undefined类型，值也是undefined

Boolean型的值只有两个值：**true** 或 **false **。

### 4.String类型

```javascript
<script> 
var a=8+5;
document.write(a); //输出13 
var b="8"+5;
document.write(b); //'8'+'5' ="85" 连接符，输出85 
var c=true+"happy";
document.write("c="+c); //布尔值转换为字符串，输出
truehappy
</script>
```

## 2.JavaScript 对象Var

### 1.JavaScript对象的成员

描述对象的特征，对象名.属性名 ;有两种方式可以访问对象属性

```javascript
.property 或 ["property"].
```

### 2.JavaScript数组

与其它程序语言不同的是，JavaScript的**数组元素的数据类型可以不相同**

```javascript

<script>
var arr1=new Array(1,true,"happy"); //数组遍历
for(var i=0;i<arr1.length;i++)
{
document.write(arr1[i]); 
document.write("<br/>"); }

```

数组操作-插入；删除

 1.从队尾插入删除元素push() 方法（在数组结尾处）向数组添加一个新的元素；pop() 方法从数组结尾处中删除最后一个元素。

2.从头部插入删除元素:unshift() 方法（在开头）向数组添加新元素 ; shift() 方法会删除开头的元素。

3.在任意位置插入删除元素:splice() 方法既可以在数组的任意位置插入元素，也可以在数组的任意位置删除元素。

```javascript
var mycars=["Saab","Volvo","BMW"];//队尾删除元素
var car=mycars.pop();
document.write("被删除的元素："+car+"<br/>"); 
for(var key in mycars) 
document.write(mycars[key]+" "); //队尾插入元素
var newlength=mycars.push("奔驰","宝马"); 
document.write("新长度"+newlength); 
for(var i=0;i<newlength;i++)
document.write(mycars[i]+" ");


```

## 3.字符串

### 1.字符串搜索

1.**indexOf()** **方法**：返回字符串中指定文本首次出现的索引（位置）；

2.**lastIndexOf()** **方法**：返回指定文本在字符串中最后一次出现的索引；

3.**search()**：用于检索字符串中指定的子字符串

4.**match()方法**：它将返回一个数组，其中存放了与它找到的匹配文本有关的信息

5.<font color=red>无匹配返回-1</font>；

```javascript
var str = 'abcdeabcde'; //lastIndexOf(搜索词,起始索引位置) 检索顺序 从后往前
var str = 'abcdeabcde'; 
console.log(str.lastIndexOf('a')); // 返回5;文本在字符串中最后一次出现的索引
console.log(str.lastIndexOf('a', 3)); // 返回0，从索引3的位置从后往前搜索
```

# 2.第4章-2-HTTP协议

## 1.HTTP协议

### 1.HTTP报文：报文首部、CR+LF 、报文主体

### 2.HTTP请求包：方法+url+请求头+正文

```javascript
GET /ntes.js HTTP/1.1 \r\n
```

### 3.HTTP响应包：协议版本+状态码+状态描述+应答头+正文

## 2.HTTPS

### 1.HTTPS=HTTP+TLS/SSL

HTTPS:HTTP的安全版，其安全基础是SSL协议,默认使用TCP端口443,优点：**信息加密，完整性校验，身份验证**

### 2.TLS/SSL的功能实现主要依赖于三类基本算法：<font color = 'red'>散列函数 Hash、对称加密和非对称加密 </font>

TLS/SSL = 非对称加密（身份验证密钥协商）+对称加密（信息加密）+散列算法（完整校验）

### 3.身份验证CA和证书

``` mermaid
graph LR
A(审核) --> B(CA)
B(CA) --> A(审核)
B(CA) --> C(server)
C(server) --> B(CA)
C(server) --> D(client)
D(client) --> C(server)
```

1.申请认证 2.审核信息 3.签发证书 4.返回证书 5.验证证书 6.密钥协商 

# 3.第4章-3-JavaScript Ajax&JSON

## 1.同步与异步

### 1.描述两者之间的行为方式

1.同步 彼此等待 -- 阻塞

2.异步 各做各的 --非阻塞

## 2.Ajax的应用

Ajax表示异 步JavaScript和XML，但是它不是像HTML、JavaScript或CSS这样的一种“正式的”技术，它是表示一些技术的混合交互的一个术语（JavaScript、Web浏览器和Web服务器），它使我们可以获取和显示新的内容而<font color =red>不必载入一个新的Web页面</font>。增强用户体验，更有桌面程序的感觉。

### 1.发送Ajax请求步骤

``` mermaid
 graph LR
A(创建XMLHttpRequest对象) --> B(准备发送) --> C(执行发送动作) --> D(指定回调函数)
```

指定回调函数（xhr.onreadystatechange=function()）

• xhr.readyState：0 xhr对象初始化   ；1 执行发送动作 ； 2 服务器端数据已经完全返回  ；3 数据正在解析 ；4 数据解析完成，可以使用了

• xhr.status： 200 数据相应正常   ； 404 没有找到资源  ；500 服务器端错误

## 3.跨域及解决方案

1.同源策略：是浏览器的一种安全策略，所谓同源指的是请求URL地址中的<font color =red>协议、域名和端口都相同</font>，只要其中之一不相同就是跨域,同源策略主要为了保证浏览器的安全性,在同源策略下，浏览器不允许Ajax跨域获取服务器数据。

2.解决方案：<font color =red >jsonp</font>  ；document.domain+iframe ； location.hash + iframe  ；window.name + iframe ； window.postMessage

jsonp原理：静态script标签的src属性进行跨域请求 ；动态创建script标签，通过标签的src属性发

送请求

## 4.JSON的应用

### 1客户端处理json的响应

服务器端返回JSON相应的文本表示，如：{“city” : “Hefei”, “province” : “Anhui”}

客户端使用eval()函数将JSON文本转化为JavaScript对象：

```javascript
var resonse =eval ("(" + request.resonseText + ")");
```

注意，使用额外的圆括号可使eval()函数将来源输入无条件地视为表达式进行解析。然后从JavaScript对象中取得相应的值：

```javascript
document.getElementById("city").value = response.city ;
document.getElementById("province").value = response.province ;
```

