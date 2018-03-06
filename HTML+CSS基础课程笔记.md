HTML和CSS的关系
	HTML是网页内容的载体
	CSS样式是表现
	JavaScript是用来实现网页上的特效效果

创建表格的四个元素：
	1. table
		整个表格以<table>开始，以</table>结束
	2. tbody
		如果不加<thread><tbody><tfooter>，table表格加载完后才显示。加上这些表格结构，tbody包含行的内容下载完优先显示，不必等待表格结束后再显示，如果表格很长，用tbody分段，可以一部分一部分的显示。（通俗理解table可以按结构一块块的显示，不再等整个表格加载完后显示）。
	3. tr
		表格的一行，有几对tr标签，表格就有几行。
	4. td
		表格的一个单元格，一行中包含几对<td>...</td>，说明一行中有几列。
	5. th
		表格头部的一个单元格，表格表头。
	6. 表格中列的个数，取决于一行中数据单元格的个数。
表格摘要
	摘要的内容不会显示出来，它的作用是增加表格的可读性，使搜索引擎更好的读懂表格内容，还可以使屏幕阅读器更好的帮助特殊用户读取表格内容。
		语法：`<table summary="表格简介文本">`
表格标题
	用以描述表格内容，标题显示在表格上方。
		语法：
```HTML
        <table>
            <caption>标题文本</caption>
            <tr>
                <td>...</td>
                <td>...</td>
                ...
            </tr>
        </table>
```

### mailto
|功能|关键字|功能详解|举例|
|:--:|:---:|:---|:---|
|邮箱地址|mailto:|浏览器会自动调用默认的客户端电子邮件程序（如Outlook），并在收件人框中自动填上收件人地址|`<a href="mailto:yy@imooc.com">发送</a>`|
|抄送地址|cc=|在收件人地址后用cc=地址，可以填写抄送地址|`<a href="mailto:yy@imooc.com?cc=imoocAdmin@imooc.com">发送</a>`|
|密件抄送地址|bcc=|在收件人地址后用bcc=地址，可以填上密件抄送地址|`<a href="mailto:yy@imooc.com?bcc=pp@imooc.com">发送</a>`|
|多个收件人、抄送、密件抄送人|;|用分号隔开多个收件人的地址，可以实现发送给多个收件人功能|`<a href="mailto:yy@imooc.com;pp@imooc.com">发送</a>`|
|邮件主题|subject=|用subject=添加邮件主题|`<a href="mailto:yy@imooc.com?subject=发送电子邮件">发送</a>`|
|邮件内容|body=|用body=添加邮件的内容|`<a href="mailto:yy@imooc.com?body=哈喽">发送</a>`|

如果mailto后面同时有多个参数，第一个参数必须以`?`开头，后面的参数每一个都以`&`分隔。

### img

语法：
```HTML
<img src="图片地址" alt="下载失败时的替换文本" title="提示文本">
```
1. src
    标识图像的位置
2. alt
    指定图像的描述性文本，当图像不可见时（下载不成功时），可看到该属性指定的文本
3. title
    提供在图像可见时对图像的描述（鼠标滑过图片时显示的文本）
4. 图像可以是GIF，PNG，JPEG格式的图像文件

### 表单标签，与用户交互
表单是可以把浏览者输入的数据传送到服务器端，这样服务器端程序就可以处理表单传过来的数据。
语法：
```HTML
<form method="传送方式" action="服务器文件"></form>
```
1. `<form>`
    `<form>`标签是成对出现的，以`<form>`开始，以`</form>`结束
2. action
    浏览者输入的数据被传送到的地方，比如一个PHP页面（save.php）
3. method
    数据传送的方式（get/post等）
```HTML
<form method="post" action="save.php">
    <label for="username">用户名：</label>
    <input type="text" name="username" />
    <label for="pass">密码：</label>
    <input type="password" name="pass">
</form>
```
注意：
1. 所有表单控件（文本框、文本域、按钮、单选框、复选框等）都必须放在`<form>``</from>`之间（否则用户输入的信息提交不到服务器上）
2. method：post、get的区别

### 文本域
语法：
```HTML
<textarea rows="行数" cols="列数">文本</textarea>
```
1. `<textarea>`是成对出现的
2. cols：多行输入域的列数
3. rows：多行输入的行数
4. 在`<textarea></textarea>`标签之间可以输入默认值

### 单选框、复选框
语法：
```HTML
<input type="radio/checkbox" name="名称" value="值" checked="checked" />
```
1. type
    当type="radio"时，控件为单选框
    当type="checkbox"时，控件为复选框
2. value
    提交到服务器的值
3. name
    为控件命名，以备后台使用
4. checked
    当设置checked="checked"时，该选项默认被选中

注意：
    同一组的单选按钮，name取值必须一致。

### 下拉框
1. value
    `<option value="值">选项</option>`
2. selected
    设置selected="selected"属性，则该选项被默认选中
3. multiple
    在`<select>`标签中设置`multiple="multiple"`属性，可以实现多选功能，Windows下，按下Ctrl单击（Mac下使用Command+单击）可以选择多个选项

### 提交按钮
语法：
```HTML
<input type="submit" value="提交" />
```
1. type
    只有当type值为submit时，按钮才有提交作用
2. value
    按钮上的显示文字

### 重置按钮
语法：
```HTML
<input type="reset" value="重置" />
```
1. type
    只有当type值设置为reset时，按钮才有重置作用
2. value
    按钮上显示的文字

### form中的label标签

label标签不会向用户呈现任何特殊效果，它的作用是为鼠标用户改进可用性。如果在label标签内点击文本，就会触发此控件。就是说，当用户选中该label标签是，浏览器就会自动将焦点转到和标签相关的表单控件上（就自动选中和该label标签相关联的表单控件上）。

语法：
```HTML
<label for="控件id名称"></label>
```

注意：
标签的for属性的值应当与相关控件的id属性值相同。

### CSS代码语法
CSS样式由选择符和声明组成，而声明又由属性和值组成，如下：
```CSS
p {
    color: blue
}
```

1. 选择符
    又称选择器，指明网页中要应用样式规则的元素
2. 声明
    在英文大括号“{}”中的就是声明，属性和值之间用英文冒号“:”分隔。当有多条声明时，中间用英文分号“;”分隔。

注意：
1. 最后一条声明可以没有分号，但是为了以后修改方便，一般也加上分号；
2. 为了使用样式更加易读，可以将每条代码写在一个新行内

### 选择器
1. 标签选择器
```HTML
p {}
img {}
body {}
```
2. 类选择器
```HTML
.stress {}

<span class="stress">...</span>
```
3. ID选择器
```HTML
# setGreen {}

<span id="setGreen">...</span>
```
4. 类选择器和ID选择器的区别
    相同点：可以应用于任意元素
    不同点：
        1. ID选择器只能在文档中使用一次
        2. 可以使用类选择器词列表方法未一个元素同时设置多个样式
5. 子选择器
    用大于符号（>）,用于选择指定标签元素的第一代子元素，如下代码：
```HTML
.food>li{border:1px solid red;}
```
6. 包含（后代）选择器
    加入空格，用于选择指定标签元素下的后辈元素，如下代码：
```HTML
.first span {color:red;}
```
7. 通用选择器
    通用选择器是功能最强大的选择器，它是以一个（*）指定，作用是匹配HTML中所有标签元素，如下代码使HTML中任意标签元素文字颜色全部设置成红色：
```HTML
* {color: red;}
```
8. 伪类选择器
    伪类选择器允许给HTML不存在的标签（标签的某种状态）设置样式，比如我们给HTML中一个标签元素鼠标滑过的状态设置字体颜色：
```HTML
a:hover {color: red;}
```
9. 分组选择器
    当想为HTML中多个标签元素设置同一个样式时，可以使用分组选择符（，），如下代码表示将h1、span标签同时设置字体颜色为红色：
```HTML
h1, span {
    color:red;
}
```
    它相当于下面两行代码：
```HTML
h1 {color:red;}
span {color:red;}
```

### 继承性
CSS的某些样式是具有继承性的，继承是一种规则，允许样式不仅应用于某个特定的HTML标签元素，而且应用于其后代。

有些样式是不具有继承性的，如`border: 1px solid red;`

### 特殊性
有时候我们为同一个元素设置了不同的CSS样式，浏览器根据权值来判断使用哪种CSS样式，下面是权值规则：

+ 标签的权值为1
+ 类选择符的权值为10
+ ID选择符的权值为100

还有一个权值比较特殊——继承也有权值，但很低，有的文献提出它只有0.1，所以可以理解为继承的权值最低。

### 层叠

层叠就是在HTML文件中对于同一个元素可以由多个CSS样式存在，当有相同权重的样式存在时，会根据这些CSS样式的前后顺序来决定，处于后面的CSS样式会被应用。

### 重要性

有些特殊的情况需要为某些样式设置具有最高权值，这时候可以使用`!important`来解决。

注意：`!improtant`要写在分号的前面。

网页制作者不设置CSS样式时，浏览器会按照自己的一套样式来显示网页。并且用户也可以在浏览器中设置自己习惯的样式，比如有的用户习惯把字号设置大一些。这时注意样式优先级为：浏览器默认样式<网页制作者样式<用户自己设置的样式，但记住!important优先级样式是个例外，权值高于用户自己设置的样式。

### 文字排版

#### 字体
```HTML
body {font-family:"宋体";}
```
注意：不要设置不常用字体，如果用户电脑上没有安装你设置的字体，就会显示浏览器默认的字体。
#### 粗体、斜体、下划线、删除线
可以使用CSS样式来改变文字的样式：粗体、斜体、下划线、删除线。
```HTML
p span{
    font-weight:blod; /*粗体*/
    font-style:italic; /*斜体*/
    text-decoration:underline; /*下划线*/
    text-decoration:line-through; /*删除线*/
}
```
#### 缩进
中文文字中的段前习惯空两个文字的空白，这个特殊的样式可以通过下面代码实现：
```HTML
p {
    text-indent:2em;
}
```
#### 行间距
如下代码实现设置段落间距：
```HTML
p {
    line-height:1.5em;
}
```
#### 中文字间距、字母间距
如果想设置文字间隔或字母间隔就可以使用letter-spacing来实现，代码如下：
```HTML
h1 {
    letter-spacing:50px;
}
```
注意：这个样式使用在英文单词是，是设置字母与字母之间的间距。

如果想设置英文单词之间的间距，可以使用word-spacing来实现，代码如下：
```HTML
h1 {
    word-spacing:50px;
}
```
#### 对齐
想为块状元素中的文本、图片设置样式，可以使用text-align样式代码：
```HTML
h1 {
    text-align:center; /*居中*/
    text-align:legt; /*左对齐*/
    text-align:right; /*右对齐*/
}
```

### 元素分类

在CSS中，HTML中的标签元素大体被分为三种不同的类型：*块状元素*、*内联元素（行内元素）*和*内联块状元素*。

常用的块状元素有：
```
<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<table>、<address>、<blockquote>、<form>
```

常用的内联元素有：
```
<a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>
```

常用的内联块状元素有：
```
<img>、<input>
```

#### 块级元素

设置`display:block`就是讲元素显示为块级元素。如下代码就是讲内联元素a转换为块状元素，从而使a元素具有块状元素的特点。
```
a {display:block;}
```

块级元素的特点：
1. 每个块级元素都是从新的一行开始，并且其后的元素也另起一行。
2. 元素的高度、宽度、行高以及顶部和底边距离都可以设置。
3. 元素宽度在不设置情况下，是其本身父容器的100%。

#### 内联元素（行内元素）

块状元素也可以通过代码`display:inline`设置成内联元素。如下代码就是将块状元素div转换为内联元素，从而使div具有内联元素的特点：
```
div{
    display:inline;
}
```

内联元素的特点：
1. 和其它元素都在一行上；
2. 元素的高度、宽度以及顶部和底边边距不可设置；
3. 元素的宽度就是它包含的文字或图片的宽度，不可改变。

#### 内联块状元素

内联块状元素就是同事具备内联元素、块状元素的特点，代码`display:inline-block`就是将元素设置为内联块状元素。

内联块状元素特点：
1. 和其它元素都在一行上；
2. 元素的高度、宽度、行高以及顶部、底部边距都可以设置。

#### 水平居中总结——不定宽块状元素方法

不定宽度的块状元素有三种方法居中：
1. 加入table标签
    利用table标签的长度自适应性——即不定义其长度也不默认父元素body的长度（table长度根据其内文本长度决定），因此可以看错一个定宽块状元素，然后利用其定宽块状居中的margin方法，使其水平居中。
    1. 为需要设置居中的元素外面加入一个table标签（包括tbody、tr、td）；
    2. 为这个table设置“左右margin居中”（这个和定宽块状元素的方法一样）；
2. 设置display:inline方法：与第一种类似，显示类型设置为行内元素，进行不定宽元素的属性设置
3. 设置position:relative和left:50%：利用相对定位的方式，将元素向左偏移50%，即达到居中的目的

#### 垂直居中

1. 父元素高度确定的单行文本
    通过设置父元素的height和line-height高度一致来实现
2. 父元素高度确定的多行文本
    1. 使用插入table（包括tbody、tr、td）标签，同时设置vertical-align:middle

### CSS核心属性和浮动

#### CSS属性组成和作用

文本字体属性
1. 文本大小 font-size
    1. 属性值为数值型时，必须给属性值加单位，属性值为0时除外；
    2. 单位还可以是pt，9pt=12px；
    3. 为了减小系统间的字体显示差异，IE Netscape Mozilla的浏览器制作商在1999年召开会议，共同确定16px/ppi为标准字体大小默认值，即1em。默认情况下1em=16px。
2. 字体类型 font-family
    1. 当字体是中文字体时需加引号，如"宋体"
    2. 当英文字体中有空格时需加引号，如"Times New Roman"；
3. 文本颜色 color
    1. rgb，例如color:#f00；
    2. color:rgba(255, 0, 0, 0.6)；
4. 文本加粗 font-weight

CSS列表属性
1. 列表符号样式 list-style-type
    取值：disc(实心圆)、circle(空心圆)、square(实心方块)、none(无)
2. 使用图片作为列表符号 list-style-image  
    list-style-image:url(图片路径及全称)
3. 列表符号的位置 list-style-position
    取值：outside、inside
4. 简写方法
    {list-style: }
    可简写直接设置列表属性，常用属性list-style:none去掉列表样式

CSS边框属性
    语法：{border: ;}
    说明：
        边框样式 border-style:solid/dashed/dotted/double
            solid 实线，dashed 虚线，dotted 点状线，double 双线，none/0 无边框
        边框厚度 border-width
        边框颜色 border-color
    单独设置某个方向的边框属性：
        border-top
        border-right
        border-bottom
        border-left

CSS背景图属性
    背景颜色
        {background-color:颜色值}，简写background:color值
    背景图片
        background-image:url(背景图片的路径及全程)
        说明：
            网页上有两种图片的形式：插入图片、 背景图；插入图片：属于网页内容，也就是结构；
            背景图：属于网页的表现，背景图上可以显示文字、插入图片、表格等
        图片图片的显示原则：
            容器尺寸等于图片尺寸，背景图片正好显示在容器中；
            容器尺寸大于图片尺寸，背景图片默认平铺，直至铺完元素；
            容器尺寸小于图片尺寸，只显示元素范围以内的背景图；
            加载背景图必须有容器区域。
        背景图片平铺属性：
            语法：
                {background-repeat:no-repeat/repeat/repeat-x/repeat-y}
                no-repeat：不平铺
                repeat：平铺（默认）
                repeat-x：横向平铺
                repeat-y：纵向平铺
        背景图片的位置
            语法：{background-position:水平方向属性值 垂直方向属性值}
                水平方向属性值：left/center/right/数值
                垂直方向属性值：top/center/bottom/数值
            说明：
                水平向右 垂直向下移动 是正数值
                水平想做 垂直向上移动 是负数值
            两个值：第一个值表示水平位置的值，第二个值表示垂直位置的值
        背景图的固定
            语法：{background-attachment:scroll(滚动)/fixed(固定)}
            说明：fixed 固定，不随内容一块滚动；Scroll：随内容一起滚动

CSS浮动属性
    float：定义网页中其他文本如何环绕该元素显示
    有三个取值：
        left：元素活动浮动在文本左面
        right：元素浮动在右面
        none：默认值，不浮动
    浮动产生副作用
        1. 背景不能显示
            由于浮动产生，如果对父级设置了（CSS background背景）CSS背景颜色或CSS背景图片，而父级不能被撑开，所以导致CSS背景不能显示。
        2. 边框不能撑开
            如果父级设置了边框属性（CSS border），由于子级里使用了float属性，产生浮动，父级不能被撑开，导致边框不能随内容而被撑开。
        3. margin padding设置值不能正确显示
            由于浮动导致父级子级之间设置了CSS padding、CSS margin属性的值不能正确表达。特别是上下边的padding和margin不能正确显示。
    清除浮动
        注：
            浮动的框可以向左或向右移动，直到它的外边缘碰到包含框或另一个浮动的边框为止。浮动框是脱离了普通的文档流。
        清除浮动的方法：
            1. 父级添加overflow:hidden
                缺点：父级这个盒子不能放其他元素
            2. clear:both
            3. 万能清除浮动法









