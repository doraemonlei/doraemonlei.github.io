---
layout: post
title: "【矮小症辅助诊断api】文档中心"
subtitle: " \"Hello World!\""
date: 2019-04-28 09:51:12
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
1.0

## <font color='red'>描述</font>
矮小症专科基础功能：
1. 传入基础信息、检查指标数据，系统自动识别处理，获得对矮小症分支疾病疑似判断排序结果。
2. 根据59个特征判断70种矮小症分支疑似疾病，获得top10排序结果

自助诊断功能
1. 首先要求诊断者自助输入基础信息
    - `姓名`
    - `性别`
    - `出生日期`
2. 输入体征信息
    - `身高`
    - `体重`
    - `自动计算BMI`
3. 输入病史信息
    - `高血压病史`（有、没有、不清楚）
    - `糖尿病病史`（有、没有、不清楚）
    - `其他`
4. 上传个人病历（可选）
5. 患者主诉，选择症状，并简单解释症状名词意义，相近表达等
    - `矮小症`
    - `慢阻肺`和`支气管哮喘`
        - `呼吸困难`：喘息和劳作性；发作性、阵发性、呼气性
        - `其他症状`：慢性咳嗽、咳痰；干咳、胸闷
        - `体征`：干湿啰音并存；哮鸣音为主
        - `病史`：长期吸烟、有害气体接触等；过敏原接触、部分有家族病史
        - `影像学表现（是否做过）`：肺纹理增多、粗乱、肺气肿征；无特殊
        - `支气管扩张剂`：有一定缓解；可迅速缓解
        - `其他`
6. 患者主诉，产生症状持续时间，常发作时间段等，也可在选择症状时同时选择
7. 询问家族病史情况
7. 询问患者药物过敏情况
8. 给出用药建议

## <font color='red'>要求</font>
- 身高	
- 体重	
- 上部量	
- 下部量	
- 指距	
- 一般性肥胖（区别于向心性肥胖）	
- 前额突出	
- 声调高	
- 皮肤干燥	
- 头发粗糙	
- 面容不成熟	
- 心率缓慢	
- 向心性肥胖	
- 紫纹	
- 痤疮	
- 高血压	
- 颈蹼	
- 黑痣	
- 盾形胸	
- 肘外翻	
- 青春发育延迟	
- 原发性闭经	
- 脸圆	
- 掌骨短小	
- 智力减退	
- 头大	
- 四肢短小	
- 出生时个头小	
- 出生时头尖	
- 出生时身体不对称	
- 坐高	
- 卧位身长	
- 顶臀长	
- 头围	
- 胸围	
- 血GH兴奋值	
- 睡眠试验血GH值	
- 运动试验血GH值	
- 血IGF-1水平测定	
- 血IGF-BP-3水平测定	
- 胰岛素低血糖生长激素刺激试验	
- 生长激素精氨基酸刺激试验	
- 生长激素左旋多巴刺激试验	
- 可乐定生长激素激发试验	
- 第13号常染色体异常	
- 第18号常染色体异常	
- 第21号常染色体异常	
- X染色体异常	
- POUIFI基因	
- PROP-1基因	
- GHRH基因	
- GHRH受体基因	
- GH_N基因	
- GH受体基因	
- IGF-1基因	
- IGF-1受体基因	
- SHOX基因	
- 骨龄	
- 鞍区MRI

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

# <span id='4'><font color='red'>2019.03.04</font></span>
- 版本
    - v1.0.3

- 功能
    - 特纳综合征识别
    - 预处理图像

- 新增

- 修复

- 优化
    - 优化人脸url
        - https://api.th-ehealth.com:32904/face/v1/
- 删除

- 即将删除

- 问题
    - 响应慢
        - 1 原图2M左右，处理较慢
        - 2 dlib人脸识别本身较慢
        - 3 程序逻辑问题