# ML [^1]

## 与AI\DL\Data Mining等的关系

![与AI\DL\Data Mining等的关系[^10]](../img/ML_relate2AI.png)

## 类别

第一类是构造间隔理论分布：聚类分析和模式识别

- 人工神经网络∈连接主义学习
- 决策树∈符号主义学习
- 感知器
- 支持向量机∈统计学习[^23]
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

![ML[^3]](../img/ML.png)

![机器学习算法工程师[^24]](../img/ML_tech_tree.jpg)

## ML VS software engineering

术语“软件工程”第一次出现是在1965年，也就是编程语言开始出现的15年后。大约20年后，软件工程研究所成立，以管理软件工程过程。今天，我们已经普遍接受了软件工程的最佳实践。另一方面，机器学习直到20世纪90年代才作为一个独立的领域开始蓬勃发展。深度学习是ML的一个子集，它在许多问题上的准确性创造了新纪录，包括图像识别和自然语言处理，直到2012年AlexNet的兴起才被广泛讨论。与软件工程相比，ML仍处于起步阶段，因此缺乏行业标准、度量标准、基础设施和工具。公司仍在探索最佳实践，扼杀应用程序。[5]

## 选择

![Machine Learning Algorithm Cheat Sheet[8]](../img/ML_cheat_sheet.png)

如何选择？[^9]

在具体算法选择上，基于Python的scikit-learn机器学习算法库提供一套算法选择方法，参考这一部分（不局限于图中的算法和方法，由于这张图大多考虑了scikit中算法的实现情况）具体介绍一下算法的选择如下： [^4]

1. 首先统计数据的容量当数据过小（小于50条）时，建议收集更多的数据，因为过小的数据训练的算法容易受噪声的影响比较大，算法效果一般。
2. 判断是否为预测一个类别的问题，如果是并且训练数据中包含标签信息则为分类问题。
3. 如果是预测一个类别的问题但是训练数据中不包含标签信息则是一个聚类问题
4. 如果不是一个分类问题，是预测一个具体的数值问题一般为回归问题，如果不是预测具体数值对数据进行分析，挖掘数据中的异常值等问题，这时可以考虑一下是否为降维问题。
5. 对于分类问题，如果数据量小于100k,建议用线性SVM的方法，如果效果不好根据是否为文本信息考虑用贝叶斯方法或者K临近分类法。如果数据量过大可以考虑加入正则化的方法来防止过拟合的问题来保证模型的稳定性。
6. 对于聚类问题，如果我们知道需要划分的数据集个数一般使用Kmeans等聚类方法即可。如果无法获知聚类的个数一般使用mean-shift的基于密度的算法可以对模型进行聚类评估，
7. 对于回归问题，如果数据量不大，直接使用SVM之类的回归即可，当然如果数据量过大可以考虑使用L1，L2的正则化方法来对权值进行正则化来防止过拟合问题的出现。这部分算法的选择与分类问题很相似。
8. 对于降维问题，如果是考虑为分类问题的输入维度进行削减，一般考虑LDA方法可以很好的对每个类别上的数据进行降维处理。如果单纯对输入维度进行降维，将原有维度信息转移到新的维度（根据维度的正交化来达到降维的目的）一般使用PCA方法是比较主流的方法。

对于算法的选择，有时不能找到确定的方法，也就是说很难根据数据是使用场景就完全锁定了那一个具体的算法，但是根据却可以缩小到指定的几个常用算法。然后通过测试集和训练集在这几个算法上做一些Demo。根据Demo反应的质量决定最终使用的算法那个。看似比较费力，其实是比较稳妥和精准的方法。

## 机器学习框架 [^6]

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

Mlperf  AI基准

AI时代需要什么样的基准？从Mlperf  AI基准测试中读出了这些 - 胡克的文章 - 知乎
https://zhuanlan.zhihu.com/p/375319613

## 指标

- 准确率（P值）是针对我们预测结果而言的，它表示的是预测为正的样本中有多少是真正的正样本。
- 召回率（R值）是针对我们原来的样本而言的，它表示的是样本中的正例有多少被预测正确了。

## 流程 [^20]

### 目标定义

确认机器学习要解决的问题本质以及衡量的标准。

机器学习的目标可以被分为：分类、回归、聚类、异常检测等。

### 数据采集

原始数据作为机器学习过程中的输入来源是从各种渠道中被采集而来的。

### 数据预处理

普通数据挖掘中的预处理包括数据清洗、数据集成、数据转换、数据削减、数据离散化。

深度学习数据预处理包含数据归一化（包含样本尺度归一化、逐样本的均值相减、标准化）和数据白化。需要将数据分为三种数据集，包括用来训练模型的训练集（training set），开发过程中用于调参（parameter tuning）的验证集（validation set）以及测试时所使用的测试集（test set）。

数据标注的质量对于算法的成功率至关重要。

### 模型训练

模型训练流程：每当有数据输入，模型都会输出预测结果，而预测结果会用来调整和更新W和B的集合，接着训练新的数据，直到训练出可以预测出接近真实结果的模型。

### 准确率测试

用第三步数据预处理中准备好的测试集对模型进行测试。

### 调参

参数可以分为两类，一类是需要在训练（学习）之前手动设置的参数，即超参数（hypeparameter），另外一类是通常不需要手动设置、在训练过程中可以被自动调整的参数（parameter）。

调参通常需要依赖经验和灵感来探寻其最优值，本质上更接近艺术而非科学，是考察算法工程师能力高低的重点环节。

### 模型输出

模型最终输出应用于实际应用场景的接口或数据集。


## 金融应用

利用传统的回归分析等方法来建模交易策略有两个弊端：首先，所用数据维度有限，仅限于交易数据；其次，模型可处理的变量有限，模型的有效与否取决于所选取变量的特征和变量间的组合，而这很大程度上取决于研究员对数据的敏感程度。利用机器学习技术，结合预测算法，可以依据历史经验和新的市场信息不断演化，预测股票、债券等金融资产价格的波动及波动间的相互关系，以此来创建符合预期风险收益的投资组合。然而，机器学习可能是个相对缓慢的过程，且该过程无法通过其他统计方法来提供担保行为。机器学习虽可能适用于寻找隐藏的趋势、信息和关系，但在金融领域的应用和效果仍存在较大不确定性。市场上对于金融领域的机器学习仍存在一定程度的炒作。[^21]

## 更多

https://yulinzhao.wordpress.com/category/3_machine-learning/

https://mitpress.ublish.com/ereader/7093/?preview=#page/

1. https://www.jianshu.com/p/ed9ae5385b89
1. https://www.jianshu.com/p/0359e3b7bb1b

《美团机器学习实践》笔记:https://www.dazhuanlan.com/2019/10/17/5da8114a3b457/

至少你要知道什么是二分类问题，什么是ground truth、熵（entropy）的概念，dynamic learning的概念等等。[2]

- https://www.reddit.com/r/MachineLearning/
- http://www.mlebook.com/wiki/doku.php

不容错过的 20 个机器学习与数据科学网站[^11]

- Andreas Mueller 的这门免费的课程《应用机器学习》[^16]（Applied Machine Learning）。
- Coursera：《机器学习》[^17]（Machine Learning），吴恩达（Andrew Ng）。
- 优达学城（Udacity）：机器学习工程纳米学位[^18]（Machine Learning Engineering Nanodegree）。
- Google速成ML课程[^19]

## 技术债务

“技术债务”，指为了产品快速迭代，做了很多临时性的代码处理。但是在未来的某一天，这些遗留问题都会以BUG方式体现出来，导致付出更大的维护成本[14]

技术债务或许可以通过重构代码，改善单元测试，删除僵尸代码，减少依赖，精简 API 和改良文档说明进行清算。其目的不在于添加新功能，而是着眼于未来的提升，减少错误和提高可维护性。延期偿还只会加重负担，隐性债务之所以危险正是因为它是悄无声息间积攒下的。[^12]

### 让技术债务公开透明

技术债务无处不在，应该成为每一次产品会议的一部分。让它成为一个可操作的项目，并寻求定期更新。为了避免看起来仅仅像一个把关者，要努力让开发人员参与解决问题，并为解决技术债务这项工作设定优先级。要清楚以下问题：开发人员更喜欢在冲刺中还是专门的时间来解决技术债务？哪个人负责哪块工作？每个人目前工作量是多少？是否需要更多员工？[22]

## ML system

机器学习系统在以下方面与其他软件系统不同：[^13]

- 团队技能：在机器学习项目中，团队通常包括数据科学家或机器学习研究人员，他们主要负责进行探索性数据分析、模型开发和实验。这些成员可能不是经验丰富的、能够构建生产级服务的软件工程师。
- 开发：机器学习在本质上具有实验性。您应该尝试不同的特征、算法、建模技术和参数配置，以便尽快找到问题的最佳解决方案。您所面临的挑战在于跟踪哪些方案有效、哪些方案无效，并在最大程度提高代码重复使用率的同时维持可重现性。
- 测试：测试机器学习系统比测试其他软件系统更复杂。除了典型的单元测试和集成测试之外，您还需要验证数据、评估经过训练的模型质量以及验证模型。
- 部署：在机器学习系统中，部署不是将离线训练的机器学习模型部署为预测服务那样简单。机器学习系统可能会要求您部署多步骤流水线以自动重新训练和部署模型。此流水线会增加复杂性，并要求您自动执行部署之前由数据科学家手动执行的步骤，以训练和验证新模型。
- 生产：机器学习模型的性能可能会下降，不仅是因为编码不理想，而且也因为数据资料在不断演变。换句话说，与传统的软件系统相比，模型可能会通过更多方式衰退，而您需要考虑这种降级现象。因此，您需要跟踪数据的摘要统计信息并监控模型的在线性能，以便系统在值与预期不符时发送通知或回滚。

More Resources[^15]

https://huyenchip.com/ml-interviews-book/contents/4.3-resources.html

AutoML:https://developer.jdcloud.com/article/1698

[^1]: https://www.pianshen.com/article/66921228716/
[^2]: http://www.uml.org.cn/DevProcess/201712283.asp
[^3]: http://www.uml.org.cn/devprocess/201910163.asp
[^4]: https://zhuanlan.zhihu.com/p/36870462
[^5]: https://radiant-brushlands-42789.herokuapp.com/towardsdatascience.com/how-to-manage-machine-learning-products-part-1-386e7011258a
[^6]: https://zhuanlan.zhihu.com/p/192633890
[^7]: https://databricks.com/solutions/machine-learning
[^8]: https://docs.microsoft.com/en-us/azure/machine-learning/algorithm-cheat-sheet
[^9]: https://docs.microsoft.com/en-us/azure/machine-learning/how-to-select-algorithms
[^10]: http://www.mysecretrainbow.com/ai/17264.html
[^11]: https://libertydream.github.io/2020/02/16/20%E4%B8%AA%E4%B8%8D%E5%AE%B9%E9%94%99%E8%BF%87%E7%9A%84AI%E8%B5%84%E6%BA%90/
[^12]: https://libertydream.github.io/2020/05/10/ML%E9%9A%90%E6%80%A7%E5%80%BA%E5%8A%A1/
[^13]: https://cloud.google.com/solutions/machine-learning/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning?hl=zh-cn
[^14]: http://www.woshipm.com/pmd/3024508.html
[^15]: https://libertydream.github.io/2020/05/10/ML%E9%9A%90%E6%80%A7%E5%80%BA%E5%8A%A1/
[^16]: https://www.infoq.cn/article/IPDVRNxwJVsx3ZGrgwzW
[^17]: https://www.coursera.org/learn/machine-learning?utm_source=gg&utm_medium=sem&utm_content=07-StanfordML-US&campaignid=685340575&adgroupid=32639001781&device=c&keyword=machine%20learning%20programming%20tutorial&matchtype=b&network=g&devicemodel=&adpostion=&creativeid=243289762754&hide_mobile_promo&gclid=EAIaIQobChMIhY7m1Pfa6wIVtR6tBh0UCQAJEAAYASAAEgJcV_D_BwEhttps://www.coursera.org/learn/machine-learning?utm_source=gg&utm_medium=sem&utm_content=07-StanfordML-US&campaignid=685340575&adgroupid=32639001781&device=c&keyword=machine%20learning%20programming%20tutorial&matchtype=b&network=g&devicemodel=&adpostion=&creativeid=243289762754&hide_mobile_promo&gclid=EAIaIQobChMIhY7m1Pfa6wIVtR6tBh0UCQAJEAAYASAAEgJcV_D_BwE
[^18]: https://www.udacity.com/course/machine-learning-engineer-nanodegree--nd009t
[^19]: https://developers.google.com/machine-learning/crash-course/static-vs-dynamic-training/video-lecture?hl=zh-cn#:~:text=%E4%BB%8E%E5%B9%BF%E4%B9%89%E4%B8%8A%E8%AE%B2%EF%BC%8C%E8%AE%AD%E7%BB%83,%E6%A8%A1%E5%9E%8B%E9%87%87%E7%94%A8%E5%9C%A8%E7%BA%BF%E8%AE%AD%E7%BB%83%E6%96%B9%E5%BC%8F%E3%80%82
[^20]: http://www.woshipm.com/pmd/2942899.html
[^21]: http://www.cstf.org.cn/newsdetail.asp?types=36&num=1165
[^22]: https://xie.infoq.cn/article/ae3c570bea05c03db982c4f1b
[^23]: https://zhuanlan.zhihu.com/p/26571486
[^24]: http://www.ppvke.com/archives/32249
