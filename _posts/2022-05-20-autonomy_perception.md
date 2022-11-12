---
layout: post
title: "《自动驾驶感知算法实战专栏（源代码）》专栏概述"
date: 2022-11-12
tags: [自动驾驶, 计算机视觉, 感知算法]
comments: true
author: Charmve
toc: true
---

<p align="left">
  <a href="https://github.com/Charmve"><img src="https://img.shields.io/badge/GitHub-@Charmve-000000.svg?logo=GitHub" alt="GitHub" target="_blank"></a> 
  <a href="https://imgconvert.csdnimg.cn/aHR0cHM6Ly9tbWJpei5xcGljLmNuL21tYml6X3BuZy9aTmRoV05pYjNJUkIzZk5ldWVGZEQ4YnZ4cXlzbXRtRktUTGdFSXZOMUdnTHhDNXV0Y1VBZVJ0T0lJa0hTZTVnVGowamVtZUVOQTJJMHhiU0xjQ3VrVVEvNjQw?x-oss-process=image/format,png" target="_blank" ><img src="https://img.shields.io/badge/公众号-@迈微AI研习社-000000.svg?style=flat-square&amp;logo=WeChat" alt="微信公众号"/></a> 
  <a href="https://www.zhihu.com/people/MaiweiE-com" target="_blank" ><img src="https://img.shields.io/badge/%E7%9F%A5%E4%B9%8E-@Charmve-000000.svg?style=flat-square&amp;logo=Zhihu" alt="知乎"/></a> 
  <a href="https://space.bilibili.com/62079686" target="_blank"><img src="https://img.shields.io/badge/B站-@Charmve-000000.svg?style=flat-square&amp;logo=Bilibili" alt="B站"/></a> 
  <a href="https://blog.csdn.net/Charmve" target="_blank"><img src="https://img.shields.io/badge/CSDN-@Charmve-000000.svg?style=flat-square&amp;logo=CSDN" alt="CSDN"/></a>
</p>

><font size = 4>导言</font>
>自动驾驶太火？高薪？跃跃欲试，又仅存于想的阶段。动起来，只是看理论，却总也学不会？看不懂，又总没有进度？如果你也有这类问题，那你来看看这个专栏。以实际项目为导向，亲自动手实践，从简单的图像分类、目标检测开始，逐渐学习掌握实例分割、目标检测、车道线检测等进阶技能。学习有回馈、有成就感，你才能继续下去。转行？你就得看看这个。

**基本思路：自动驾驶感知模块的生产流水线，输入+输出**

<br>

# 专栏订阅

<p align="center">
  <a href="https://blog.csdn.net/charmve/category_12097938.html">
    <img src="https://user-images.githubusercontent.com/29084184/201481991-bfc30f6e-7d2b-49aa-9ae6-1022162cf153.png" />
  </a>
  <a href="https://blog.csdn.net/charmve/category_12097938.html">点击学习 💯</a>
</p>

# 专栏大纲
## 零、感知系统整体概述 （5%）

<img width="1593" alt="image" src="https://user-images.githubusercontent.com/29084184/201470301-b7fc5110-b910-47ba-b87c-fd55d4af918f.png">

1. 在自动驾驶系统中的位置，上下游
2. 解决什么问题
3. 实现方案

## 一、输入：相机+雷达 （10%）
1. 相机
1.1 相机的成像原理
1.2 数字图像处理：去畸变、resize、颜色变换、转柱面、透视变换等（原理及源代码实现）
1.3 实现方案及性能分析：opencv、nvmedia

2. 激光雷达
2.1 雷达模块概述
2.2 雷达感知原理
2.3 雷达感知算法概述

## 二、感知系统任务/目标 （20%）
1. 目标检测：行人检测、车辆检测、车道线检测、可通行区域检测、多目标跟踪
主要模型介绍分析：Mask R-CNN、Inception v2（原理及源代码实现）

2. 目标分类：红绿灯识别、障碍物检测
主要模型介绍分析：AlexNet、VGG、FCN（原理及源代码实现）

3. 实例分割：可通行区域检测、障碍物检测、异形物检测
主要模型介绍分析：UNet、SegNet（原理及源代码实现）

## 三、图像分类（机器学习方法） （15%）（原理及源代码实现）
3.1 数据驱动方法
  3.1.1 语义上的差别
  3.1.2 图像分类任务面临着许多挑战
  3.1.3 数据驱动的方法

3.2 k 最近邻算法
  3.2.1 k 近邻模型
  3.2.2 k 近邻模型三个基本要素
  3.2.3 KNN算法的决策过程
  3.2.4 k 近邻算法Python实现

3.3 支持向量机
  3.3.1 概述
  3.3.2 线性支持向量机
  3.3.3 从零开始实现支持向量机
  3.3.4 支持向量机的简洁实现

3.4 逻辑回归 LR
  3.4.1 逻辑回归模型
  3.4.2 从零开始实现逻辑回归
  3.4.3 逻辑回归的简洁实现

## 四、多传感器融合感知方案详解 （20%）

1. 感知方案：前融合、后融合、中融合

1.1 lidar-基于激光雷达进行障碍物检测、分割、分类
1.2 相机-红绿灯检测、障碍物检测和分类
1.3 radar-基于毫米波传感器进行速度、姿态估计
1.4 融合Fusion-前融合、后融合、中融合中两种及以上

2. BEV模型

BEV 基于图像/Lidar/多模态数据的3D检测与分割任务

2.1 坐标变换
2.3 时间同步、时序任务
2.4 精度选择
2.5 性能分析

3. 发展方向：多模态感知、多任务处理、大模型

## 五、感知算法模型生产线 （20%）
（闭环框图）
1. 数据选择（数据采集、数据增强）
2. 数据标注
3. 模型训练
4. 模型量化
5. 模型部署
6. 测试与验证

## 六、纯视觉感知和雷达方案对比（5%）

成本和效果两个角度，第一性原理

1. 特斯拉方案

2. 非特斯拉方案

## 七、总结：如何打造“高可靠、多冗余、可量化、数据驱动的感知系统”（5%）

1. 高可靠：对障碍物、红绿灯的识别精度有保证
2. 多冗余：各个模块相互支撑、非串行
3. 可量化：PRT、仿真场景测试、Profiling
4. 数据驱动（全流程闭环）


# 面向人群

1. 自动驾驶行业研发相关从业人员；转行？你就得看看这个。
2. 对自动驾驶系统感兴趣，尤其是感知模块，对自动驾驶有相关了解，有数理基础；
3. 对机器人系统有相关实践经验，对感知算法有基本了解；
4. 其他算法从业者，有数理基础；

# 课后收益

1. 对自动驾驶有更深的理解，尤其是视觉和雷达感知系统；
2. 有较为全面的认识，对感知系统全算法链路有一定了解，能够自己动手开始一些感知系统中的子任务；
3. 动手实现车道线检测、目标识别、可通行区域检测等算法，源代码实现；
3. 对当前自动驾驶行业有更深的了解，抛砖引玉开展相关工作；
4. 了解几种经典的感知算法模型，从实现原理到模型产出；


<p align="center">
  <a href="https://blog.csdn.net/charmve/category_12097938.html">
    <img src="https://user-images.githubusercontent.com/29084184/201481991-bfc30f6e-7d2b-49aa-9ae6-1022162cf153.png" />
  </a>
  <a href="https://blog.csdn.net/charmve/category_12097938.html">点击学习 💯</a>
</p>