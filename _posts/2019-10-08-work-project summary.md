---
layout: post
title: "【工作】项目总结"
subtitle: " \"Hello World！\""
date: 2018-12-20 09:39:34
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: test
tags: 工作
---

# <font color = "red">目录</font>

- **[2018.09.13儿童医院京津冀项目答辩](#1)**
- **[2018.09.25朝阳区安贞社区卫生服务中心访谈记录](#2)**
- **[2018.10.30中日友好医院开会记录](#3)**
- **[2018.11.21睡眠学术交流会记录](#4)**
- **[2018.12.13儿童医院眼科](#5)**
- **[2018.12.17儿童医院OSAS汇报](#6)**
- **[2018.12.19迪谱诊断肥胖](#7)**

> 注：由于浏览器原因，不能直接展示高清原图，请使用ctrl+滚轮缩放页面比例查看或者拖动、右键保存后放大图片查看。

# <span id='1'><font color = "red">2018.09.13儿童医院京津冀项目答辩</font></span>


# <span id='2'><font color = "red">2018.09.25朝阳区安贞社区卫生服务中心访谈记录</font></span>

<div align="center">
    <img src = "https://note.youdao.com/yws/api/personal/file/BC71AFD67F7E441B85C594D0D16DF31B?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5">
</div>

# <span id='3'><font color = "red">2018.10.30中日友好医院开会记录</font></span>

## <font color='red'>慢阻肺分级诊疗系统</font>

<div align="center">
    <img src = "https://note.youdao.com/yws/api/personal/file/10C2DC12F711498ABC52A58C02DEF261?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5">
</div>

## <font color='red'>慢阻肺防、诊、治决策系统</font>

<div align="center">
    <img src = "https://note.youdao.com/yws/api/personal/file/1AF285755278455C945972D9968A86F9?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5">
</div>

# <span id='4'><font color = "red">2018.11.21睡眠学术交流会记录</font></span>

## <font color='red'>正常儿童睡眠特点及多导睡眠监测-儿童医院许志飞</font>

<div align="center">
    <img src = "https://note.youdao.com/yws/api/personal/file/C7DB3761D1DB494DBD59F9FA3E0E38CA?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5">
</div>

## <font color='red'>失眠的认知行为治疗（CBT-I）-安定医院任艳萍</font>

<div align="center">
    <img src = "https://note.youdao.com/yws/api/personal/file/8669F38B9B0749AE84FE3FC4002546C4?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5">
</div>

# <span id='5'><font color = "red">2018.12.13儿童医院眼科</font></span>
## 1 数据与需求
### <font color = "red">角膜塑形镜治疗整理汇总表</font>
**说明**    
- 已有数据
- 包括检查，复查，格式三张表。
- 检查表中数据最全，包含近视患儿初次配镜检查结果，以及后期随访检查结果。表中数据包括了5个不同角膜塑形镜厂商，其中还包括超过一次配镜的患者（佩戴十八个月后重新配镜的患者，眼镜中途损坏的患者等）。因为一般佩戴18个月后眼睛各项检查数据已接近未佩戴初次检查数据，视为独立，所以可以与初次检查患者数据混合分析。

**需求1**  
- 矫正效果分析（视力，k值，地形图）
- 初验指标差异分析
- 划分年龄层（6，7-12，13-18）分析
- 划分性别分析
- 可以找出有随访的单独分析

**需求2**  
- 相关性分析
- 相关实验会具体设计
- 主要分析1天，1周，1个月与视力，k1值，k2值，眼轴长之间的相关性。
- 同时可以将初检近视程度划分成轻，中，重度来分析

**本数据集的附加数据**  
配套的眼底图像数据
- 分析近视在眼底图像中有哪些具体体现。
- 黄斑，Gamma Zone区域，视神经盘中心与黄斑中心距离等

### <font color = "red">20W学龄儿童眼部基础检查数据</font>
**说明**   
- 未获得
- 包括年龄，性别，球镜，柱镜，视力，屈光度等数据。
- 数据中大部分为7-12岁儿童，13-18岁大约有2k例

**需求**  
- 近视预警模型
- 根据数据建立近视预警模型，可以实现对于儿童近视的预警
- 最终目的：（1）判断这样的数据是否容易近视，（2）根据数据判断是否已经是近视。

### <font color = "red">近视危险因素调查问卷数据</font>
**说明**  
- 未获得
- 查阅资料看儿童在日常生活中的哪些因素在长期或短期作用下可能会导致儿童近视。反过来也可以看哪些因素会有效的预防近视。
- 制定需求调查问卷表，在公众号给家长填写，收集到相关信息后进行分析。

**需求**    
- 儿童近视危险因素分析模型

## 2 现阶段任务
1. 基于之前的分析方法对最新数据进行分析，其中要更加细化年龄层与添加对性别的分析。统计有用的数据之后汇总，传给儿童医院后可调取相应的眼底图像数据。最终总结成论文发表。
    - 分析不同年龄与性别层初验指标的差异；
    - 分析矫正效果总体趋势与矫正差异；
2. 总结还需要的数据（字段）
3. 我们使用的方法简单说明文件

# <span id='6'><font color = "red">2018.12.17儿童医院OSAS汇报</font></span>
## 儿童医院人脸
1. 分层分析特征差异
    - osas 轻中重
    - 腺大 轻中重
    - 扁大 轻中重
    - 腺扁大 轻中重
2. osas识别
3. 补充同一个医院对照组数据
4. 重点是要区别疑似病例
5. 根据一些临床数据分层聚类
6. 和脑网络交叉

## 协和人脸
- 前沿性验证：使用新收集的进行验证
- 分层次进行聚类
- 优化模型，提高准确率
- 年龄分组分析，找出激素治疗的人
- 特征可解释性，可视化

😃重点：论文数量，抢占先机

# <span id='7'><font color = "red">2018.12.19迪谱诊断肥胖</font></span>

<div align="center">
    <img src = "https://note.youdao.com/yws/api/personal/file/74CA5352D5844F11BA42E5E3A984ADDF?method=download&shareKey=71cbe034cae2b331db0dc9f7e7cc1eb5">
</div>