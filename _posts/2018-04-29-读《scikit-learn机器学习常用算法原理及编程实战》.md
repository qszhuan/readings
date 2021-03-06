---
title: 读《scikit-learn机器学习常用算法原理及编程实战》 
category:  
tags: [阅读]  
layout: post  
author:  
name: 
thumbnail: /assets/images/books/scikit-learn机器学习常用算法原理及编程实战.jpg
---

吴恩达在coursera上的机器学习课程讲解了机器学习的基础知识和算法，但主要是用matlab/octave进行教学的。所以一直想找一本使用Python进行机器学习的书籍。

这本书完全出乎我的意料，本来以为只不过是一本类似cookbook的书，能学点scikit的示例也不错。但读了几章后发现，这本书思路非常清晰，把机器学习的原理讲解得非常明白，该讲的地方都有讲到，而且没有什么废话。如果要推荐一本机器学习基础的中文书，这本我觉得应该是首选了。


下面是读书笔记：

## 分类

机器学习分为两大类：有监督学习和无监督学习。

**有监督学习**是指已经有标记（有输入和输出）的数据，通过该数据建立并训练模型，从而达到对新的输入作出合理的预测。

该分类中，根据预测结果又可以分为回归学习和分类学习。回归学习的预测模型是一个连续的函数，比如根据历史数据预测房价。分类学习的结果是离散的，比如分析一封邮件是不是垃圾邮件。


**无监督学习**中数据是没有标记的，模型去分析这些数据，从而对数据进行分类（聚类，clustering）。

## 机器学习开发的步骤

1. 数据采集和标记
1. 数据清洗
1. 特征选择
1. 模型选择
1. 模型训练和测试
1. 模型新能评估和优化
1. 模型使用

## scikit-learn一般性原理和通用原则

* scikit-learn的所有算法都以一个评估模型对象来对外提供接口，创建模型对象时可以指定不同的参数，参数会直接影响模型训练效率及准确率

* 所有评估模型对象都提供了fit()接口，该接口用来训练模型

* 所有的有监督学习算法，模型对象提供了predict()接口，来进行预测。针对分类问题，有的模型还提供了predict_proba()输出结果所属类别的可能性，而predict（）直接返回可能性最高的类别。

* 几乎所有模型都提供了score()接口来评估模型好坏（准确度）。但是该结果不是评估模型好坏的唯一标准（其他还有查准率和召回率）。

* 针对无监督学习算法，predict()接口用来对数据进行聚类分析，此外，无监督学习算法还有transform()接口，用来进行转化（如数据降维处理）。

* sklearn.metrics提供了其他一些模型性能检测的方法。

* 下面是scikit-learn官网提供的如何选择算法的速查表：

[![image][scikit-cheatsheet]][scikit-cheatsheet]

[scikit-cheatsheet]: {{ site.baseurl }}/assets/images/ml_map.png "scikit-learn 算法速查表"