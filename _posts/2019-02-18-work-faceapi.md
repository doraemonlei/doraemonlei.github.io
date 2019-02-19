---
layout: post
title: "【人脸诊断api】更新日志"
subtitle: " \"Hello World!\""
date: 2019-02-18 10:42:32
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: 
tags: api
---

# 目录

- **[2019.02.14-v1.0.0](#1)**
- **[2019.02.18-v1.0.1](#2)**

# <span id='1'><font color='red'>2019.02.14</font></span>
- 版本
    - v1.0.0

- 功能
    - 特纳综合征识别
    - 预处理图像

- 新增

- 修复

- 优化

- 删除

- 即将删除

- 问题
    - 响应慢
        - 1 原图2M左右，处理较慢
        - 2 dlib人脸识别本身较慢
        - 3 程序逻辑问题

# <span id='2'><font color='red'>2019.02.18</font></span>
- 版本
    - v1.0.1

- 功能
    - 特纳综合征识别
    - 预处理图像

- 新增

- 修复

- 优化
    - 图像重命名
        - 修改为：秒级时间戳_图像原文件名
    - 优化人脸url
        - http://api.th-ehealth.com:32921/face/v1/

- 删除

- 即将删除

- 问题
    - 响应慢
        - 1 原图2M左右，处理较慢
        - 2 dlib人脸识别本身较慢
        - 3 程序逻辑问题