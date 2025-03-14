---
title:      "The Not So Short Introduction to Typst(updating)"
date:       2025-01-18
categories: [Computer Science,Typst]
tag: [Typst]
math: true
pin: false
#media_subpath : /assets/img/in-post/2025/2025-01-18-weicheng/
description: A Quick Start Guide to Typst, including its advantages, environment setup, and syntax.
image: 
    path: /assets/img/in-post/2025/typst/cover.png
---


**Typst**大概诞生于2023年4月,定位为传统的排版工具$\LaTeX$的替代品,是一种类似于Markdown的标记型语言,通过输入带有标记的文本文件,将其输出为PDF格式文件,尤其适合排版带有大量数学公式的数学和物理论文或者书籍.
## 为什么选择Typst?
Typst相对于传统的排版工具$\LaTeX$具有如下优点:

- **语法比$\LaTeX$简洁很多,很快就能上手**.不像$\LaTeX$大量使用反斜杠"\\"与花括号"\{\}",Typst的语法更为自然简洁.比如同样是输入行内分数$\frac{2}{3}$,$\LaTeX$语法为`$\frac{2}{3}$`或者`$\dfrac{2}{3}$`,而Typst的语法就是自然的`$2/3$`.对于行间公式,$\LaTeX$经常要用一对双美元符\$\$,然而Typst只需要在一对单美元符\$之间增加两个空格即可.例如对于场方程

$$ G_{\mu\nu}=R_{\mu\nu}-\dfrac{1}{2}g_{\mu\nu}R=\dfrac{8\pi G}{c^4}T_{\mu\nu} $$ 

$\LaTeX$的语法为
```latex
$$ G_{\mu\nu}=R_{\mu\nu}-\dfrac{1}{2}g_{\mu\nu}R=\dfrac{8\pi G}{c^4}T_{\mu\nu} $$ 
```
而Typst的语法为
```typst
$ G_(mu nu)=R_(mu nu)-1/2 g_(mu nu) R=(8 pi G)/(c^4)T_(mu nu) $
```
- **Typst渲染速度与Markdown相当,因此可以实时预览**,这正是$\LaTeX$的一大痛点.$\LaTeX$的编译速度受文档和图表大小影响,编译速度很慢,即使是开启自动编译也几乎无法像Markdown一样实时预览,而Typst采用一种增量编译算法和一种有约束的版面缓存方案,文档长度基本不会影响编译速度.
- **Typst环境搭建比较简单**.可以使用官方的Web App(类似于$\LaTeX$的Overleaf)在线编辑,或者使用VS Code安装Tinymist Typst插件本地开发,而不必像$\LaTeX$一样在本地安装好几个G的Texlive.
-  **Typst是现代的编程语言**.Typst拥有变量、函数、包管理与错误检查等现代编程语言的特性,同时也提供了闭包等特性,便于进行函数式编程,包括了`[标记模式]`、`{脚本模式}`与`$数学模式$`等多种模式的作用域,并且它们可以不限深度地、交互地嵌套,并且通过包管理.



尽管相较于$\LaTeX$有这么多的优势,Typst自身因为太新,目前仍然存在一些[BUG](https://github.com/typst/typst/issues).此外,目前对于Typst的支持并不如$\LaTeX$一样丰富(毕竟$\LaTeX$诞生于1984年,距今已经过41年的发展),具体表现在以下两方面:

- 暂时没有OCR软件支持将数学公式识别为Typst代码.使用Typst写文档,涉及的数学公式必须自行输入.
- 目前使用的ChatGPT的训练数据截止2023年10月,而Typst自诞生之日起发展日新月异,这意味着对于Typst的语法问题,即使是ChatGPT也无法给出准确的回答.

## 配置Typst运行环境

### [使用官方的webapp](https://typst.app/)
类似于$\LaTeX$的Overleaf,Typst官方提供了在线且免费的多人协作编辑器.该编辑器会从远程下载WASM编译器,并在浏览器内运行编辑器,提供预览服务.可以注册一个账户并开箱即用该编辑器.
![官方的webapp](/assets/img/in-post/2025/typst/1.png)

### 使用VS Code编辑
打开VS Code扩展界面,搜索并安装Tinymist Typst插件.它会提供语法高亮,代码补全,代码格式化,即时预览等功能.
![官方的webapp](/assets/img/in-post/2025/typst/2.png)
![官方的webapp](/assets/img/in-post/2025/typst/3.png)

## $\LaTeX$用户快速入门
### 创建文档、章节标题与斜体、粗体以及列表
如同$\LaTeX$创建`.tex`文件一样,Typst只需要创建一个`.typ`文件即可.默认使用A4纸张,而段落同样只需要空行.

Typst使用`= 一级标题`、`== 二级标题`来输出标题,标题的深度取决于`=`的数量,这一点类似于Markdown的`# 一级标题`.此外,Typst使用`_ 斜体_`来表示斜体,使用`* 粗体 *`来表示粗体.

对于无序列表,只需要在项目前面加上连字符`-`,如

```Typst
- First
- Second
- Third
```
有序列表在项目前面加上`+`,即
```Typst
+ First
+ Second
+ Third
```

### 标记模式与代码模式
### 模板与导入包
### 数学公式输入
## 语法介绍









## 参考
1. [Typst 小蓝书](https://typst-doc-cn.github.io/tutorial/)
2. [Typst 中文社区导航FAQ](https://typst-doc-cn.github.io/guide)
3. [Typst 非官方中文文档网站](https://typst-doc-cn.github.io/docs/)
4. [Typst Examples Book](https://sitandr.github.io/typst-examples-book/book/)
5. Casea,一份(不太)简短的Typst介绍,2023.6.30