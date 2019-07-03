---
layout: post
title: "【姿态估计api】文档中心"
subtitle: " \"Hello World!\""
date: 2019-07-03 11:58:24
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: 
tags: api
---

# 目录

- **[文档中心](#0)**
- **[](#1)**
- **[](#2)**
- **[](#3)**
- **[](#4)**

# <span id='0'><font color='red'>文档中心</font></span>
## <font color='red'>版本</font>
0.1

## <font color='red'>描述</font>
姿态估计api基础功能：
1. 传入基础信息、儿童运动视频，系统自动根据已训练模型识别视频中人物身体18关键点，并建立关键点-骨骼模型。
2. 系统返回每帧关键点坐标，可以计算关键点位置，角度等数值，从而进行姿态估计。
3. 根据已有标准，对比计算数值，从而进行儿童运动异常检测。如立定跳远中，儿童起跳膝盖弯曲角度，双臂上摆角度，跳远距离等。

综合功能：
1. 运动异常检测评估，结合儿童其他身体指标信息，可以对儿童进行运动综合评价，最终给出合理建议。

18特征点模型示意：  

![](https://note.youdao.com/yws/api/personal/file/C0B0BA9D3ABF4C56992A53A12378D539?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5)


## <font color='red'>数据要求</font>


## <font color='red'>调用URL</font>
https://api.th-ehealth.com:32904/ztgj/v1/

## <font color='red'>调用方法</font>
POST

## <font color='red'>权限</font>
暂无设置

## <font color='red'>请求参数</font>


## <font color='red'>返回值说明</font>


## <font color='red'>成功请求返回值示例</font>


## <font color='red'>失败请求返回值示例</font>


## <font color='red'>通用的ERROR_MESSAGE</font>




## <font color='red'>调用示例</font>

