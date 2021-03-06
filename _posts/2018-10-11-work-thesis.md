---
layout: post
title: "【科研】研究生题目及资料"
subtitle: " \"Hello World！\""
date: 2018-10-11 09:27:15
author: "doraemonlei"
#header-img: "img/post-bg-2015.jpg"
#cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
categories: 科研 课题
tags: 
---

> 暂定，目前侧重研究，根据实际情况修改。

# 人脸

## <font color='red'>基于生成对抗网络的儿童面部畸变疾病形态学变化研究与应用</font>
### **课题背景**

**说明**  
- 主要针对《基于深度人脸检测和计算机视觉技术的儿童面部畸变疾病人脸形态学变化技术研究》项目
- 梁雅琪侧重研究

**课题研究目的**  
本课题旨在利用人脸识别、机器学习、深度学习与计算机视觉等人工智能技术对儿童面部畸变疾病进行形态学分析，具体研究内容为：
- 研究患者在未进行治疗之前面部形态学特点；
- 除正常生长发育外治疗（药物治疗、激素治疗、手术治疗等）对面部形态的影响，对治疗前后的面容变化进行形态学特征对比；
- 分析同年龄健康对照组面部形态学特点；
- 分析治疗对面部整体与局部结构的影响。通过研究分析，可生成各阶段人脸图像，给患者提供一个治疗后面容参考，生成的量化分析结果能辅助解决医学临床专科应用中的典型问题，最终形成一整套完整的系统。

**课题任务**  
本课题以几种儿童面部畸变疾病为主要研究对象，其中，由染色体变异使内分泌系统紊乱，从而导致面部出现畸变的疾病为特纳综合征；由气道阻塞导致长期张口呼吸从而使面容发生畸变的疾病为儿童腺样体异常疾病。通过抽样，对一些患儿与同年龄、性别的健康对照组进行长期的检查和和随访，研究在儿童生长发育阶段对照者正常生长发育的面容特点、患者患病之后面容的特点与患者接受治疗一定时间之后面容出现的改变与特点。通过研究面部形态学特点，可以精确掌握每种疾病在患病期间与治疗之后的面容特点，具有很大的临床意义与科研价值。其中具体任务包括：
- 研究患者在未进行治疗之前面部形态学特点；
- 除正常生长发育外治疗（药物治疗、激素治疗、手术治疗等）对面部形态的影响，对治疗前后的面容变化进行形态学特征对比；
- 分析同年龄健康对照组面部形态学特点；
- 分析治疗对面部整体与局部结构的影响。

**导致面部畸变的疾病类型**  
儿童面部畸形主要是由各种原因导致的非正常的生长发育所引起的面部整体或部分结构的缺陷。畸形分为轻度和重度，需要药物或外科手术治疗的均为重度(如腭裂)。轻度通常普遍存在，不需要干预治疗但影响美观。不同患儿的面部特征有显著不同，但大多是家族性遗传病的特征，即同一家族成员在外貌上有共同的与其他家族不同的特征，并非病理性的。一般而言，轻度畸形在健康普通人中发病率不少于4％，在新生儿当中有13％至少有一种轻度畸形。三种或三种以上轻度畸形同时存在的个体，合并重度畸形或某种综合征的概率明显增加。以下几类原因可导致患儿面部出现不同程度的相似面部畸形。
- 染色体异常导致内分泌系统紊乱从而使面部出现一些相似的畸形特征，如患儿内资赘皮明显可能为唐氏综合征；患儿内眦赘皮明显，眼距较宽，面部多黑痣则可能为特纳综合征。
- 先天或家族遗传性的淋巴系统病变导致儿童面部畸变，如儿童双睫毛，并且伴有淋巴水肿，患双行睫-淋巴水肿综合征可能性较大；儿童眼部水肿、颈淋巴结肿大可能为传染性单核细胞增多症。
- 由于某种原因导致某些物理干预长期作用使儿童出现面部畸变，如腺样体面容。由于儿童鼻咽部比较狭小，当腺样体肥大时，由于鼻塞影响呼吸而靠嘴张口呼吸，长期用口呼吸，气流冲击硬腭会使硬腭变形、高拱，长期物理干预下，儿童面部发育发生变形，出现上唇短厚翘起、下颌骨下垂、鼻唇沟消失、硬腭高拱、牙齿排列不整齐、上切牙突出、咬合不良、鼻中隔扁曲等面部畸形特点。

### **相关技术**
- 具体技术有人脸识别相关技术，图像处理相关技术，生成对抗网络相关技术。

### **技术路线**
- 规范化人脸图像采集。主要步骤包括：采集人脸图像，筛选可用图像，重命名，分组等步骤。
- 人脸图像进行预处理。主要步骤包括：人脸检测，人脸对齐，人脸截取，人脸图像几何归一化，人脸图像灰度归一化，人脸图像光照均衡，图像增强，人脸特征点建模等步骤。
- 特征分析。
    - 分析患者未进行治疗（药物治疗、激素治疗、手术治疗）前人脸形态学特点。
    - 分析患者进行治疗之后的人脸形态学特点。
    - 分析同年龄健康对照组人脸形态学特点。
- 边界平衡生成对抗网络建模。
    - 任务概述。通过以上三方面分析，训练三个深度学习边界平衡生成对抗网络（Boundary Equilibrium Generative Adversarial Networks, BEGAN）模型。通过生成各个时期的人脸图像，分析患者健康状态下的人脸和手术之后的人脸图像的不同特征。
    - BEGAN基本网络结构：
        - 生成器：BEGAN生成器的设计借鉴了 Wasserstein GAN 定义损失的思路。传统的生成对抗网络会尝试直接匹配数据分布，BEGAN使用从Wasserstein距离衍生而来的损失去匹配自编码器的损失分布。实现方法通过传统的GAN目标加上一个用来平衡判别器和生成器的平衡项实现的。
        - 判别器：使用自编码器作为BEGAN的判别器。
    - BEGAN的优势与创新点：
        - 一个简单且鲁棒的 GAN 结构，使用标准的训练步骤实现了快速且稳定的收敛；
        - 一个平衡的概念，用于平衡判别器和生成器的竞争力；
        - 一种控制图像多样性和视觉质量之间的权衡的新方法；
        - 一种近似衡量收敛的方法。目前已发表的这类方法的工作只有一个，就是 Wasserstein GAN（WGAN）。
- 分析结果展示。通过生成患者治疗之后的形态学人脸图像，可以给患者提供一个治疗后面容参考，同时能辅助解决医学临床专科应用中的典型问题。

## <font color='red'>基于深度卷积神经网络的儿童面部畸变疾病通用识别技术研究与应用</font>
### **说明**
- 主要针对几种不同原因导致的人脸畸变的多分类问题，形成一套通用多分类识别系统。
- 王星月侧重。 

**课题任务**  
通过在协和内分泌科与儿童医院呼吸科部署采集工具近两年的人脸图像采集工作，目前采集到患儿图像共计5000余条，经过统计，其中的十余种疾病占主要部分，主要包括矮小，特纳综合征，生长激素缺乏症，小于胎龄儿，生长激素部分缺乏症，PAH	，性早熟，生长激素分泌过少，特发性矮小，腺扁大，腺大，扁大，鼾症，过敏性鼻炎等，其中，由于不同原因导致儿童面部出现畸变的疾病有特纳综合征，腺扁大，腺大等。主要任务有：
- 研发标准化人脸数据采集中心与标准化人脸采集硬件设备制定规范
- 研发儿童面部畸变疾病通用识别技术，制定一套规范流程

### **相关技术**
- 主要技术有人脸识别相关技术，图像处理相关技术，深度神经网络，深度卷积神经网络等。

### **技术路线**
基本步骤思想跟之前类似

# 知识图谱

## <font color='red'>基于哮喘知识图谱的疾病特征分析系统研究与应用</font>
### 说明
- 主要技术有知识图谱相关技术，图数据库相关技术，web框架相关技术等
- 李伟岩侧重

### 相关技术

### 技术路线

## <font color='red'>基于慢阻肺知识图谱的自动问答系统研究与应用</font>
### 说明
- 主要技术有知识图谱相关技术，图数据库相关技术，web框架相关技术等
- 贾辛洪侧重

### 相关技术

### 技术路线