---
title: Markdown Usage Memo
date: 2017-10-29 23:41:32
tags:
 - Markdown
 - Hexo
categories: Websites
---

# Markdown Usage Memo

If it's the first time to make a personal blog by Hexo, we need to know what this framework and its render engine can do and cannot do. Here is the Usage Memo.
Let’s have a LOOK!

----

<!-- more -->

## 斜体和粗体

使用 * 和 ** 表示斜体和粗体。

示例：

这是 *斜体*，这是 **粗体**。

## 分级标题

使用 === 表示一级标题，使用 --- 表示二级标题。

示例：

```
这是一个一级标题
============================

这是一个二级标题
--------------------------------------------------

### 这是一个三级标题
```

你也可以选择在行首加井号表示不同级别的标题 (H1-H6)，例如：# H1, ## H2, ### H3，#### H4。

## 外链接

使用 \[描述](链接地址) 为文字增加外链接。

示例：

这是去往 [本人博客](http://ghosertblog.github.com) 的链接。

## 无序列表

使用 *，+，- 表示无序列表。

示例：

- 无序列表项 一
- 无序列表项 二
- 无序列表项 三

## 有序列表

使用数字和点表示有序列表。

示例：

1. 有序列表项 一
2. 有序列表项 二
3. 有序列表项 三

## 文字引用

使用 > 表示文字引用。

示例：

> 野火烧不尽，春风吹又生。

## 行内代码块

使用 `代码` 表示行内代码块。

示例：

让我们聊聊 `html`。

<span id="inline-red">red（#FF0000</span>
<span id="inline-yellow">yellow（#FFFF00</span>
<span id="inline-blue">蓝色</span>
<span id="inline-green">绿色</span>
<span id="inline-cyan">青色</span>
<span id="inline-orange">橙色</span>
<span id="inline-purple">紫色</span>
<span id="inline-gray">灰色</span>
<span id="inline-white">白色</span>
<span id="inline-brown">棕色</span>
<span id="inline-pink">粉红色</span>

[More custom style info](http://yangbingdong.com/2017/build-blog-hexo-advanced/#好玩的样式)

##  代码块

使用 四个缩进空格 表示代码块。

示例：

    这是一个代码块，此行左侧有四个不可见的空格。

##  插入图像

使用 \!\[描述](图片链接地址) 插入图像。

示例：

![我的头像](http://wenchao4quant.cn/images/avatar.gif)

# Markdown Advance


## 删除线

使用 ~~ 表示删除线。

~~这是一段错误的文本。~~

## Footnote

basic footnote [^1]
here is an inline footnote [^2](inline footnote)
and another one [^3]
and another one [^4]

## LaTeX 公式

$ 表示inline公式：

质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。

$$ 表示整行公式：

$$\sum_{i=1}^n a_i=0$$

$$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$

$$\sum_{k=0}^{j-1} z_k \widehat{\gamma}_k$$

$$d_{1}=\frac{\ln(S_{t}/K)  +(r+\sigma^{2}/2)(T-t)}{\sigma\sqrt{T-t}}$$

\begin{align*}
x &= a +b+c+d\\
 &= e +f\\
 &= g
\end{align*}

$$\begin{equation} \theta_j := \theta_j +
\alpha\sum\limits_{i=1}^n(y^{(i)}-h_{\theta}(x^{(i)}))x_j^{(i)}
\label{mini-BGD} \end{equation}$$

Equation$(\ref{mini-BGD})$

```
在_后加{}无法正常显示公式
_用\_转义即可
```

## Code Blocks

支持四十一种编程语言的语法高亮的显示，行号显示。

非代码示例：

```
$ sudo apt-get install vim-gnome
```

Python 示例：

```python
@requires_authorization
def somefunc(param1='', param2=0):
    '''A docstring'''
    if param1 > param2: # interesting
        print 'Greater'
    return (param2 - param1 + 1) or None

class SomeClass:
    pass

>>> message = '''interpreter
... prompt'''
```

JavaScript 示例：

``` javascript
/**
* nth element in the fibonacci series.
* @param n >= 0
* @return the nth element, >= 0.
*/
function fib(n) {
  var a = 1, b = 1;
  var tmp;
  while (--n >= 0) {
    tmp = a;
    a += b;
    b = tmp;
  }
  return a;
}

document.write(fib(10));
```


## Table

| Item        | P   |  Q  |
| --------   | -----:  | :----:  |
| Computer     | \$1600 |   5     |
| Mobile Phone |   \$12   |   12   |
| Cable        |    \$1    |  234  |


## Html 标签

本站支持在 Markdown 语法中嵌套 Html 标签，譬如，你可以用 Html 写一个纵跨两行的表格：

<table><tr>
        <th rowspan="2">值班人员</th>
        <th>星期一</th>
        <th>星期二</th>
        <th>星期三</th>
    </tr>
    <tr>
        <td>李强</td>
        <td>张明</td>
        <td>王平</td>
</tr></table>

## Fontawesome

本站的图标系统对外开放，在文档中输入

        `<i class="fa fa-fw fa-weibo icon-2x"></i>`

即显示微博的图标： <i class="fa fa-fw fa-weibo icon-2x"></i>

替换 上述 `i 标签` 内的 `icon-weibo` 以显示不同的图标，例如：

        `<i class="fa fa-fw fa-renren icon-2x"></i>`

即显示人人的图标： <i class="fa fa-fw fa-renren icon-2x"></i>

<i class="fa fa-fw fa-flag"></i>

更多的图标和玩法可以参看 [font-awesome](http://fontawesome.io/icons/) 官方网站。

## Flowchart

The flowchart below use `hexo-filter-flowchart`.

```flow
st=>start: Start|past:>http://www.google.com[blank]
e=>end: End:>http://www.google.com
op1=>operation: My Operation|past
op2=>operation: Stuff|current
sub1=>subroutine: My Subroutine|invalid
cond=>condition: Yes
or No?|approved:>http://www.google.com
c2=>condition: Good idea|rejected
io=>inputoutput: catch something...|request

st->op1(right)->cond
cond(yes, right)->c2
cond(no)->sub1(left)->op1
c2(yes)->io->e
c2(no)->op2->e
```

## Todo-list
If you want render a todo-list, you can only use `hexo-renderer-marked`. Latex won't work because Hexo itself has many special Escape Characters.

<ul>
<li><i class="fa fa-check-square"></i> Complete</li>
<li><i class="fa fa-square"></i> Incomplete</li>
</ul>

使用带有 [ ] 或 [x] （未完成或已完成）项的列表语法撰写一个待办事宜列表，并且支持子列表嵌套以及混用Markdown语法，例如：

    - [ ] **Cmd Markdown 开发**
        - [ ] 改进 Cmd 渲染算法，使用局部渲染技术提高渲染效率
        - [ ] 支持以 PDF 格式导出文稿
        - [x] 新增Todo列表功能 [语法参考](https://github.com/blog/1375-task-lists-in-gfm-issues-pulls-comments)
        - [x] 改进 LaTex 功能
            - [x] 修复 LaTex 公式渲染问题
            - [x] 新增 LaTex 公式编号功能 [语法参考](http://docs.mathjax.org/en/latest/tex.html#tex-eq-numbers)
    - [ ] **七月旅行准备**
        - [ ] 准备邮轮上需要携带的物品
        - [ ] 浏览日本免税店的物品
        - [x] 购买蓝宝石公主号七月一日的船票


## Bootstrap Callout
{% note default %} Content (md default supported) {% endnote %}
{% note primary %} Content (md primary supported) {% endnote %}
{% note success %} Content (md success supported) {% endnote %}
{% note info %} Content (md info supported) {% endnote %}
{% note warning %} Content (md warning supported) {% endnote %}
{% note danger %} Content (md danger supported) {% endnote %}

## Tab tag
{% tabs 选项卡, 2 %}
<!-- tab -->
**Tab tag 1** blablabla
<!-- endtab -->
<!-- tab -->
**Tab tag 2**
<!-- endtab -->
<!-- tab -->
**Tab tag 3** φ(≧ω≦*)♪～
<!-- endtab -->
{% endtabs %}

{% tabs Sixth unique name %}
<!-- tab Solution 1@text-width -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab Solution 2@amazon -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab Solution 3@bold -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}


[More info](https://almostover.ru/2016-01/hexo-theme-next-test/#Label-tag-test)

## Button with icon
```
Usage: {% button /path/to/url/, text, icon [class], title %}
Alias: {% btn /path/to/url/, text, icon [class], title %}
```

<p>{% btn #,, home fa-3x %}</p>

<p>{% btn #, Text & Large Icon, home fa-fw fa-lg %}</p>

<div class="text-center">{% btn #, Almost, adn fa-fw fa-lg %} {% btn #, Over, terminal fa-fw fa-lg %}</div>


<div class="text-center"><span>{% btn #,, header %}{% btn #,, edge %}{% btn #,, times %}{% btn #,, circle-o %}</span>
<span>{% btn #,, italic %}{% btn #,, scribd %}</span>
<span>{% btn #,, google %}{% btn #,, chrome %}{% btn #,, opera %}{% btn #,, diamond fa-rotate-270 %}</span>
</div>

[More info](https://almostover.ru/2016-01/hexo-theme-next-test/#Label-tag-test)

[^1]: basic footnote content
[^3]: paragraph footnote content
[^4]: footnote content with some [markdown](https://en.wikipedia.org/wiki/Markdown) content