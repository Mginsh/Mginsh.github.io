---
title: Markdown语法简介
date: 2017-04-30 12:22:46
photo: /img/md.png
tags: 工具
excerpts: '记录点基础用法。'
---

开始正文
>  标题 

Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。

类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），任何数量的 = 和 - 都可以有效果。例如：

【效果】

这是一级标题
=============

这是二级标题
-------------

【语法】
    ```
    这是一级标题
    =============

    这是二级标题
    -------------
    ```

类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

【效果】

# 这是一级标题

## 这是二级标题

### 这是三级标题

#### 这是四级标题

##### 这是五级标题

###### 这是六级标题

【语法】
    ```
    # 这是一级标题
    ## 这是二级标题
    ### 这是三级标题
    #### 这是四级标题
    ##### 这是五级标题
    ###### 这是六级标题
    ```

>  文本

文本的显示形式可分为粗体、斜体两种，通过在文本前后输入若干个*。

【效果】

**这是粗体**
*这是斜体*
***这是斜体+粗体***

【语法】
    ```
    **这是粗体**
    *这是斜体*
    ***这是斜体+粗体***
    ```

>  图片

在hexo/source目录下新建一个img文件夹，将图片放入该文件夹下，插入图片时链接即为/img/图片名称，或者使用微博图床。

【效果】

![测试图片](/img/markdown.jpg)

【语法】
    ```
    ![图片内容](图片链接)
    ```

>  链接

链接的语法与图片类似，只要在图片的基础上去掉!即可。

【效果】

[这是我的github主页](https://github.com/Tvinsh)

【语法】
    ```
    [这是我的github主页](https://github.com/Tvinsh)
    ```


>  列表

列表可分为有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：

【效果】

* **星号**实现的列表

- **减号**实现的列表

+ **加号**实现的列表

【语法】
    ```
    * **星号**实现的列表

    - **减号**实现的列表

    + **加号**实现的列表
    ```

有序列表则使用数字接着一个英文句点：

【效果】

1. 这是有序列表

2. 注意是英文符号

3. 注意符号和文字之间保留一个空格

【语法】
    ```
    1. 这是有序列表

    2. 注意是英文符号

    3. 注意符号和文字之间保留一个空格
    ```

很重要的一点是，你在列表标记上使用的数字并不会影响输出的 HTML 结果，上面的列表所产生的 HTML 标记为：
    ```
    122. 这是有序列表

    233. 注意是英文符号

    3. 注意符号和文字之间保留一个空格
    ```
你都会得到完全相同的 HTML 输出。重点在于，你可以让 Markdown 文件的列表数字和输出的结果相同，或是你懒一点，你可以完全不用在意数字的正确性。

另外，如果列表项目间用空行分开，在输出 HTML 时 Markdown 就会将项目内容用 <p> 标签包起来，举例来说：
    ```
    * 注意是英文符号

    * 注意符号和文字之间保留一个空格
    ```
会被转换成：
    ```
    <ul>
    <li><p>注意是英文符号</p></li>
    <li><p>注意符号和文字之间保留一个空格</p></li>
    </ul>
    ```

>  引用

使用类似 email 中用 > 的引用方式。如果你还熟悉在 email 信件中的引言部分，你就知道怎么在 Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上 > ：

【效果】

> 是的，本文从开始时就出现的这个样式，就是引用。。。。。

【语法】
    ```
    > 是的，本文从开始时就出现的这个样式，就是引用。。。。。
    ```

>  代码区块

和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 < pre> 和 < code> 标签来把代码区块包起来。

在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以。

【效果】

    这是一个区块

行内代码块用法为在文字内容开始与结尾添加"`"。

【效果】

`这是行内代码块`

【语法】
    ```
    `这是行内代码块`
    ```

加强代码块是代码块的增强版，省去了多行代码每行输入Tab键的烦恼，只要在多行代码的开始和结尾输入｀｀｀即可。

【效果】
    ```
    这个是加强代码块
    用起来比tab键方便
    ```

【语法】
    ```
    ｀｀｀
    这个是加强代码块
    用起来比tab键方便
    ｀｀｀
    ```

> 表格

表格的语法主要用到的符号为|、-、:，效果如下：

【效果】

|默认|居中|左对齐|右对齐|
|--|:-:|:-|-:|
|*支持斜体*|**粗体**|***斜体+粗体***|**正常**|
|# 不支持标题|[支持链接](https://github.com/Tvinsh)|`支持图片`| `支持行内代码块` |

【语法】
    ```
   |默认|居中|左对齐|右对齐|
   |--|:-:|:-|-:|
   |*支持斜体*|**粗体**|***斜体+粗体***|**正常**|
   |# 不支持标题|[支持链接](https://github.com/Tvinsh)|`支持图片`|`支持行内代码块` |
    ```

> 分隔线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

【效果】

* * *

***

*****

- - -

---------------------------------------

【语法】
    ```
   * * *

    ***

    *****

    - - -

    ---------------------------------------
    ```

>  删除线

使用波浪号，效果如下：

【效果】

~~删除线~~

【语法】
    ```
    ~~删除线~~
    ```

>  反斜杠

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

【效果】

\\ 反斜线
\` 反引号
\* 星号
\_ 底线
\{} 花括号
\[] 方括号
\() 括弧
\#  井字号
\+  加号
\-  减号
\.  英文句点
\!  惊叹号

【语法】
    ```
    \\ 反斜线
    \` 反引号
    \* 星号
    \_ 底线
    \{} 花括号
    \[] 方括号
    \() 括弧
    \#  井字号
    \+  加号
    \-  减号
    \.  英文句点
    \!  惊叹号
    ```

