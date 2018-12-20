---
layout: post
title: "【工作】开发建议"
subtitle: "\"Hello World\""
date: 2018-10-11 15:56:36
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: test
tags: 工作 开发建议
---

# 💻医学相机web端

## <font color='red'>界面</font>
### 排序
- 默认是根据ID进行排序  
- 可以通过点击其他字段进行相应排序

## <font color='red'>易用性</font>
### 图像命名
患者ID_出生日期_检查日期_序号（正面1，图像中脸朝左2，图像中脸朝右3，病例等数据4，5，6……）

### 导出目录
根据图像序号，只导出某种图像（正面，侧面）

## <font color='red'>其他</font>
- 查询日期最早在哪一天
- 不知道有没有超级用户（可以同时查询所有数据）
- - [x] 按年龄查，只要有一个输入是10（或以上）的时候没反应

## 更新记录
### 2018.11.23
修复按诊断查询

### 2018.12.11
增加多条件查询

### 2018.12.17
增加反选查询

### 2018.12.18
小孩如果名字一样的话。1）他们在app上输入名字之后就会把id，性别，出生日期，民族这四个字段直接关联到之前一样名字的那个人上。2）现在如果在系统里改id的话会将同名的人的信息一起改了。

# 📱医学相机app
## <font color='red'>界面</font>

## <font color='red'>易用性</font>
### ID

### 诊断
- 是否可以加上儿童医院几种主要疾病类型
    - 腺大
    - 扁大
    - 腺扁大
    - 鼾症
    - 过敏性鼻炎
    - ……

## <font color='red'>其他</font>
- 增加初步识别人脸框功能