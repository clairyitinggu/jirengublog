# HTML入门笔记1

# HTML 是谁发明的

HTML是由Tim Berners-Lee（全称Sir **Timothy John Berners-Lee**）发明的, 英国的计算机科学家，1990年12月25日，他成功利用互联网实现了超文本传输协议客户端与服务器的第一次通讯。 伯纳斯-李是万维网联盟的主席，为关注万维网发展而创办的组织。--摘自维基百科

![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Sir_Tim_Berners-Lee_%28cropped%29.jpg/500px-Sir_Tim_Berners-Lee_%28cropped%29.jpg)

# HTML 起手应该写什么

Emmet

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

lang表示language, 中文一般写成zh-CN

head里写的都是看不见的元素

meta charset="UTF-8",代表字符串编码是“UTF-8”，这个字符串集涵盖了世界上所有的语言，如果charset设置和实际写的语言不同的话，就会造成乱码。

meta name="viewport"，viewport代表视窗，整行代码可以防止页面缩放。

meta http-equiv: content="IE=edge",告诉浏览器，如果使用的是IE浏览器，请升级成最新的IE内核。



# 常用的表章节的标签有哪些，分别是什么意思

### 标题`h1 - h6`

### 章节`section`

### 文章`article`

### 段落`p`

### 头部`header`

### 脚部`footer`

### 主要内容`main`

### 旁支内容`aside`

### 划分`div`



# 全局属性有哪些

### `class` 给标签分类 `.class`

### `contenteditable` 使用户可编辑

### `hidden`隐藏

### `id` 不到万不得已不要用id，因为重复id不会报错。`#id`

id可以在js中直接被调用

凡是window.的保留字串不可以拿来做id name,可以在开发者模式console打window.来查看

### `style`每个元素里可以写一个style

style（在html）优先级高于css，如果两个地方都写了style的话

如果js里也写了，js会覆盖所有的style

### `tabindex`可以用键盘控制

正值表示顺序访问

tabindex=0 代表最后一个访问

tabindex=-1代表不要到这个位置

### `title`可以显示完整内容

鼠标悬浮，会显示title的内容

#### title太长不想换行：

```css
white-space:nowrap//不要换行

Text-overflow:ellipsis//溢出就省略

Overflow:hidden//省略用...
```



# 常用的内容标签有哪些，分别是什么意思

`ol`+`li`: 有序列表

`ul`+`li`：无序列表

`dl`+`dt`+`dd`

dl:discription list

dt:discription term

dd:description data

`pre`:

一般打多个空格只显示一个空格，如果想保留就用`pre`

`hr`

水平分割线

`br`

换行

`a`

用来创建链接

国内：会加target="_blank"

国外：不加，让用户自己选择怎么打开页面

`em`语气强调

`strong`本质强调

`code`

写代码的，字体全部是等宽，默认是内连元素，可以使用`pre`包裹

`quote`内联引用

`blockquote`块级引用
