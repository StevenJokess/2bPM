# ML [1]

## 与AI\DL\Data Mining等的关系

![与AI\DL\Data Mining等的关系[10]](../img/ML_relate2AI.png)

## 类别

第一类是构造间隔理论分布：聚类分析和模式识别

- 人工神经网络
- 决策树
- 感知器
- 支持向量机
- 集成学习AdaBoost
- 降维与度量学习
- 聚类
- 贝叶斯分类器

第二类是构造条件概率：回归分析和统计分类

- 高斯过程回归
- 线性判别分析
- 最近邻居法
- 径向基函数核

第三类是通过再生模型构造概率密度函数

- 最大期望算法
- 概率图模型：包括贝叶斯网和Markov随机场
- Generative Topographic Mapping

第四类是近似推断技术

- 马尔可夫链
- 蒙特卡罗方法
- 变分法

![ML[3]](../img/ML.png)


## ML VS software engineering

术语“软件工程”第一次出现是在1965年，也就是编程语言开始出现的15年后。大约20年后，软件工程研究所成立，以管理软件工程过程。今天，我们已经普遍接受了软件工程的最佳实践。另一方面，机器学习直到20世纪90年代才作为一个独立的领域开始蓬勃发展。深度学习是ML的一个子集，它在许多问题上的准确性创造了新纪录，包括图像识别和自然语言处理，直到2012年AlexNet的兴起才被广泛讨论。与软件工程相比，ML仍处于起步阶段，因此缺乏行业标准、度量标准、基础设施和工具。公司仍在探索最佳实践，扼杀应用程序。[5]

## 选择

![Machine Learning Algorithm Cheat Sheet[8]](../img/ML_cheat_sheet.png)

如何选择？[9]

在具体算法选择上，基于Python的scikit-learn机器学习算法库提供一套算法选择方法，参考这一部分（不局限于图中的算法和方法，由于这张图大多考虑了scikit中算法的实现情况）具体介绍一下算法的选择如下： [4]

1. 首先统计数据的容量当数据过小（小于50条）时，建议收集更多的数据，因为过小的数据训练的算法容易受噪声的影响比较大，算法效果一般。
2. 判断是否为预测一个类别的问题，如果是并且训练数据中包含标签信息则为分类问题。
3. 如果是预测一个类别的问题但是训练数据中不包含标签信息则是一个聚类问题
4. 如果不是一个分类问题，是预测一个具体的数值问题一般为回归问题，如果不是预测具体数值对数据进行分析，挖掘数据中的异常值等问题，这时可以考虑一下是否为降维问题。
5. 对于分类问题，如果数据量小于100k,建议用线性SVM的方法，如果效果不好根据是否为文本信息考虑用贝叶斯方法或者K临近分类法。如果数据量过大可以考虑加入正则化的方法来防止过拟合的问题来保证模型的稳定性。
6. 对于聚类问题，如果我们知道需要划分的数据集个数一般使用Kmeans等聚类方法即可。如果无法获知聚类的个数一般使用mean-shift的基于密度的算法可以对模型进行聚类评估，
7. 对于回归问题，如果数据量不大，直接使用SVM之类的回归即可，当然如果数据量过大可以考虑使用L1，L2的正则化方法来对权值进行正则化来防止过拟合问题的出现。这部分算法的选择与分类问题很相似。
8. 对于降维问题，如果是考虑为分类问题的输入维度进行削减，一般考虑LDA方法可以很好的对每个类别上的数据进行降维处理。如果单纯对输入维度进行降维，将原有维度信息转移到新的维度（根据维度的正交化来达到降维的目的）一般使用PCA方法是比较主流的方法。

对于算法的选择，有时不能找到确定的方法，也就是说很难根据数据是使用场景就完全锁定了那一个具体的算法，但是根据却可以缩小到指定的几个常用算法。然后通过测试集和训练集在这几个算法上做一些Demo。根据Demo反应的质量决定最终使用的算法那个。看似比较费力，其实是比较稳妥和精准的方法。

## 机器学习框架 [6]

机器学习方面的新框架层出不穷，一方面我们需要掌握经典框架的使用方式，理解其模块构成，接口规范的设计，一定程度上来说其它新框架也都需要遵循这些业界标准框架的模块与接口定义。另一方面对于新框架或特定领域框架，我们需要掌握快速评估，上手使用，并且做一定改造适配的能力。一些比较经典的框架有：

- 通用机器学习：scikit-learn，Spark ML，LightGBM
- 通用深度学习：Keras/TensorFlow，PyTorch
- 特征工程：tsfresh, Featuretools，Feast
- AutoML：hyperopt，SMAC3，nni，autogluon
- 可解释机器学习：shap，aix360，eli5，interpret
- 异常检测：pyod，egads
- 可视化：pyecharts，seaborn
- 数据质量：cerberus，pandas_profiling，Deequ
- 时间序列：fbprophet，sktime，pyts
- 大规模机器学习：Horovod，BigDL，mmlspark
- Pipeline：MLflow, metaflow，KubeFlow，Hopsworks
- 迁移学习：http://www.mysecretrainbow.com/ai/17262.html#1

一般的学习路径主要是阅读这些框架的官方文档和tutorial，在自己的项目中进行尝试使用。对于一些核心接口，也可以阅读一下相关的源代码，深入理解其背后的原理。

![Machine Learning Lifecycle[7]](../img/ML_lifecycle.png)

## 更多

https://mitpress.ublish.com/ereader/7093/?preview=#page/v

1. https://www.jianshu.com/p/ed9ae5385b89
1. https://www.jianshu.com/p/0359e3b7bb1b

《美团机器学习实践》笔记:https://www.dazhuanlan.com/2019/10/17/5da8114a3b457/

至少你要知道什么是二分类问题，什么是ground truth、熵（entropy）的概念，dynamic learning的概念等等。[2]

- https://www.reddit.com/r/MachineLearning/
- http://www.mlebook.com/wiki/doku.php

[1]: https://www.pianshen.com/article/66921228716/
[2]: http://www.uml.org.cn/DevProcess/201712283.asp
[3]: http://www.uml.org.cn/devprocess/201910163.asp
[4]: https://zhuanlan.zhihu.com/p/36870462
[5]: https://radiant-brushlands-42789.herokuapp.com/towardsdatascience.com/how-to-manage-machine-learning-products-part-1-386e7011258a
[6]: https://zhuanlan.zhihu.com/p/192633890
[7]: https://databricks.com/solutions/machine-learning
[8]: https://docs.microsoft.com/en-us/azure/machine-learning/algorithm-cheat-sheet
[9]: https://docs.microsoft.com/en-us/azure/machine-learning/how-to-select-algorithms
[10]: http://www.mysecretrainbow.com/ai/17264.html
