---
layout: post
title: "“半路出家”的Kaggle Grandmaster：如何正确打开数据科学竞赛？"
subtitle: " \"Hello World！\""
date: 2018-11-12 15:04:12
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: test
tags: ML DL kaggle
---

> 整理自大数据文摘专栏[“半路出家”的Kaggle Grandmaster：如何正确打开数据科学竞赛？](https://baijiahao.baidu.com/s?id=1616901585364846715&wfr=spider&for=pc)

# 1 时间安排

## 1 给需要做的事情排序
- 《优秀到不能被忽视：擅长比喜爱更重要》（So Good They Can’t Ignore You: Why Skills Trump Passion in the Quest for Work You Love ）
- 《深度工作：如何有效使用没一点脑力》（ Deep Work: Rules for Focused Success in a Distracted World）

## 2 具体安排
- 健身：6点起床健身
- 上班路上：提高软技巧和商务领域的书
- 活动：适当参加活动，放松身心
- 保持机器学习领域的熟悉度：阅读科技文献，为竞赛，副业或其他开源项目编程。
- 早上列出我这天想完成的事情:尽量全部完成,使用Trello协助我完成规划和管理
- 避免让时间过于碎片化

> 由 Alexander Buslaev、 Alex Parinov、Eugene Khvedchenia和我联合创办的图像增广技术资料库

# 2 技巧
## 开发系统
- Ubuntu + i3 系统
- 4个GPU的电脑做高负荷训练
- 2个GPU的电脑做模型设计

## 开发IDE
jupyter
- EDA
- 可视化任务

PyCharm+flake8

> Flake8 是由Python官方发布的一款辅助检测Python代码是否规范的工具，相对于目前热度比较高的Pylint来说，Flake8检查规则灵活，支持集成额外插件，扩展性强。Flake8是对下面三个工具的封装：
1）PyFlakes：静态检查Python代码逻辑错误的工具。
2）Pep8： 静态检查PEP8编码风格的工具。
3）NedBatchelder’s McCabe script：静态分析Python代码复杂度的工具。
不光对以上三个工具的封装，Flake8还提供了扩展的开发接口。

## 创建代码库
- 机器学习问题相似
- 新的问题只需重构旧代码

## 版本管理
- [https://github.com/iterative/dvc](https://github.com/iterative/dvc)
- 优化ML pipelines的输出结果

## 框架
Pytorch框架
- Pytorch中的DataLoader模块更加强大

## 计算机视觉库
albumentations
- 它可以100%的利用CPU进行计算，但是没有办法充分利用GPU。

libjpeg-turbo、PyVips  
- 加快从硬盘读取jpeg图像的速度

## 队友选择
- 排行榜筛选
- 专业知识

# 3 对kaggle参赛者建议
1. 去论坛复制借鉴一下别人的核心代码
2. 调整一些参数，重新训练你的模型，提交你的预测结果
3. 发展出这一种直觉，你需要能够感觉出什么方案可行或者什么方案不可行
    - 在这一阶段，你就需要将学习作为实验的一部分
    - 首先就是在mlcourse.ai, CS231n网站上或者专业书中学习数学、统计学、如何编写代码等基础知识
    - 其次，你会在论坛上看到很多与你试图解决的问题相关的新术语，你需要记住这些术语，这些都是你需要学习的新事物
    - 你不能只学习或者实验，你需要两个同时进行
4. 浏览论坛，看一看那些获胜者分享的解决方案，尝试着去找到更好的解决办法。当下一次你遇到了相似问题的时候，你会比现在好得多。
5. 在不同的竞赛中一遍又一遍的尝试，你就可以到达顶峰。更重要的是，对于各种问题你都会有好的解决方法。同时，如果你在比赛、工作或者科研中遇到了一些机器学习的难题，你会拥有更好的直觉知道下一步该怎么解决。

# 4 总结
1. 写下你自己的策略，或者重构别人在论坛上分享的策略
2. 这一策略需要以合适的方式囊括从输入数据到提交结果的所有过程，并定义一些交叉验证的标准。
3. 通过结合你所定义的标准和排行榜上的排名，你可以看到自已的进步。
4. 你进行尝试性的数据分析，仔细阅读论坛内容，阅读文章、书籍以及从前相似竞赛的解决方法。此时你完全独立进行工作。
5. 在某一时间点，通常在截止日期2-4周前，你会被卡住。你尝试了一切可能的方法，但都无法对结果有所改进。此时你需要你一些新的想法。
6. 这时你可以看看排行榜上排名和你相近的用户或者和与你有类似想法的活跃用户进行交流。
7. 首先，你的预测结果的平均值，会给你一个很小的但及其重要的起点。其次，通常而言你的方法会与别人的有所不同。只是通过列出你尝试过或没有尝试的方法，都会对你的学习有所帮助。第三，因为你们都认真参与了比赛，每个人都单独对数据进行了观察，对策略进行了梳理，并且都把这次比赛放在了较高的优先级上，这时你能找到的队友多半是靠谱的。
