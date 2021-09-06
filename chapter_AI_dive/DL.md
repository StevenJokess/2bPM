# 深度学习算法

## 本质

深度学习是连接主义和机器学习相结合的产物，最大的贡献是找到了一种在多层神经网络上进行机器学习的方法，本书作者杨立昆和约书亚·本吉奥、杰弗里·辛顿因此获得2018年度图灵奖。

深度学习首先回答了什么样的神经网络可以训练出智能，包括多层神经网络和卷积神经网络，也回答了训练（学习）方法问题，包括受限玻尔兹曼机模型、反向传播算法、自编码模型等。

深度学习对连接主义的重大意义是给出了一条训练智能的可行途径，对机器学习的重大意义则是给出了一个凝聚学习成效的可塑载体。[^10]

## DL 模型的表达能力

相较传统统计模型来说，深度神经网络有着数量众多的参数。如果用 MDL 衡量深度神经网络的复杂度，并将参数数量视为模型描述长度，那模型看起来可会惨不忍睹。模型描述
L(H) 很容易失控性疯涨。

但为使表达能力够强，对神经网络而言这许许多多的参数 必不可少。正因为神经网络对灵活多样的数据表示具备出色的捕获能力，它才能在许多应用中取得辉煌战绩。[^4]

## 神经网络组成 [1]

解析：

- 公式：$A^{(n+1)}=\delta^{n}\left(W^{n} A^{n}+b^{n}\right)$
- Weights（网络权重）：表示不同神经元处理的特征对下个神经元的重要性
- bias （偏移）：主观偏见的处理
- 激活函数：对每一层整体的输出做改进，把每层的结果做非线性的变化，去更好地拟合数据分布，或者说来更好地展示给下一层级，常见的激活函数有 ReLU、tanh、Sigmoid 等等，我们用 δn() 表示

原理：目标就是在给定一个任务的情况下，找到最优的 Weights 和 bias，使得 Loss 最低。采用反向传播，把 Loss 误差从最后逐层向前传递，使当前层知道自己在哪里，然后再更新当前层的 Weights 权重和 bias 偏移，进而减小最后的误差

- 常见的深度学习算法：CNN、LSTM、RNN、Seq2Seq、GAN
- 常用的深度学习框架：TensorFlow、PyTorch

解析：

越复杂的图像，采用全连接层的形式，计算量就会变得很大

卷积层提取图片初步特征[^5]

池化：

- 目的是提取特征，减少向下一阶段传递的数据量，池化过程的本质是“丢弃”，即只保留图像主体特征，过滤掉无关信息的数据特征
- 模糊化图像操作：通过 CNN 的卷积和池化，丢弃到无用的特征，识别出关键因素
- 全连接层的Softmax分类：再卷积池化后通过softmax进行分类

全连接层将各部分特征汇总[^5]

CNN优缺点：

- 缺点：可解释性弱，模型训练慢，对数据依赖很强，模型复杂
- 优点：

1. 可以拟合任意复杂的数据分布
1. 比我们之前讲过的所有算法的性能都要好

## 卷积神经网络是最为实用且通常最为正确的方法的一些原因如下：

1. 它们可以通过层传递学习，保存推理并在后续层上创建新的推理。
1. 在使用该算法之前，无需进行特征提取，而是在训练过程中完成的。
1. 它可以识别重要的特征。

但是，它们也有自己的警告。目前已知它们在旋转和缩放方式不同的图像上会失效，但这里的情况并非如此，因为数据已经经过预处理。而且，尽管其他方法在这个数据集上未能提供良好的结果，但它们仍然可以用于其他与图像处理相关的任务（如锐化、平滑等等）。[^7]

## 历史脉络

![目标检测的历史脉络[^5]](../img/obj_detect_history.png)

## 关键问题 [^8]

- 网络结构问题
- 特征表示问题
- 海量数据标注问题
- 数据升维降维问题
- 反向传播优化问题
- 损失函数设计问题
- 过拟合问题
- 泛化问题
- 大规模训练性能问题

## 更多

- 见我的Repo：https://github.com/StevenJokess/d2l-en-read/tree/moreme
- NLP: http://reader.epubee.com/books/mobile/0a/0a480147f4d747140345a9a3fda529cf/text00017.html?fromPre=last
- GAN: http://reader.epubee.com/books/mobile/0a/0a480147f4d747140345a9a3fda529cf/text00017.html?fromPre=last
- Reddit:https://www.reddit.com/r/deeplearning/
- AI算法工程师手册: https://www.bookstack.cn/books/huaxiaozhuan-ai
- CV: http://www.uml.org.cn/ai/202012021.asp?artid=23430
- 训练秘籍: https://deeplearning-ai.github.io/
- 深度学习从 0 到 1，从图像，自然语言处理，音频信号三方面分别介绍了深度学习算法的实际应用。案例实战部分使用的深度学习框架为 Tensorflow2/Keras：https://www.zhihu.com/pub/book/120217202

## 学科与应用

对于深度学习、统计的专家来说，他们更加关注于模型、算法等等，找到可以普适性解决问题的办法。而对于我们应用来说，具体的算法实现不需要我们考虑太多，而是找到适合的场景、合适的模型、匹配的算法，所以应用人工智能实际上是一个计算机、统计、知识工程、行业知识的一个交叉应用。 [^3]

## Robust

无人驾驶领域，在极端情况会不会做出很不好的答案。

## 安装

https://www.bilibili.com/video/BV18p4y1h7Dr?p=1

## 资源

- DL：https://www.classcentral.com/subject/deep-learning
- Tensorflow框架：中文[^6]
- 资讯：http://soblog.cc/a/%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0


[^1]: https://www.yinxiang.com/everhub/note/e7f0c50e-dc27-488f-a9f9-35c121e20bb1
[^2]: https://github.com/StevenJokess/d2l-en-read/tree/moreme
[^3]: http://www.uml.org.cn/ai/201707041.asp
[^4]: https://libertydream.github.io/2020/06/28/%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0%E6%A8%A1%E5%9E%8B%E4%B8%BA%E4%BB%80%E4%B9%88%E6%B2%A1%E8%BF%87%E6%8B%9F%E5%90%88/
[^5]: https://coffee.pmcaff.com/article/1909387571608704/pmcaff?utm_source=forum&newwindow=1
[^6]: http://www.tensorfly.cn/
[^7]: https://www.infoq.cn/article/W2koiEheFZEEOv1rOu1d
[^8]: http://shujuren.club/a/AI0102.html
[^9]: https://www.bilibili.com/video/BV1J54y187f9?p=2
[^10]: https://zhuanlan.zhihu.com/p/405262917
