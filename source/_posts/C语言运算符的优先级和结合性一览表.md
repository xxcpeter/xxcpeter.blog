---
title: C语言运算符的优先级和结合性一览表
date: 2018-07-10 22:20:39
tags: 
    - C
    - C++
categories: checklists
---
C语言的运算符众多，具有不同的优先级和结合性，我将它们全部列了出来，方便大家对比和记忆

<!--more-->

基本上这个表记住了就可以应对一切奇葩运算表达式了！

<table><tbody><tr><th>优先级</th><th>运算符</th><th>名称或含义</th><th>使用形式</th><th>结合方向</th><th>说明</th></tr><tr><td rowspan="4">1</td><td>[]</td><td>数组下标</td><td>数组名[常量表达式]</td><td rowspan="4">左到右</td><td>&nbsp;</td></tr><tr><td>()</td><td>圆括号</td><td>（表达式）/函数名(形参表)</td><td>&nbsp;</td></tr><tr><td>.</td><td>成员选择（对象）</td><td>对象.成员名</td><td>&nbsp;</td></tr><tr><td>-&gt;</td><td>成员选择（指针）</td><td>对象指针-&gt;成员名</td><td>&nbsp;</td></tr><tr><td rowspan="9">2</td><td>-</td><td>负号运算符</td><td>-表达式</td><td rowspan="9">右到左</td><td>单目运算符</td></tr><tr><td>(类型)</td><td>强制类型转换</td><td>(数据类型)表达式</td><td>&nbsp;</td></tr><tr><td>++</td><td>自增运算符</td><td>++变量名/变量名++</td><td>单目运算符</td></tr><tr><td>--</td><td>自减运算符</td><td>--变量名/变量名--</td><td>单目运算符</td></tr><tr><td>\*</td><td>取值运算符</td><td>\*指针变量</td><td>单目运算符</td></tr><tr><td>&amp;</td><td>取地址运算符</td><td>&amp;变量名</td><td>单目运算符</td></tr><tr><td>!</td><td>逻辑非运算符</td><td>!表达式</td><td>单目运算符</td></tr><tr><td>~</td><td>按位取反运算符</td><td>~表达式</td><td>单目运算符</td></tr><tr><td>sizeof</td><td>长度运算符</td><td>sizeof(表达式)</td><td>&nbsp;</td></tr><tr><td rowspan="3">3</td><td>/</td><td>除</td><td>表达式/表达式</td><td rowspan="3">左到右</td><td>双目运算符</td></tr><tr><td>\*</td><td>乘</td><td>表达式\*表达式</td><td>双目运算符</td></tr><tr><td>%</td><td>余数（取模）</td><td>整型表达式/整型表达式</td><td>双目运算符</td></tr><tr><td rowspan="2">4</td><td>+</td><td>加</td><td>表达式+表达式</td><td rowspan="2">左到右</td><td>双目运算符</td></tr><tr><td>-</td><td>减</td><td>表达式-表达式</td><td>双目运算符</td></tr><tr><td rowspan="2">5</td><td>&lt;&lt;</td><td>左移</td><td>变量&lt;&lt;表达式</td><td rowspan="2">左到右</td><td>双目运算符</td></tr><tr><td>&gt;&gt;</td><td>右移</td><td>变量&gt;&gt;表达式</td><td>双目运算符</td></tr><tr><td rowspan="4">6</td><td>&gt;</td><td>大于</td><td>表达式&gt;表达式</td><td rowspan="4">左到右</td><td>双目运算符</td></tr><tr><td>&gt;=</td><td>大于等于</td><td>表达式&gt;=表达式</td><td>双目运算符</td></tr><tr><td>&lt;</td><td>小于</td><td>表达式&lt;表达式</td><td>双目运算符</td></tr><tr><td>&lt;=</td><td>小于等于</td><td>表达式&lt;=表达式</td><td>双目运算符</td></tr><tr><td rowspan="2">7</td><td>==</td><td>等于</td><td>表达式==表达式</td><td rowspan="2">左到右</td><td>双目运算符</td></tr><tr><td>!=</td><td>不等于</td><td>表达式!= 表达式</td><td>双目运算符</td></tr><tr><td>8</td><td>&amp;</td><td>按位与</td><td>表达式&amp;表达式</td><td>左到右</td><td>双目运算符</td></tr><tr><td>9</td><td>^</td><td>按位异或</td><td>表达式^表达式</td><td>左到右</td><td>双目运算符</td></tr><tr><td>10</td><td>|</td><td>按位或</td><td>表达式|表达式</td><td>左到右</td><td>双目运算符</td></tr><tr><td>11</td><td>&amp;&amp;</td><td>逻辑与</td><td>表达式&amp;&amp;表达式</td><td>左到右</td><td>双目运算符</td></tr><tr><td>12</td><td>||</td><td>逻辑或</td><td>表达式||表达式</td><td>左到右</td><td>双目运算符</td></tr><tr><td>13</td><td>?:</td><td>条件运算符</td><td>表达式1? 表达式2: 表达式3</td><td>右到左</td><td>三目运算符</td></tr><tr><td rowspan="11">14</td><td>=</td><td>赋值运算符</td><td>变量=表达式</td><td rowspan="11">右到左</td><td>&nbsp;</td></tr><tr><td>/=</td><td>除后赋值</td><td>变量/=表达式</td><td>&nbsp;</td></tr><tr><td>\*=</td><td>乘后赋值</td><td>变量\*=表达式</td><td>&nbsp;</td></tr><tr><td>%=</td><td>取模后赋值</td><td>变量%=表达式</td><td>&nbsp;</td></tr><tr><td>+=</td><td>加后赋值</td><td>变量+=表达式</td><td>&nbsp;</td></tr><tr><td>-=</td><td>减后赋值</td><td>变量-=表达式</td><td>&nbsp;</td></tr><tr><td>&lt;&lt;=</td><td>左移后赋值</td><td>变量&lt;&lt;=表达式</td><td>&nbsp;</td></tr><tr><td>&gt;&gt;=</td><td>右移后赋值</td><td>变量&gt;&gt;=表达式</td><td>&nbsp;</td></tr><tr><td>&amp;=</td><td>按位与后赋值</td><td>变量&amp;=表达式</td><td>&nbsp;</td></tr><tr><td>^=</td><td>按位异或后赋值</td><td>变量^=表达式</td><td>&nbsp;</td></tr><tr><td>|=</td><td>按位或后赋值</td><td>变量|=表达式</td><td>&nbsp;</td></tr><tr><td>15</td><td>,</td><td>逗号运算符</td><td>表达式,表达式,…</td><td>左到右</td><td>从左向右顺序运算</td></tr></tbody></table>

**注：同一优先级的运算符，运算次序由结合方向所决定。**

上面的表无需死记硬背，很多运算符的规则和数学中是相同的，用得多，看得多自然就记得了. 如果你是在记不住，可以使用`()`.

## 一些容易出错的优先级问题

上表中，优先级同为1的几种运算符如果同时出现，那怎么确定表达式的优先级呢？这是很多初学者迷糊的地方。下表就整理了这些容易出错的情况:

![table](http://p9snag9p7.bkt.clouddn.com/CSymbolOrder.jpg)

这些容易出错的情况，希望读者好好在编译器上调试调试，这样印象会深一些。一定要多调试，光靠看代码，水平是很难提上来的。调试代码才是最长水平的.
