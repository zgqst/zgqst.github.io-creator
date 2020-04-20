---
title: "HMTL入门笔记1"
date: 2020-04-18T12:47:52+08:00
draft: flase
---
 # HTML入门笔记1
 ## HTML的发明者
 - HTML由Tim Berners-Lee（李爵士）在1990年发明  
  同时 李爵士也发明了WWW（万维网） HTML HTTP URL
 ## HTML的起手式
 ~~~html
 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
~~~
代码说明：  
- `<!DOCTYPE html>`：文档类型为HTML。意为向计算机说明解析方式为html。
- `<html lang="en">`：`<html>`标签为网页的顶级容器，一个网页只能有一个`<html>`标签，用来放置网页的元信息，内容为隐藏状态。lang为默认语言。意为该网页的默认语言为英语。
- `<head>`标签为`<html>`标签的第一个元素，如果不写网页会自动创建一个，一般包含7个子元素。
- `<meta>`:设置或说明网页的元数据。一般来说，网页的`<head>`中必须具有如上两个`<meta>`，且必须在`<head>`中的最上面。`name`为元数据的名字，`content`为元数据的内容。
  - `charset`：网页的编码方式，有许多种编码方式，但是几乎都选择UTF-8的编码方式。UTF-8 编码是 Unicode 字符集的一种表达方式。这个字符集的设计目标是包含世界上的所有字符，目前已经收入了十多万个字符。
  - `viewport`为窗口，content中的内容表示窗口宽度为设备屏幕的宽度，初始缩放比例为1。
- `<title>`标签为网页的标题，会影响网页在搜索引擎的排名，`<title>`标签中不能放其他的标签，只能放纯文本。
- `<body>`:网页的主体，用来放置网页的主题部分。
  
## HTML的标签
### 章节标签
   1. 标题`h1~h6`
   2. 章节`section`
   3. 文章`article`
   4. 段落`p`
   5. 头部`header`：网页、文章、章节的头部。
   6. 尾部`footer`：网页、文章、章节的底部，`$copy;`为版权符号，`header`和`footer`不能嵌套。
   7. 主要内容`main`：表示网页的主要内容，网页只能有一个`main`。
   8. 旁支内容`aside`
   9. 划分`div`：无语义，仅用来划分区块，应先使用有语义的其他标签。
### 内容标签
   1. `ol`（ordered list）:有序列表即123这样的排序，其中可嵌套`ol` `li`标签。属性含有reserved、start、type。
   2. `ul`（unordered list）：表示无序标签，即没有123的排序，其中可嵌套`ul` `li`标签。
   3. `li`：表示列表内容，含有属性`value`表示编号。
   4. `dl`(discreption list) `dt`(discreption term) `dd`(discreption detail):表示描述列表，对象，内容。
   5. `pre`:由于HTML会将重复的空格、换行符合并成一个空格，`pre`会保留其中的原格式。
   6. `code`：用于编写代码，其中字体等宽。
   7. `hr`：用于表示水平分割线，该标签没有闭合，单独使用。
   8. `br`(break):用于换行，单独使用，没有闭合。
   9. `em`（emphasis）:`em`为行内标签，表示强调，是语气上的强调，浏览器默认样式为斜体。
   10. `strong`:强调，表示内容上有很强的重要性，浏览器默认样式为加粗。
   11. `quote`：表示引用。
   12. `breakquote`：表示换行引用。
   13. `a`:用于表示链接，此处不详细展开。
## 默认样式
上文已经提到了浏览器的默认样式，因为大多数浏览器的默认样式违反大多数人的审美，因此基本都需要进行CSS reset，一般经过编写保存后作为一般预设，在实际情况下进行适当调整。
## 全局属性
1. class：对标签进行标记分类，同一个标签可以含有多个class，放在一个class中，用空格区分。
2. id：id为标签的唯一标识符，网页中不能有同样的id属性，且id的值中不能有空格。id属性的值还可以在最前面加上#，放到URL中作为锚点，定位到该元素在网页内部的位置。比如，用户访问网址https://foo.com/index.html#bar的时候，浏览器会自动将页面滚动到bar的位置，让用户第一眼就看到这部分内容。
3. contenteditable：用来表示用户是否可以编辑内容，他有两个值，true、false，使用的时候要带上值。
4. hidden：用来隐藏标签的内容，不会出现在网页上。注意，CSS可见性高于hidden。
5. style：用来指定标签的CSS样式，具体看CSS教程。
6. tableindex：指使用键盘的tab键进行索引，其值为-1，0，正整数，-1时代表不被tab索引，0代表最后被tab缩影，正整数代表按顺序被tab索引，不必连续。
7. title：代表鼠标悬浮到标签内容时显示的内容。