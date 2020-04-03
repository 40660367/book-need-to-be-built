---
title: "sklearn简介"
meta_title: ''
meta_description: ''
keywords: 
    - sklearn
    - sklearn简介
    - intro
sidebar: "sklearn"
---
# sklearn简介

https://www.tutorialspoint.com/scikit_learn/scikit_learn_anomaly_detection.htm

在本章中，我们将了解什么是Scikit-Learn或Sklearn，Scikit-Learn的起源以及其他一些相关主题，例如负责Scikit-Learn的开发和维护的社区和贡献者，其先决条件，安装及其功能。

## 什么是Scikit-Learn（Sklearn）

Scikit-learn（Sklearn）是Python中用于机器学习的最有用和最强大的库。它通过Python中的一致性接口为机器学习和统计建模提供了一系列有效的工具，包括分类，回归，聚类和降维。该库主要使用Python编写，基于**NumPy，SciPy**和**Matplotlib构建**。

## Scikit-Learn的起源

它最初称为***scikits.learn\***，最初由David Cournapeau于2007年在Google的夏季代码项目中开发。后来，在2010年，FIRCA（法国科学研究所）的Fabian Pedregosa，Gael Varoquaux，Alexandre Gramfort和Vincent Michel计算机科学与自动化），将该项目带入了另一个层次，并于2010年2月1日发布了第一个公开版本（v0.1 beta）。

让我们看看它的版本历史-

- 2019年5月：scikit-learn 0.21.0
- 2019年3月：scikit-learn 0.20.3
- 2018年12月：scikit-learn 0.20.2
- 2018年11月：scikit-learn 0.20.1
- 2018年9月：scikit-learn 0.20.0
- 2018年7月：scikit-learn 0.19.2
- 2017年7月：scikit-learn 0.19.0
- 2016年9月。scikit-learn 0.18.0
- 2015年11月。scikit-learn 0.17.0
- 2015年3月。scikit-learn 0.16.0
- 2014年7月。scikit-learn 0.15.0
- 2013年8月。scikit-learn 0.14

## 社区和贡献者

Scikit-learn是一项社区活动，任何人都可以为此做出贡献。该项目托管在[https://github.com/scikit-learn/scikit-learn上。](https://github.com/scikit-learn/scikit-learn)目前，以下人员是Sklearn开发和维护的主要贡献者-

- Joris Van den Bossche（数据科学家）
- Thomas J Fan（软件开发人员）
- Alexandre Gramfort（机器学习研究员）
- Olivier Grisel（机器学习专家）
- Nicolas Hug（副研究员）
- Andreas Mueller（机器学习科学家）
- 秦汉民（软件工程师）
- Adrin Jalali（开源开发人员）
- Nelle Varoquaux（数据科学研究员）
- Roman Yurchak（数据科学家）

像Booking.com，JP Morgan，Evernote，Inria，AWeber，Spotify等各种组织都在使用Sklearn。

## 先决条件

在开始使用scikit-learn最新版本之前，我们需要满足以下条件-

- Python（> = 3.5）
- NumPy（> = 1.11.0）
- Scipy （> = 0.17.0）li
- Joblib（> = 0.11）
- Sklearn绘图功能需要Matplotlib（> = 1.5.1）。
- 使用数据结构和分析的某些scikit学习示例需要使用Pandas（> = 0.18.0）。

## 安装

如果您已经安装了NumPy和Scipy，则以下是安装scikit-learn的两种最简单的方法-

### 使用pip

以下命令可用于通过pip安装scikit-learn-

```
pip install -U scikit-learn
```

### 使用conda

以下命令可用于通过conda安装scikit-learn-

```
conda install scikit-learn
```

另一方面，如果您的Python工作站上尚未安装NumPy和Scipy，则可以使用**pip**或**conda进行安装**。

使用scikit-learn的另一种方法是使用***Canopy\***和***Anaconda之\***类的Python发行版，因为它们都发布了最新版本的scikit-learn。

## 特点

Scikit-learn库不是专注于加载，处理和汇总数据，而是专注于对数据建模。Sklearn提供的一些最受欢迎的模型组如下-

**监督学习算法** -几乎所有流行的监督学习算法，例如线性回归，支持向量机（SVM），决策树等，都是scikit-learn的一部分。

**无监督学习算法** -另一方面，它还具有从聚类，因子分析，PCA（主成分分析）到无监督神经网络的所有流行的无监督学习算法。

**群集** -此模型用于对未标记的数据进行分组。

**交叉验证** -用于检查看不见的数据上监督模型的准确性。

**降维** -用于减少数据中的属性数量，这些属性可进一步用于汇总，可视化和特征选择。

**集成方法** -顾名思义，它用于组合多个监督模型的预测。

**特征提取** -用于从数据中提取特征，以定义图像和文本数据中的属性。

**特征选择** -用于识别有用的属性以创建监督模型。

**开源** -它是开源库，并且在BSD许可下也可以商业使用。
<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=python></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>
