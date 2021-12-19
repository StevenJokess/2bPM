# 深度学习算法

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

池化：

- 目的是提取特征，减少向下一阶段传递的数据量，池化过程的本质是“丢弃”，即只保留图像主体特征，过滤掉无关信息的数据特征
- 模糊化图像操作：通过 CNN 的卷积和池化，丢弃到无用的特征，识别出关键因素
- 全连接层的Softmax分类：再卷积池化后通过softmax进行分类

CNN优缺点：

- 缺点：可解释性弱，模型训练慢，对数据依赖很强，模型复杂
- 优点：

1. 可以拟合任意复杂的数据分布
1. 比我们之前讲过的所有算法的性能都要好

## 更多

更多见：https://github.com/StevenJokess/d2l-en-read/tree/moreme

https://www.reddit.com/r/deeplearning/

[1]: https://www.yinxiang.com/everhub/note/e7f0c50e-dc27-488f-a9f9-35c121e20bb1
[2]: https://github.com/StevenJokess/d2l-en-read/tree/moreme
