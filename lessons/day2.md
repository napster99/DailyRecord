今天主要讲解 标签这块
html中下的标签主要有以下几个，我将列举出重点的几个标签（html元素）

* 标签分类 (重点标签)
    
    1、块级元素 block  
      div  h1 h2 h3 h4 h5 h6 p ul li ol 

    2、行内元素 inline   
      span  label  a 

    3、两者之间 inline-block
      img  input button

* 非常用标签


* html5新增标签

一、Html介绍
    1、Html和CSS的关系
        1. HTML是网页内容的载体
        2. CSS样式是表现（用来改变内容外观的东西称之为表现）
        3. JavaScript是用来实现网页上的特效效果（有动画的，有交互的一般都是用JavaScript来实现的）
    2、html标签
        <p></p>是段落标签
        <img>图片标签
    3、标签的语法
        1. 标签由英文尖括号<和>括起来
        2. html中的标签一般都是成对出现的，分开始标签和结束标签。结束标签比开始标签多了一个/。
        3. 标签与标签之间是可以嵌套的，但先后顺序必须保持一致
        4. HTML标签不区分大小写
    4、认识html文件基本结构
        一个HTML文件是有自己固定的结构的。
        <html>
            <head>...</head>
            <body>...</body>
        </html>
        1. <html></html>称为根标签，所有的网页标签都在<html></html>中。
        2. <head> 标签用于定义文档的头部，它是所有头部元素的容器
        3. 在<body>和</body>标签之间的内容是网页的主要内容
    5、head标签
        文档的头部描述了文档的各种属性和信息，包括文档的标题等。绝大多数文档头部包含的数据都不会
        真正作为内容显示给读者
        <title>标签：在<title>和</title>标签之间的文字内容是网页的标题信息，出现在浏览器的标题栏中
            网页的title标签用于告诉用户和搜索引擎这个网页的主要内容是什么，搜索引擎可以通过网页标题，迅速的判断出网页的主题。每个网页的内容都是不同的，每个网页都应该有一个独一无二的title。
    6、HTML的代码注释
        <!--注释文字 -->

二、认识标签（即 html中的元素）
   1、语义化，让你的网页更好的被搜索引擎理解
        标签的用途：语义化，明白每个标签的用途，
        1. 更容易被搜索引擎收录。
        2. 更容易让屏幕阅读器读出网页内容。
    2、<body>标签
        网页上显示的内容放在这里
    3、<p>标签
        添加段落
        <p>标签的默认样式，段前段后都会有空白，如果不喜欢这个空白，可以用css样式来删除或改变它。
    4、<hx>标签
        添加标题，有6个，h1、h2、h3、h4、h5、h6
        <hx>标题文本</hx> (x为1-6)
    5、<strong>和<em>标签
        加入强调语气：<em> 默认用斜体表示，<strong> 用粗体表示
        <em>需要强调的文本</em>  
        <strong>需要强调的文本</strong>
    6、<span>标签
        为文字设置单独样式：<span>文本</span>
        和em/strong比较
        1. <em>和<strong>标签是为了强调一段话中的关键字时使用，它们的语义是强调。
        2. <span>标签是没有语义的，它的作用就是为了设置单独的样式用的。
  
    7、<q>标签
        短文本引用：<q>引用文本</q>
        1. “庄生晓梦迷蝴蝶。望帝春心托杜鹃。” 这是一句诗歌，出自晚唐诗人李商隐的《锦瑟》 。因为不是作者自己的文字，所以需要使用<q></q>实现引用。
        2. 注意要引用的文本不用加双引号，浏览器会对q标签自动添加双引号。
        注意：用<q>标签的真正关键点不是它的默认样式双引号（如果这样我们不如自己在键盘上输入双引号就行了），而是它的语义：引用别人的话。
    8、<blockquote>标签
        长文本引用：<blockquote>引用文本</blockquote>
        浏览器对<blockquote>标签的解析是缩进样式
    9、<br>标签
        分行显示文本：作用相当于word文档中的回车
        xhtml1.0写法：
            <br />
        html4.01写法：
            <br>
        在html代码中输入回车、空格都是没有作用的。在html文本中想输入回车换行，就必须输入<br />
    10、&nbsp;
        空格
    11、<hr>标签
        添加水平横线
        html4.01版本 <hr>
        xhtml1.0版本 <hr />
        1. <hr />标签和<br />标签一样也是一个空标签，所以只有一个开始标签，没有结束标签。
        2. <hr />标签的在浏览器中的默认样式线条比较粗，颜色为灰色
    12、<address>标签
        加入地址信息
        <address>地址信息</address>：在浏览器上显示的样式为斜体
    13、code标签
        加入一行代码
        <code>代码语言</code>
        注：如果是多行代码，可以使用<pre>标签。
    14、pre标签
        <pre>语言代码段</pre>
        <pre> 标签的主要作用:预格式化的文本。被包围在 pre 元素中的文本通常会保留空格和换行符。
        注意：<pre> 标签不只是为显示计算机的源代码时用的，在你需要在网页中预显示格式时都可以使用它，只是<pre>标签的一个常见应用就是用来展示计算机的源代码。

    1、ul标签
        ul-li是没有前后顺序的信息列表。
            <ul>
                <li>....</li>
            </ul>
    2、ol标签
        有序列表来展示
            <ol>
                <li>...</li>
            </ol>
        每项<li>前都自带一个序号，序号默认从1开始
    3、div标签在排版中的作用
        可以把一些独立的逻辑部分划分出来，放在一个<div>标签中，这个<div>标签的作用就相当于一个容器。
        <div>…</div>
    4、给div命名
        <div  id="版块名称">…</div>
    5、table标签
        创建表格的四个元素：table、tbody、tr、th、td
        1、<table>…</table>：整个表格以<table>标记开始、</table>标记结束。
        2、<tbody>…</tbody>：当表格内容非常多时，表格会下载一点显示一点，但如果加上<tbody>标签后，这个表格就要等表格内容全部下载完才会显示。如右侧代码编辑器中的代码。
        3、<tr>…</tr>：表格的一行，所以有几对tr 表格就有几行。
        4、<td>…</td>：表格的一个单元格，一行中包含几对<td>...</td>，说明一行中就有几列。
        5、<th>…</th>：表格的头部的一个单元格，表格表头。
        6、表格中列的个数，取决于一行中数据单元格的个数。
            1、table表格在没有添加css样式之前，在浏览器中显示是没有表格线的
            2、表头，也就是th标签中的文本默认为粗体并且居中显示
    6、caption标签
        表格还是需要添加一些标签进行优化，可以添加标题和摘要。
        摘要：的内容是不会在浏览器中显示出来的。它的作用是增加表格的可读性(语义化)，使搜索引擎更好的读懂表格内容，还可以使屏幕阅读器更好的帮助特殊用户读取表格内容。<table summary="表格简介文本">
        标题：用以描述表格内容，标题的显示位置：表格上方。在<table> 和 <tr>之间：<caption>标题文本</caption>
    1、<a>标签
        <a  href="目标网址"  title="鼠标滑过显示的文本">链接显示的文本</a>
        title属性的作用，鼠标滑过链接文字时会显示这个属性的文本内容。这个属性在实际网页开发中作用很大，主要方便搜索引擎了解链接地址的内容（语义化更友好）
    2、在新建浏览器窗口中打开链接
        <a href="目标网址" target="_blank">click here!</a>
    3、使用mailto在网页中链接Email地址
        <a>标签还有一个作用是可以链接Email地址，使用mailto能让访问者便捷向网站管理者发送电子邮件
        注意：如果mailto后面同时有多个参数的话，第一个参数必须以“?”开头，后面的参数每一个都以“&”分隔。
        邮箱地址：mailto:
        抄送地址：cc=
        密件抄送地址：yy=
        多个收件人、抄送、密送抄送人（;)
        邮件主题：subject=
        邮件内容：body=
    4、<img>标签，插入图片
        <img src="图片地址" alt="下载失败时的替换文本" title = "提示文本">
        1、src：标识图像的位置；
        2、alt：指定图像的描述性文本，当图像不可见时（下载不成功时），可看到该属性指定的文本；
        3、title：提供在图像可见时对图像的描述(鼠标滑过图片时显示的文本)；
        4、图像可以是GIF，PNG，JPEG格式的图像文件。

三、表单标签=>与浏览者交互


   1、使用表单标签，与用户交互
        <form   method="传送方式"   action="服务器文件">
        1.<form> ：<form>标签是成对出现的，以<form>开始，以</form>结束。
        2.action ：浏览者输入的数据被传送到的地方,比如一个PHP页面(save.php)。
        3.method ： 数据传送的方式（get/post）。
        注意：
        1、所有表单控件（文本框、文本域、按钮、单选框、复选框等）都必须放在<form></form>标签之间（否则用户输入的信息可提交不到服务器上！）。
        
    2、文本输入框、密码输入框
        <form>
               <input type="text/password" name="名称" value="文本" />
        </form>
            1、type
            当type="text"时，输入框为文本输入框;
            当type="password"时, 输入框为密码输入框。
            2、name：为文本框命名，以备后台程序ASP 、PHP使用。

            3、value：提示作用
    3、文本域（多行文本输入）
        <textarea  rows="行数" cols="列数">文本</textarea>
        1、<textarea>标签是成对出现的，以<textarea>开始，以</textarea>结束。
        2、cols ：多行输入域的列数。
        3、rows ：多行输入域的行数。
        4、在<textarea></textarea>标签之间可以输入默认值。

    4、单选框、复选框
        单选框中的选项用户只能选择一项
        复选框中用户可以任意选择多项，甚至全选
        <input   type="radio/checkbox"   value="值"    name="名称"   checked="checked"/>
        radio：单选
        checkbox：复选
        value：提交到服务器的值
        name：控件命名
        checked：当设置为checked时，该选项被默认选中
        注意：同一组的单选按钮，name取值一定要一致，这样同一组的单选按钮才可以起到单选的作用。

    5、下拉列表
        <option value = "向服务器提交的值">显示的值</option>
            selected:有设置是默认被选中

    6、下拉列表多选
        <select multiple="multiple">
            <option value = "向服务器提交的值">显示的值</option>
        </select>
        在<select>标签中设置multiple="multiple"属性，就可以实现多选功能，进行多选时按下Ctrl键同时进行单击，可以选择多个选项

    7、提交按钮
        <input   type="submit"   value="提交">
        只有type值为submit时按钮才有提交作用，value是按钮上显示的文字

    8、重置按钮
        <input type="reset" value="重置">
        只有当type值设置为reset时，按钮才有重置作用,value是按钮上显示的文字

    9、form表单中的label标签
        label标签不会向用户呈现任何特殊效果，它的作用是为鼠标用户改进了可用性
        如果你在 label 标签内点击文本，就会触发此控件。就是说，当用户单击选中该label标签时，浏览器就会自动将焦点转到和标签相关的表单控件上（就自动选中和该label标签相关连的表单控件上）。
        <label for="控件id名称">
        注意：标签的 for 属性中的值

