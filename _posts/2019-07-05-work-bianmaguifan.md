---
layout: post
title: "【开发】机器学习项目编码规范"
subtitle: " \"Hello World!\""
date: 2019-07-05 13:41:27
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: 
tags: 机器学习 编码规范
---

# 目录

- **[项目目录规范](#0)**
- **[项目编码规范](#1)**

# <span id='0'><font color='red'>项目目录规范</font></span>
## <font color='red'>机器学习项目目录</font>
- mlproject
    - dataset：包括数据，模型等文件
    - doc：文档
    - src：源码
        - ipynb：ipynb文件
        - xxx：项目组件1
        - xxx：项目组件2
        - xxx：项目组件n
    - tools：工具目录，包括已有的一些工具代码等
    - tests:单元测试
    - exampes：demo
    - scripts:服务器运行脚本
    - README.md
    - .gitignore
    - requirements.txt
    - LICENSE

> 参考，根据实际情况进行优化更改
## <font color='red'>api接口项目目录</font>
- apiproject
    - static：包括数据，模型等文件
        - data
        - models
    - doc：文档
    - src：源码
        - ipynb：ipynb文件
        - xxx：项目组件1
        - xxx：项目组件2
        - xxx：项目组件n
    - tools：工具目录，包括已有的一些工具代码等
    - tests:单元测试
    - exampes：demo
    - scripts:服务器运行脚本
    - logs:日志文件
    - settings：配置文件
        - settings.py
        - config.py
    - README.md
    - .gitignore
    - requirements.txt
    - app.py 入口
    - LICENSE

> 参考，根据实际情况进行优化更改
# <span id='1'><font color='red'>项目编码规范</font></span>
> 针对以Python语言为主开发的项目

## <font color='red'>1 重要原则</font>
保持风格的一致性

## <font color='red'>2 最简规范</font>
- 只使用空格缩进，4个空格表示1个缩进层次

- 使用UTF-8编码
- 每行只写一条语句
- 使用行末反斜杠折叠长行，限制每行最大79字符
- 导入包：每行唯一、从大到小、绝对路径
- 类内方法空1行分隔，类外空2行分隔
- 运算符除 * 外，两边空1格分隔，函数参数=周围不用空格
- 除类名使用驼峰法以外，其他模块、函数、方法、变量均使用全小写+下划线
- 1个前导下划线表示半公开，2个前导下划线表示私有，与保留字区分使用单个后置下划线
- 开发时使用中文注释

## <font color='red'>3 命名规范</font>
- 一行只import一个包，imports的顺序为：标准库、相关主包、特定应用，每组导入之间放置1行空行，所有导入使用包的绝对路径。

- 分割顶层函数和类的定义使用2行空行，分割类内方法定义使用1行空行，class行与第一个方法定义之间要有1行空行。

- 整体使用英文书写方式来使用空格，即仅在逗号、分号后面添加1个空格，其他任何符号如圆括号、方括号、花括号等都不用空格把符号与字符分开，写在一起表示一个整体;运算符除 * 号以外，其他符号两边都各用1个空格分隔;函数参数=号周围不用空格。

- 模块名：不含下划线、简短、全小写;

- 类名、异常名：首字母大写单词串的驼峰法;

- 函数名、全局变量名、方法名、实例变量：全小写，加下划线增加可读性;

- 一个前导下划线仅用于不想被导入的全局变量(还有内部函数和类)前加一个下划线)、不打算作为类的公共接口的内部方法和实例变量;

- 两个前导下划线以表示类私有的名字，只用来避免与类(为可以子类化所设计)中的属性发生名字冲突。

- 私有属性必须有两个前导下划线，无后置下划线;

- 非公有属性必须有一个前导下划线，无后置下划线。

- 公共属性没有前导和后置下划线，除非它们与保留字冲突，此情况下，单个后置下划线比前置或混乱的拼写要好，例如:class_优于klass。

## <font color='red'>4 文档和注释</font>
- 开发时，注释全部用中文来写，当要发布脚本工具时，再写英文文档。

- 注释应该是是完整的句子(短语也可)，首字母大写;如果注释很短，省略末尾句号;注释块由一个or多个完整句子构成的段落组成，则每个句子使用句子结尾;句末句号后使用两个空格。

- 注释块每行以#和一个空格开始，并且跟随注释的代码具有相同的缩进层次，注释块上下方有一空行包围。

- 谨慎使用行内注释，至少使用两个空格与语句分开。

- 使用 pydoc; epydoc; Doxgen 等文档化工具，为所有公共模块、函数、类和方法边写文档字符串，文档字符串对非公开的方法不是必要的，但你应该有一个描述这个方法做什么的注释，这个注释应该在"def"这行后。

- 多行文档字符串结尾的""" 应该单独成行。

- 版本注记：定义一个变量__version__ = "$Revision: 1.4 $"

## <font color='red'>5 程序设计</font>
- 与None之类的单值比较，永远用:'is'或'is not'来做：if x is not None

- 在模块和包内定义基异常类(base exception class)

- 使用字符串方法(methods)代替字符串模块。

- 在检查前缀或后缀时避免对字符串进行切片，用startswith()和endswith()代替，如：No: if foo[:3] == 'bar':Yes: if foo.startswith('bar'):

- 只用isinstance()进行对象类型的比较，如：No: if type(obj) is type(1):Yes: if isinstance(obj, int)

- 判断True或False不要用 ==，如：No: if greeting == True:Yes: if greeting: