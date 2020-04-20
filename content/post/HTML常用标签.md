---
title: "HTML常用标签"
date: 2020-04-20T09:56:53+08:00
draft: false
---

# a标签
a标签用于编写链接，包括页面的跳转，页面标签的定位，邮件链接，手机端也可用于电话的跳转。
~~~html
<a href="//gogle.com" target="_blank" download="xxx">
<img src="1.jpg" width="100%" alt="图片">
</a>
~~~
   a标签中可放置文字、图片、多媒体等，a标签将其转化为可以点击的链接。
## a标签常用属性。
* href href中可以填写链接的请求地址，主要有以下几种
   > 1. 网址<br>`https://google.com`  
   `http://google.com`  
   `//google.com`  
   根据协议的不同 网址也会不同 因此基本使用第三种写法，浏览器会自动匹配协议类型  
   > 2. 路径地址 需要注意的是http协议的根目录不是硬盘的根目录 而是打开服务的路径 因此填写的路径地址会打开服务的路径里进行寻找 
   >3. 文件名 会打开当前路径下的文件
   >4. 留空 效果为点击后刷新页面
   >5. #aaa 与id属性连用 aaa为页面中的id属性 效果为点击后转到id属性的标签处
   >6. 伪协议 填入Js的空代码 效果为点击后没有动作;mailto： 填写邮箱会启用默认邮件程序向目标地址发送邮件 不填写则由用户进行地址填写 一般用来邮件分享;tel： 填写手机会自动拨号 一般用于手机页面
* target target代表了网页的打开方式 不写target浏览器默认为在原页面直接打开 target主要有几个值
   > 1. _self 与默认相同 在原页面直接打开  
   > 2. _blank 在新标签页打开  
   > 3. _top 在最高层级页面打开（有分级页面时  
   > 4. _parent 在父级页面打开（有分级页面时  
   > 5. iframe引用页面的名字 在iframe引用的页面中打开 可以制作切换网站  
   > 6.  XXX XXX为文本 意为在名为XXX的页面打开 若没有则新建页面 多用于防止页面过多增加
* download 用于下载的链接 注意下载链接要与网页属同一网站才可使用 download如果设置了值 那么这个值即是文件名
# img标签
如上面的代码，img标签是单独使用的，没有闭合，默认是行内元素，与前后文字处于同一行。  
  ## img标签的常用属性
> 1. src 指明图片的地址 地址为相对路径  
> 2. alt 文本值 用于图片加载失败或用户停止加载使用 提示用户图片内容  
> 3. width height 宽度和高度值 设置其中一个 图片会自动比例缩放 同时设置图片会变形 绝对不可以让图片变形  
> 4. 图形的响应式 此处不做详解
## img标签事件
onload/onerror 使用Js代码编写用以监听图片的加载情况。
# iframe标签
iframe用于生成一个区域，在该区域中嵌入其他的网页。需要浏览器的支持，现在多用AJAX。  
## iframe的常用属性
  >1. src 用来填写网页地址  
  >2. width height 设置网页格式大小  
  >3. frameborder 框架边界 设置边框格式  
  >4. name 设置内嵌窗口的名字 可用于a标签、form标签、base标签等的target值  
  >5. sandbox 用于设置内嵌窗口的权限 权限默认拥有正常权限 比如执行脚本、提交表单、弹出窗口等 通过sandbox可以逐项打开权限 不填写值表示拥有所有权限  
  >6. loading 指定的网页会立即加载 有时这不是希望的行为 滚动进入视口以后再加载 这样会比较节省带宽 loading有三个值 auto表示浏览器默认值 与不用loading相同；lazy表示启用懒加载；eager表示立即加载 注意如果iframe是隐藏的 则会立即加载 隐藏条件不详细展开
# table标签
table标签用于生成表格 是一个容器元素
 ~~~html
 <table>
        <thead>
        <caption>成绩</caption>
            <tr>
                <th> </th>
                <th>小明</th>
                <th>小红</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <th>语文</th>
                <td>85</td>
                <td>95</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <th>数学</th>
                <td>95</td>
                <td>100</td>
            </tr>
        </tfoot>
    </table>
~~~  
上面的代码效果如下  
![](/images/tabel.png)
************  
## table内的常用元素  
如上图所示   
1. caption表示表的标题  
2. thead、tbody、tfoot表示表头、身、脚 可以打乱顺序 浏览器将自动调整头至脚的顺序 如果不写这三个元素直接开始编写表格的行列 浏览器将给所有的内容加上tbody   
3. thead、tbody、tfoot中可以嵌套tr、th、td tr表示表格的一行 th表示行列的标题 td表示行列的数据 th、td还有许多的属性 举colspan、rowspan来说明 colspan用在一个单元格跨两列的情况 rowspan则相反 其他属性不详细展开 另外不写tr而直接编写th、td 浏览器会自动加上tr标签
  
# form标签
表单（form）是用户输入信息与网页互动的一种形式。大多数情况下，用户提交的信息会发给服务器，比如网站的搜索栏就是表单。
表单由一种或多种的小部件组成，比如输入框、按钮、单选框或复选框。这些小部件称为控件。
~~~html
<form action="https://example.com/api" method="post">
        <label for="POST-name">用户名：</label>
        <input id="POST-name" type="text" name="user">
        <input type="submit" value="提交">
    </form>
~~~
代码的运行结果如下图 这是一个比较常见的表单
![](/images/htmlform.png)  
## form的常用属性
>1. action 用来填入提交数据的地址
>2. method 表示请求的方式 有get和post两个值
>3. target 表示服务器返回数据页面的打开方式(_self _blank _top _parent)
>4. autocomplete 有两个值on、off 意为用户如果没有填写某个控件浏览器是否可以自动填写 效果为下拉一个框 其中有历史填写记录
## form的控件
form中通常会配合label、input等控件 但是提交按钮也可以不使用input来写 可以用button控件来编写 相比于input的按钮 button可以对其中的内容进行控制 可以是图片 也可以加上strong等属性 但是input不可以对内容进行编辑
## form的事件
onsubmit
# input标签
input标签是一个行内元素，用来接收用户的输入。它是一个单独使用的标签，没有结束标志。  
## input的类型
input有多种类型 用type属性来控制 不写type则默认为text类型
~~~html
<input>
   等同于 
<input type="text">
~~~
1. text类型 效果为输入框  
2. color类型 作用为选择颜色
3. password类型 效果为用 · 代替填入的文本 用于保密
4. radio类型 圈选类型 单选框
~~~html
<form> 
  <p>Please select your preferred contact method:</p>
  <div>
    <input type="radio" id="contactChoice1"
           name="contact" value="email">
    <label for="contactChoice1">Email</label>
    <input type="radio" id="contactChoice2"
           name="contact" value="phone">
    <label for="contactChoice2">Phone</label>
    <input type="radio" id="contactChoice3"
           name="contact" value="mail">
    <label for="contactChoice3">Mail</label>
  </div>
  <div>
    <button type="submit">Submit</button>
  </div>
</form>
~~~
上图代码得到的效果为![](/images/inputradio.png)
注意多个单选框的name应是一致的 input使用id属性来与label标签的for属性进行对应 注意不要忘记设置value的值！设置balue的值 选中提交给浏览器的表单数据为contact=mail 不设置value的值 表单数据则为contact=on 没有意义  
****
5. checkbox 多选框 
~~~html
<fieldset form="interestchoices" name="interest">
        <legend>你的兴趣是？
        </legend>
        <p>
            <input type="checkbox" id="cbox1" value="sing" name="interest" disabled>
            <label for="interest">唱</label>
        </p>
        <p>
            <input type="checkbox" id="cbox2" value="dance" name="interest" checked>
            <label for="interest">跳</label>
        </p>
        <p>
            <input type="checkbox" id="cbox3" value="basketball" name="interest">
            <label for="interest">篮球</label>
        </p>
    </fieldset>
~~~
上图代码得到的效果为![](/images/inputcheckbox.png)
下面对代码进行解释
- fieldset 用来包容所有的控件的合集 form属性对应表单的id name属性对应控件的名字 disabled一旦设置则其中的控件都变成灰色失去能力
- legend 用来编辑控件组的标题
- p 标签用来分段
- checked 用来表示默认选中  
***
6. file类型 用于文件的上传 添加属性multiple可多选文件
7. hidden类型 不显示 主要留给浏览器输入
# select标签+option标签
select标签用于生成一个下拉菜单。
~~~html
<select id="pet-select" name="pet-select">
            <option value="">--请选择一项--</option>
            <option value="dog"selected>狗</option>
            <option value="cat">猫</option>
            <option value="others">其他</option>
        </select>
~~~
上述代码效果为  
![](/images/selcet.png)  
selected为默认选项 因此默认为狗
# textarea标签
textarea标签用来生成一个可以让用户编辑的文本框
他的主要属性有  
1. id name disabled等属性
2. rows cols规定文本框大小
3. autofocus 布尔属性 自动获得鼠标焦点
4. placeholder 空文字时显示的文本
5. readonly 布尔属性 只读文本
6. required 布尔属性 必填文本
7. wrap 是否换行 有三个值hard、soft、off 具体不详细展开



