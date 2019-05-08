---
layout: post
title: Daily works
author: RyuTian
---

## 2019/5/8
从周日开始到今天，虽然只有四天时间，可是，这四天里踩过的雷也是记忆尤新了！
现在，注意记录在此，以示警醒：
1. 推公式时，把Gaussian-Weishart分布和Gaussian-Gamma分布搞混，导致对精度矩阵的参数更新发生错误；后更正；
2. coding实现时，更新Gaussian分布的参数和Gamma分布的参数时，对Gaussian分布的精度矩阵的系数更新错误，每次更新应该是基于数据的似然，在初始参数值下进行更新；对Gamma分布的shape参数更新时，发生了一样的错误；后更正；
3. 在计算z（指示变量）的期望时，发生了数值计算溢出，起初没有发现，后来测试的时候发现pi的超参数跟初始化比没有发生变化，一路找下去，才发现这个错误；后用logsumexp进行解决；
4. 在adam参数更新时，发现对learning rate做衰减十分重要，否则不论是baseline还是自己的方法都不收敛，会严重的震荡；虽然最后test上的识别率也能有一定的效果
5. 对于我们的方法，K=1时退化成Relation Network，可以达到与作者报告的相似的性能；现在主要在调K > 1时的性能；
6. 对于Zhang报告的结果以及实验过程，发现，用RN的结构其实可以收敛的更快且性能比原始的单层结构更好，所以很奇怪Zhang为什么要这么做！
7. 实验中发现，不论是Zhang的方法还是我们的，用多层的结构都会较单层有明显的优势；
8. 如果再有性能上的bug，拟决定对另一路也引入expert机制，和分类器对应起来。

另外，今天要阅读的文章，mark一下：
1. an attentive survey of attention models
2. Supervising Unsupervised Learning
3. META-LEARNING UPDATE RULES FOR UNSUPERVISED REPRESENTATION LEARNING
