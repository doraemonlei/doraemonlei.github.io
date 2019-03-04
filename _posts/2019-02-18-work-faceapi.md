---
layout: post
title: "【人脸诊断api】文档中心"
subtitle: " \"Hello World!\""
date: 2019-02-18 10:42:32
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: 
tags: api
---

# 目录

- **[文档中心](#0)**
- **[2019.02.14-v1.0.0](#1)**
- **[2019.02.18-v1.0.1](#2)**
- **[2019.02.26-v1.0.2](#3)**

# <span id='0'><font color='red'>文档中心</font></span>
## <font color='red'>版本</font>
1.0

## <font color='red'>描述</font>
- 传入人脸图片、几个基础数据（身高，身高百分位），系统自动识别处理，最终获得对特纳综合征疑似程度判断结果。
- 一次调用支持一张人脸的分析。如果图片中有多张人脸，只对人脸框面积最大的一个人脸进行分析。 （相同面积，随机选一张人脸）。
- 选用正脸高清大图判断效果最佳。

## <font color='red'>图片要求</font>
- 图片格式：JPG(JPEG)，PNG
- 图片像素尺寸：最小 100\*100 像素，最大 4096\*4096 像素
- 图片文件大小：2 MB
- 最小人脸像素尺寸： 系统能够检测到的人脸框为一个正方形，正方形边长的最小值为图像短边长度的 24 分之一，最小值不低于 100 像素。 例如图片为 4096\*3200 像素，则最小人脸像素尺寸为 132\*132 像素。

## <font color='red'>调用URL</font>
https://api.th-ehealth.com:32904/face/v1/

## <font color='red'>调用方法</font>
POST

## <font color='red'>权限</font>
暂无设置

## <font color='red'>请求参数</font>

|是否必选|参数名|类型|参数说明|
|---|---|---|---|
|必选|img|File|图片的二进制文件，需要用 post multipart/form-data 的方式上传。|
|必选|height|String|身高|
|必选|hp|String|身高百分位（'hp_\<3%', 'hp_3%~10%', 'hp_10%~25%', 'hp_25%~50%', 'hp_50%~75%','hp_75%~90%','hp_90%~97%'',hp_>97%'） |

## <font color='red'>返回值说明</font>

|字段|类型|说明|
|---|---|---|
|time_used|float|预测所用时间|
|features|list|提取的特征|
|predict_proba|list|预测结果概率[un-TS,TS]|
|processed_img|string|预处理后的人脸图片|

## <font color='red'>faces 数组中单个元素的结构</font>
待添加

## <font color='red'>landmark 中包含的元素说明</font>
待添加

## <font color='red'>成功请求返回值示例</font>
```JSON
{
    "time_used": 2.6634907722473145,
    "features": [
        0.23,
        0.17,
        0.442,
        0,
        2,
        1,
        0,
        0,
        0,
        0,
        0,
        0,
        0
    ],
    "predict_proba": [
        0.6960068941116333,
        0.3039931058883667
    ],
    "processed_img": "http://api.th-ehealth.com:32921/static/pro/1551165069_22.jpg"
}
```

## <font color='red'>失败请求返回值示例</font>
```JSON
{
    "msg": "IMAGE_ERROR_UNSUPPORTED",
    "data": "没有检测到人脸，请重新上传图像。",
    "status": 400
}
```

## <font color='red'>通用的ERROR_MESSAGE</font>

|HTTP 状态代码|错误信息|说明|
|---|---|---|
|400|IMAGE_ERROR_UNSUPPORTED|图像未检测到人脸，请重新上传。|


## <font color='red'>调用示例</font>
```SHELL
curl -X POST "https://api.th-ehealth.com:32904/face/v1/" 

-F "height=<height>" \
-F "hp=<hp>" \
-F "image_file=@image_file.jpg" \

```

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

# <span id='3'><font color='red'>2019.02.26</font></span>
- 版本
    - v1.0.2

- 功能
    - 特纳综合征识别
    - 预处理图像

- 新增

- 修复

- 优化
    - 未检测到人脸时返回错误信息

- 删除

- 即将删除

- 问题
    - 响应慢
        - 1 原图2M左右，处理较慢
        - 2 dlib人脸识别本身较慢
        - 3 程序逻辑问题