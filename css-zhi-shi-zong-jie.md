# CSS 知识总结

# 浏览器渲染原理

# 浏览器渲染过程

1. 根据HTML构建HTML树（DOM）
2. 根据CSS构建CSS树（CSSOM）
3. 将两棵树合并成一颗渲染树（render tree）
4. Layout布局（文档流，盒模型，计算大小和位置）
5. Paint绘制（把边框颜色，文字颜色，阴影等画出来）
6. Compose合成（根据层叠关系展示画面）

# 如何更新样式

## 一般我们用JS来更新样式

```javascript
div.style.background = 'red'
div.style.display = 'none'
div.classList.add('red')//class的效率更高
div.remove()//直接删除节点
```

那么这些方法有什么不同吗？

## 有三种不同的渲染方式

![Screen Shot 2022-01-02 at 1.24.53 PM](Screen%20Shot%202022-01-02%20at%201.24.53%20PM.png)

## 第一种：全走

`dir.remove()`会触发当前消失，其他元素relayout

例子：http://js.jirengu.com/jagel/1/edit?html,css,js,output

## 第二种，跳过layout

改变背景颜色，直接repaint+composite

例子：http://js.jirengu.com/jidam/1/edit?html,css,js,output

## 第三种，跳过layout和paint

改变transform，只需composite，注意必须全屏查看效果，在iframe里看有问题

例子：http://js.jirengu.com/wusew/1



⚠️如果想知道CSS触发浏览器的哪个流程，直接看https://csstriggers.com/，这个网站已经把所有属性全试过了。

# CSS 动画的两种做法

# transition过渡

## 作用

补充中间帧

## 语法

```css
transition:属性名 时长 过渡方式 延迟
transition:left 200ms linear
可以用逗号分隔两个不同属性
transition:left 200ms, top 400ms
可以用all代表所有属性
transition:all 200ms
过渡方式有：linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier | step-start | step-end | steps 具体含义要靠数学知识
```

opacity从1到0，尽管元素消失，但是还是占着位置的。

⚠️并不是所有属性都能过渡

- display:none => block 没法过渡
- 一般改成visibility:hidden => visible
- display和visibility的区别自己搜一下
- background颜色可以过渡吗
- opacity透明度可以过渡吗

**过渡必须要有起始**，一般只有一次动画，或者两次，比如hover和非hover状态的过渡

# 如果除了起始，还有中间点，怎么办？

## 两种办法

### 使用两次transform

.a === transform ===> .b

.b === transform ===> .c

如何知道到了中间点呢？

用setTimeout或者监听transitionend事件

http://js.jirengu.com/buwah/1/edit?html,css,js,output

### 使用animation

声明关键帧

添加动画

http://js.jirengu.com/peran/1/edit?html,css,output

# 提问：如何让动画停在最后一帧

搜索css animation stop at end

网友给出的答案是加个forwards

```css
animation: 1.5s ease 1s 10  reverse forwards xxx;
```

http://js.jirengu.com/lodoy/1/edit?html,css,output

# @keyframes完整语法

## 标准写法

搜索[keyframes MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)讲的很清楚

一种写法是from to

另一种写法是百分数

```css
@keyframs slidein{
 from{
 transform:translateX(0%);
 }
 to{
 transform:translateX(100%);
 }
}

```

```css
@keyframes identifier{
0% {top: 0; left: 0;}
30% {top: 50px;}
68%, 72% {left:50px;}
100% {top:100px; left:100%;}
}

//百分比代表关键帧
```

# animation

## 缩写语法

```css
animation:时长 ｜ 过渡方式 ｜延迟 ｜次数 ｜ 方向 ｜ 填充模式 ｜ 是否暂停 ｜ 动画名；
```

- 时长：1s或者1000ms
- 过渡方式：跟transition取值一样，如linear
- 次数：3或者2.4或者infinite
- 方向：reverse | alternate | alternate-reverse
- 填充模式：none | forwards | backwards | both
- 是否暂停：paused | running
- 以上所有属性都有对应的单独属性

其他更多CSS内容：[https://notes.newb.codes/css-quan-jie](https://notes.newb.codes/css-quan-jie)
