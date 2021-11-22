# JavaScript 诞生记

JavaScript由美国程序技术专家布兰登（Brendan Eich）于1995年任职于网景公司期间开发。

JavaScript的诞生始于偶然，当时的网景公司想搭Java的顺风车，与Sun公司结盟，它允许Java程序以applet的形式直接在浏览器上运行。网景公司最初要求布兰登为浏览器添加一个脚本功能，即可以让浏览器可以与网页互动，比如，检查用户名是否天蝎。网景公司高层希望未来的网页脚本语言必须看上去和Java足够相似，但是要比Java简单，使得非专业的网页作者也能很快上手。

布莱登队Java一点兴趣都没有，为了应付公司安排的任务，布兰登仅花了10天时间就把JavaScript设计出来了。由于设计时间太短，语言的一些细节考虑得不够周全，导致后来很长一段时间，JavaScript写出来的程序混乱不堪。

JavaScript的设计思路整体是这样的：

1. 借鉴C语言的基本语法；

2. 借鉴Java语言的数据类型和内存管理；

3. 借鉴Scheme语言，将函数提升到"第一等公民"（first class）的地位；

4. 借鉴[Self语言](https://en.wikipedia.org/wiki/Self_(programming_language))，使用基于原型（prototype）的继承机制。

因此，JavaScript实际上是两种语言风格的混合产物，简化的函数式编程+简化的面向对象编程。

Brendan本人多年以后还是看不起Java，他说，Java队JavaScript的影响，主要是把数据分成基本类型（primitive）和对象类型（Object），比如字符和字符串对象，以及引入了Y2K（千年虫）问题。

作为设计者，他一点也不喜欢自己的这个作品，“与其说我爱JavaScript，不如说我恨它。它是C语言和Self语言一夜情的产物。十八世纪英国文学家约翰逊博士说过，它的优秀之处并非原创，它的原创之处并不优秀”。

网景公司为了压制微软公司的Jscript，于1996年11月，向ECMA (/ˈɛkmə/) （前身为欧洲计算机制造商协会）提交语言标准，由于版权问题，JS语言标准不叫JavaScript，叫ECMAScript。ECMAScript是JavaScript的纸质标准，而JavaScript是浏览器的实现。

JavaScript的兴起和杀手级应用Gmail有密不可分的关系。2004年愚人节，谷歌发布Gmail在线网页。当时的人们认为网页只能用来看新闻和图片。Gmail的发布让用户和开发者眼前一亮。2005年，Jesse将谷歌用到的技术命名为AJAX

从此，前端技术正式出现。

再次之前的网页开发都是由后端和设计师完成。

2006年，jQuery发布，是目前最长寿的JS库后来的十年，jQuery大发异彩，直到IE不行了，jQuery才稍微没有那么火

JavaScript的爆发和Chrome也有着千丝万缕的联系。Chrome的JS引擎叫做V8

2009年，Ryan基于V8创建了Node.js。2010年，Isaac基于Node.js写出了npm

前端工程师可以在浏览器之外执行JS了，Node.js快速风靡。同年，TJ受Sinatra启发，发布了express.js。

从此，前端工程师可以愉快的写后端应用了

这就是JS的历史，低开高走，备胎的逆袭。





